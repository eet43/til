MongoDB에서 데이터 받아와 사용하기
==


**mongodb 의 자동 pk 값인 _id 는 자료형이 특이한 필드 값이라 그대로 받아오면 화면을 구성할 때
에러가 발생한다.**<br>

```python
# 옵션을 설정해 _id 값은 가져오면 안된다.
words = list(db.words.find({}. {“_id” : False})
```
