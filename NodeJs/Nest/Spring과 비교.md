## 들어가며

기존에 spring만을 학습했기 때문에 새로운 프레임워크인 nest를 학습할 때 기존 개념과
`어떤게 비슷하고 다른지 정리`를 하고 학습을 하면 도움이 될 것이라 생각해 정리를 하게 됐다.

결국 프레임워크를 이루는 DI, IOC 등 핵심은 같기에 nest, spring만의 각각 특이점들을 위주로 학습하는게 좋을 것 같다.

---

## decorator

“@”를 앞에 붙인 후 특정 키워드들을 입력해서 사용할 수 있으며 사용시 특정 기능을 제공해주는 spring의 어노테이션과 비슷하다.

ex)) @Injectable()

---

## controller

spring에서 요청을 받아서 서비스를 호출하고 서비스로부터 적절한 처리를 거친 후
응답을 내려줬던 그 controller와 일치하는 개념인것 같다.
(문법들이 조금씩은 다르지만 천천히 익혀가면 될듯)

```tsx

import { Controller, Get } from '@nestjs/common';

@Controller()
export class HelloController {

    @Get("/test")
    test(): string {
        return "OK";
    }
}
```

---

## provider

nest에서 클래스들을 관리하는 기본적인 단위이다. (spring의 빈이라는 개념과 비슷할듯)
@Injectable()이라는 어노테이션을 사용하면 spring에서 생성자 주입 방식으로 DI를 했던 것처럼
쉽게 의존성 주입이 가능하다. 그러나 **spring과는 다르게 module이라는 것을 통해서 설정**해줄 것이 있다.

---

## module

nest에서 `provider들간의 관계, 의존성 등을 관리하기 위한 것`이다.

---

## middleware

**handler가 호출되기 전**에 **요청, 응답에 접근**해서 원하는 동작(ex - 로깅)을 할 수 있도록 하는 것이다.
- 어플리케이션 전체 또는 모듈 단위로 적용이 가능
- 사용하기 위해선 NestInterceptor라는 인터페이스를 구현하면 됨

---

## exceptionfilter

nest는 exception을 처리하는 계층이 프레임워크 내에서 이미 구축이 되어있다.
하지만 응답을 커스텀하거나 예외 처리 단계에서 추가하고 싶은게 있는 경우
ExceptionFilter 인터페이스를 구현해서 커스텀이 가능하다.

---

## pipe

**요청 데이터의 형식 검증이나 데이터 수정** 등을 하기 위한 것이다.
spring에서는 ArgumentResolver, Validator 등을 떠올리면 된다.
기본적으로 지원하는 Pipe 클래스들도 여럿 있고 따로 커스텀하고 싶으면 PipeTransform을 구현하면 된다.

---

## Guards

spring security와 비슷하게 nest에서 **인증, 인가들을 처리하기 위한 것**이다.
CanActivate 인터페이스를 구현해서 요청을 통과시킬지 차단시킬지 등을 true, false로 반환 가능하다.

---

## 참고
- [https://medium.com/zigbang/spring-개발자의-nestjs-적응하기-a816fa0f38a9](https://medium.com/zigbang/spring-%EA%B0%9C%EB%B0%9C%EC%9E%90%EC%9D%98-nestjs-%EC%A0%81%EC%9D%91%ED%95%98%EA%B8%B0-a816fa0f38a9)
- nest docs
---