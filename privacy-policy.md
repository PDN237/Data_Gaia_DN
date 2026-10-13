# Chính Sách Quyền Riêng Tư — Tiện Ích Chrome Gaia AutoFill

**Ngày có hiệu lực:** 13 tháng 10 năm 2026
**Cập nhật lần cuối:** 13 tháng 10 năm 2026
**Phiên bản tiện ích:** 2.0

---

> **Tóm tắt:** Gaia AutoFill không thu thập, không lưu trữ và không truyền bất kỳ thông tin cá nhân nào của người dùng ra bên ngoài thiết bị. Tiện ích chỉ lưu dữ liệu sĩ số lớp học trên máy bạn và đọc lịch dạy từ nguồn GitHub công khai của Trung tâm Gaia.

---

## 1. Giới Thiệu

**Gaia AutoFill** là tiện ích trình duyệt Chrome được phát triển nhằm hỗ trợ giáo viên **Trung tâm Gaia khu vực Đồng Nai** tự động điền phiếu báo giảng điện tử (Google Forms) dựa trên lịch dạy của từng giáo viên, giúp tiết kiệm thời gian và hạn chế sai sót khi nhập liệu thủ công.

Chính sách quyền riêng tư này mô tả rõ ràng:
- Tiện ích truy cập, thu thập, lưu trữ hoặc truyền đi những dữ liệu nào
- Lý do và cách thức sử dụng từng quyền của trình duyệt
- Quyền của bạn đối với dữ liệu được lưu cục bộ
- Cách liên hệ khi có thắc mắc về quyền riêng tư

Bằng việc cài đặt và sử dụng Gaia AutoFill, bạn đồng ý với các nội dung được mô tả trong chính sách này.

---

## 2. Thông Tin Chúng Tôi KHÔNG Thu Thập

Gaia AutoFill được thiết kế theo nguyên tắc **ưu tiên bảo mật**. Tiện ích hoàn toàn **không**:

- ❌ Thu thập, lưu trữ hoặc truyền tên, địa chỉ email, số điện thoại hay bất kỳ thông tin định danh cá nhân nào
- ❌ Theo dõi lịch sử duyệt web, các trang đã truy cập, hay hành vi sử dụng trình duyệt
- ❌ Truy cập nội dung của bất kỳ trang web nào ngoài trang Google Forms báo giảng mà bạn đang chủ động mở
- ❌ Sử dụng cookie theo dõi, công cụ phân tích dữ liệu (analytics), hoặc bất kỳ SDK theo dõi nào của bên thứ ba
- ❌ Gửi dữ liệu người dùng đến máy chủ của chúng tôi (chúng tôi không vận hành máy chủ backend)
- ❌ Chia sẻ dữ liệu với các đơn vị quảng cáo, môi giới dữ liệu, hay bất kỳ bên thứ ba nào
- ❌ Thực thi mã từ xa — toàn bộ logic xử lý được đóng gói cục bộ trong gói tiện ích

---

## 3. Dữ Liệu Tiện Ích Truy Cập

### 3.1 Dữ Liệu Đọc Từ Nguồn Bên Ngoài (Chỉ Đọc)

Tiện ích tải các dữ liệu **công khai, không chứa thông tin cá nhân** từ GitHub:

| Nguồn | Dữ liệu tải về | Chứa thông tin cá nhân? |
|---|---|---|
| `raw.githubusercontent.com/PDN237/Data_Gaia_DN/` | Lịch dạy theo tuần (JSON) — tên lớp, tiết học, thời gian, tên môn | ❌ Không |
| `Data/form.json` | Cấu hình trường biểu mẫu — tên trường, bí danh, giá trị mặc định | ❌ Không |
| `Data/class.json` | Danh sách lớp học và trường liên kết | ❌ Không |
| `api.github.com` | Kiểm tra phiên bản dữ liệu lịch dạy mới nhất | ❌ Không |

Các yêu cầu này là **đọc một chiều**. Không có dữ liệu từ thiết bị của bạn được gửi đến GitHub trong nội dung yêu cầu, ngoại trừ các thông tin HTTP tiêu chuẩn (địa chỉ IP, User-Agent trình duyệt) do trình duyệt và hạ tầng GitHub xử lý, tuân theo [Chính sách Quyền Riêng Tư của GitHub](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement).

### 3.2 Dữ Liệu Lưu Trữ Cục Bộ Trên Thiết Bị Của Bạn

Tiện ích lưu trữ dữ liệu sau **hoàn toàn trên thiết bị của bạn** thông qua API `chrome.storage.local` của Chrome:

| Dữ liệu lưu trữ | Ví dụ | Mục đích | Gửi ra ngoài? |
|---|---|---|---|
| Sĩ số lớp học theo trường | `{ "truong": "Trường ABC", "lop": "Lớp 5A", "siSo": 35 }` | Tự động điền sĩ số khi báo giảng lần sau, tránh nhập lại thủ công | ❌ Không bao giờ |

**Những điều quan trọng về dữ liệu cục bộ này:**
- Dữ liệu **không bao giờ rời khỏi thiết bị của bạn**
- Chỉ tiện ích Gaia AutoFill mới có thể truy cập — không có trang web hay tiện ích nào khác đọc được
- Không chứa thông tin định danh cá nhân — chỉ lưu tên lớp, tên trường và sĩ số (dữ liệu tổ chức, không phải cá nhân)
- Bạn có thể xóa bất kỳ lúc nào (xem Mục 7)

### 3.3 Dữ Liệu Điền Vào Google Forms (Chỉ Trong Trình Duyệt)

Khi bạn kích hoạt chức năng tự động điền, tiện ích đọc dữ liệu từ lịch dạy cục bộ và điền vào các trường của trang Google Forms báo giảng **mà bạn đã mở sẵn**. Thao tác này:

- Diễn ra **hoàn toàn trong trình duyệt của bạn**, trên tab bạn đã mở
- **Không** truyền dữ liệu đến bất kỳ máy chủ nào do chúng tôi kiểm soát
- Chỉ điền vào đúng Google Form bạn đang sử dụng
- Sau khi bạn nhấn Nộp biểu mẫu, dữ liệu thuộc phạm vi điều chỉnh của [Chính sách Quyền Riêng Tư của Google](https://policies.google.com/privacy)

---

## 4. Giải Thích Các Quyền Trình Duyệt

Gaia AutoFill yêu cầu các quyền Chrome sau. Mỗi quyền được sử dụng đúng và đủ cho mục đích đã nêu:

### Quyền `storage` — Lưu trữ
**Lý do cần thiết:** Lưu sĩ số lớp học (`chrome.storage.local`) trên thiết bị của bạn để tự động điền vào phiếu báo giảng lần tiếp theo, giúp không phải nhập lại.

**Không được dùng để:** Đọc hoặc ghi cookie, dấu trang, mật khẩu hay bất kỳ dữ liệu nào ngoài thông tin sĩ số lớp đã mô tả ở trên.

---

### Quyền `activeTab` — Tab Đang Hoạt Động
**Lý do cần thiết:** Đọc URL của tab bạn đang xem để xác nhận đó là trang Google Forms báo giảng của Gaia trước khi thực hiện tự động điền.

**Không được dùng để:** Truy cập nội dung trang, văn bản, hay bất kỳ dữ liệu duyệt web nào khác. Chỉ kích hoạt khi bạn bấm nút trong tiện ích.

---

### Quyền `scripting` — Chèn Script
**Lý do cần thiết:** Chèn script (`content.js`) vào tab Google Forms bạn đã mở, cho phép tiện ích tự động điền các trường trong biểu mẫu (mã giáo viên, ngày dạy, tên lớp, thông tin bài học, sĩ số, v.v.).

**Không được dùng để:** Chèn script vào bất kỳ trang web nào khác. Việc chèn script bị giới hạn chỉ ở `https://docs.google.com/forms/*`.

---

### Quyền `tabs` — Quản Lý Tab
**Lý do cần thiết:** Xác định tab nào đang hiển thị Google Forms báo giảng để tiện ích gửi dữ liệu lịch dạy đúng đến tab đó.

**Không được dùng để:** Đọc tiêu đề tab, nội dung trang, hay lịch sử duyệt web của bất kỳ tab nào.

---

## 5. Giải Thích Các Quyền Truy Cập Máy Chủ

Tiện ích khai báo quyền truy cập vào các tên miền sau. Quyền truy cập được **giới hạn nghiêm ngặt** cho các mục đích đã nêu:

| Tên miền | Mục đích sử dụng |
|---|---|
| `https://docs.google.com/*` | Đọc cấu trúc trang Google Forms báo giảng và điền dữ liệu vào các trường |
| `https://*.googleusercontent.com/*` | Tải tài nguyên tĩnh (hình ảnh, script) do Google phục vụ trong trang Google Forms |
| `https://raw.githubusercontent.com/*` | Tải dữ liệu lịch dạy (file JSON) từ repository GitHub công khai của Gaia |
| `https://api.github.com/*` | Kiểm tra phiên bản mới nhất của file dữ liệu lịch dạy |
| `https://forms.gle/*` | Hỗ trợ link rút gọn Google Forms chuyển hướng đến `docs.google.com` |

Tiện ích **không truy cập** bất kỳ tên miền nào ngoài danh sách trên.

---

## 6. Chính Sách Không Dùng Mã Từ Xa

**Gaia AutoFill không sử dụng thực thi mã từ xa.**

Toàn bộ logic JavaScript được đóng gói trong gói tiện ích cài trên thiết bị của bạn (`content.js`, `controler.js`, `backgroup.js`). Dữ liệu tải từ GitHub (các file `.json`) là **dữ liệu cấu hình tĩnh** — không bao giờ được thực thi như mã lệnh. Điều này tuân thủ chính sách mã từ xa của Chrome Web Store.

---

## 7. Lưu Giữ Dữ Liệu & Quyền Của Bạn

### Xóa Dữ Liệu Lưu Cục Bộ
Dữ liệu sĩ số lớp học được lưu bởi tiện ích sẽ tồn tại trên thiết bị của bạn cho đến khi bạn xóa. Để xóa toàn bộ:

**Cách 1 — Qua cài đặt Chrome:**
1. Mở Chrome, truy cập `chrome://settings/`
2. Chọn **Quyền riêng tư và bảo mật → Cài đặt trang → Xem quyền và dữ liệu được lưu trữ trên các trang**
3. Tìm kiếm **Gaia AutoFill** và chọn **Xóa**

**Cách 2 — Gỡ cài đặt tiện ích:**
Gỡ cài đặt Gaia AutoFill sẽ xóa toàn bộ dữ liệu cục bộ liên quan.

### Dữ Liệu Trên Google Forms
Sau khi bạn nộp phiếu báo giảng, dữ liệu đó được quản lý theo điều khoản của Google và quy định nội bộ của Trung tâm Gaia. Tiện ích không có quyền kiểm soát dữ liệu sau khi nộp.

---

## 8. Bảo Vệ Trẻ Em

Gaia AutoFill được thiết kế dành riêng cho giáo viên người lớn tại Trung tâm Gaia. Tiện ích không hướng đến và không cố ý thu thập thông tin từ bất kỳ cá nhân nào dưới 13 tuổi.

---

## 9. Thay Đổi Chính Sách

Chúng tôi có thể cập nhật Chính sách Quyền Riêng Tư này theo thời gian để phản ánh các thay đổi về chức năng tiện ích hoặc yêu cầu pháp lý. Khi có thay đổi:

- Ngày **"Cập nhật lần cuối"** ở đầu trang sẽ được sửa đổi
- Các thay đổi quan trọng sẽ được ghi chú trong nhật ký cập nhật của tiện ích trên Chrome Web Store

Tiếp tục sử dụng tiện ích sau khi có thay đổi đồng nghĩa với việc bạn chấp nhận chính sách đã được sửa đổi.

---

## 10. Luật Áp Dụng

Chính sách Quyền Riêng Tư này được điều chỉnh theo pháp luật **Cộng hòa Xã hội Chủ nghĩa Việt Nam**. Mọi tranh chấp sẽ được giải quyết theo thẩm quyền tài phán Việt Nam.

---

## 11. Liên Hệ

Nếu bạn có bất kỳ câu hỏi, thắc mắc hay yêu cầu nào liên quan đến Chính sách Quyền Riêng Tư này hoặc cách Gaia AutoFill xử lý dữ liệu, vui lòng liên hệ:

- **Email:** binbkhoa123@gmail.com
- **GitHub:** [PDN237/Data_Gaia_DN](https://github.com/PDN237/Data_Gaia_DN)

Chúng tôi sẽ phản hồi các yêu cầu liên quan đến quyền riêng tư trong vòng **5 ngày làm việc**.

---

*Chính sách này chỉ áp dụng cho Tiện ích Chrome Gaia AutoFill và không bao gồm bất kỳ dịch vụ hay sản phẩm nào khác của Trung tâm Gaia.*
