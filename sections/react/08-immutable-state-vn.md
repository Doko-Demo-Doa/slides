# Immutable state - Trạng thái bất biến

## Immutable state

**Immutability**: Một trong những khái niệm quan trọng trong functional programming, được sử dụng trong React / Redux

Dữ liệu không được sửa đổi trực tiếp, mà sẽ có dữ liệu khác tạo ra, biến đổi từ dữ liệu cũ (có thể sẽ thay thế dữ liệu cũ)

## Immutable state

Khi có object hoặc array, ta thường thử thay đổi chúng trực tiếp

và điều này là _không nên_, React sẽ không nhận ra thay đổi và sẽ không render lại view.

State nên được xem như một dạng dữ liệu bất biến (immutable).

## Immutable state

Khi `setState` được gọi, React sẽ so sánh

- Object mà state cũ trỏ tới
- Object mà state mới trỏ tới

Nếu state cũ và state mới đều tham chiếu (refer) đến cùng một object (dù có thay đổi), component cũng sẽ **không** được render lại.

## Immutable state

demo (xem thêm: <https://codesandbox.io/s/exciting-dust-w7hni>):

```js
function App() {
  const [numbers, setNumbers] = useState([0, 1, 2]);
  return (
    <div>
      <div>{JSON.stringify(numbers)}</div>
      <button
        onClick={() => {
          // không hợp lệ - sửa state
          numbers.push(numbers.length);
          setNumbers(numbers);
        }}
      >
        add (mutate)
      </button>
      <button
        onClick={() => {
          // hợp lệ - thay state
          setNumbers([...numbers, numbers.length]);
        }}
      >
        add (replace)
      </button>
    </div>
  );
}
```

## Immutable state

code dạng như sau sẽ **không** được chấp nhận khi thay đổi state và React sẽ không render lại:

```js
todos[0].completed = true;
todos.push({ title: 'study', completed: false });
```

## Quản lý dữ liệu mà không biến đổi data: Mảng

Dữ liệu ban đầu:

```js
const names = ['Alice', 'Bob', 'Mallory'];
```

**mutation**: Cách này sẽ biến đổi mảng gốc

```js
names.push('Dan');
```

**không có mutation**: Tạo ra array mới (spread syntax)

```js
const newNames = [...names, 'Dan'];
```

## Quản lý dữ liệu mà không biến đổi data: Object

Dữ liệu ban đầu:

```js
const user = {
  name: 'john'
  email: 'john@doe.com'
}
```

**mutation**: cái này sẽ biến đổi object

```js
user.email = 'johndoe@gmail.com';
```

**không có mutation**: tạo ra object mới (spread syntax)

```js
const newUser = { ...user, email: 'johndoe@gmail.com' };
```

## immer.js

**immer.js** là một thư viện giúp làm việc với dữ liệu bất biến (immutable)

và được Redux khuyến nghị sử dụng

## immer.js

đoạn code này sẽ biến đổi mảng todos:

```js
todos[0].completed = true;
todos.push({ title: 'study', completed: false });
```

tránh biến đổi trực tiếp, bằng cách dùng _immer.js_

```js
import produce from 'immer';

const newTodos = produce(todos, (todosDraft) => {
  todosDraft[0].completed = true;
  todosDraft.push({ title: 'study', completed: false });
});
```
