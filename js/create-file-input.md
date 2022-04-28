파일 입력창 만들기
==


**파일 입력창은 정형화된 패턴이 있기에 참고하면 좋다.**
<br><br>
```html
<!--파일을 불러오는 입력 태그들-->
<form>
  <div class="custom-file">
    <input type="file" class="custom-file-input" id="customFile">
    <label class="custom-file-label" for="customFile">Choose file</label>
  </div>
</form>
```
<br>

```jsx
///파일을 가져오면 입력창에 보여주는 라이브러리
<script src="https://cdn.jsdelivr.net/npm/bs-custom-file-input/dist/bs-custom-file-input.js"></script>
```
<br>
```javascript
//화면이 처음 시작되면 실행시키면된다.
bsCustomFileInput.init()
```

<br><br>
**파일 저장과 같은 버튼이 클릭되었을 때 파일을 서버로 보내려면 다음과 같은 함수가 필요하다.**
<br>

```javascript
function posting() {
    let title = $('#title').val() // 추가 데이터 1
    let content = $("#content").val() // 추가 데이터 2

    let file = $('#file')[0].files[0] // $('#file')[0] : id 값이 file인 태그 하나를 가져온다. .files[0] 은 그 태그에 해당하는 데이터들 중 첫번째이다.
    let form_data = new FormData() // 파일데이터는 폼데이터로 감싸야함

    form_data.append("file_give", file)
    form_data.append("title_give", title)
    form_data.append("content_give", content)

    $.ajax({
        type: "POST",
        url: "/diary",
        data: form_data,
        cache: false,
        contentType: false,
        processData: false, //옵션
        success: function (response) {
            alert(response["msg"])
            window.location.reload()
        }
    });
}
```
