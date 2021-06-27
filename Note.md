# SwiftStudy
- Based on: KxCoding

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
  - 각 변수, 연산자, 함수 같은 것들(Token)이 모여서 하나의 값으로 표현되는 것을 Expressions(표현식)라고 한다
  - let x = 7
  - 참과 거짓으로 구분되는 것은 Boolean Expressions라고 한다
  - 표현식은 코드를 평가했을 때 하나의 결과값을 나타내는 것을 의미한다.


- Statements
  - 하나 이상의 표현식(Expression)이 모이면 특정 작업을 실행하는 코드가 되는데, 이를 Statements라고 한다
  - Swift에서는 문장의 끝에 ;를 붙이지 않아도 된다



### 1-2. Literal, Identifier, Keyword
- Literals
  - 코드 내에서 의미가 변하지 않고 사용되는 것을 Literal이라고 한다
  - Integer Literals, Floating-point Literals, String Literals, Boolean Literals, nil Literals이 있다


- Identifiers
  - 변수의 이름, 자료형의 이름, 함수의 이름 등 모든 것이 식별자다
  - let x = 7에서는 x가 식별자이다


- Keywords
  - 예약어라고 부르기도 한다
  - let x = 7에서는 let이 keyword이다
  - 키워드는 식별자 이름으로 사용할 수 없다
  - 단어 사이에 포함되면 사용할 수 있다



### 1-3. Compile, Link, Run
- Compile
  - 사람이 작성한 코드를 컴퓨터가 이해할 수 있는 바이너리 코드로 변환하는 작업이 compile이다
  - Compiler는 사람이 작성한 코드를 분석한 후 오류가 없는 경우에만 바이너리 코드를 생성한다
  - Compiler는 소스코드를 분석할 때 Warning(경고)과 Error(오류)로 분류한다


- Link
  - 작성된 코드들을 서로 연결하는 것을 Link라고 한다
  - Link를 담당하는 코드들도 Xcode 안에 내장되어 있고, 이런 도구들을 Linker라고 한다
  - 커맨드 + R 키만 누르면 컴파일과 링크를 완료 후 실행한다


- Run 
  - 작성한 코드가 컴파일 후 링크되어 실행파일이 생성되는 시점까지를 Compile Time이라고 한다
  - 실행된 생성 파일을 시뮬레이터나 실제 디바이스에서 실행하는 시점을 Run Time이라고 한다



### 1-4. Special Characters
- 느낌표(!) -> Bool값을 반대로 바꿀 때 사용
- ~ (Tilde) -> 비트 연산자에서 주로 사용
- ` (Grave Accent / Back Tick) -> 키워드를 Identifier로 바꿀 때 사용
- @ (At Symbol) -> 코드 자체의 특성을 지정하는 용도로 사용됨
- # (Sharp / Pound / Hashtag) -> Swift가 제공하는 특수한 명령어들은 전부 #으로 시작한다
- $ (Dollar Sign) -> 클로저에서 파라미터 이름을 대체할 때 주로 사용한다
- % (Percent Sign) -> 나머지를 구할 때 사용
- ^ (Caret 캐럿) -> 비트 연산자에서 사용
- & (Ampersand) -> 주로 메모리 주소를 얻거나 참조를 전달할 때 사용
- * (Asterisk) -> 곱하기 연산에서 사용
- ( ) (Parentheses 퍼랜더시스) -> 함수를 호출하거나 계산의 순서를 정할 때
- _ (Underscore) -> Wild Card 패턴을 구현할 때 자주 사용 됨
- = (Equal Sign)
- [ ] (Square Bracket) -> 컬렉션에 저장된 값에 접근할 때 사용
- { } (Curly Bracket / Brace) -> 코드 블록의 범위를 지정할 때 사용
- \ (Backtrash) -> String Interpolation 문법이나, KeyPath 표현식에서 사용
- | (Vertical Bar / Pipe) -> 논리 연산이나 비트 연산에서 사용
- ; (Semicolon) -> 쓰는 경우 거의 없다
- : (Colon)
- , (Comma)
- . (Period) -> 메서드를 호출하거나 속성에 접근할 때
- < > (Angle Bracket) -> 주로 크기를 비교할 때 사용, 제네릭에서는 형식 파라미터를 지정할 때 사용
- / (Slash)
- ? (Question Mark)



### 1-5. First Class Citizen
- 상수와 변수에 저장할 수 있다(can be stored in variables and data structures)
- 파라미터로 전달할 수 있다(can be passed as a parameter to a function)
- 함수에서 리턴할 수 있다(can be returned as the result of a function)
- 이 세 가지 특성을 암기해라


## Working with Variables
- 변수와 상수를 선언하는 방법과 이름 정의 규칙 등 데이터를 저장하는 가장 기초적인 과정


### 2-1. Variables and Constants
- 프로그램에서 데이터를 처리하기 위한 첫 번째 단계는 메모리에 값을 저장하는 것
- 이 때 필요한 것이 바로 변수와 상수이다
- 변수는 '변할 수 있는 수'를 의미한다
- 상수를 선호하는 이유
  - 실수로 값을 변경하는 일이 생기지 않는다
  - 상수로 선언하면 컴파일러가 별도의 최적화를 하기 때문에 좀 더 빨라진다



### 2-2. 변수와 상수 올바르게 선언하기
- Swift는 Camel Case를 사용해 이름을 만든다


### 2-3. 자료형 직접 선언하기

### 2-4. Naming Convention

### 2-5. Scope
- Global Scope
- Local Scope
- 코드의 범위는 { }(브레이스)에 의해 정해진다
- Global Scope는 브레이스 밖에, Local Scope는 브레이스 안에 있다



## Literals, Data Types
- 문자열, 숫자와 같이 다양한 값을 프로그래밍 언어에서 표현하는 방법과, Swift에서 제공하는 기본 자료형

### 3-1. Data Types with Memory
- 메모리는 1과 0을 저장할 수 있는 저장공간을 가진 반도체이다
- 메모리는 전압 차이를 이용해서 데이터를 저장한다
- 전기가 들어오면 1을 저장하고, 전기가 들어오지 않으면 0을 저장한다
- 메모리의 저장 단위 중 가장 작은 것은 Bit이고, 현재 가장 큰 단위는 YB(요타바이트)이다
- 하나의 Bit에는 1과 0을 저장할 수 있다
- 컴퓨터공학에서 정보의 기본 단위이다
- Bit가 8개가 모이면 Byte가 된다
- 프로그래밍 언어는 Byte를 기본 단위로 사용한다
- 컴퓨터는 데이터의 종류에 관계 없이 항상 2진수로 바꿔서 메모리에 저장한다
- 음수와 0, 양수를 모두 저장할 수 있다면 Signed 자료형이라고 한다(앞에 부호를 붙일 수 있다는 의미)
- 음수를 제외한 0과 양수만 저장할 수 있다면 Unsigned 자료형이라고 한다(앞에 부호를 붙일 수 없음)
- 음수를 표현할 때는 -문자로 표현하는데, -는 메모리에 직접 저장할 수 없다
- 그래서 이 또한 0 또는 1로 표현해야 한다
- 대부분의 컴퓨터는 최상위 비트를 통해 양수와 음수를 표현한다
- 최상위 비트(Most Significant Bit)가 0이라면 양수(Positive Number)이고,
- 최상위 비트(Most Significant Bit)가 1이라면 음수(Negative Number)이다
- 이런 식으로 쓰이는 최상위 비트들을 부호 비트(Sign Bit)라고 한다
- 실수를 저장할 때는 지수와 가수를 나눠서 저장한다
- 동일한 메모리 크기에서 정수에 비해 더 넓은 범위를 표현할 수 있다
- 부동소수점 오차로 인해서 100% 정확한 실수를 저장할 수 없다
- 메모리 내부에는 1바이트를 저장할 수 있는 공간마다 메모리 주소가 할당되어 있다
- CPU는 이 주소를 통해서 메모리에 접근한다
- 1 킬로바이트를 예로 들었을 때, 1 킬로바이트는 1024개의 바이트로 구성되어 있다
- 여기에 0번부터 1023번까지의 주소가 할당된다
- 만약 CPU가 첫 번째 메모리에 접근하고 싶다면 0번 주소를 사용한다
- 반대로 마지막 메모리에 접근하고 싶다면 1023번 주소를 사용한다
- CPU가 작업을 처리하려면 메모리 주소에 접근해서 데이터를 가져와야 한다
- 이 때 특정 주소에 접근하기 위해서 주소 레지스터라는 것을 사용한다
- CPU가 32비트라는 것은 주소 레지스터의 크기가 32비트라는 것을 의미한다
- 메모리가 저장할 수 있는 범위를 넘어서 저장하면 오버플로(overflow)가 발생한다
- Swift는 오버플로를 에러로 판단한다



### 3-2. Numbers
```swift
// 1000000과 같이 회계적인 표현을 쓸 때 1,000,000을 쓸 수는 없다. 대신 이렇게 쓸 수 있다.
1_000_000 // 1000000

// 10진수로 10 표현하기
10 // 10

// 2진수로 10 표현하기
0b1010 // 10

// 8진수로 10 표현하기
0o12 // 10

// 16진수로 10 표현하기
0xA // 10

// 메모리 크기 확인하기
MemoryLayout<Int8>.size // 1 -> 1 Byte를 의미함
MemoryLayout<Int>.size // 8


```

### 3-3. 숫자 리터럴과 숫자 자료형 이해하기
### 3-4. Boolean
### 3-5. 불린 자료형 이해하기
### 3-6. Strings and Characters
### 3-7. 문자열, 문자 자료형 이해하기
### 3-8. Type Inference
### 3-9. Type Annotation 이해하기
### 3-10. Type Safety
- 형식 안정성
- Swift는 형식을 엄격히 구분함으로써 형식 안정성을 보장한다


### 3-11. Type Conversion
- Type Conversion vs Type Casting
- Type Conversion은 메모리에 저장된 값을 다른 형식으로 바꿔서 새로운 값을 생성한다
- Type Casting은 메모리에 저장된 값을 그대로 두고 컴파일러가 다른 형식으로 처리하도록 지시한다

### 3-12. 자료형이 다른 두 값을 더하기
### 3-13. Type Alias
- 타입 앨리어스를 사용할 때는 Upper camel case로 만들어야 한다



## Operators
- Swift가 제공하는 다양한 연산자를 활용해서 값을 계산하고 결과를 얻기

### 4-1. Operator Basics
- 피연산자가 하나인 경우에는 '단항 연산자(Unary Operator)'라고 한다(ex: +a)
- 피연산자가 두 개인 경우에는 '이항 연산자(Binary Operator)'라고 한다(ex: a + b)
- 피연산자가 세 개인 경우에는 '삼항 연산자(Ternary Operator)', 또는 '조건 연산자'라고 한다(ex: a ? b : c)
- 연산자가 피연산자 앞에 있으면 '전치연산자(Prefix Operator)'라고 한다(+a)
- 연산자가 피연산자 뒤에 있으면 '후치연산자(Postfix Operator)'라고 한다(a+)
- 두 피연산자 사이에 있으면 Infix Operator라고 한다(a + b)
- 결합규칙(Associativity)
  - 왼쪽에서 오른쪽으로 계산할 것인지, 오른쪽에서 왼쪽으로 계산할 것인지 두 가지 경우가 있다
  - 왼쪽부터면 좌결합성(Left Associative), 오른쪽부터면 우결합성(Right Associative)이라고 한다
- 괄호만 잘 쓰면 결합규칙을 굳이 외울 필요가 없다



### 4-2. Arithmetic Operators
- 나머지 연산자(%)는 정수만 지원한다. 실수에 대한 나머지를 구할 때는 truncatingRemainder(dividingBy: )연산자를 활용해야 한다
- 자료형에 저장할 수 있는 값의 범위를 벗어나는 문제를 overflow라고 한다
- Swift는 overflow를 허용하지 않는다. overflow가 필요하다면 overflow 연산자를 사용해야 한다
### 4-3. 올바른 산술 연산자 채우기
### 4-4. Overflow Operators ***
- a &+ b <- 이와 같은 식으로 연산자를 사용하면 overflow가 허용된다
```swift
let a: Int8 = Int8.max // 127
let b: Int8 = a &+ 1 // -128 -> 메모리 구조에 따른 연산 결과

let c: Int8 = Int8.min // -128
let d: Int8 = c &- 1 // 127 -> 메모리 구조에 따른 연산 결과

let e: Int8 = Int8.max &* 2 // -2

```


### 4-5. 올바른 오버플로우 연산자 채우기
### 4-6. Comparison Operators
### 4-7. 올바른 비교 연산자 채우기
### 4-8. Logical Operators
### 4-9. 올바른 논리 연산자 채우기
### 4-10. Ternary Conditional Operator
### 4-11. 조건 연산자로 짝수 or 홀수 출력하기
### 4-12. Short-circuit Evaluation(단락평가), Side Effect ***
- 논리 연산자가 논리식을 평가하는 방법
- Swift는 논리식에서 결과를 얻을 수 있는 최소한의 연산만 수행한다(단락평가)
- Side Effect는 코드의 실행 결과로 인해서 값 또는 상태가 변경되는 것을 의미한다. 반드시 부정적인 의미로 쓰이는 것은 아니라는 것을 기억해라

### 4-13. Bitwise Operators
- 비트 연산자
- 비트 연산자를 공부할 때는 논리 연산자를 염두에 두고 공부하면 좋다

### 4-14. Assignment Operators
- 값을 저장하는데 사용하는 할당 연산자와 복합(Compound) 할당 연산자(Assignment Operators)에 대한 공부
### 4-15. Range Operators
```swift
1...10 // 가능
10...1 // 불가능
(1...10).reversed() // 가능

let list = ["A", "B", "C", "D", "E"]
list[2...] // ["C", "D", "E"]
list[...2] // ["A", "B", "C"]
list[..<2] // ["A", "B"]
```
### 4-16. 올바른 범위 연산자 채우기


## Operators - 고급

### 4-17. Operator Methods ***
- 기존 연산자가 새로운 형식을 지원하도록 확장하는 방법
```swift
struct Point {
  var x = 0.0
  var y = 0.0
}

extension Point: Equatable { // Equatable 프로토콜을 채용했다면 아래 == 메소드는 없어도 정상적으로 비교 연산이 가능하다
  static func ==(lhs: Point, rhs: Point) -> Bool {
    return (lhs.x == rhs.x) && (lhs.y == rhs.y)
  }
}

let p1 = Point(x: 12, y: 34)
let p2 = Point(x: 67, y: 89)

p1 == p2 // false
p1 != p2 // true

extension Point {
  static prefix func -(pt: Point) -> Point {
    return Point(x: -pt.x, y: -py.y)
  }
}

let p3 = -p1
p3.x // -12
p3.y // -34
```
### 4-18. Int 형식에 저장된 값과 Double 형식에 저장된 값 더하기
### 4-19. Custom Operators ***
- Swift가 제공하지 않는 새로운 연산자를 직접 구현하는 방법(사용자 정의 연산)
```swift
prefix operator +++

extension Int {
  static prefix func +++(num: inout Int) {
    num += 2
  }
}

var a = 1
+++a
a // 3

// 이항연산자는 infix로 선언한다
infix operator *+*: MultiplicationPrecedence

extension Int {
  static func *+*(left: Int, right: Int) -> Int {
    return (left * right) + (left * right)
  }
}

1 *+* 2 // 4 -> (1 * 2) + (2 * 1)
```
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
