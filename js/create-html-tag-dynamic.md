동적으로 HTML 코드 설계하기
==


**데이터가 리스트 형태로 여러개 존재하고 반복문을 돌며 그 값들을 적용하여 화면을 그려줘야 한다면**

```javascript

//우선 반복문을 실행켜 값을 가져온다.
let tmp_html = `
    <div>
        <p>${name}</p>
    </div>
`;

$('#model_card').append(tmp_html);

//id값이 model_card 값 뒤에 해당 html 코드를 붙인다.
```
