# Compiler Options

http://json.schemastore.org/tsconfig

**최상위 프로퍼티**

- compileOnSave
- extends
- compileOptions
- files
- include
- exclude

**compileOnSave**

- 저장하면 자동으로 컴파일
- true / false (default false)
- 최상단에 설정해야 한다 ?

**extends**

- 공통적인 면들이 많은 ts파일에 사용?
- 파일 (상대) 경로명 : string

**files, include, exclude**

- 셋다 설정이 없으면, 전부다 컴파일
- files
    - 상대 혹은 절대 경로의 리스트 배열임
    - exclude 보다 쎔
- include, exclude
    - glob 패턴 (마치 .gitnore)
    - include
        - exclude 보다 약함
        - * 같은걸 사용하면, .ts/.tsx/.d.ts 만 include (allowJS)
    - exclude
        - 설정 안하면 4가지 (node_modules, bower_components, jspm_pakages, <outDir>)를 default로 제외함
        - <outDir>은 항상 제외함 (include에 있어도)