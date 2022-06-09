# DTO 생성 어노테이션

## @Data
Lombok 라이브러리에서 제공하는 종합선물 어노테이션이라 생각하면 된다.<br><br>
기본적으로 필요한 `@Getter`, `@Setter`, `@ToString`, `@RequiredArgsConstructor` 어노테이션을 모두 포함한다.<br><br>

```java
@Data
public class OrderDto {
...

```


<br><br>

## @RequestBody, @ResponseBody
HTTP 통신에 Body 부분은 JSON 혹은 XML 형태이다. 스프링에서는 객체와 JSON 형식의 데이터를 맞추기 위해 추가설정이 필요하다. <br><br>
`@RequestBody` : 자바 객체를 Http 요청 Body 로 요청 받을 수 있게 해준다. <br><br>
`@ResponseBody` : 자바 객체를 Http 응답 Body 로 전송할 수 있게 해준다.

<br><br>

## @Valid
제약 조건이 부여된 객체의 빈 유효성 검사를 진행해주는 표준 어노테이션이다.<br><br>
예를 들어 @NotNull 어노테이션이 있는 필드 값은 Null 값이 들어가지 않게 확인해준다.<br><br>

```java
@PostMapping("/api/orders")
    public CreateOrderResponse postOrder(@RequestBody @Valid CreateOrderRequest createOrderRequest) {
        ...
    }
```
