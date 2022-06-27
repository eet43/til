# JUnit5 테스트
보통 assertThat 을 많이 선호하는데, JUnit 5 에는 따로 추가를 안 해주면 못 쓰는 거 같다.<br><br>

```java
import static org.hamcrest.CoreMatchers.is;
import static org.hamcrest.MatcherAssert.assertThat;
```

<br><br>
이 두개를 정적으로 추가 시키면, 잘 동작하는거 같다.<br><br>
추가로 계속 테스트 관련 문서들을 기록해보자.
