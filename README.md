# AI-CHALLENGE
# 🍱 Make Your Meal - AI Web Nhận Diện Món Ăn

## 📦 Giới thiệu
Trang web này cho phép người dùng chụp ảnh món ăn thông qua webcam, sử dụng YOLOv8 + CNN để nhận diện tên món và tính tiền.

## 🧠 Pipeline mô hình
1. YOLOv8m (Object Detection) phát hiện các vùng chứa món ăn
2. Cắt vùng ảnh và resize
3. CNN (MobileNetV2) phân loại món ăn chi tiết
4. Flask server hiển thị tên món và tổng tiền lên web

## 📂 Các thư mục & file quan trọng
- `app.py` - Flask backend nhận ảnh và trả về tên món, tổng tiền
- `detect.html` - Trang nhận diện món ăn qua webcam
- `class_indices.json` - Thứ tự class chuẩn khi train CNN
- `best.pt` - Mô hình YOLOv8
- `food_classifier_mobilenetv2_best.h5` - Mô hình CNN

## 🚀 Cách chạy website

### 1. Cài đặt thư viện
Tại terminal (VS Code hoặc cmd):

pip install flask flask-cors opencv-python-headless tensorflow ultralytics
### 2. Chạy server Flask

python app.py

Sau khi thấy: Runiing on: 1207...
Click chuột phải vào detect.html chọn "Open with Livesever"
## 📷 Cách sử dụng
1. Click **"Bắt đầu"**
2. Cho phép truy cập camera
3. Click **"Chụp ảnh"**, sau đó click **"Gửi để nhận diện"**
4. Xem kết quả món ăn và tổng tiền
5. Nếu bị lỗi không thể gửi đến sever hãy thử reload lại web, hoặc kiểm tra kết nối mạng. Nếu vẫn không được thì hãy xem check lại các thư viện ở phần "app.py" có được cài đặt các thư viện cần thiết chưa (chú thich tải các thư viện ở trên).
## 🧩 Lưu ý
- Đảm bảo môi trường Python 3.8+ 
- Đảm bảo tổng số class trong `class_indices.json (1)` khớp với CNN
- Webcam hoạt động tốt trong trình duyệt
