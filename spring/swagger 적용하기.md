# swagger 적용하기

Swagger란 개발한 REST API를 편리하게 문서화 해주고, 이를 통해서 편리하게 API를 호출해보고 테스트할 수 있는 오픈소스이다.<br><br>
Swagger 에서 제공해주는 다양한 기능 툴이 있지만 우리는 springfox-boot-starter 을 통해 손 쉽게 핵심 기능들을 사용할 수 있다.<br><br>

```gradle
// https://mvnrepository.com/artifact/io.springfox/springfox-boot-starter
implementation group: 'io.springfox', name: 'springfox-boot-starter', version: '3.0.0'
```
<br><br>
프로그램을 실행한 뒤 url 끝에 /swagger-ui/ 를 붙이면 작성한 API를 확인할 수 있다.<br><br>
따로 설정파일을 만들어 커스텀 할 수도 있다. 이에 대해서는 후에 설명하겠다.
