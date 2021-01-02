# Input & form

## Input

Trong React, thẻ `<input>` khá đặc biệt:

Thuộc tính (property, `.value`) có thể được thay đổi trực tiếp bởi người dùng.

Do đó sẽ có một số phương diện của UI state sẽ không được nhận bởi React state.

## Input

Đây là cách ta điều khiển và theo dõi giá trị của `input` trong state:

```jsx
const [inputText, setInputText] = useState('');

<input
  value={inputText}
  onChange={(event) => {
    setInputText(event.target.value);
  }}
/>
```

## Form action

Hành vi mặc định của một form khi được submit: Gửi thẳng data lên server

Ta sẽ thay thế hành vi đó:

```jsx
<form
  onSubmit={(event) => {
    event.preventDefault(); // Quan trọng
    // handle submit
  }}
>
  <input />
</form>
```

## Form validation

Form validation thủ công:

```js
const NewsletterRegistration = () => {
  const [email, setEmail] = useState('');
  const [emailEdited, setEmailEdited] = useState(false);
  const emailInvalid = !isEmail(email);
  return (
    <form
      onSubmit={(e) => {
        e.preventDefault();
        console.log(email);
      }}
    >
      <input
        type="email"
        name="email"
        value={email}
        onChange={(event) => setEmail(event.target.value)}
        onBlur={() => setEmailEdited(true)}
      />
      <button disabled={emailInvalid}>subscribe</button>
      {emailEdited && emailInvalid ? (
        <div>email không hợp lệ</div>
      ) : null}
    </form>
  );
};

const isEmail = (email) =>
  email.match(/^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,}$/i);
```
