# Hướng dẫn Convert Tensorflow Model thành ONNX Model (*.pb -> *.onnx)
## 1. Tại sao lại là ONNX

> ONNX is a open format to represent deep learning models. With ONNX, AI developers can more easily move models between state-of-the-art tools and choose the combination that is best for them. ONNX is developed and supported by a community of partners.

**Open Neural Network Exchange Format** là một thỏa thuận giữa Microsoft và các công ty khác hoạt động trong lĩnh vực AI nhằm tạo ra định dạng chung cho các mô hình Neural Network (NN).

Do được Microsoft hỗ trợ, nên ONNX sẽ được hỗ trợ trong việc phát triển các ứng dụng thuộc nền tảng Windows.

## 2. Vấn đề
Gồm 3 công đoạn:
 1. Tôi sẽ tiến thành xây dựng mô hình nhận dạng hoa (flowers) dựa trên kiến trúc NN có sẵn từ Tensorflow.
 2. Sau đó, convert mô hình Tensorflow thành ONNX.
 3. Tạo Inference Model Library (C#) từ công cụ Microsoft AI Tools.
## 3. Môi trường
Vì đặc thù của mô hình object detection của Tensorflow, nên việc huấn luyện và convert được thực hiện trong môi trường Linux. Trường hợp này, tôi sử dụng Compute Engine **VPS** của Google Cloud Platform. Bạn cũng có thể sử dụng một máy ảo local (VMWare) chạy Ubuntu 18.04 LTS

Để tạo thư viện C# cho NN, tôi cài đặt Extension MS AI Tools trên Visual Studio 2017.
## 4. Phương pháp thực hiện
### 1. Thực hiện training mô hình Flowers
SSH đến VPS của bạn và thực hiện các lệnh sau:
