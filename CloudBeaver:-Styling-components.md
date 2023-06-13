We use [CSS Modules](https://github.com/css-modules/css-modules) for styling components.

### Example

#### ExampleComponent.tsx
```jsx title="ExampleComponent.tsx"
import { useState } from 'react';
import { useS, s } from '@cloudbeaver/core-blocks';
import style from './ExampleComponent.m.css';

function ExampleComponent({ className }) {
  const [mode, setMode] = useState('enabled');
  const [status, setStatus] = useState(false);
  const styles = useS(style);

  function handleClick() {
    setStatus(!status);
    if(status) {
      setMode('enabled');
    } else {
      setMode('disabled');
    }
  }

  return (
    <div className={s(styles, { box: true }, className)}>
      <h2 className={s(styles, { header: true })}>This is Header</h2>
      <p className={s(styles, { message: true, status })}>This is message</p>
      <button
        className={s(styles, { switch: true })}
        data-s-mode={mode}
        type="button"
        onClick={handleClick}
      >
        Change status
      </button>
    <div>
  );
}
```

#### ExampleComponent.m.css
```css title="ExampleComponent.m.css"
.box {
  border-radius: 3px;
  border: solid 1px;
}
.header {
  margin: 0;
}
.message {
  padding: 8px;
}
.status {
  color: red;
}
.switch {
  padding: 2px; 4px;
}
.switch[data-s-mode="disabled"] {
  opacity: 0.75;
}
```