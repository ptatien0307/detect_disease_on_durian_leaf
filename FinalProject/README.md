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
Label 1: Bệnh cháy lá
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171002992-38021761-1b44-4d33-b79d-3d6c4d14cd63.png" style="display: block;margin-left: auto;margin-right: auto;width: 100%; height:100%;"/>
<br>
<a style="text-align: center">Hình . Bệnh cháy lá.</a>
</p>
Label 2: Bệnh đốm trắng
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171003346-7fcb90d1-2dca-4df7-a45f-1c85d4cf9db8.png" style="display: block;margin-left: auto;margin-right: auto;width: 100%; height:100%;"/>
<br>
<a style="text-align: center">Hình . Bệnh đốm trắng.</a>
</p>

## **3.4. THỐNG KÊ BỘ DƯ LIỆU** 
Bộ dữ liệu gốc bao gồm 200 hình ảnh và được tăng cường dữ liệu lên 19993 ảnh
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171526388-c3f5a10c-a39e-44c8-9965-4eddb89f3443.png" style="display: block;margin-left: auto;margin-right: auto;width: 100%; height:100%;"/>
<br>
<a style="text-align: center">Hình . Bệnh đốm trắng.</a>
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
YOLO là một mô hình mạng CNN cho việc phát hiện, nhận dạng, phân loại đối tượng. YOLO được tạo ra từ việc kết hợp giữa các convolutional layers và connected layers. Trong đó các convolutional layers sẽ trích xuất ra các đặc trưng của ảnh, còn full-connected layers sẽ dự đoán ra xác suất đó và bounding box của đối tượng.

YOLOv4 được giới thiệu bởi Alexey Bochoknovskiy, Chien-Yao Wang, and Hong-Yuan Mark Liao trong bài báo YOLOv4: Optimal Speed and Accuracy of Object Detection xuất bản ngày 23/4/2020 [1]

<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171307372-bb8b4868-4d3a-454c-adf5-eab1c939b085.png" style="display: block;margin-left: auto;margin-right: auto;width: 50%; height:50%;"/>
<br>
<a style="text-align: center">Hình . So sánh performance YOLOv4.</a>
</p>

YOLOv4 runs twice faster than EfficientDet with comparable performance. Improves YOLOv3’s AP and FPS by 10% and 12%, respectively. YOLOv4 can achive 43.5% AP (65.7% AP50) for the MS COCO dataset at a realtime speed of ∼65 FPS on Tesla V100
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171000673-06d74018-9757-4b93-aaab-23d96abfbdfe.png" style="display: block;margin-left: auto;margin-right: auto;width: 100%; height:100%;"/>
<br>
<a style="text-align: center">Hình . Cấu trúc YOLOv4.</a>
</p>

#### **4.2.1.2 THIẾT LẬP TRAINING**
Chỉnh sửa các thông số của model YOLOv4 trong file yolov4-custom.cfg:

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

Tạo file obj.names chứa tên của các class
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171179582-4b6d2814-a50f-443d-800a-9e41e2942002.png" style="display: block;margin-left: auto;margin-right: auto;width: 25%; height:25%;"/>
<br>
<a style="text-align: center">Hình . File obj.names.</a>
</p>

Tạo file obj.data có nội dung như sau
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171179655-968ac023-d903-45e9-a1ec-916a9058096a.png" style="display: block;margin-left: auto;margin-right: auto;width: 25%; height:25%;"/>
<br>
<a style="text-align: center">Hình . File obj.data.</a>
</p>

Tạo file train.txt chứa đường dẫn tới các ảnh dùng để train
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171178593-f2c535a0-5876-4586-8c0c-7b251b0a13c0.png" style="display: block;margin-left: auto;margin-right: auto;width: 75%; height:75%;"/>
<br>
<a style="text-align: center">Hình . File train.txt.</a>
</p>

Tạo file valid.txt chứa đường dẫn tới các ảnh dùng để đánh giá trong quá trình train

<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171178723-d0e22c94-95e3-4148-bd30-3b7b6cad06c2.png" style="display: block;margin-left: auto;margin-right: auto;width: 75%; height:75%;"/>
<br>
<a style="text-align: center">Hình . File valid.txt.</a>
</p>

### **4.2.2 FASTER R-CNN**

#### **4.2.2.1 SƠ LƯỢC VỀ FASTER R-CNN**  

#### **4.2.2.2 THIẾT LẬP TRAINING**

## **4.3 ĐÁNH GIÁ MODEL**
### **4.3.1 METRIC ĐÁNH GIÁ**
.....
### **4.3.2 KẾT QUẢ ĐÁNH GIÁ**
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/171077401-840643c4-006a-4a92-a543-5a94039bae5d.png" style="display: block;margin-left: auto;margin-right: auto;width: 100%; height:100%;"/>
<br>
<a style="text-align: center">Hình . Kết quả đánh giá model YOLOv4.</a>
</p>
<a name="ungdung"></a>

# **5. HƯỚNG PHÁT TRIỂN ỨNG DỤNG VÀ CẢI TIẾN**

<a name="thamkhao"></a>
# **6. NGUỒN THAM KHẢO**
[1] Alexey Bochkovskiy, Chien-Yao Wang, Hong-Yuan Mark Liao, In YOLOv4: Optimal Speed and Accuracy of Object Detection. arXiv:2004.10934, 2020

[2] Shaoqing Ren, Kaiming He, Ross Girshick, and Jian Sun, In Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks. arXiv:1506.01497, 2016

[3] https://github.com/AlexeyAB/darknet
