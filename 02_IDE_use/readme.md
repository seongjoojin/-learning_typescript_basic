# IDE 활용

vs code 에 컴파일러가 내장되어 있음.

내장된 컴파일러를 선택할 수 있고, 직접 설치한 컴파일러를 선택할 수도 있음.

tslint를 설치하여 컨벤션을 맞춤

```
yarn add tslint
```

tslint.json 생성

```
tslint --init
```

vscode에서 tslint 확장프로그램으로 설치가능

웹스톰이나 인텔리제이는 기본적으로 타입스크립트의 에러를 보여줌

Languages & Frameworks -> TypeScript -> TSLint 세부 설정가능