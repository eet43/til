파일 입력창 만들기
==


**파일 입력창은 정형화된 패턴이 있기에 참고하면 좋다.**

```html
<!--파일을 불러오는 입력 태그들-->
<form>
  <div class="custom-file">
    <input type="file" class="custom-file-input" id="customFile">
    <label class="custom-file-label" for="customFile">Choose file</label>
  </div>
</form>
```


```jsx
///파일을 가져오면 입력창에 보여주는 라이브러리
<script src="https://cdn.jsdelivr.net/npm/bs-custom-file-input/dist/bs-custom-file-input.js"></script>
```

```javascript
//화면이 처음 시작되면 실행시키면된다.
bsCustomFileInput.init()
```
