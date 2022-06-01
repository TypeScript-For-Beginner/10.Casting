## 10.1 **타입 캐스팅(Type Casting)**

JAVA나 C++등 다른 프로그래밍언어에서 타입 캐스팅이란 형 변환을 의미한다. 타입스크립트에서도 특정 타입임을 단언해야하는 상황이 있는데 특별한 검사나 데이터 재구성을 하지 않기 때문에 Type Casting과는 별개의 개념이다.

## 10.2 **타입 어설션(Type Assertion)**

Type Assertion이란 시스템이 추론한 타입의 내용을 변경하는 것이다. 실행시간에 어떤 동작이 일어날것인지를 내포하는 Type Casting보다 Type assertion이 더 적합한 표현이기 때문에 헷갈리지 않아야 한다. 타입 어설션은 **`<>`** 표기법과 `as` 연산자를 이용한 두 가지 방법이 있다.

### 10.2.1 `<>` 표기법

`<type>`을 변수 앞에 작성한다.

> 예제 10-1

```tsx
var val: any;
var foo1 = <string>val;
```

### 10.2.2 `as` 연산자

`as type`을 변수 뒤에 작성힌다.

> 예제 10-2

```tsx
var val: any;
var foo2 = val as number;
```

`<>`표기법은 `JSX`문법에서 헷갈리기 때문에 `as` 연산자 사용을 권장한다.

### 10.2.3 주의해야할 점

> 예제 10-3

```tsx
const str = "hello world";
console.log((str as number[]).push(123)); //Error
```

문자열로 선언되어있는 `str` 변수를 `as number[]`를 통해 타입 에러를 무시하고 숫자형을 넣었을 때 런타입 과정에서 에러가 발생한다. 코드 타입이 확실해야 오류가 발생하지 않으므로 주의해야한다.
