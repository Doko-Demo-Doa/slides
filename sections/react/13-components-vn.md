# Component

## Component

React app có thể được chia thành các component nhằm:

- Tái sử dụng code
- Bố trí code để quản lý

## Component và state

Component cha có thể "truyền" state xuống component con.

Component con có thể kích hoạt event để component cha cập nhật.

## Nên đặt state ở đâu?

Nếu nhiều component cần truy cập state giống nhau, thường ta sẽ đặt state ở component cha **chung**. Sau đó truyền vào các component con dưới dạng props.
Xem thêm: [React docs: lifting state up](https://reactjs.org/docs/lifting-state-up.html)

## Ví dụ: component và state trong TODO app:

<img src="assets/todo-components-state.svg" />

## Ví dụ: prop và event trong TODO app:

<img src="assets/todo-components-state-props-events.svg" />

## Định nghĩa component

Có 2 cách phổ biến:

- Dưới dạng function (trước đây gọi là stateless component)
- Dưới dạng class (phổ biến trước khi có Hooks)

## Định nghĩa component

Để phân biệt component với các tag HTML khác, component phải được đặt tên chữ cái đầu viết hoa.
