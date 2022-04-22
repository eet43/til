radio 값 함수에 전달하기
==


**input 태그 radio 값들 중 선택된 값을 js 함수로 넘기고 싶다면**

```html
<input type="radio" name="rating" value="5" onclick="createStar(this.form)">⭐</label>
```

**클릭 되었을 때 실행시킬 함수에 매개변수로 this.form 값으로 준다.**


```javascript
let radio = $('input[name=rating]:checked').val();
```

**실행시킬 함수 안에서 name 값과 연결시켜 해당 값을 변수에 담아준다.**

