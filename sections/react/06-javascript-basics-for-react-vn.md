# JavaScript cơ bản cho React

## Chuẩn của JavaScript

JavaScript là ngôn ngữ đã được chuẩn hóa bởi tổ chức [_ECMAScript_ (ES)](https://www.ecma-international.org/ecma-262/)

## Phiên bản JavaScript

_ES5_: Hỗ trợ bởi tất cả các trình duyệt, kể cả Internet Explorer

Từ 2015: chuẩn này được cập nhật vào tháng 6 mỗi năm (ES2015, ES2016, ...)

JS hiện đại được biên dịch về ES5 qua các công cụ như Babel, Webpack,...

## Import và export

import và export có tên:

```js
// mymodule.js
const foo = 1;
const bar = 2;
const baz = 3;

export { foo, bar, baz };
```

```js
// index.js
import { foo, bar } from 'mymodule.js';
```

## Import và export

Chỉ có thể có 1 `default export`

```js
// mymodule.js
const foo = 1;
const bar = 2;
const baz = 3;

export { foo, bar, baz };

const main = 0;

export default main;
```

```js
// index.js
import main, { foo, bar } from 'mymodule.js';
```

## Import trong webpack

Các công cụ bundler như webpack có thể hơi khác so với chuẩn import Javascript thông thường:

- Import có thể không cần đuôi `.js`
- Nếu import vào folder, webpack sẽ tự tìm file `index.js`

## Arrow function

- Cú pháp ngắn gọn cho function vô danh
- Giữ biến _this_ nguyên trạng (không bị thay đổi scope)

```js
const multiply = (a, b) => {
  return a * b;
};

const multiply = (a, b) => a * b;
```

## Arrow function

nếu ta muốn return ra object trực tiếp: bọc nó trong ngoặc tròn

```js
const getState = () => ({
  loggedIn: true,
  userName: 'user',
});
```

## Template string

- Cú pháp mới để __tạo ra__ string
- Phân tách bởi dấu backtick \`
- Có thể tạo ra string nhiều dòng và nội suy

```js
const name = 'Mike';
const greeting = `Hello, ${name}!
                  This is ES2015!`;
```

## Dấu chấm phẩy trong JavaScript

Dấu chẩm phẩy cuối câu lệnh trong JavaScript hoàn toàn không bắt buộc.

<!-- prettier-ignore -->
```js
const a = 3
console.log(a)
```

được xem như là:

```js
const a = 3;
console.log(a);
```

## Dấu chấm phẩy trong JavaScript

Tuy nhiên cũng cần lưu ý một số trường hợp như

<!-- prettier-ignore -->
```jsx
const Foo = () => {
  return
    <div>
      <h1>some content</h1>
    </div>;
};
```

sẽ bị coi là return sớm và có thể lỗi:

```jsx
const Foo = () => {
  return;
  <div>
    <h1>some content</h1>
  </div>;
};
```

## Destructuring

```js
const [result, errors] = someComputation();

// đổi giá trị
let a = 1;
let b = 2;
[a, b] = [b, a];
```

## Destructuring

```js
const person = { name: 'John', age: 48 };
const { name, age } = person;

const TodoItem = ({ title, completed }) => (
  <div>
    {completed ? 'DONE: ' : 'TODO: '}
    {title}
  </div>
);
```

## Spread syntax (array và object)

```js
const squares = [1, 4, 9];
const moreSquares = [...squares, 16, 25];
// moreSquares: [1, 4, 9, 16, 25]
```

```js
const person = {
  firstName: 'Joe',
  lastName: 'Doe',
  age: 31,
};
const newPerson = { ...person, email: 'j@d.com', age: 32 };
// {firstName: 'Joe', lastName: 'Doe', email: 'j@d.com', age: 32}
```

## Map và filter

Là 2 phương thức trong functional programming

## Map

- Biến đổi mỗi phần tử trong mảng bằng function
- Tạo ra một array mới, không biến đổi array cũ

```js
const myNumbers = [1, 2, 3, 4];

const tripledNumbers = myNumbers.map((n) => 3 * n);
// [3, 6, 9, 12]
```

## Filter

- Chỉ giữ lại một số phần tử nhất định trong array
- Sử dụng một function để kiểm tra phần tử có đáp ứng điều kiện nào đó hay không
- Cũng tạo ra một array mới, không biến đổi array cũ

```js
const myNumbers = [1, 2, 3, 4];

const isEven = (n) => n % 2 === 0;

const evenNumbers = myNumbers.filter(isEven);
// [2, 4]
```
