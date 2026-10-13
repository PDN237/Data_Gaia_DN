# Chính sách Quyền Riêng Tư — Gaia AutoFill

**Cập nhật lần cuối:** Tháng 10/2026

---

## 1. Giới thiệu

Gaia AutoFill là tiện ích Chrome được phát triển nhằm hỗ trợ giáo viên Trung tâm Gaia khu vực Đồng Nai tự động điền phiếu báo giảng điện tử (Google Forms) một cách nhanh chóng và chính xác.

---

## 2. Dữ liệu chúng tôi thu thập

**Gaia AutoFill KHÔNG thu thập bất kỳ thông tin cá nhân nào của người dùng.**

Tiện ích không:
- Thu thập tên, email, số điện thoại hay bất kỳ thông tin định danh nào
- Theo dõi lịch sử duyệt web
- Gửi dữ liệu đến máy chủ của bên thứ ba

---

## 3. Dữ liệu lưu trữ cục bộ

Tiện ích lưu trữ **trên chính máy tính của giáo viên** (thông qua `chrome.storage.local`):

| Loại dữ liệu | Mục đích | Gửi ra ngoài? |
|---|---|---|
| Sĩ số các lớp học (VD: "Lớp 5A - 35 HS") | Tự động điền vào phiếu báo giảng lần sau | ❌ Không |

Giáo viên có thể xóa toàn bộ dữ liệu này bất kỳ lúc nào thông qua cài đặt Chrome: `chrome://settings/content/all` → Tìm tiện ích và xóa dữ liệu.

---

## 4. Dữ liệu tải từ bên ngoài

Tiện ích tải **dữ liệu lịch dạy dạng JSON** từ repository GitHub công khai của Trung tâm Gaia:

- URL: `https://raw.githubusercontent.com/PDN237/Data_Gaia_DN/`
- Nội dung: Lịch dạy theo tuần (tên lớp, tiết học, thời gian) — **không chứa thông tin cá nhân**
- Mục đích: Hiển thị đúng lịch dạy của từng giáo viên trong tiện ích

---

## 5. Quyền truy cập và lý do sử dụng

| Quyền | Lý do |
|---|---|
| `storage` | Lưu sĩ số lớp học cục bộ để tự điền lần sau |
| `activeTab` | Xác nhận tab đang mở đúng trang Google Forms báo giảng |
| `scripting` | Tiêm script vào Google Forms để tự động điền các trường |
| `tabs` | Xác định đúng tab đang mở Google Forms và gửi dữ liệu đến đó |
| `docs.google.com` | Truy cập trang Google Forms báo giảng để điền dữ liệu |
| `raw.githubusercontent.com` | Tải dữ liệu lịch dạy JSON từ GitHub của Gaia |
| `api.github.com` | Kiểm tra phiên bản dữ liệu mới nhất |
| `forms.gle` | Hỗ trợ link rút gọn Google Forms |

---

## 6. Chia sẻ dữ liệu

Gaia AutoFill **không chia sẻ bất kỳ dữ liệu nào** với bên thứ ba. Toàn bộ xử lý diễn ra cục bộ trên máy tính của giáo viên.

---

## 7. Bảo mật

Dữ liệu lưu trong `chrome.storage.local` chỉ có thể truy cập bởi chính tiện ích Gaia AutoFill trên máy đó, không thể truy cập từ bên ngoài.

---

## 8. Thay đổi chính sách

Bất kỳ thay đổi nào về chính sách quyền riêng tư sẽ được cập nhật tại trang này kèm ngày sửa đổi.

---

## 9. Liên hệ

Nếu có câu hỏi về chính sách này, vui lòng liên hệ:

- **Email:** binbkhoa123@gmail.com
- **Tổ chức:** Trung tâm Gaia — Khu vực Đồng Nai
