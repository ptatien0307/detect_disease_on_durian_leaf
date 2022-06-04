<p align="center">
  <a href="https://www.uit.edu.vn/" title="Trường Đại học Công nghệ Thông tin" style="border: 5;">
    <img src="https://i.imgur.com/WmMnSRt.png" alt="Trường Đại học Công nghệ Thông tin | University of Information Technology">
  </a>
</p>

<!-- Title -->
<h1 align="center"><b>ĐỒ ÁN CUỐI KÌ</b></h1>
<h1 align="center"><b>TÊN ĐỒ ÁN</b></h1>

# **BẢNG MỤC LỤC**

1. [Tổng Quan Về Đồ Án](#tongquan)
2. [Các Nghiên Cứu Về Bài Toán Của Tiền Nhân](#cacnghiencuu)
3. [Xây Dựng Bộ Dữ Liệu](#dulieu)
4. [Training Và Đánh Giá Model](#training)
5. [Hướng Phát Triển Ứng Dụng Và Cải Tiến](#ungdung)
6. [Nguồn Tham Khảo](#thamkhao)

<a name="tongquan"></a>
# **1. TỔNG QUAN VỀ ĐỒ ÁN** 
## **1.1 MÔ TẢ BÀI TOÁN**
.....

Input: Truyền vào một ảnh chứa một hoặc nhiều chiếc lá sầu riêng.

Output: Trả về loại bệnh trên từng lá có trong ảnh đó.
## **1.2 MÔ TẢ DỮ LIỆU**
.....
<a name="cacnghiencuu"></a>
# **2. CÁC NGHIÊN CỨU TRƯỚC ĐÓ**
.....

<a name="dulieu"></a>
# **3. XÂY DỰNG BỘ DỮ LIỆU**
.....
## **3.1 QUÁ TRÌNH THU THẬP**
.....
## **3.2 TIÊU CHÍ KHI THU THẬP DỮ LIỆU**
.....
## **3.3 GÁN NHÃN DỮ LIỆU**
**Label 1: Bệnh cháy lá**
* Bệnh cháy lá sầu riêng có thể phát sinh trên cả lá non và lá già, biểu hiện ban đầu là những đốm nhỏ, sũng nước, sau đó chúng liên kết lại thành mảng bất dạng nhũn nước hay phỏng nước sôi trên lá. Sau đó những đốm bệnh này khô đi và chuyển sang màu nâu sáng với rìa màu nâu tối khiến cho lá bị biến dạng và bị quăn lại.
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171002992-38021761-1b44-4d33-b79d-3d6c4d14cd63.png" style="display: block;margin-left: auto;margin-right: auto;width: 100%; height:100%;"/>
<br>
<a style="text-align: center">Hình . Một số ví dụ về bệnh cháy lá.</a>
</p>

**Label 2: Bệnh đốm trắng**
* Bệnh thường xuất hiện chủ yếu trên lá già trong những điều kiện độ ẩm cao, mật độ cây trong vườn dày đặc, rậm rạp. Đặc biệt xuất hiện ở giai đoạn trước và sau khi thu hoạch cho cây đang suy yếu trong thời gian mang trái. Lá bị bệnh thường có những đốm nhung có màu sắc giống như sắt rỉ hoặc màu vàng cam, một thời gian sau chuyển sang màu xanh xám. Những đốm này có thể tụ họp lại thành mảng lớn trên lá
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171003346-7fcb90d1-2dca-4df7-a45f-1c85d4cf9db8.png" style="display: block;margin-left: auto;margin-right: auto;width: 100%; height:100%;"/>
<br>
<a style="text-align: center">Hình . Một số ví dụ về bệnh đốm lá.</a>
</p>

## **3.4. THỐNG KÊ BỘ DƯ LIỆU** 
* Bộ dữ liệu gốc bao gồm 200 hình ảnh và được tăng cường dữ liệu lên 2000 ảnh. Bộ dữ liệu sau đó được chia thành hai bộ train và test với tỉ lệ 7:3

<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/172002598-7f736d9e-bf14-4a64-8c72-72b1bb125422.png" style="display: block;margin-left: auto;margin-right: auto;width: 50%; height:50%;"/>
<br>
<a style="text-align: center">Hình . Thống kê dữ liệu.</a>
</p>

* Sau khi đã tăng cường dữ liệu có tổng số object là 3861, trong đó:
    * Có 1472 object thuộc lớp ChayLa
    * Có 2389 object thuộc lớp DomTrang

<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/172002852-052a35e4-9192-4d28-accc-bf38ca053357.png" style="display: block;margin-left: auto;margin-right: auto;width: 50%; height:50%;"/>
<br>
<a style="text-align: center">Hình . Thống kê dữ liệu.</a>
</p>

* Tỉ lệ object ở bộ dữ liệu train và test
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/172001821-949e068f-d401-47b4-9caa-2197a00fb04f.png" style="display: block;margin-left: auto;margin-right: auto;width: 50%; height:50%;"/>
<br>
<a style="text-align: center">Hình . Thống kê dữ liệu train và test.</a>
</p>

<a name="training"></a>
# **4. TRAINING VÀ ĐÁNH GIÁ MODEL**
## **4.1 CẤU HÌNH TRAINING**
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171001486-19287188-83ef-42b0-98ce-981c36e2c36b.png" style="display: block;margin-left: auto;margin-right: auto;width: 100%; height:100%;"/>
<br>
<a style="text-align: center">Hình . Cấu trúc YOLOv4.</a>
</p>

## **4.2 TRAINING MODEL**

### **4.2.1 YOLOv4**

#### **4.2.1.1 SƠ LƯỢC VỀ YOLOv4**
* YOLO là một mô hình mạng CNN cho việc phát hiện, nhận dạng, phân loại đối tượng. YOLO được tạo ra từ việc kết hợp giữa các convolutional layers và connected layers. Trong đó các convolutional layers sẽ trích xuất ra các đặc trưng của ảnh, còn full-connected layers sẽ dự đoán ra xác suất đó và bounding box của đối tượng.

* YOLOv4 được giới thiệu bởi Alexey Bochoknovskiy, Chien-Yao Wang, and Hong-Yuan Mark Liao trong bài báo YOLOv4: Optimal Speed and Accuracy of Object Detection xuất bản ngày 23/4/2020 [1]

<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171307372-bb8b4868-4d3a-454c-adf5-eab1c939b085.png" style="display: block;margin-left: auto;margin-right: auto;width: 50%; height:50%;"/>
<br>
<a style="text-align: center">Hình . So sánh performance YOLOv4.</a>
</p>

* YOLOv4 runs twice faster than EfficientDet with comparable performance. Improves YOLOv3’s AP and FPS by 10% and 12%, respectively. YOLOv4 can achive 43.5% AP (65.7% AP50) for the MS COCO dataset at a realtime speed of ∼65 FPS on Tesla V100
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171000673-06d74018-9757-4b93-aaab-23d96abfbdfe.png" style="display: block;margin-left: auto;margin-right: auto;width: 100%; height:100%;"/>
<br>
<a style="text-align: center">Hình . Cấu trúc YOLOv4.</a>
</p>

#### **4.2.1.2 THIẾT LẬP TRAINING**
* Thiết lập các thông số của model YOLOv4 trong file yolov4-custom.cfg:

    * batch: 64
    * subdivisions = 16
    * max_batches = 4000 (Bằng số class * 2000)
    * steps = 3200, 3600 (Bằng 0.8 * max_batches, 0.9 * max_batches)
    * width = 416, height = 416 (Kích thước của ảnh)
    * classes = 2 (Số class)
    * filters = 21 (Tính theo công thức filters = (classes + 5) * 3)
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171085332-e76d9e1d-df86-479b-b7c9-fccec6f22831.png" style="display: block;margin-left: auto;margin-right: auto;width: 50%; height:50%;"/>
<br>
<a style="text-align: center">Hình . Cấu hình training.</a>
</p>

<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171085414-aebb5e64-caea-455e-b2a3-f63bb8d2ccf3.png" style="display: block;margin-left: auto;margin-right: auto;width: 25%; height:25%;"/>
<br>
<a style="text-align: center">Hình . Cấu hình training.</a>
</p>

<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171085453-0c938965-60a6-46ee-af31-846157f4d49c.png" style="display: block;margin-left: auto;margin-right: auto;width: 25%; height:25%;"/>
<br>
<a style="text-align: center">Hình . Cấu hình training.</a>
</p>

* Tạo file obj.names chứa tên của các class
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171179582-4b6d2814-a50f-443d-800a-9e41e2942002.png" style="display: block;margin-left: auto;margin-right: auto;width: 25%; height:25%;"/>
<br>
<a style="text-align: center">Hình . File obj.names.</a>
</p>

* Tạo file obj.data có nội dung như sau
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171179655-968ac023-d903-45e9-a1ec-916a9058096a.png" style="display: block;margin-left: auto;margin-right: auto;width: 25%; height:25%;"/>
<br>
<a style="text-align: center">Hình . File obj.data.</a>
</p>

* Tạo file train.txt chứa đường dẫn tới các ảnh dùng để train
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171178593-f2c535a0-5876-4586-8c0c-7b251b0a13c0.png" style="display: block;margin-left: auto;margin-right: auto;width: 75%; height:75%;"/>
<br>
<a style="text-align: center">Hình . File train.txt.</a>
</p>

* Tạo file valid.txt chứa đường dẫn tới các ảnh dùng để đánh giá trong quá trình train

<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171178723-d0e22c94-95e3-4148-bd30-3b7b6cad06c2.png" style="display: block;margin-left: auto;margin-right: auto;width: 75%; height:75%;"/>
<br>
<a style="text-align: center">Hình . File valid.txt.</a>
</p>

#### **4.2.1.3 TIẾN HÀNH TRAINING**
* Nhóm sử dụng pretrained weights yolov4.conv.137 và tiến hành training lần đầu tiên
* Trong quá trình train model các file trọng số được lưu lại:
    * yolov4-custom_last.weights (Trọng số của interation mới nhất)
    * yolov4-custom_best.weights (Trọng số tốt nhất)
    * Các file trọng số được lưu lại cứ mỗi 1000 iteration
* Cú pháp tiến hành training
<p align="center">
  ./darknet <đường dẫn file obj.data> <đường dẫn file config> <đường dẫn file trọng số>
</p>
* Tiến hành training lần đầu

<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171991176-1936258f-07f4-4844-a9f1-f455dfe2da71.png" style="display: block;margin-left: auto;margin-right: auto;width: 75%; height:75%;"/>
<br>
<a style="text-align: center">Hình . Tiến hành training YOLOv4.</a>
</p>

* Tiếp tục training trên file trọng số mới nhất
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171991207-5fe5e8d8-46b7-4e08-9a18-a1e50510ccf9.png" style="display: block;margin-left: auto;margin-right: auto;width: 75%; height:75%;"/>
<br>
<a style="text-align: center">Hình . Tiếp tục training YOLOv4.</a>
</p>

### **4.2.2 FASTER R-CNN**

#### **4.2.2.1 SƠ LƯỢC VỀ FASTER R-CNN**  
* Faster R-CNN là một mô hình single-stage, được giới thiệu bởi Shaoqing Ren, Kaiming He, Ross Girshick, and Jian Sun trong bài báo Towards Real-Time Object Detection with Region Proposal Networks vào năm 2016
* Faster R-CNN là một phương pháp cải tiến hơn dựa trên 2 phương pháp trước đó là R_CNN và Fast R-CNN. Faster R-CNN là một sự kết hợp giữa Faster RCNN là sự kết hợp giữa Fast-RCNN với một mạng mới có tên gọi là Region Proposal Network(RPN)
* Bằng việc sử dụng RPN để tìm ra vùng có khả năng chứa đối tượng, Faster R-CNN đã tiết kiệm được nhiều thời gian hơn so với cách sử dụng thuật toán Selective Search 
  
#### **4.2.2.2 THIẾT LẬP TRAINING**
Nhóm sử dụng detectron 2, Detetron2 là một framework để xây dựng bài toán Object Detetion and Segmentation. Nhóm sử dụng X101-FPN là model pretrained để tiến hành huấn luyện trên tập dữ liệu mới.
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171989700-e8dcac29-84ca-4ff4-9ee5-5b4159bbbcd2.png" style="display: block;margin-left: auto;margin-right: auto;width: 75%; height:75%;"/>
<br>
<a style="text-align: center">Hình . Chọn pretrained model.</a>
</p>

#### **4.2.2.3 TIẾN HÀNH TRAINING**

### **4.2.3 YOLOv5**
#### **4.2.3.1 SƠ LƯỢC VỀ YOLOv5**
YOLOv5 là một mô hình Object Detection thuộc họ mô hình YOLO. Nếu các bạn chưa biết thì 3 phiên bản YOLO đầu tiên được phát triển bởi Joseph Redmon. Sau đó, Alexey Bochkovskiy cho ra mắt YOLOv4 với sự cải thiện cả về tốc độ cũng như độ chính xác. Và rồi YOLOv5 được công bố gần đây với những so sánh ban đầu cho thấy độ chính xác tương đương YOLOv4 và có tốc độ nhanh hơn khi thực hiện dự đoán (tuy nhiên vẫn có rất nhiều hoài nghi về độ tin cậy của những so sánh này vì YOLOv5 mới được ra mắt trên GitHub chứ chưa có bài báo chính thức nào cả).
#### **4.2.3.2 THIẾT LẬP TRAINING**
* Tạo file data.yaml như sau:
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171991051-0de1c835-7ee9-464b-8067-034dc68f2434.png" style="display: block;margin-left: auto;margin-right: auto;width: 75%; height:75%;"/>
<br>
<a style="text-align: center">Hình . File data.yaml.</a>
</p>

* Thiết lập training
    * batch: 32
    * img: 416
    * epochs: 500
* Nhóm chọn pretrained model YOLOv5s để tiến hành huấn luyện
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/172003627-13fc664d-bc19-4953-9ec9-e16a380eb72b.png" style="display: block;margin-left: auto;margin-right: auto;width: 75%; height:75%;"/>
<br>
<a style="text-align: center">Hình . Tiến hành training YOLOv5.</a>
</p>

#### **4.2.3.3 TIẾN HÀNH TRAINING**
* Tiến hành training lần đầu
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171991086-44dc560d-9a35-4317-8550-0dc2c5112aae.png" style="display: block;margin-left: auto;margin-right: auto;width: 75%; height:75%;"/>
<br>
<a style="text-align: center">Hình . Tiến hành training YOLOv5.</a>
</p>

* Tiếp tục training trên file trọng số mới nhất
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/172000648-b14adb95-3681-4b23-a0ce-f5c16a53f6bf.png" style="display: block;margin-left: auto;margin-right: auto;width: 75%; height:75%;"/>
<br>
<a style="text-align: center">Hình . Tiến hành training YOLOv5.</a>
</p>

* Trong quá trình train model các file trọng số được lưu lại:
    * last.pt (Trọng số của interation mới nhất)
    * best.pt (Trọng số tốt nhất)
#### **4.2.3.3 KẾT QUẢ TRAINING**
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/172000457-29f43cd8-59c9-41ef-90b8-c802c7335518.png" style="display: block;margin-left: auto;margin-right: auto;width: 75%; height:75%;"/>
<br>
<a style="text-align: center">Hình . Kết quả training.</a>
</p>

## **4.3 ĐÁNH GIÁ MODEL**
### **4.3.1 METRIC ĐÁNH GIÁ**
.....
### **4.3.2 KẾT QUẢ ĐÁNH GIÁ**

<a name="thamkhao"></a>
# **5. HƯỚNG PHÁT TRIỂN ỨNG DỤNG VÀ CẢI TIẾN**

  
# **6. NGUỒN THAM KHẢO**
[1] Alexey Bochkovskiy, Chien-Yao Wang, Hong-Yuan Mark Liao, In YOLOv4: Optimal Speed and Accuracy of Object Detection. arXiv:2004.10934, 2020

[2] Shaoqing Ren, Kaiming He, Ross Girshick, and Jian Sun, In Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks. arXiv:1506.01497, 2016

[3] https://github.com/AlexeyAB/darknet
