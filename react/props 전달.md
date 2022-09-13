# props 전달하기

다른 컴포넌트에 매개변수를 전달하려면 props를 통해 전달할 수 있다.<br><br>

크게 2가지 방법이 있다.
1. props.~ 로 접근하기.
2. 비구조화 할당으로 접근하기.


## 1. props.~ 로 접근하기.

### App.js
```javascript
import React from 'react';
import Hello from './Hello';

function App() {
  return (
    <Hello name="react" color="red"/>
  );
}

export default App;
```

### Hello.js
```javascript
import React from 'react';

function Hello(props) {
  return <div style={{ color: props.color }}>안녕하세요 {props.name}</div>
}

export default Hello;
```

---

## 2. 비구조화 할당으로 접근하기.

### App.js
```javascript
import React from 'react';
import Hello from './Hello';

function App() {
  return (
    <Hello name="react" color="red"/>
  );
}

export default App;
```

### Hello.js
```javascript
import React from 'react';

function Hello({ color, name }) {
  return <div style={{ color }}>안녕하세요 {name}</div>
}

Hello.defaultProps = {
  name: '이름없음' //default 값을 지정해줄 수도 있다.
}

export default Hello;
```
