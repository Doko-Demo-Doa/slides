# Tổng quan về React.JS

## React là gì?

1 trong 3 framework phổ biến nhất hiện nay (bên cạnh [Angular](https://angular.io/) và [VueJS](https://vuejs.org/))

## Tính chất của framework JavaScript hiện đại

- Declarative
- Component

## Declarative

- Kiểu dữ liệu định nghĩa trạng thái (state) của cả ứng dụng
- Tương tác của người dùng sẽ thay đổi data, khiến cho view được cập nhật tự động

## Component

- Luồng dữ liệu phân định bằng props và event
- Dữ liệu truyền theo nhiều hướng: Từ cha đến con và có thể ngươc lại

## Ví dụ: Kiểu data và luồng chạy của data trong ứng dụng todo-list

<img src="assets/todo-components-datamodel.svg" />

## Điều gì khiến React đặc biệt?

- Cú pháp "lạ" dựa trên JavaScript
- Thay đổi state rõ ràng thông qua setter
- State object bất biến

## Lịch sử ra đời

- Được Facebook công bố mã nguồn năm 2013
- Tháng 2 năm 2019: React hook ra đời
- Các cải tiến sắp ra mắt: [khả năng chờ xử lý trước khi render](https://reactjs.org/docs/concurrent-mode-suspense.html) và [concurrent mode](https://reactjs.org/docs/concurrent-mode-intro.html)
