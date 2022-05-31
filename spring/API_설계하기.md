# API 설계하기
웹 MVC 패턴과 API 서버는 아키텍처가 조금 다르기에, 별도의 API 패키지로 구분하는게 좋다.<br><br>

## 핵심
API를 설계할 때에는 절대 ! 엔티티를 직접 사용하면 안된다. <br><br>
***반드시 !*** 별도의 요청, 응답 객체 (DTO) 를 생성한 후, 사용해야 한다. <br><br>
API 따라 다른 속성, null or notempty 등 속성은 그 DTO 객체에 부여해야한다. <br><br>

## 예시
```java
@RestController //API 전용 컨트롤러 어노테이션
@RequiredArgsConstructor
public class MemberApiController {
    private final MemberService memberService;

    @PostMapping("/api/v2/members") //POST
    public CreateMemberResponse setMember(@RequestBody @Valid CreateMemberRequest request) { //별도의 응답, 요청 객체를 만들었다.
        Member member = new Member();
        member.setName(request.getName());

        Long id = memberService.join(member);
        return new CreateMemberResponse(id);
    }

    @Data //Getter, Setter 포함되어있다.
    static class CreateMemberResponse { //반드시 정적 클래스로 선언 (static)
        private Long id;

        public CreateMemberResponse(Long id) {
            this.id = id;
        }
    }

    @Data //Getter, Setter 포함되어있다.
    static class CreateMemberRequest { //반드시 정적 클래스로 선언 (static)
        @NotEmpty //API 마다 다른 속성 부여
        private String name;
    }
}
```
