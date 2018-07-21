# Type assertions, Type alias

#### 타입 어설션 (Type assertions)

- 형변환과 다름
    - 형변환은 실제 데이터 구조를 바꿔줌
- '타입이 이것이다'라고 컴파일러에게 알려주는 것을 의미함
    - 그래서 행동에 대해서 작성자가 100% 신뢰하는 것이 중요함
- 문법적으로 두가지 방법이 있음
    - 변수 as 강제할타입
    - <강제할타입>변수
    
```typescript
let someValue: any = "this is a string";

let strLength: number = (<string>someValue).length;
let strLength: number = (someValue as string).length;

/*
* 1. 주로 넓은 타입에서 좁은 타입으로 강제하는 경우가 많다.
* 2. jsx 에서 as를 쓴다
* */
```

#### 타입 별칭 (별명) : Type alias

- 인터페이스랑 비슷해 보임.
- Primitive, Union Type, Tuple
- 기타 직접 작성해야하는 타입을 다른 이름으로 지정할 수 있음
- 만들어진 타입의 refer 로 사용하는 것이지 타입을 만드는 것이 아님

##### Aliasing Primitive

```typescript
type MyStringType =  string;

const str = 'world';

let myStr: MyStringType = 'hello';
myStr = str;

// 별 의미가 없음..
```

##### Aliasing Union Type

```typescript
let person: string | number = 0;
person = 'Mark';

type StringOrNumber = string | number;

let another: StringOrNumber = 0;
another = 'Anna';

/*
* 1. 유니온 타입은 A 도 가능하고 B 도 가능한 타입
* 2. 길게 쓰는걸 짧게
* */
```

##### Aliasing Tuple

```typescript
let person: [string, number] = ['Mark', 35];

type PersonTuple = [string, number]

let another: PersonTuple = ['Anna',24];

/*
* 1. 튜플 타입에 별칭을 줘서 여러군데서 사용할 수 있게 함
* */
```

##### Interface 와 차이점 (1)

```typescript
type Alias = { num:number }

interface Interface {
    num: number;  
}

declare function aliased(arg: Alias): Alias;
declare function interfaced(arg: Interface): Interface;

/*
* 1. type alias 는 object literal type 로
* 2. interface 는 interface 로
* */
```

##### Interface 와의 차이점 (2)

```typescript
type PersonAlias = {
    name: string;
    age: number;
};

interface  IPerson extends PersonAlias {
  
};

let ip: IPerson = {
    name: 'Mark',
    age: 35
};

class PersonImpl implements PersonAlias {
    name: string;
    age: number;
    
    hello() {
        console.log('안녕하세요');
    }
}

let pi: PersonImpl = new PersonImpl();
pi.hello()

class PersonChild extends PersonAlias {
  
}

/*
* 1. 당연한건 type alias 끼리는 extends, implements 불가
* 2. interface extends type alias 가능
* 3. class implements type alias 가능
* 4. class extends type alias 불가 ( interface 도 마찬가지 )
* 5. 마치 interface 처럼 동작함
* */
```