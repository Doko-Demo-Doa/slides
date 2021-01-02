# JSX chi tiết

## JSX chi tiết

mục lục:

- thuộc tính
- lặp phần tử
- if / else
- if
- khoảng trắng
- comment
- fragment
- element hợp lệ
- compilation

## Tên thuộc tính

Một số thuộc tính có tên khác với HTML:

- `className` (thay cho `class`)
- `onClick` (thay cho `onclick`)
- `htmlFor` (thay cho `for`)

## Tên thuộc tính

Ví dụ: CSS class

```jsx
<li
  className={
    isCompleted ? 'todoitem completed' : 'todoitem'
  }
>
  [...]
</li>
```

Có rất nhiều thư viện giúp cho việc tạo _className_ động, ví dụ: [classnames](https://www.npmjs.com/package/classnames)

## Thuộc tính style

Trong JSX, thuộc tính _style_ nhận đầu vào là object:

```jsx
<div
  style={{
    backgroundColor: '#333',
    fontSize: getFontSize(),
  }}
/>
```

## Lặp phần tử
Xây dựng một danh sách HTML (thẻ `ul`) từ data sau:

```js
const initialTodos = [
  { id: 1, title: 'groceries', completed: false },
  { id: 2, title: 'cooking', completed: true },
  { id: 3, title: 'gardening', completed: false },
];
```

## Lặp phần tử

Ta có thể sinh ra mảng các phần tử JSX bằng `.map`:

```jsx
const TodoApp = () => {
  const [todos, setTodos] = useState(initialTodos);
  return (
    <ul>
      {todos.map((todo) => (
        <li>{todo.title}</li>
      ))}
    </ul>
  );
};
```

## Lặp phần tử

Với đoạn code trên, console sẽ cảnh báo đỏ vì thiếu thuộc tính `key`, ta thêm vào như sau:

```jsx
<ul>
  {todos.map((todo) => (
    <li key={todo.id}>{todo.title}</li>
  ))}
</ul>
```

## if / else

```jsx
<div>{Math.random() > 0.5 ? 'heads' : 'tails'}</div>
```

## if / else

```jsx
let face;
if (Math.random() > 0.5) {
  face = 'heads';
} else {
  face = 'tails';
}

return <div>{face}</div>;
```

## if

```jsx
<div>{state.hasError && state.errorMessage}</div>
```

Toán tử `&&` trong JavaScript: Dùng để rút gọn biểu thức

```js
true && 'my message'; // 'my message'

false && 'my message'; // false
```

## Khoảng trắng

Các đoạn code HTML dưới đây là như nhau (hiển thị một dấu cách giữa các ảnh):

<!-- prettier-ignore-start -->

```html
<img src="foo.png" /> <img src="bar.png" />
```

```html
<img src="foo.png" />    <img src="bar.png" />
```

```html
<img src="foo.png" />
<img src="bar.png" />
```

<!-- prettier-ignore-end -->

## Khoảng trắng

quy tắc trong JSX:

- Khoảng trắng giữa 2 element trên 1 dòng sẽ được tính như 1 khoảng trắng.

- Khoảng trắng giữa 2 element trong 2 dòng khác nhau sẽ được bỏ qua

<!-- prettier-ignore-start -->

Một khoảng trắng:

```xml
<img src="foo.png" />     <img src="bar.png" />
```

Không có khoảng trắng:

```xml
<img src="foo.png" />
<img src="bar.png" />
```

<!-- prettier-ignore-end -->

## Khoảng trắng

"ép" hiển thị khoảng trắng trong JSX:

```xml
<img src="foo.png" />{" "}
<img src="bar.png" />
```

## Comment trong JSX

Comment có thể được viết dưới dạng JavaScript:

```jsx
a = <div>Hello World!{/*this is a comment*/}</div>;
```

## Fragment

Fragment cho phép return nhiều element trong một component mà không cần có thẻ nào khác bao ngoài (thường là `div`):

```jsx
return (
  <>
    <td>Hello</td>
    <td>World</td>
  </>
);
```

hoặc

```jsx
return (
  <React.Fragment>
    <td>Hello</td>
    <td>World</td>
  </React.Fragment>
);
```

## element hợp lệ

- string
- number
- component (ví dụ: `<div>`, `<img>`, `<MyComponent>`)
- một mảng các element
- null, undefined, true, false (sẽ không được render)

## JSX compilation

```jsx
const element = <a href="https://google.com">Google</a>;
```

được compile thành:

```js
const element = React.createElement(
  'a',
  { href: 'https://google.com' },
  'Google'
);
```

## JSX compilation

```jsx
const element = (
  <MyComponent prop1={1} prop2={2}>
    <div>test 1</div>
    <div>test 2</div>
  </MyComponent>
);
```

được compile thành:

```js
const element = React.createElement(
  MyComponent,
  { prop1: 1, prop2: 2 },
  React.createElement('div', null, 'test 1'),
  React.createElement('div', null, 'test 2')
);
```
