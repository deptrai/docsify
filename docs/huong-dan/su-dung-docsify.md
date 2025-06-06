# Hướng dẫn sử dụng Docsify để thêm tài liệu

## 1. Cấu trúc tài liệu (Documentation Structure)

Docsify tạo ra trang tài liệu từ các file Markdown. Dưới đây là cấu trúc thư mục tiêu chuẩn:

```
docs/
├── README.md         # Trang chính (homepage)
├── _sidebar.md       # Menu bên trái
├── _navbar.md        # Menu trên cùng (navigation)
├── _coverpage.md     # Trang bìa
├── index.html        # Cấu hình của Docsify
└── [thư mục]/        # Các thư mục phân loại tài liệu
    └── [file].md     # Các file tài liệu
```

## 2. Thêm trang tài liệu mới (Adding New Pages)

### Bước 1: Tạo file Markdown

- Tạo file `.md` trong thư mục `docs` hoặc thư mục con
- Đặt tên file rõ ràng, ví dụ: `authentication.md`, `api-reference.md`
- Bắt đầu file với heading level 1 (H1): `# Tiêu đề trang`

### Bước 2: Thêm nội dung theo cấu trúc

```markdown
# Tiêu đề chính (Main Title)

> Mô tả ngắn gọn về trang (Brief description)

## Phần 1 (Section 1)

Nội dung phần 1...

## Phần 2 (Section 2)

Nội dung phần 2...

### Phần 2.1 (Subsection)

Chi tiết phụ...
```

### Bước 3: Cập nhật thanh điều hướng

Thêm liên kết đến trang mới trong file `_sidebar.md`:

```markdown
- Tài liệu của tôi
  - [Trang chủ](/)
  - [Trang đã có](existing-page.md)
  - [Trang mới của bạn](your-new-page.md)
```

## 3. Cách tổ chức tài liệu hiệu quả (Organizing Documentation)

### Nhóm theo chủ đề (Topic-based)

```
docs/
├── guide/              # Hướng dẫn sử dụng
│   ├── README.md       # Tổng quan hướng dẫn
│   ├── quickstart.md   # Bắt đầu nhanh
│   └── advanced.md     # Tính năng nâng cao
│
├── api/                # Tài liệu API
│   ├── README.md       # Tổng quan API
│   ├── authentication.md
│   └── endpoints.md
│
└── tutorials/          # Các bài hướng dẫn
    ├── tutorial1.md
    └── tutorial2.md
```

### Cấu trúc sidebar theo nhóm

```markdown
- Hướng dẫn (Guide)

  - [Tổng quan](guide/)
  - [Bắt đầu nhanh](guide/quickstart.md)
  - [Nâng cao](guide/advanced.md)

- API Reference
  - [Tổng quan](api/)
  - [Xác thực](api/authentication.md)
  - [Endpoints](api/endpoints.md)
```

## 4. Kỹ thuật viết tài liệu Markdown cho Docsify

### Code blocks với highlight

````markdown
```javascript
function hello() {
  console.log('Xin chào thế giới!');
}
```
````

### Bảng dữ liệu

```markdown
| Tên  | Kiểu   | Mô tả          |
| ---- | ------ | -------------- |
| id   | string | ID duy nhất    |
| name | string | Tên người dùng |
```

### Danh sách công việc

```markdown
- [x] Tạo trang chính
- [ ] Thêm tính năng tìm kiếm
- [ ] Tùy chỉnh giao diện
```

### Ghi chú và cảnh báo

```markdown
!> Đây là một cảnh báo quan trọng

?> Đây là một ghi chú thông tin
```

### Liên kết và hình ảnh

```markdown
[Liên kết nội bộ](folder/file.md)

[Liên kết ngoài](https://example.com)

![Alt text](images/hinhanh.png)
```

## 5. Tính năng nâng cao (Advanced Features)

### Sử dụng biến trong tài liệu

```markdown
<!-- Định nghĩa biến -->

[var1]: Giá trị 1
[var2]: Giá trị 2

<!-- Sử dụng biến -->

Biến 1: [var1]
Biến 2: [var2]
```

### Nhúng nội dung từ file khác

```markdown
[filename](path/to/file.md ':include')
```

### Tạo tabs

```markdown
<!-- tabs:start -->

#### **Tab 1**

Nội dung tab 1

#### **Tab 2**

Nội dung tab 2

<!-- tabs:end -->
```

## 6. Plugins hữu ích

Docsify có nhiều plugin mở rộng tính năng. Để thêm plugin, chỉnh sửa file `index.html`:

```html
<script>
  window.$docsify = {
    // Cấu hình hiện tại
    plugins: [
      // Plugin hiện tại
    ],
  };
</script>
<!-- Thêm script của plugin -->
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/plugin-name.min.js"></script>
```

### Một số plugin phổ biến

- **Full-text search**: Tìm kiếm toàn văn
- **Copy code**: Thêm nút copy cho code blocks
- **Zoom image**: Phóng to hình ảnh khi click
- **Pagination**: Điều hướng trang trước/sau
- **Emoji**: Hỗ trợ emoji

## 7. Deploy tài liệu

### GitHub Pages

1. Push code lên GitHub repository
2. Vào Settings > Pages
3. Chọn branch và thư mục `/docs`

### Netlify

1. Kết nối repository với Netlify
2. Thiết lập thư mục publish là `/docs`
3. Đảm bảo không có lệnh build

### Vercel

1. Import project từ repository
2. Thiết lập cấu hình như sau:
   - Output Directory: `docs`
   - Build Command: (để trống)

## 8. Một số lưu ý quan trọng

- **Luôn kiểm tra trước khi commit**: Xem trước tài liệu để đảm bảo hiển thị đúng
- **Sử dụng markdown linter**: Kiểm tra định dạng markdown chuẩn
- **Cập nhật sidebar khi thêm trang**: Không quên cập nhật thanh điều hướng
- **Tạo file README.md trong mỗi thư mục**: Giúp navigation tốt hơn
- **Đặt tên file và thư mục không dấu**: Tránh lỗi URL khi deploy

## 9. Ví dụ hoàn chỉnh cho một trang tài liệu

````markdown
# Hướng dẫn API (API Guide)

> Tài liệu hướng dẫn sử dụng API của hệ thống

## Xác thực (Authentication)

### Lấy token

```curl
curl -X POST https://api.example.com/auth/token \
  -H "Content-Type: application/json" \
  -d '{"username": "user", "password": "pass"}'
```
````

### Sử dụng token

```javascript
fetch('https://api.example.com/data', {
  headers: {
    Authorization: 'Bearer YOUR_TOKEN_HERE',
  },
});
```

## Endpoints

| Phương thức | Đường dẫn  | Mô tả                    |
| ----------- | ---------- | ------------------------ |
| GET         | /api/users | Lấy danh sách người dùng |
| POST        | /api/users | Tạo người dùng mới       |

## Xử lý lỗi

!> Lưu ý: Tất cả lỗi đều trả về mã HTTP tương ứng

| Mã lỗi | Mô tả                                  |
| ------ | -------------------------------------- |
| 400    | Bad Request - Yêu cầu không hợp lệ     |
| 401    | Unauthorized - Không có quyền truy cập |

```

```
