url에서 원하는 값 사용하기
==


**url 파라미터 값 사용하기**<br>

```python
# ex) url : localhost:5000/api/board/?var_name="11"
data = request.args.get(“var_name”)
#data=11
```
<br><br>

**url 특정 문자열 값 사용하기**<br>

```python
# ex) url : localhost:5000/api"
@app.route(‘/<keyword>’)
def def_name(keyword)
return render_template(‘’,keyword = keyword)
#keyword="api"
```
