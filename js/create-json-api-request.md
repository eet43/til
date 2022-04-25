JSON 데이터를 실어 API 호출하기
==


**데이터가 JSON으로 묶이지 않아 제대로 된 요청이 되지 않을 때 JSON 으로 데이터 포맷하기.**<br>

```javascript
request_body = {
        "content": content
    } //데이터를 묶어준다. JSON화

    $.ajax({
        type: "POST",
        url: `/api/board/${url}/comment`,
        dataType: 'json', //데이터 타입을 지정해준다.
        contentType: 'application/json; charset=utf-8',
        data: JSON.stringify(request_body), //다시 string으로 바꿔 묶은 데이터를 보낸다.
        success: function (response) {
            console.log(response)
        }
    })
}
```
