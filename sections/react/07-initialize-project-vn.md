# Khởi tạo một project React

## Làm việc với node.js và npm

- node.js: JS-Runtime
  - Chạy server dev local
  - Uni test
- npm: package manager: bộ quản lý các gói công cụ
  - Quản lý thư viện
  - Các package cài đặt đều nằm ở _node_modules_
  - Cài đặt trong file _package.json_

## Khởi tạo một project React

Nhiều cách:

- **create-react-app** (phổ biến nhất)
- gatsby (bao gồm cả tool tạo ra site tĩnh)
- next.js (bao gồm cả tool tạo ra site tĩnh và server-side rendering)

## Khởi tạo một project React

Một số câu lệnh có thể dùng để tạo project có tên "todolist":

```bash
npx create-react-app todolist
npx create-react-app todolist --template typescript
npx create-react-app todolist --template cra-template-pwa-typescript
```

```bash
npx create-next-app todolist
npx create-next-app todolist --example with-typescript
```

```bash
npx gatsby new
```

<!--
gatsby and creact-next-app will ask for more config
during creation
gatsby has built-in support for typescript -
just change .js to .tsx -->

xem thêm: https://reactjs.org/docs/create-a-new-react-app.html

## Khởi tạo một project React

Có rất nhiều thứ có thể config trong quá trình tạo project:

- Webpack và babel để build
- Môi trường dev local
- Unit test
- CSS và SCSS
- ...

## Create-react-app: cấu trúc project mặc định

- `public/index.html`, `src/index.js`: các file đầu vào
- `App.js`, `App.css`: Component App gốc
- `node_modules`: thư viện

## Create-react-app: Môi trường dev local và build

Trong thư mục project:

- `npm run start` (or `npm start`): Chạy server dev để có thể truy cập qua `localhost`
- `npm run build`: tiến hành build (phục vụ cho quá trình dev)

## Create-react-app: server dev

Ghi chú:

Đôi khi server dev sẽ báo lỗi mặc dù đã sửa. Có thể khắc phục bằng cách nhấn Ctrl + C và chạy lại.
