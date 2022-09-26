# CONCAT 이란

가끔 여러 문자열 혹은 컬럼 값을 합쳐서 가져와야 하는 경우가 있다.<br><br>
이 때 CONCAT 함수를 사용하면 해결 할 수 있다.<br><br>
CONCAT 함수는 둘 이상의 문자열을 입력한 순서대로 합쳐 반환해준다.<br><br>

~~~~sql
CONCAT(ad_width, 'x', ad_height) AS ad_size,
~~~~

<br><br>
반환 값에는 ad_size 컬럼에 "ad_width x ad_height" 형태로 나타난다.<br><br>
주로 `높이+너비` 혹은 `년+월` 형태일 때 자주 사용된다.<br><br>
