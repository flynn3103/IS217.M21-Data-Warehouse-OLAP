# Super Store Data Warehouses
 
## Giới thiệu tổng quan về datasets:

### 1. Phát biểu về dữ liệu:
 - Kho dữ liệu Super Store là một kho dữ liệu thu thập việc bán lẻ trực tuyến của một siêu thị toàn cầu trong vòng 4 năm (từ năm 2011-2015)
 - Thông qua kho dữ liệu người dùng có thể biết được thông tin ngày đặt hàng, giao hàng của một đơn hàng, thông tin đơn hàng đó của khách hàng nào, giá, số lượng, tỉ lệ khuyến mãi, phí vận chuyển, loại khách hàng, …
 - Link gốc: https://www.kaggle.com/jr2ngb/superstore-data <br>
**Data Khi chưa Xử Lý**
![](image/DataChuaXuLy.png)<br>
**Data sau khi đã xử lý (loại bỏ các cột không xử dung, xử lý dữ liệu NULL)**
![](image/DataXuLy.png)

### 2. Xây dựng data warehouses: 
**Snow Flake Schema:**
![](image/SnowFlakeSchema.png) <br>
**Fact SuperStore**
| Khóa chính|Tên thuộc tính| Kiểu dữ liệu  |Mô tả Dữ Liệu|Null|
|:---------| :----------: | --------------:|-----------: |--:|
|PK |ID_FACT|varchar|Mã bảng Fact|
|FK | ID_Location |int  |Mã địa điểm|
|FK | ID_date |int |Mã ngày|
|FK| Customer_ID |varchar  |Mã khách hàng|
|FK| Product_ID | int |Mã sản phẩm|
|   | Order_ID | varchar |Mã đơn hàng|
|FK | ID_ShipMode | int |Mã chế độ vận chuyển|
|   | Sales | money |Đơn giá ($)|
|   | Quantity | varchar |Số lượng|
|   | Quantity | varchar |% khuyến mãi|
**Dim Location**
| Khóa chính|Tên thuộc tính| Kiểu dữ liệu  |Mô tả Dữ Liệu|Null|
| :---------| :----------: | -----------: |-----------: |--:|
| PK |ID_LOCATION| int|Mã địa điểm|
|   | City |varchar  |Tên thành phố|
|   | Stage |varchar |Tên tiểu bang|
|   | Country |varchar  |Tên quốc gia|
|   | Market | varchar |Tên thị trường|
|   | Region | varchar |Tên vùng lãnh thổ|
**Dim Date**
| Khóa chính|Tên thuộc tính| Kiểu dữ liệu  |Mô tả Dữ Liệu|Null|
| :---------| :----------: | -----------: |-----------: |--:|
| PK |ID_DATE| int|Mã ngày|
|   | Order_date |Datetime|Ngày đặt hàng|
|   | Ship_date |Datetime |Ngày giao hàng|X|
|   | OrderMonth |int  |Tháng đặt hàng|
|   | OrderYear | int |Năm đặt hàng|
|   | OrderQuater | int |Quí đặt hàng|
|   | ShipMonth | int |Tháng giao hàng|X|
|   | ShipYear | int |Năm giao hàng|X|
|   | ShipQuater | int |Quí giao hàng|X
**Dim Customer**
| Khóa chính|Tên thuộc tính| Kiểu dữ liệu  |Mô tả Dữ Liệu|Null|
| :---------| :----------: | -----------: |-----------: |--:|
| PK |CUSTOMER_ID| varchar|Mã khách hàng|
|   | CustomerName |varchar  |Tên khách hàng|
|   | Segment |varchar |Bộ phận khách hàng ( có 3 bộ phận: Consumer, Home office, Corperate )|

**Dim Product**
| Khóa chính|Tên thuộc tính| Kiểu dữ liệu  |Mô tả Dữ Liệu|Null|
| :---------| :----------: | -----------: |-----------: |--:|
| PK |PRODUCT_ID| number|Mã sản phẩm|
|   | ProductName |int  |Tên sản phẩm|
| FK| Category_ID |varchar |Mã loại sản phẩm|

**Dim Category**
| Khóa chính|Tên thuộc tính| Kiểu dữ liệu  |Mô tả Dữ Liệu|Null|
| :---------| :----------: | -----------: |-----------: |--:|
| PK |Category_ID| varchar|Mã loại sản phẩm|
|   | Category  |varchar  |Loại sản phẩm|
|   | Sub-Category |varchar |Tiểu mục của loại sản phẩm|
**Dim ShipMode**
| Khóa chính|Tên thuộc tính| Kiểu dữ liệu  |Mô tả Dữ Liệu|Null|
| :---------| :----------: | -----------: |-----------: |--:|
| PK |ID_ShipMode| int|Mã chế độ vận chuyển|
|   | Ship_Mode |varchar  |Tên chế độ vận chuyển|


## Tích hợp dữ liệu (SSIS):

## Phân tích dữ liệu:

### 1. Phân tích SSAS trên các CUBE:
### 2. Phân tích trên Pivot Table:

### Phân tích trên MDX:

## Trực quan hóa dữ liệu trên Power BI:

