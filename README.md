<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
</head>
<body>
    <h1 align="center">Hệ thống AI Phân loại & Ưu tiên Email Khách hàng</h1>
     <div align="center">
        <img src="logo.png" width="200" style="margin: 10px;">
        <img src="AIoTLab_logo.png" alt="Ảnh giao diện ứng dụng" width="200" style="margin: 10px;">
    </div>
    <p>Dự án <strong>EMAIL_AI</strong> được xây dựng bằng Python và FastAPI, kết hợp công nghệ <em>Xử lý Ngôn ngữ Tự nhiên (NLP)</em> và <em>Machine Learning</em> để phân loại, gán mức độ ưu tiên, tóm tắt nội dung email và hỗ trợ quản lý email khách hàng hiệu quả.</p>
    <p align="center">
        <img src="https://img.shields.io/badge/Python-3.10%2B-blue" alt="Python">
        <img src="https://img.shields.io/badge/FastAPI-Backend-success" alt="FastAPI">
        <img src="https://img.shields.io/badge/NLP-scikit--learn%2FNLTK%2FspaCy-yellow" alt="NLP">
    </p>
    <h2>📋 Mục lục</h2>
    <ul>
        <li><a href="#features">Tính năng chính</a></li>
        <li><a href="#tech">Công nghệ sử dụng</a></li>
        <li><a href="#structure">Cấu trúc dự án</a></li>
        <li><a href="#install">Hướng dẫn cài đặt</a></li>
        <li><a href="#usage">Hướng dẫn sử dụng</a></li>
        <li><a href="#screenshots">Hình ảnh ứng dụng</a></li>
    </ul>

<h2 id="features">✨ Tính năng chính</h2>
<h3>📥 Thu thập email tự động</h3>
<ul>
    <li>Kết nối Gmail API (OAuth2) và đồng bộ email mới.</li>
    <li>Lưu trữ thông tin người gửi, tiêu đề, nội dung, thời gian.</li>
</ul>

<h3>🤖 Phân loại & Ưu tiên</h3>
<ul>
    <li>Phân loại email theo chủ đề: Khiếu nại, Đặt hàng, Hỏi đáp, Góp ý</li>
    <li>Đánh nhãn mức độ ưu tiên: Cao / Trung bình / Thấp.</li>
    <li>Tóm tắt nội dung và trích xuất từ khóa.</li>
</ul>

<h3>📊 Quản lý & Báo cáo</h3>
<ul>
    <li>Tìm kiếm email theo người gửi, từ khóa, thời gian.</li>
    <li>Dashboard thống kê số lượng email theo loại & mức ưu tiên.</li>
    <li>Xuất dữ liệu ra CSV/Excel.</li>
</ul>

<h2 id="tech">🛠 Công nghệ sử dụng</h2>
<ul>
    <li><strong>Ngôn ngữ:</strong> Python 3.10+</li>
    <li><strong>Backend:</strong> FastAPI (Uvicorn)</li>
    <li><strong>Machine Learning / NLP:</strong> scikit-learn, NLTK, spaCy</li>
    <li><strong>Xử lý dữ liệu:</strong> Pandas, NumPy</li>
    <li><strong>Frontend:</strong> Jinja2, HTML5, CSS3, Bootstrap</li>
    <li><strong>Dữ liệu:</strong> SQLite/CSV</li>
    <li><strong>Tích hợp:</strong> Gmail API (OAuth2)</li>
</ul>

<h2 id="structure">📁 Cấu trúc dự án</h2>
<pre>

EMAIL_AI/
├── data/
│   └── email_training.csv       # Dữ liệu huấn luyện
├── static/
│   └── header.png               # Logo / banner
├── templates/
│   ├── login.html               # Trang đăng nhập
│   ├── register.html            # Trang đăng ký
│   └── trang_chu.html           # Dashboard
├── app.py                       # Ứng dụng chính FastAPI
├── du_doan.py                   # Phân loại email
├── lay_email.py                 # Lấy email từ Gmail API
├── gui_email.py                 # Gửi email phản hồi
├── train_email.py               # Huấn luyện mô hình
├── mo_hinh_email.pkl            # Mô hình ML đã huấn luyện
├── email_da_lam_sach.csv        # Email đã xử lý
├── email_gmail_sach.csv         # Email từ Gmail đã làm sạch
├── credentials.json             # Gmail OAuth2 client
├── token.json                   # Token Gmail API
├── token_send.json              # Token gửi email
└── venv/                        # Môi trường ảo
    </pre>

<h2 id="install">🚀 Hướng dẫn cài đặt</h2>
<ol>
    <li>Clone repository:
            <pre><code>git clone https://github.com/your-repo/EMAIL_AI.git
cd EMAIL_AI</code></pre>
        </li>
        <li>Tạo môi trường ảo:
            <pre><code>python -m venv venv
venv\Scripts\activate   # Windows
source venv/bin/activate  # Linux/Mac</code></pre>
        </li>
        <li>Cài đặt thư viện:
            <pre><code>pip install -r requirements.txt</code></pre>
        </li>
        <li>Cấu hình Gmail API:
            <ul>
                <li>Tải <code>credentials.json</code> từ Google Cloud Console</li>
                <li>Lần đầu chạy sẽ tạo file <code>token.json</code></li>
            </ul>
        </li>
        <li>Chạy ứng dụng:
            <pre><code>uvicorn app:app --reload --port 8000</code></pre>
        </li>
        <li>Truy cập tại: <a href="http://127.0.0.1:5000">http://127.0.0.1:5000</a></li>
    </ol>

  <h2 id="usage">📖 Hướng dẫn sử dụng</h2>
  <ol>
        <li><strong>Đăng nhập Gmail:</strong> để đồng bộ email.</li>
        <li><strong>Xem Dashboard:</strong> hiển thị email, nhãn phân loại, mức độ ưu tiên.</li>
        <li><strong>Tìm kiếm/Lọc:</strong> theo từ khóa, người gửi, thời gian.</li>
        <li><strong>Xuất CSV/Excel:</strong> để báo cáo.</li>
        <li><strong>Gửi phản hồi:</strong> ngay trong giao diện nếu bật chức năng gửi mail.</li>
    </ol>

<h2 id="screenshots">🖼 Hình ảnh ứng dụng</h2>

<p><strong>🔐 Giao diện Đăng nhập / Đăng ký:</strong></p>
<p align="center">
    <img src="Ảnh chụp màn hình 2025-08-28 071023.png" width="700" alt="Login/Register">
</p>

<p><strong>🏠 Giao diện Trang chủ:</strong></p>
<p align="center">
    <img src="Ảnh chụp màn hình 2025-08-19 135335.png" width="700" alt="Home Page">
</p>

<p><strong>🔎 Chức năng Lọc email:</strong></p>
<p align="center">
    <img src="Ảnh chụp màn hình 2025-08-22 230335.png" width="700" alt="Filter Emails">
</p>

<p><strong>📧 Xem chi tiết Email:</strong></p>
<p align="center">
    <img src="Ảnh chụp màn hình 2025-08-22 230427.png" width="700" alt="Email Detail">
</p>

<p><strong>✉️ Chức năng Gửi mail cho khách:</strong></p>
<p align="center">
    <img src="Ảnh chụp màn hình 2025-08-22 230533.png" width="700" alt="Send Mail">
</p>


  <h2 id="copyright">© Bản quyền</h2>
    <div align="center">
        <p>© 2025 Lương Thị Trà My - Nhóm 17-CNTT_17-04, Khoa Công nghệ Thông tin, Đại học Đại Nam.</p>
        <p>Được thực hiện bởi<br>
        <strong>Nhóm 17-CNTT_17-04 tại Đại học Đại Nam</strong></p>
        <p><strong>Email liên hệ:</strong> <a href="mailto:myltt.sil@gmail.com">myltt.sil@gmail.com</a></p>
    </div>
</body>
</html>
