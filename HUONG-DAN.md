# Hướng dẫn dùng website Nhà May Đức Tâm

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
| `Nhà May Đức Tâm` | Tên tiệm | nhiều chỗ — dùng *Replace All* |
| `0912 345 678` | Số điện thoại hiện to ở phần Liên hệ | 1 chỗ |
| `128 Nguyễn Trãi, Phường Bến Thành, TP. Hồ Chí Minh` | Địa chỉ tiệm | 1 chỗ |
| `lienhe@nhamayductam.vn` | Email | 1 chỗ |
| `Thứ 2 – Thứ 7: 8:00 – 19:00` | Giờ mở cửa | 1 chỗ |
| `May đo thủ công từ 1998` | Dòng chữ nhỏ trên đầu trang | 1 chỗ |
| `<span class="mk">Đ</span>` | Chữ cái trong vòng tròn ở logo | 1 chỗ |

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

## 6. Đưa website lên mạng (miễn phí)

Cách dễ nhất, không cần biết kỹ thuật:

1. Vào **https://app.netlify.com/drop**
2. Kéo nguyên thư mục `website-may-do` thả vào khung giữa trang
3. Đợi khoảng 20 giây → Netlify cho bạn một địa chỉ dạng
   `ten-ngau-nhien.netlify.app` — gửi link đó cho khách là xem được
4. Tạo tài khoản (miễn phí) để đổi tên địa chỉ cho đẹp, ví dụ `nhamayductam.netlify.app`

Muốn tên miền riêng kiểu `nhamayductam.vn` thì mua tại các nhà cung cấp Việt Nam
(Mắt Bão, PA Vietnam, Tenten...), giá khoảng 700.000đ/năm cho đuôi `.vn`,
rồi trỏ về Netlify theo hướng dẫn của họ.

Sau này sửa file `index.html` xong, kéo thả lại thư mục lần nữa là web trên mạng cập nhật.

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
