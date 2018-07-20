# TypeScript Basic Types

- Typescript 에서 프로그램 작성을 위해 기본 제공하는 데이터 타입
- **사용자가 만든 타입은 결국은 이 기본 자료형들로 쪼개짐.**
- Javascript 기본 자료형을 포함 (superset)
    - ECMAScript 표준에 따른 기본 자료형은 6가지
        - Boolean
        - Number
        - String
        - Null
        - Undefined
        - Symbol (ES6에 추가)
        - Array :  object 형
    - 프로그래밍을 도울 몇가지 타입이 더 제공됨
        - Any
        - Void
        - Never
        - Enum
        - Tuple : object 형

#### Primitive Type

- 오브젝트와 레퍼런스 형태가 아닌 실제 값을 저장하는 자료형임
- 프리미티브 형의 내장 함수가 사용 가능한것은 자바스크립트 처리 방식 덕분

```typescript
let name = 'mark';

name.toString();
```

#### literal ?

- 값 자체가 변하지 않는 값을 의미함.
- 상수와 다른 것은 상수는 가리키는 포인터가 고정이라는 것이고, 리터럴은 그 자체가 값이자 그릇임.

```
35; // number 리터럴
'mark'  // string 리터럴
true    // boolean 리터럴

// object 리터럴
{
    name: 'mark',
    age: 35
}
```
#### Boolean / boolean

- 가장 기본적인 데이터 타입
- 단순한 true 혹은 false 값 임
- javascript / TypeScript 에서 'boolean'이라고 부른다