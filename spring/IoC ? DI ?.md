# IoC ? DI ?
스프링을 공부하다보면, IoC 와 DI 키워드를 많이 볼 수 있다. 예제를 통해 자세히 알아보자.<br><br>

OrderServiceImpl.java
```java
  public class OrderServiceImpl implements OrderService {
  //    private final DiscountPolicy discountPolicy = new FixDiscountPolicy();
      private final DiscountPolicy discountPolicy = new RateDiscountPolicy();
  }
```
주문 인터페이스인 `OrderService`의 구현체인 `OrderServiceImpl` 가 있다. `OrderServiceImpl` 은 할인정책이 바뀔 때마다, 구현체의 코드를 수정해주어야 한다. 즉 할인 인터페이스인 `DiscountPolicy`
뿐만 아니라 할인 구현체인 `FixDiscountPolicy`와`RateDiscountPolicy`를 함께 의존한다는 뜻이다. <br><br>

이는 OOP 원칙 중 OCP, DIP 를 위반하는 행위이다. 때문에 우리는 구현체를 생성해주고 연결해주는 외부생성자가 필요하다.<br><br>

## AppConfig 등장
이제부터 구현체는 생성자 주입을 통해, 더이상 구현체에 의존하지 않고 AppConfig 에서 정한 구현체를 받아 사용할 것이다.<br><br>

AppConfig.java
```java
  public class AppConfig {
    public OrderService orderService() {
      return new OrderServiceImpl(
        new FixDiscountPolicy()); //외부에서 주입
      )
    }
  }
```

OrderServiceImpl.java
```java
  public class OrderServiceImpl implements OrderService {
      private final DiscountPolicy discountPolicy;
      
      public OrderServiceImpl(DiscountPolicy discountPolicy) {
        this.discountPolicy = discountPolicy; //생성자 주입을 통해 구현체를 입력받는다.
      }
  }
```

OrderApp ( main 함수 )
```java
  public class OrderApp {
    public static void main(String[] args) {
      AppConfig appConfig = new AppConfig();
      OrderService orderService = appConfig.orderService();
    }
  }
```
<br><br>
SRP : 실행하는 객체와 생성하고 연결하는 객체가 구분됨. 하나의 책임만을 가진다. <br>
DIP : 구현체에 의존하지 않고, 인터페이스에만 의존한다. ( 더이상, Fix, Rate 할인 정책에 의존하지 않는다 ) <br>
OCP : 더이상 구현체 클라이언트 코드는 건드리지 않는다. 그저  AppConfig 파일만 수정하면 된다. <br>

<br><br>

## 그래서 IoC가 뭔데 ?
IoC란 제어의 역전의 의미를 가진다. 기존 코드에서는 클라이언트 구현 객체가 스스로 서버 구현 객체를 `new` 키워드와 함께 생성하고 연결하여 실행했다.<br>
`AppConfig`가 등장한 이후로 구현 객체는 로직을 실행하는 역할만 담당하고 프로그램의 제어 흐름은 `AppConfig`가 가지고 있다.<br>
심지어 `OrderServiceImpl` 또한 `AppConfig` 가 생성하여 실행한다. 이처럼 프로그램의 제어 흐름을 직접 제어하는게 아닌 외부에서 관리해 사용하는 것을 제어의 역전 `IoC` 라고 한다. <br><br>

## 그럼 DI는 뭐야 ?
DI란 의존관계 주입의 의미로, 자세히 알기 전에 의존관계의 종류를 확인해야한다. 크게 2가지 의존관계가 있다.<br>
1. 정적인 클래스 의존관계
2. 동적인 클래스 의존관계 (실행 시점에 결정) <br>

### 정적 클래스 의존관계
정적 클래스 의존관계란, 코드만 보고 어떤 클래스를 의존하는지 그 관계를 알 수 있는 것을 의미한다.<br>
위 코드로 보았을 때 `OrderServiceImpl` 는 `DiscountPolicy` 에 의존하는 것을 알 수 있다.<br>
그러나 실제로 DiscountPolicy 의 어떤 구현체가 주입 될지 알 수 없다.<br><br>

### 동적 클래스 의존관계
동적 클래스 의존관계란, 실제 실행 시점에 생성된 객체 인스턴스의 참조가 연결된 의존관계이다.<br>
`OrderServiceImpl` 는 AppConfig에 의해 실행시점에 `FixDiscountPolicy` 의 참조를 연결받아 의존하는 것을 알 수 있다.<br>


## DI란
이처럼 실행시점에 외부 (AppConfig) 에서 실제 구현 객체를 생성하고 (FixDiscountPolicy) 클라이언트 (OrderServiceImpl) 에 전달해서 클라이언트, 서버의 의존관계가 연결되는 것을 의존관계 주입 `DI` 라고 한다.<br>Dㅇ
DI를 사용하게 되면, 클라이언트 코드를 변경하지 않고, 호출하는 대상의 인스턴스(Fix? Rate?)를 변경할 수 있다.<br>
**또한 정적인 클래스 의존관계를 변경하지 않고, 동적인 객체 인스턴스 의존관계를 쉽게 변경할 수 있다.**










