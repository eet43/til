# Left Join 과 Inner Join 의 차이점

## JOIN 이란 ?
보통 데이터베이스를 설계할 때 기능에 따라 도메인과 테이블을 구분한다. <br>
JOIN 는 두 테이블에 나누어져있는 데이터들을 합쳐서 사용해야할 때 쓰이는 sql 문법이다.<br>
가장 많이 사용되는 Left Join 과 Inner Join 의 차이점에 대해 설명하겠다. <br><br>

## 테이블 소개
<img width="685" alt="01" src="https://user-images.githubusercontent.com/59008469/169740265-3137d72f-826e-4e1d-8d2f-4e587236f70d.png">



## Left Join 이란 ?
Left Join 은 Outer Join 의 일종이며, 합집합의 종류 중 하나이다.<br>
왼쪽 테이블의 모든 정보를 가져오며, 테이블을 연결하는 key 의 값이 NULL 일 때 오른 쪽 테이블의 정보들은 NULL 값으로 채워진다.<br><br>
<img width="762" alt="02" src="https://user-images.githubusercontent.com/59008469/169740374-763d9ab2-485a-4ae7-aa65-dfbf1846e9ad.png">



## Inner Join 이란 ?
Inner Join 은 교집합이라고 생각하면 편하다.<br>
테이블을 연결하는 key 의 값이 겹치는 부분의 레코들의 집합만 가져와 두 테이블을 합친다.<br><br>
<img width="758" alt="03" src="https://user-images.githubusercontent.com/59008469/169740377-b128df12-8c1d-4b0c-90de-4d538949b854.png">
