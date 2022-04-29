동적으로 태그를 선택해 클래스 추가하기.
==


**선택적으로 클래스 추가하기**<br>

```javascript
// 선택적 클래스 추가
${`#id`).addClass(“class_name”)
```
<br><br>

**형제 태그들을 찾아 클래스 없애기**<br>

```javascript
// 형제 태그들을 찾아 클래스 없애기 (하나의 태그에만 클래스 적용하기 위함 )
${`#id`).siblings().removeClass(“class_name”)
```
<br><br>


**특정 태그를 찾아 화면 이동하기**<br>

```javascript
// 형제 태그들을 찾아 클래스 없애기 (하나의 태그에만 클래스 적용하기 위함 )
${`#id`).scrollIntoView()
```
