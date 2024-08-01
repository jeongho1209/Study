```jsx
const user = await this.userRepository.findById(id);
 
 if (!user) {
      throw new NotFoundException('User Not Found');
 }
```

## ! 사용

JavaScript에서 `!를 사용하면 → 연산을 부정`하게 되는 것인데
만약 user 객체가 **null, undefined, false 등의 값인 경우 true를 반환**하게 된다.
그렇기 때문에 !를 사용해서 user 객체가 없을 경우를 핸들링 하는 경우 간편하다.

### 주의할점
expect 메소드에서 `toBeTruthy, toBeFalsy`를 사용할 때 주의해야 한다.<br>
null, undefined, false 등의 값을 제외하고는 true를 반환하기 때문이다.<br>
그래서 toBe, equal 메소드를 통해서 값을 확실하게 검증해야 한다.

---