# 컬렉션 Null 값 처리

제일 좋은 건 Optional<> 을 사용하는 것인데, 익숙지 않아서 임시방편으로 Null 값에 대한 처리를 해보자.<br>
stream.filter() 를 사용하면 null 컬렉션을 stream() 할 때 에러가 발생하는거기 때문에 의미 없다.<br>
``` java
List<Education> educationList = Optional.ofNullable(editResumeRequest.getEducations()).orElse(Collections.emptyList())
                .stream()
                .map(educationRepository::save)
                .collect(Collectors.toList());
```
이렇게 하면 null 값이 오면 빈 컬렉션을 만들어준다.
