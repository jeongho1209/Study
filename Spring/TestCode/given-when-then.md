## given

메소드를 **텅 빈 stub 상태**로 불러오고 **실행 결과를 조작할 상태를 지정**한다.

```java
given(testRepository.findById(mockId)) // 이 메소드를 불러와서
	      .willReturn(Optional.empty()) // 이 상태로 조작한다
```

### tip

**mockito**에서는 **given 단계에서 실행**해야 할 `메소드의 이름을 when으로 두어서 헷갈릴 여지`가 있다.
이때문에 **BDDMockito**에서는 `기능은 동일`하지만 `메소드의 이름을 given으로 두어서 가독성`을 높였다.

---

## when

given으로 **정해진 상태를 테스트**하기 위해 **상태 변화**를 가한다. (즉, 메서드를 실행시킴)

```java
Executable executable = () -> testService.execute(mockId);
```

---

## then

**when 단계에서 얻은 결과 값**이 `실제 기대하는 값과 일치하는지 확인`한다.

```java
Assertions.assertEquals(expectedErrorCode, actualErrorCode);
```

---