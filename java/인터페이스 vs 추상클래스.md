# 인터페이스 vs 추상클래스

## 그전에, tips

```java
Person person = new Student();
```
person 인스턴스는 Person 타입으로 선언된 Student 객체이다. 때문에 person 인스턴스는 Person 변수와 메소드에만 접근할 수 있다. Student 객체 안에 선언된 메소드에는 접근할 수 없다.<br><br>

## 인터페이스 vs 추상클래스

**인터페이스** 
<ul>
  <li>객체의 동작을 명세화 한다.</li>
  <li>다중 상속이 가능하다.</li>
  <li>메소드에 대한 선언만 가능하다. 구현은 불가능하다</li>
  <li>implements 사용.</li>
</ul>


  
**추상클래스** 
<ul>
  <li>클래스를 상속 받아 확장하기 위함이다.</li>
  <li>단일 상속만 가능하다.</li>
  <li>메소드에 대해 직접 구현도 가능하다.</li>
  <li>extends 사용.</li>
</ul>

