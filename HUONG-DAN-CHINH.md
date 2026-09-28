# Portfolio Thanh Hà — hướng dẫn

**Web:** https://thanhha-portfolio.pages.dev (Cloudflare Pages, tự cập nhật từ GitHub)
**Code:** https://github.com/thanhha02061/portfolio-web
**Thư mục làm việc:** `Documents\github-ca-nhan\portfolio-web\`
**Chi phí:** 0 đồng, không giới hạn thời gian

---

## Quan trọng: ai sửa file nào

| File | Ai đụng vào | Ghi chú |
|---|---|---|
| `sua.html` | **Claude** cập nhật khi đổi thiết kế | Đây là công cụ, chị chỉ dùng chứ không sửa |
| `index.html` | **Sinh ra từ sua.html** | Đừng sửa tay file này — lần sau xuất lại là mất |
| `noi-dung.json` | **Chị** | Bản lưu nội dung của chị. Giữ kỹ. |
| `images\` | **Chị** | Ảnh chân dung, ảnh dự án, file CV |

Claude ghi thẳng `sua.html` và `index.html` vào thư mục này mỗi lần có thay đổi — chị không phải tải về chép tay nữa.

---

## Vòng lặp sửa nội dung

**1. Mở `sua.html`** (double-click → mở bằng Chrome)

Bên trái là form 9 mục, bên phải là bản xem trước, gõ tới đâu đổi tới đó.

> Đã có `noi-dung.json` từ lần trước? Bấm **Nạp nội dung đã lưu** → chọn file đó trước khi sửa tiếp.

**2. Gõ vào các ô.** Vài ô có quy ước:

| Ô | Cách viết |
|---|---|
| Danh sách kỹ năng | Mỗi dòng: `Tên kỹ năng\|Số phần trăm` — ví dụ `Power BI\|90` |
| Bảng thông tin nhanh | Mỗi dòng: `Nhãn\|Giá trị` |
| Công nghệ dùng | Ngăn cách bằng dấu phẩy |
| Gạch đầu dòng kinh nghiệm | Mỗi dòng một ý |
| Chứng chỉ | `Tên\|Mô tả\|Năm` |
| Bài blog | `Ngày\|Tiêu đề\|Tóm tắt\|Link` |
| Giới thiệu bản thân | Cách nhau **một dòng trống** để tách đoạn |

**Xoá bớt:** để trống ô là khối đó tự biến mất.
Xoá *Tên dự án* → mất cả thẻ dự án. Xoá 3 ô đầu một mốc kinh nghiệm → mất mốc đó. Xoá *Link GitHub* → mất nút GitHub. Xoá hết bài blog và link blog → mất cả mục Blog.

**3. Bấm hai nút:**

- **Lưu nội dung (.json)** → chép `noi-dung.json` vào thư mục này, đè bản cũ
- **Tải index.html** → chép vào thư mục này, đè bản cũ

**4. Đưa lên web:** mở **GitHub Desktop** → repo **portfolio-web** → ghi Summary (vd `Cập nhật dự án`) → **Commit to main** → **Push origin**. Khoảng 1 phút sau Cloudflare tự đưa bản mới lên web.

> ⚠️ Nhớ commit cả ảnh trong `images\` — GitHub Desktop tự liệt kê mọi file mới/đổi, để tick hết là được.

Hoặc nhắn Claude, tôi commit hộ.

---

## Ảnh — chỉ cần đặt đúng tên

Bỏ vào thư mục `images\`, không phải sửa gì trong form:

```
chan-dung.jpg   ảnh chân dung (tỉ lệ 4:5)
du-an-1.png     ảnh dự án 1
du-an-2.png     ảnh dự án 2
du-an-3.png     ảnh dự án 3
du-an-4.png     ảnh dự án 4
CV.pdf          file CV
```

> ⚠️ **Bắt buộc che số liệu thật của công ty trên ảnh dashboard.** An toàn nhất: tạo file Power BI riêng, đổi tên brand và nhân doanh thu với một hệ số, rồi chụp file đó.

---

## Form liên hệ

Form “Gửi lời nhắn” mở ứng dụng email của người gửi với nội dung điền sẵn, gửi tới email ở ô **Email** (mục Contact trong `sua.html`). Không cần máy chủ hay dịch vụ ngoài.

---

## Blog trên Hashnode

1. [hashnode.com](https://hashnode.com) → Sign up bằng Google → tạo blog, ví dụ `thanhha.hashnode.dev`
2. Bấm **Write** để viết. Chèn code SQL/DAX bằng ba dấu huyền + tên ngôn ngữ, nó tự tô màu.
3. Dán link blog vào **mục 8** trong `sua.html` → menu **Blog** và nút **Xem tất cả bài viết** tự hiện

Miễn phí không giới hạn bài, gắn domain riêng cũng miễn phí.

**Ba bài gợi ý** — đều lấy từ chính 3 dự án trong portfolio, viết một lần dùng hai chỗ:

- Vì sao "doanh thu" của công ty bạn có ba con số khác nhau
- Star schema cho báo cáo bán lẻ đa kênh
- Báo cáo Power BI chậm: 5 chỗ kiểm tra theo thứ tự ưu tiên

---

## Mở Public khi sẵn sàng

Link Cloudflare Pages mặc định là **public**: ai có link là xem được. Khi nội dung chưa xong thì **chưa gửi link** cho ai (hoặc nhờ Claude bật Cloudflare Access để khoá tạm).

Kiểm tra lại bằng **cửa sổ ẩn danh** (`Ctrl+Shift+N`). Vào được là đúng.

> Chỉ gắn link vào CV / LinkedIn **sau khi** đã test ở cửa sổ ẩn danh.

---

## Hoàn tác khi lỡ làm hỏng

Hai cách, đều không mất gì:

- **Cloudflare:** Workers & Pages → **thanhha-portfolio** → tab **Deployments** → chọn bản trước → **Rollback to this deployment**.
- **GitHub Desktop:** tab **History** → chuột phải commit lỗi → **Revert changes in commit** → Push origin.

---

## Checklist trước khi gắn link vào CV

- [ ] Đã điền hết nội dung thật qua `sua.html`
- [ ] Số kết quả dự án là số thật (chưa đo được thì viết định tính, **đừng bịa số**)
- [ ] Ảnh chân dung + ít nhất 2 ảnh dashboard đã có trong `images\`
- [ ] Ảnh dashboard **đã che số liệu công ty**
- [ ] File CV PDF đã có, ô *Link file CV* trỏ đúng
- [ ] Email / SĐT / LinkedIn đúng
- [ ] Đã test link ở cửa sổ ẩn danh
- [ ] Mở thử trên điện thoại
- [ ] Đã lưu `noi-dung.json`

---

## Thiết kế hiện tại

```
Nền      linear-gradient(180deg,#EFF5FF → #FFFFFF 48% → #EDF4FF), cố định khi cuộn
Chữ      #0F2A43 (navy)   ·  phụ #3A5470  ·  nhạt #7B8FA5
Accent   #1A5FE8          ·  cyan phụ #0099CC
Viền     #DCE5EE
Mục Liên hệ: dải navy đậm #0F2A43
```

Muốn đổi màu: nhắn Claude, đừng sửa tay trong `index.html` (lần sau xuất lại là mất).
