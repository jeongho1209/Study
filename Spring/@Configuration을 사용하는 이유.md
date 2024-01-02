## 서론

스프링에서 빈을 등록하는 방법은 

@Component, @Configuration + @Bean, @Bean 정도가 있을 것인데

각각에 대한 개념과 @Configuration을 쓰는 이유에 대해서 알아보자.

미리 알아둬야하는건 스프링은 IOC 컨테이너에 `Bean 객체를 생성할 때 싱글톤을 적용해서 객체를 생성`한다.

---

## @Confiugration

`Bean을 등록`하거나 `설정 파일`을 만들 때 사용하는 어노테이션이다.

---

## @Component

Bean을 등록할 때 사용하는 어노테이션 (보통 개발자가 제어가 가능한 클래스에 사용)

---

## @Bean

Bean을 등록할 때 사용하는 어노테이션 (보통 개발자가 제어가 불가능한 클래스(라이브러리)에 사용)

---

## @Configuration 쓰는 이유

보통 @Bean 어노테이션을 사용할 때는 @Configuration과 같이 사용하는데 그 이유는 아래와 같다.

@Bean 어노테이션만 사용해서 Bean 등록을 하게 되면 `싱글톤으로 만들어지지 않는다.`

하지만 `@Configuration과 함께 @Bean을 사용`하면 `싱글톤`을 보장 가능하다.

---