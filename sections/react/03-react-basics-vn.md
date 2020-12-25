# React cơ bản

## Công cụ sửa code online

khuyến cáo: <https://codesandbox.io>

khác:

- Glitch: <https://glitch.com/edit/#!/remix/starter-react-template>
- CodePen: <https://reactjs.org/redirect-to-codepen/hello-world>

## Ví dụ component tự tạo

```jsx
import React, { useState } from 'react';

function CounterApp() {
  const [count, setCount] = useState(0);

  return (
    <div>
      count: {count}
      <button onClick={() => setCount(count + 1)}>+</button>
    </div>
  );
}

export default CounterApp;
```

## Ví dụ component (2)

```jsx
import React, { useState } from 'react';

function SlideshowApp() {
  const [img, setImg] = useState(0);
  return (
    <div>
      <button onClick={() => setImg(0)}>start</button>
      <button onClick={() => setImg(img - 1)}>prev</button>
      <img
        src={`https://picsum.photos/200?image=${img}`}
        alt="slideshow"
      />
      <button onClick={() => setImg(img + 1)}>next</button>
    </div>
  );
}

export default SlideshowApp;
```

## Function component và class component

tùy vào lựa chọn:

- tạo component dạng function
- tạo component dạng class (là lựa chọn phổ biến trước khi react hooks ra đời)

## Định nghĩa component

Để phân biệt component với các thẻ thông thường của HTML, tên component bắt đầu bằng chữ cái viết hoa
