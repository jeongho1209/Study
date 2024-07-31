## Mock

실제 객체를 만들기에는 비용이 높거나, 결합도가 강해서
구현하기 힘들 경우 **가짜 객체를 만들어 사용하는 방법**

---

## Mock 객체

**행위를 검증하기 위해 사용되는 객체**

---

### `@ExtendWith(MockitoExtension.class)`

Mockito에서 제공하는 **Mock** **객체를 사용**하기 위해 클래스 위에 붙여준다

```java
public class test() {
    @Before
    public void setUp(){ MockitoAnnotations.initMocks(this); }
}

// 안 달면 이 코드가 필요하다
```

---

### **@Mock**

**Mock 객체를 생성**한다 (빈 생성은 안 됨)

---

### **@InjectMocks**

`@Mock이 붙은 Mock 객체 -> @InjectMocks이 붙은 객체에 주입`시킬 수 있다.

```java
    @Mock
    QueryUserPort queryUserPort;

    @Mock
    CommandUserPort commandUserPort;

    @Mock
    UserSecurityPort userSecurityPort;

    @InjectMocks
    UserSignUpUseCase userSignUpUseCase;
```

**`UserSignUpUseCase 객체에 각 Port 들들 주입`**

---

### @MockBean

ApplicationContext에 `해당 어노테이션이 달린 타입의 빈을 등록`해준다.
(이미 존재하면 MockBean으로 갈아끼워짐)

**기존 Bean의 껍데기**만 가져오기 때문에 `원하는대로 상태 조작이 가능`하다.

---