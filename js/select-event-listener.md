이벤트 리스너 선택해 실행하기
==


**특정 HTML 태그에 이벤트 리스너를 장착해 그에 맞는 함수를 실행시키기**

```javascript
function func() {
  document.querySelector("#id값").addEventListener("click", 실행시킬 함수명);
}
```



**문서가 열지마자 실행시키기**

```javascript
$(document).ready(function () {
            let url = window.location.href.substring(32)
        });
}
```

해당 문서가 열리자마자, function()을 실행시킨다. 해당 문서의 url의 32번째 인덱스부터 끝까지 불러와 url에 담는다.

