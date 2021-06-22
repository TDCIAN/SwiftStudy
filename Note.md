# SwiftStudy

## Warming up
- 프로그래밍에서 공통적으로 사용되는 기본 용어

### 1-1. Token,Expression, Statement
- expression은 '식' 또는 '표현식'이라고 부른다
- statement는 '문장' 또는 '구문'이라고 부른다
- 국내에서는 expression을 '표현식', statement를 '문장'이라고 부른다


- Tokens
  - 공백이나 구두점으로 분리할 수 없는 가장 작은 단위의 요소를 Token이라고 한다
  - 2+3;의 경우 2, +, 3, ; 총 네 가지 토큰으로 이루어졌다
  - 토큰의 종류
    - Identifiers(식별자)
    - Keywords
    - Punctuations(구두점)
    - Operators(연산자)
    - Literals
  - 공백(space, 탭, 줄바꿈)은 프로그래밍에서 토큰을 구분하는 역할을 한다


- Expressions
  - 각 변수, 연산자, 함수 같은 것들이 모여서 하나의 값으로 표현되는 것을 Expressions(표현식)라고 한다
  - let x = 7
  - 참과 거짓으로 구분되는 것은 Boolean Expressions라고 한다
  - 표현식은 코드를 평가했을 때 



### 1-2. Literal, Identifier, Keyword
### 1-3. Compile, Link, Run
### 1-4. Special Characters
### 1-5. First Class Citizen


## Working with Variables
- 변수와 상수를 선언하는 방법과 이름 정의 규칙 등 데이터를 저장하는 가장 기초적인 과정

### 2-1. Variables and Constants
### 2-2. 변수와 상수 올바르게 선언하기
### 2-3. 자료형 직접 선언하기
### 2-4. Naming Convention
### 2-5. Scope


## Literals, Data Types
- 문자열, 숫자와 같이 다양한 값을 프로그래밍 언어에서 표현하는 방법과, Swift에서 제공하는 기본 자료형

### 3-1. Data Types with Memory
### 3-2. Numbers
### 3-3. 숫자 리터럴과 숫자 자료형 이해하기
### 3-4. Boolean
### 3-5. 불린 자료형 이해하기
### 3-6. Strings and Characters
### 3-7. 문자열, 문자 자료형 이해하기
### 3-8. Type Inference
### 3-9. Type Annotation 이해하기
### 3-10. Type Safety
### 3-11. Type Conversion
### 3-12. 자료형이 다른 두 값을 더하기
### 3-13. Type Alias


## Operators
- Swift가 제공하는 다양한 연산자를 활용해서 값을 계산하고 결과를 얻기

### 4-1. Operator Basics
### 4-2. Arithmetic Operators
### 4-3. 올바른 산술 연산자 채우기
### 4-4. Overflow Operators ***
### 4-5. 올바른 오버플로우 연산자 채우기
### 4-6. Comparison Operators
### 4-7. 올바른 비교 연산자 채우기
### 4-8. Logical Operators
### 4-9. 올바른 논리 연산자 채우기
### 4-10. Ternary Conditional Operator
### 4-11. 조건 연산자로 짝수 or 홀수 출력하기
### 4-12. Short-circuit Evaluation, Side Effect ***
### 4-13. Bitwise Operators
### 4-14. Assignment Operators
### 4-15. Range Operators
### 4-16. 올바른 범위 연산자 채우기


## Operators - 고급

### 4-17. Operator Methods ***
### 4-18. Int 형식에 저장된 값과 Double 형식에 저장된 값 더하기
### 4-19. Custom Operators ***
### 4-20. 2의 거듭 제곱을 계산하는 ** 연산자 구현하기


## Conditional Statements
- 조건문을 사용해서 조건에 따라 실행할 코드를 선택하는 방법

### 5-1. if statement
### 5-2. if 문으로 짝수 or 홀수 구분하기
### 5-3. switch Statement
### 5-4. switch 문으로 요일 출력하기
### 5-5. guard Statement
### 5-6. guard 문으로 코드 분기하기


## Conditional Statements

### 5-7. Value Binding Pattern ***
### 5-8. Expression Pattern ***


## Loop Statements
- 반복문을 통해 코드를 반복해서 실행하는 방법

### 6-1. for-in Loop
### 6-2. for-in 반복문으로 지정된 범위까지의 합 구하기
### 6-3. while Loop
### 6-4. while 반복문으로 지정된 범위까지의 합 구하기


## Control Transfer Statements, Labeld Statements
- 흐름 제어 구문을 통해 프로그램의 실행 흐름을 조절하는 방법에 대해 공부합니다.

### 7-1. Control Transfer Statements
### 7-2. break Statement
### 7-3. break로 반복문 제어하기
### 7-4. continue Statement
### 7-5. 홀수 합 구하기
### 7-6. Labeled Statements
### 7-7. 중첩된 반복문 제어하기


## Optionals
- "값이 없음"을 표현하는 방법에 대해 공부

### 8-1. Optionals
### 8-2. 옵셔널 이해하기
### 8-3. Optional Binding
### 8-4. 옵셔널 바인딩을 사용해서 안전한 코드로 바꾸기
### 8-5. Implicitly Unwrapped Optionals

## Optionals - 고급

### 8-6. Nil-Coalescing Operator
### 8-7. ?? 연산자로 기본값 지정하기
### 8-8. Optional Chaining ***
### 8-9. Optional Pattern ***
### 8-10. 옵셔널 패턴을 활용해서 유효한 값만 처리하기


## Functions
- 자주 사용하는 기능을 함수로 만들고 재사용하는 방법

### 9-1. Functions
### 9-2. Return Values
### 9-3. Parameters
### 9-4. Argument Label

## Functions - 고급

### 9-5. Variadic Parameters ***
### 9-6. In-Out Paramters
### 9-7. 전달된 숫자의 합을 리턴하는 함수 구현하기
### 9-8. Function Notation
### 9-9. Function Types ***
### 9-10. Function Type 이해하기
### 9-11. Nested Functions ***


## Closures
- 익명 코드 블록을 구현하는 방법

### 10-1. Closures
### 10-2. Syntax Optimization
### 10-3. 클로저와 문법 최적화

## Closures - 고급

### 10-4. Capturing Values
### 10-5. Escaping Closure ***


## Tuples
- 튜플을 통해 두 개 이상의 값을 하나로 묶어서 처리하는 방법

### 11-1. Tuples
### 11-2. Named Tuples
### 11-3. Tuple Decomposition
### 11-4. Tuple Matching
### 11-5. 튜플을 리턴하는 함수 구현하기


## String and Character
- 가장 기초적인 형식인 문자열과 문자를 다루는 방법

### 12-1. Strings and Characters
### 12-2. Multiline String Literals
### 12-3. String Interpolation
### 12-4. 원하는 포멧으로 문자열 출력하기
### 12-5. String Indices
### 12-6. 문자열에서 원하는 범위 추출하기
### 12-7. String Basics
### 12-8. Substring
### 12-9. String Editing #1
### 12-10. String Editing #2
### 12-11. 문자열에서 원하는 부분 편집하기
### 12-12. String Comparison
### 12-13. String Searching
### 12-14. 문자열에서 문자 검색하기

## String and Character - 고급

### 12-15. String Options #1
### 12-16. String Options #2
### 12-17. 올바른 문자열 옵션 사용하기
### 12-18. Character Set ***
### 12-19. 문자열에서 불필요한 문자 제거하기
