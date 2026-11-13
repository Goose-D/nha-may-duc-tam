# Hướng dẫn dùng website Nhà May Goose D

Dành cho người mới hoàn toàn. Bạn không cần cài gì cả.

---

## 1. Xem website

Mở thư mục `D:\Study-H\website-may-do` → **bấm đúp vào file `index.html`**.
Website sẽ mở ngay trong trình duyệt (Chrome, Edge, Cốc Cốc...).

Toàn bộ website nằm gọn trong **một file duy nhất** là `index.html`.
Muốn sửa gì, bấm chuột phải vào file đó → *Open with* → **Notepad** (hoặc tải
[VS Code](https://code.visualstudio.com) cho dễ nhìn hơn). Sửa xong nhấn `Ctrl+S`,
quay lại trình duyệt nhấn `F5` là thấy thay đổi.

> **Mẹo:** trước khi sửa, copy file `index.html` ra một bản dự phòng.
> Sửa hỏng thì xoá đi, copy bản cũ về là xong.

---

## 2. Đổi thông tin tiệm của bạn

Trong Notepad/VS Code nhấn `Ctrl+F` để **tìm**, rồi thay bằng thông tin thật của bạn.

| Tìm chữ này | Nó là gì | Xuất hiện |
|---|---|---|
| `Nhà May Goose D` | Tên tiệm | nhiều chỗ — dùng *Replace All* |
| `0000 1234 8686` | Hotline hiện to ở phần Liên hệ | 1 chỗ |
| `128 Nguyễn Trãi, Phường Bến Thành, TP. Hồ Chí Minh` | Địa chỉ tiệm | 1 chỗ |
| `lienhe@nhamaygoosed.vn` | Email | 1 chỗ |
| `Thứ 2 – Thứ 7: 8:00 – 19:00` | Giờ mở cửa | 1 chỗ |
| `May đo thủ công từ 1998` | Dòng chữ nhỏ trên đầu trang | 1 chỗ |
| `<span class="mk">G</span>` | Chữ cái trong vòng tròn ở logo | 1 chỗ |

**Các con số ở trang đầu** (27 năm, 12.400 bộ...) tìm chữ `NĂM TRONG NGHỀ` là thấy,
sửa con số ngay phía trên nó.

**Ba lời khen của khách** — tìm chữ `Anh Trần Quốc Hưng`. Đây là nội dung mẫu,
bạn nên thay bằng nhận xét thật của khách mình.

---

## 3. Sửa danh sách mẫu may và bảng giá

Tìm dòng `var SP = [`. Dưới đó là danh sách sản phẩm. Mỗi sản phẩm là **một dòng**:

```js
{id:'vest2', ten:'Vest nam 2 mảnh', nhom:'nam', loai:'vest-nam', ic:'vest',
 cong:2500000, tron:4800000, vai:'Len pha, tuýt-xi', ngay:'10–14 ngày',
 mo:'Áo vest + quần tây, dáng slim hoặc regular, lót toàn thân, 1–2 khuy.'},
```

Ý nghĩa từng phần:

- `id` — mã riêng, **không được trùng** với sản phẩm khác (tự đặt, viết liền không dấu)
- `ten` — tên hiện trên web
- `nhom` — dùng cho nút lọc: `'nam'`, `'nu'` hoặc `'dp'` (đồng phục)
- `loai` — nối với ô "Loại trang phục" trong form đặt may. Chỉ được dùng một trong các giá trị:
  `vest-nam`, `so-mi-nam`, `quan-tay`, `khoac-nam`, `ao-dai`, `dam`, `vest-nu`, `chan-vay`, `dong-phuc`
- `ic` — hình vẽ minh hoạ. Chọn một trong: `vest`, `shirt`, `polo`, `trousers`, `coat`, `aodai`, `dress`, `skirt`
- `cong` — tiền công may (viết số liền, **không có dấu chấm**: `2500000`)
- `tron` — giá trọn gói gồm vải
- `vai`, `ngay`, `mo` — chất liệu, thời gian may, mô tả ngắn

**Thêm sản phẩm:** copy một dòng, dán xuống dưới, sửa nội dung. Nhớ có dấu phẩy `,` cuối dòng.
**Xoá sản phẩm:** xoá nguyên dòng đó đi.

Bảng giá ở phần "Bảng giá" **tự động lấy từ danh sách này**, bạn không phải sửa hai lần.

---

## 4. Sửa các số đo trong form đặt may

Tìm dòng `var SO_DO = {`. Mỗi loại trang phục có một danh sách số đo riêng:

```js
'so-mi-nam' : ['Chiều cao|cm','Cân nặng|kg','Vòng cổ','Vòng ngực','Vòng eo','Rộng vai','Dài tay','Dài áo'],
```

Muốn thêm số đo, viết thêm tên vào trong dấu nháy, cách nhau bằng dấu phẩy.
Mặc định đơn vị là **cm**; muốn đơn vị khác thì viết kiểu `'Cân nặng|kg'`.

---

## 5. Đổi màu sắc

Tìm dòng `--accent:#A3703A;` (màu đồng/nâu vàng chủ đạo). Đổi mã màu đó là cả web đổi theo.
Bạn lấy mã màu ở [htmlcolorcodes.com](https://htmlcolorcodes.com).

Lưu ý: trong file có **hai bộ màu** — một cho nền sáng, một cho nền tối (web tự đổi
theo cài đặt máy người xem). Nếu đổi màu chính, nên đổi cả hai chỗ `--accent` cho đồng bộ.

---

## 6. Website đã lên mạng — địa chỉ của bạn

> ## https://goose-d.github.io/nha-may-duc-tam/

Ai bấm vào link này cũng xem được: điện thoại, máy tính, không cần tài khoản.
Bạn gửi link qua Zalo, Facebook, in lên danh thiếp đều được.

Website đang chạy trên **GitHub Pages** — miễn phí vĩnh viễn, không giới hạn
lượt xem, không có quảng cáo. Kho chứa file nằm tại
https://github.com/Goose-D/nha-may-duc-tam

### Cập nhật web sau khi sửa file

Sửa xong `index.html` trên máy, mở **PowerShell** tại thư mục này rồi chạy 3 lệnh:

```powershell
git add .
git commit -m "Cap nhat noi dung"
git push
```

Đợi khoảng 1 phút là địa chỉ trên tự cập nhật theo. (Hoặc nhắn mình, mình chạy giúp.)

### Muốn tên miền riêng kiểu `nhamayductam.vn`?

1. Mua tên miền tại Mắt Bão, PA Vietnam hoặc Tenten — khoảng 700.000đ/năm cho đuôi `.vn`,
   hoặc ~300.000đ/năm cho đuôi `.com`
2. Trong trang quản lý tên miền, thêm 4 bản ghi `A` trỏ về:
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
3. Vào https://github.com/Goose-D/nha-may-duc-tam/settings/pages →
   mục **Custom domain** → gõ tên miền của bạn → Save

Bước này hơi rối, cứ nhắn mình làm giúp khi bạn mua xong tên miền.

---

## 7. Điều website này **chưa** làm được

Đây là website tĩnh — tức là nó chạy hoàn toàn trên máy người xem, không có máy chủ
phía sau. Hệ quả:

- **Đơn đặt may không tự động gửi về cho bạn.** Khi khách bấm "Gửi đơn đặt may",
  web hiện ra phiếu đơn có mã đơn và nút *"Sao chép đơn để gửi Zalo"*. Khách phải
  chủ động gọi hoặc nhắn Zalo cho bạn. Phiếu đơn cũng được lưu trên máy của chính
  khách để họ đọc lại mã đơn.
- **Chưa có thanh toán online.** Hiện tại tiền cọc thu khi khách đến tiệm.
- **Chưa có trang quản trị** để bạn xem danh sách đơn.

Muốn đơn hàng **tự chạy về email hoặc Google Sheet của bạn**, cần nối thêm một dịch vụ
nhận form (Formspree, Google Forms, hoặc một máy chủ nhỏ). Việc này mình làm giúp bạn
được — cứ nhắn là mình nối vào.

---

## 8. Danh sách file

```
D:\Study-H\website-may-do\
├── index.html      ← toàn bộ website nằm ở đây
└── HUONG-DAN.md    ← file bạn đang đọc
```
