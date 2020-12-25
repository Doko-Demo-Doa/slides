# State

## State

Component có thể có _state_ nội tại

State có thể được tham chiếu trong template, giao diện sẽ được tự động cập nhật nếu state có thay đổi.

## State hook

Trong function component, ta sử dụng _state hook_:

```js
import { useState } from 'react';
```

## State hook

`useState` có thể được gọi lại (nhiều lần) trong function component

- `useState` nhận 1 tham số đầu vào: giá trị đầu tiên được khởi tạo
- mỗi lần call `useState` sẽ trả về một mảng gồm 2 phần tử: state hiện tại và một hàm để set giá trị mới cho state

```js
const App = () => {
  const [count, setCount] = useState(0);
  const [title, setTitle] = useState('React app');

  return ...
};
```

## Ví dụ: nút đếm số

Chúng ta sẽ thêm một nút vào app. Ban đầu trên nút sẽ hiển thị số 0, sau mỗi click thì tăng lên 1.

## Ví dụ: nút đếm số

```jsx
const Counter = () => {
  const [count, setCount] = useState(0);

  return (
    <button
      onClick={() => {
        setCount(count + 1);
      }}
    >
      {count}
    </button>
  );
};
```

## Ví dụ: Slideshow

Làm một trang slideshow hiển thị ảnh như dưới đây:

`https://picsum.photos/200?image=10`

- có 2 nút _previous_ và _next_
- có 1 nút _về trang đầu_
- chặn không cho số thứ tự bị âm
