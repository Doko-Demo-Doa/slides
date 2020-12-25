# JSX cơ bản

## JSX: JS + XML

JSX = cú pháp của React

- **<** chuyển JS sang XML/HTML
- **{** chuyển lại về JS

## Gán dữ liệu

```jsx
<div>Một năm có {365 * 24} giờ</div>
```

## Gán nội dung

Task:

- Hiển thị ngày giờ hiện tại
- Hiển thị một trong 2 chữ "sấp" và "ngửa" trong một `<div>`

## Gán nội dung

hiển thị ngày:

```jsx
const dateString = new Date().toLocaleDateString();
```

```jsx
<div>ngày hiện tại: {dateString}</div>
```

sấp hay ngửa:

```jsx
<div>{Math.random() > 0.5 ? 'sấp' : 'ngửa'}</div>
```

## Gán biến

chúng ta cũng có thể chuyển từ XML sang JS:

```jsx
<a href={'https://en.wikipedia.org/wiki/' + articleName}>
  bài viết
</a>
```

Lưu ý: Không có kí tự nháy kép xung quanh giá trị của _href_

## Gán event

```jsx
const hello = () => {
  console.log('hello world');
  // ...
};
```

```jsx
<button onClick={hello}>Say Hello</button>
```

Danh sách các browser event:
https://www.w3schools.com/jsref/dom_obj_event.asp

## Gán event

Lưu ý: Một event handler phải là **function** (chứ không phải việc gọi function)

Đúng:

```js
<button onClick={alert}>Say something</button>
```

Không đúng:

```js
<button onClick={alert('hello')}>Say Hello</button>
```

Đúng:

```js
<button onClick={() => alert('hello')}>Say Hello</button>
```

## Lặp lại phần tử

Nhiều phần tử có thể được thêm vào bằng mảng (array):

```jsx
const elements = [
  <div>dota</div>,
  <div>lol</div>,
  <div>csgo</div>,
];
```

```xml
<h1>3 phần tử:</h1>
{ elements }
```

## Lặp lại phần tử

Ví dụ: Hiển thị tất cả các tên phương thức của _React_ trong element _ul_

```jsx
const reactMethods = [];
for (let method in React) {
  reactMethods.push(<li>{method}</li>);
}
```

```jsx
<div>
  React Methods:
  <ul>{reactMethods}</ul>
</div>
```
