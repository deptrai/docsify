# Hướng dẫn cài đặt (Installation Guide)

> Tài liệu này hướng dẫn cách cài đặt và thiết lập dự án

## Yêu cầu hệ thống (System Requirements)

- Node.js v14 trở lên
- npm hoặc pnpm

## Các bước cài đặt (Installation Steps)

### 1. Clone repository

```bash
git clone https://github.com/username/project.git
cd project
```

### 2. Cài đặt dependencies

```bash
pnpm install
```

### 3. Cấu hình môi trường

Tạo file `.env` từ file `.env.example`:

```bash
cp .env.example .env
```

### 4. Chạy ứng dụng

```bash
pnpm dev
```

## Xử lý sự cố thường gặp (Troubleshooting)

### Lỗi khi cài đặt dependencies

Nếu bạn gặp lỗi khi cài đặt dependencies, hãy thử xóa thư mục `node_modules` và file `package-lock.json`, sau đó cài đặt lại:

```bash
rm -rf node_modules
rm package-lock.json
pnpm install
```

## Cấu trúc thư mục (Project Structure)

```
project/
├── src/          # Source code
├── public/       # Public assets
├── docs/         # Documentation
└── tests/        # Test files
```
