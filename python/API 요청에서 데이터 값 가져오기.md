# API 요청에서 데이터 값 가져오기

## HTML 게시물 혹은 JSON으로 인코딩 하지 않을 경우
```python
search = request.form['search'] #키 이름을 알 경우
page = request.form.get('name') #get 키가 없을 때
```

## url 쿼리 매개 변수

**url 파라미터 값 사용하기**<br>

```python
# ex) url : localhost:5000/api/board/?var_name="11"
data = request.args.get(“var_name”)
#data=11
```
<br>

**url 특정 문자열 값 사용하기**<br>

```python
# ex) url : localhost:5000/api"
@app.route(‘/<keyword>’)
def def_name(keyword)
return render_template(‘’,keyword = keyword)
#keyword="api"
```


## JSON으로 인코딩 처리 해 보낼 경우
```python
search = request.data['search'] #키 이름을 알 경우
```
