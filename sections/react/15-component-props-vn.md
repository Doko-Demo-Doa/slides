# Component props

## State và props

- state = thuộc nội bộ component
- props = các tham số được truyền vào từ component cha

## Component props

ví dụ:

```jsx
<ProgressBar value={0.75} color="green" />
```

<img src="assets/progress-bar.png" style="width:16em" />

## Component props

Ví dụ khởi tạo component (TypeScript) với props:

```tsx
type Props = { value: number; color?: string };

const ProgressBar = (props: Props) => {
  // ...
};
```

## Component props

Ví dụ khởi tạo component với props object destructuring:

```tsx
const ProgressBar = ({ value, color }: Props) => {
  // ...
};
```
