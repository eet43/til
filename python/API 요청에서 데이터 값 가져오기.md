# API 요청에서 데이터 값 가져오기

## HTML 게시물 혹은 JSON으로 인코딩 하지 않을 경우
```python
search = request.form['search'] #키 이름을 알 경우
page = request.form.get('name') #get 키가 없을 때
```

## url 쿼리 매개 변수
```python
search = request.args.get("search")
page = request.args.get("page")
```


## JSON으로 인코딩 처리 해 보낼 경우
```python
search = request.data['search'] #키 이름을 알 경우
```
