<p align="center">
  <a href="https://www.uit.edu.vn/" title="Trường Đại học Công nghệ Thông tin" style="border: 5;">
    <img src="https://i.imgur.com/WmMnSRt.png" alt="Trường Đại học Công nghệ Thông tin | University of Information Technology">
  </a>
</p>

<!-- Title -->
<h1 align="center"><b>ĐỒ ÁN CUỐI KÌ</b></h1>
<h1 align="center"><b>PHÁT HIỆN MỘT SỐ LOẠI BỆNH TRÊN LÁ CÂY SẦU RIÊNG</b></h1>

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
* Ngữ cảnh ứng dụng:
    * ...
    * ...
    * ...


* Input: 

* Output:
## **1.2 MÔ TẢ DỮ LIỆU**
.....
<a name="cacnghiencuu"></a>
# **2. CÁC NGHIÊN CỨU TRƯỚC ĐÓ**
Hiện nay, trong lĩnh vực thị giác máy tính nói riêng hay lĩnh vực máy học nói chung, các vấn đề phân loại (classification) và nhận diện vật thể (object detection) xuất hiện rất nhiều trong bài toán đã được đặt ra và đã được giải quyết. Những bài toán này được giải quyết bằng các mô hình machine learning và deep learning như YOLO, VGG-16, Resnet-50 dựa trên kiến trúc mạng CNN (Convolutional Neural Network) và nhiều mô hình với các kiến trúc khác.

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
* YOLOv4 được giới thiệu bởi Alexey Bochoknovskiy, Chien-Yao Wang, and Hong-Yuan Mark Liao trong bài báo YOLOv4: Optimal Speed and Accuracy of Object Detection xuất bản ngày 23/4/2020 [1]

* YOLO là một mô hình mạng CNN cho việc phát hiện, nhận dạng, phân loại đối tượng. YOLO được tạo ra từ việc kết hợp giữa các convolutional layers và connected layers. Trong đó các convolutional layers sẽ trích xuất ra các đặc trưng của ảnh, còn full-connected layers sẽ dự đoán ra xác suất đó và bounding box của đối tượng. 

* Hiện nay, yolov4 vẫn được đánh giá là một trong những model để xây dựng state-of-the-art objects detector tốt nhất.


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
<img src="https://user-images.githubusercontent.com/79583501/172000648-b14adb95-3681-4b23-a0ce-f5c16a53f6bf.png" style="display: block;margin-left: auto;margin-right: auto;width: 25%; height:25%;"/>
<br>
<a style="text-align: center">Hình . Tiếp tục training trên file trọng số mới nhất.</a>
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
* Để đánh giá các model detector và cũng như để so sánh các model với nhau thì nhóm sẽ sử dụng thông số mAP (mean average precision), đặc biệt tập trung vô các chỉ số mAP như AP, AP50, AP75. mAP cũng là một các đánh giá phổ biển cho các model detector hiện nay.
  
* Trước khi vào phần đánh giá mAP, nhóm xin trình bày lại các khái niệm có liên quan trước:
    * **IoU (Intersection Over Union)**: độ do overlap giữa các bbox, cụ thể là giữa grounth truth bounding box, bbox mà nhóm đã gán nhãn với bounding box mà mô hình dự đoán. 
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/172040923-471cd707-b884-473f-a667-1ef56502d5bf.png" style="display: block;margin-left: auto;margin-right: auto;width: 75%; height:75%;"/>
<br>
<a style="text-align: center">Hình . IOU.</a>
</p>
  
* a
    * Giá trị IoU sẽ có giá trị nằm trong đoạn [0,1]. Dựa vào đó có thể xác định được cái kết quả:
        * **True Positive (TP)**: những bbox có IOU >= ngưỡng
        * **False Positive (FP)**: những bbox có IOU < ngưỡng
        * **False Negative (FN)**: những bbox model không dự đoán được 
    * **Precision**: cho biết tỉ lệ bbox được dự đoán có IOU >= ngưỡng 
    $$Precision = \frac{TP}{TP + FP} = \frac{TP}{All detections}$$
    * **Recall**: cho biết tỉ lệ bbox được sự đoán có IOU >= ngưỡng trên tổng số ground-truth bbox 
    $$Recall = \frac{TP}{TP + FN} = \frac{TP}{All ground-truth}$$
    * Nếu có nhiều predicted bbox xếp chồng lên nhau trong cùng một ground-truth bbox thì ta sẽ chọn predicted bbox có IoU lớn nhất là TP, còn lại là FP   
    * **AP (Average precision)**: là chỉ số được tính dựa trên precision và recall. Trong các bài toán detection, với mỗi chỉ số IOU khác nhau ta sẽ có chỉ số precision và recall khác nhau.
Khi tổng hợp lại các precision và recall ở các ngưỡng IoU khác nhau, ta sẽ có biểu đồ precision-recall curve (PR-Curve)

  
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/172042729-471c39c1-4c9e-48df-8e38-fa5c0f8be627.png" style="display: block;margin-left: auto;margin-right: auto;width: 75%; height:75%;"/>
<br>
<a style="text-align: center">Hình . Ví dụ về Precision-Recall Curve.</a>
</p>

* a
    * Khi đó AP sẽ là diện tích phần màu xanh nằm dưới PR-Curve. Khi đó mAP sẽ là trung bình các AP của tất cả các lớp.
    * IoU có ý nghĩa quan trọng đối với chỉ số mAP và việc lựa chọn giá trị của IoU sẽ ảnh hưởng đến kết quả đánh giá của model. Khi ngưỡng IoU thay đổi Precision – Recall cũng thay đổi. Trong các bài toán detection, chúng ta tính toán chỉ số precision và recall với một ngưỡng IoU cho trước, ví dụ đơn giản nhất là nếu ta cho ngưỡng IoU bằng 0.4 và chỉ số IoU sau khi tính toán trên bbox được dự đoán là 0.5 thì ta tính rằng bbox được dự đoán đó là đúng, tuy nhiên nếu đặt ngưỡng IoU bằng 0.6 thì với chỉ số IoU sau khi tính toán trên bbox được dự đoán là 0.5 thì bbox được dự đoán đó là sai. Do đó, tại một giá trị IoU xác định,ta có thể do/đánh giá được mô hình một cách tốt nhất.
### **4.3.2 KẾT QUẢ ĐÁNH GIÁ**
<p align="center">
<img src="" style="display: block;margin-left: auto;margin-right: auto;width: 75%; height:75%;"/>
<br>
<a style="text-align: center">Hình . Kết quả đánh giá model YOLOv4.</a>
</p>
  

  
<div align="center">
  
| Class    |      mAP@.5      | 
|----------|:----------------:| 
| ChayLa   |  0.929           |  
| DomLa    |  0.923           |  
| all      |  0.926           |  
  
</div>
  
<p align="center">
Bảng . Kết quả đánh giá model YOLOv4
</p>
  
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/172160564-d85c05ad-2fa6-4cc2-858f-df2ca72dccf6.png" style="display: block;margin-left: auto;margin-right: auto;width: 75%; height:75%;"/>
<br>
<a style="text-align: center">Hình . Kết quả đánh giá model YOLOv5.</a>
</p>
  

  
<div align="center">
  
| Class    |      mAP@.5      |  
|----------|:----------------:| 
| ChayLa   |  0.932           |  
| DomLa    |  0.924           |  
| all      |  0.928           |  

</div>

<p align="center">
Bảng . Kết quả đánh giá model YOLOv5
</p>
  
<p align="center">
<img src="https://user-images.githubusercontent.com/79583501/172338486-62b41336-5c6d-4563-9762-a269467e3371.png" style="display: block;margin-left: auto;margin-right: auto;width: 75%; height:75%;"/>
<br>
<a style="text-align: center">Hình . Kết quả đánh giá model Faster R-CNN.</a>
</p>


 
<div align="center">
  
| Class    |      mAP@.5      |  
|----------|:----------------:|
| ChayLa   |  0.9318          |  
| DomLa    |  0.9152          |  
| All      |  0.9235          |  
</div>
  
<p align="center">
Bảng . Kết quả đánh giá model Faster R-CNN
</p>
<a name="thamkhao"></a>
  
# **5. HƯỚNG PHÁT TRIỂN ỨNG DỤNG VÀ CẢI TIẾN**
* **Cách cải tiến:**
    * Về dữ liệu:
        * Tăng cường sự đa dạng của dự liệu bằng cách thu thập thêm nhiều ảnh về các bệnh khác nhau, thu thập dữ liệu tại nhiều thời điểm trong ngày, thu thập dữ liệu khi cây ở nhiều thời điểm phát triển khác nhau.
        * Áp dụng thêm các kỹ thuật Data Augmentation (mosaic, blur, contrast, cutout, ...). Chọn lựa phù hợp các kỹ thuật tăng cường khác nhau để phù hợp với bộ dữ liệu.
        * Quá trình thu thập dữ liệu cũng cần kỹ càng hơn. Cần xác định đúng điều kiện ánh nhiên hay cách chụp ảnh để phù hợp với ngữ cảnh bài toán.
    * Về mô hình:
        * Áp dụng thêm nhiều pretrained model khác nhau để có thể tìm được mô hình phù hợp nhất với bài toán và bộ dữ liệu
        * Áp dụng một số kỹ thuật như thay đổi cấu trúc mô hình, tùy chỉnh tham số để có thể cải thiện mô hình hơn
* **Hướng phát triển:**
    * Hướng tới việc phát hiện các loại bệnh trên nhiều loại lá cây trồng khác nhau dựa trên các đặc điểm giống nhau của các loại bệnh khi xuất hiện trên lá.
# **6. NGUỒN THAM KHẢO**
[1] Alexey Bochkovskiy, Chien-Yao Wang, Hong-Yuan Mark Liao, In YOLOv4: Optimal Speed and Accuracy of Object Detection. arXiv:2004.10934, 2020

[2] Shaoqing Ren, Kaiming He, Ross Girshick, and Jian Sun, In Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks. arXiv:1506.01497, 2016

[3] https://github.com/AlexeyAB/darknet
