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
```swift
import Foundation

let a = 1
let b = 2.3

var validCount = 0

infix operator +: MultiplicationPrecedence

extension Int {
  static func + (left: Int, right: Double) -> Double {
    return Double(left) + right
  }
  
  static func + (left: Double, right: Int) -> Double {
    return left + Double(right)
  }
}

if a + b == 3.3 {
  validCount += 1
}

if b + a == 3.3 {
  validCount += 1
}

print(validCount)
```
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
```swift
import Foundation

var validCount = 0

infix operator **: MultiplicationPrecedence

extension Int {
  static func **(left: Int, right: Int) -> Int {
    if right == 0 {
      return 1
    } else {
      var result: Int = 1
      for _ in 0..<right {
        result = result * left
      }
      return result
    }
  }
}

if 2 ** 3 == 8 {
  validCount += 1
}

if 2 ** 10 == 1024 {
  validCount += 1
}

print(validCount)

```

## Conditional Statements
- 조건문을 사용해서 조건에 따라 실행할 코드를 선택하는 방법

### 5-1. if statement
- if 문에서 '문'은 곧 '문장(statement)'을 의미한다

### 5-2. if 문으로 짝수 or 홀수 구분하기
```swift
import Foundation

func solution(_ num:Int) -> String {
    var result: String = ""    
    if num % 2 == 0 {
        result = "짝수"
    } else {
        result = "홀수"
    }
    return result
}
```
### 5-3. switch Statement
### 5-4. switch 문으로 요일 출력하기
```swift
import Foundation


func solution(_ weekday: Int) -> String {
    var ret: String = ""
    
    switch weekday {
    case 0:
        ret = "일요일"
    case 1:
        ret = "월요일"
    case 2:
        ret = "화요일"
    case 3:
        ret = "수요일"
    case 4:
        ret = "목요일"
    case 5:
        ret = "금요일"
    case 6:
        ret = "토요일"
    default:
        break
    }
    
    return ret
}
```


### 5-5. guard Statement
- Early Exit: 원하는 조건이 충족되지 않으면 불필요한 코드실행을 멈추고 바로 종료한다
- guard문 내부(else)에는 종료하는 내용이 있어야 한다
- guard문은 optional binding과 함께 사용된다

```swift
func validateUsingGuard() {
  var id: String? = nil
  
  guard let str = id else { return }
  guard str.count >= 6 else { return }
  
  print(str)
}
```
- 복잡한 조건을 사용해야 하는 경우 if보다 guard를 쓴다



### 5-6. guard 문으로 코드 분기하기
```swift
import Foundation

func solution(_ userName:String) -> Bool {
    guard 
userName.count >= 7 else
 {
        return false
    }
    return true
}
```


## Conditional Statements

### 5-7. Value Binding Pattern ***
- switch 문에서 활용할 수 있는 Value Binding Pattern
- 매칭시킬 대상을 상수(let)나 변수(let)로 변환한 다음에 case 블록에서 활용하는 패턴
- 주로 where 절과 결합해서 사용한다
```swift
let a = 1

switch a {
case var x where x > 100:
  x = 200
  print(x) // 1
default:
  break
}

let pt = (1, 2)

switch pt {
case let(x, y):
  print(x, y)
case (let x, let y):
  print(x, y)
case (let x, var y):
  print(x, y)
case let(x, _): // wildcard pattern
  print(x)
}
```


### 5-8. Expression Pattern ***
-직접 구현한 형식에 대해 패턴 매칭을 적용하는 방법
```swift
struct Size {
  var width = 0.0
  var height = 0.0
  
  static func ~=(left: Range<Int>, right: Size) -> Bool {
    return left.contains(Int(right.width))
  }
}

let s = Size(width: 10, height: 20)

switch s {
case 1..<9:
  print("1 ~ 9")
case 10..<99:
  print("10 ~ 99") // 이게 실행됨
default:
  break
}
```


## Loop Statements
- 반복문을 통해 코드를 반복해서 실행하는 방법

### 6-1. for-in Loop
```swift
let power = 10
var result = 1

for _ in 1...power {
  result *= 2
}

result // 1024

// 0부터(from) 10까지(to) 2씩(by)
for num in stride(from: 0, to: 10, by: 2) {
  print(num) // 0 2 4 6 8
}
```
### 6-2. for-in 반복문으로 지정된 범위까지의 합 구하기
```swift
import Foundation

func solution(_ upperBound:Int) -> Int {
    var sum = 0
    
    // 여기에서 구현해 주세요.
    for i in 1...upperBound {
        sum += i
    }
    
    return sum
}
```
### 6-3. while Loop
```swift
var num = 100
while num < 100 {
  num += 1
}
print(num) // 100

num = 100
repeat {
  num += 1
} while num < 100
print(num) // 101
```
### 6-4. while 반복문으로 지정된 범위까지의 합 구하기
```swift
import Foundation

func solution(_ upperBound:Int) -> Int {
    var sum = 0
    
    // 여기에서 구현해 주세요.
    var i = 1
    while i <= upperBound {
        sum += i
        i += 1
    }
    
    return sum
}
```


## Control Transfer Statements, Labeld Statements
- 흐름 제어 구문을 통해 프로그램의 실행 흐름을 조절하는 방법에 대해 공부합니다.

### 7-1. Control Transfer Statements
- 흐름 제어 구문에 대해 소개하고 "제어를 전달한다"는 것이 어떤 의미인지 설명
- "제어를 전달한다"는 것은 현재 실행중인 scope에서 코드를 중지하고 다음에 실행할 코드를 바로 실행하는 것


### 7-2. break Statement
- break를 통해서 실행중인 블록을 종료
```swift
let num = 1

switch num {
case 1...10:
  print("begin block")
  
  if num % 2 != 0 {
    break
  }
  
  print("end block")

default:
  break
}

print("done")

// num이 1일 때 -> begin block, done 순으로 출력
// num이 2일 때 -> begin block, end block, done 순으로 출력
```
### 7-3. break로 반복문 제어하기
```swift
import Foundation

func solution(_ upperBound:Int) -> Bool {
    var repeatCount = 0
    
    while repeatCount < Int.max {
        
        // 여기에서 구현해 주세요.
        if repeatCount == upperBound {
            break        
        } else {
            repeatCount += 1            
        }
    }
    
    return repeatCount == upperBound
}
```


### 7-4. continue Statement
- continue를 통해 반복 회차를 종료하고 다음 반복으로 이동
```swift
for index in 1...10 {
  if index % 2 == 0 {
    continue
  }
  
  print(index) // 1 3 5 7 9
}

for i in 1...10 {
  print("OUTER LOOP", i)
  
  for j in 1...10 {
    if j % 2 == 0 {
      continue
    }
    
    print(" inner loop", j)
  }
}
/* 
OUTER LOOP 1
  inner loop 1
  inner loop 3
  inner loop 5
  inner loop 7
  inner loop 9
OUTER LOOP 2
  inner loop 1
  ...
*/
```

### 7-5. 홀수 합 구하기
```swift
import Foundation

func solution(_ upperBound:Int) -> Int {
    var sum = 0
    
    // 여기에서 구현해 주세요.
    for i in 1...upperBound {
        if i % 2 == 0 {
            continue
        }
        sum += i
    }
    
    return sum
}
```
### 7-6. Labeled Statements
- 문장에 이름을 붙이고 제어를 전달하는 방법
```swift
outer: for i in 1...3 {
  print("OUTER LOOP", i)
  
  for j in 1...3 {
    print(" inner loop", j)
    
    break outer // outer로 이름이 붙은 바깥 반복문을 중단시킴
  }
}

/* 
OUTER LOOP 1
  inner loop 1
*/
```
### 7-7. 중첩된 반복문 제어하기
```swift
import Foundation

var repeatCount = 0

outer: for i in 1...10 {
    for j in 1...10 {
        for k in 1...10 {
            if k > 3 {
                break outer
            }
            repeatCount += 1
        }
    }
}

print(repeatCount)
```


## Optionals
- "값이 없음"을 표현하는 방법에 대해 공부

### 8-1. Optionals
- "값이 없음"을 표현하는 옵셔널에 대해 설명하고, 값이 없음을 나타내는 특별한 값인 nil과 옵셔널 형식에 저장된 값을 추출하는 방법
### 8-2. 옵셔널 이해하기
```swift
// 문제: 최종적으로 "zero or nil"이 출력되어야 합니다.
import Foundation

var a: Int? = 0 

if a! == 0 {
    print("zero or nil")
}
```
### 8-3. Optional Binding
```swift
let a: Int? = 12
let b: String? = "str"

// a와 b가 nil이 아니고, b의 count가 5보다 클 때만 if문 내부가 실행된다
if let num = a, let str = b, str.count > 5 {

}
```
### 8-4. 옵셔널 바인딩을 사용해서 안전한 코드로 바꾸기
```swift
// 옵셔널 바인딩을 활용해서 안전한 코드로 수정해 주세요.

import Foundation

let str: String? = "Hello"

if let string = str {
    print(string)
} else {
    print("empty string")
}
```
### 8-5. Implicitly Unwrapped Optionals
- 암시적 추출 옵셔널, 자동 추출 옵셔널
- 특정 컨텍스트에서 값이 자동으로 추출되는 IUO(Implicitly Unwrapped Optionals)
- 실제 코드에서는 거의 사용되지 않는다
- outlet을 연결할 때, API에서 IUO를 리턴할 때만 사용된다
- 우리가 직접 선언하고 사용하는 것은 적절치 않다
- 그냥 옵셔널과 옵셔널 바인딩을 사용해야 크래시를 줄일 수 있다

```swift
let num: Int! = 12
let a = num

let b: Int = num
```

## Optionals - 고급

### 8-6. Nil-Coalescing Operator
- Nil-Coalescing 연산자를 활용해서 옵셔널에 값이 저장되어 있지 않을 때 사용할 값을 지정하는 방법
- Nil-Coalescing Operator는 이항연산자
```swift
input = nil
str = "Hello, " + (input ?? "Stranger")
print(str) // Hello, Stranger
```

### 8-7. ?? 연산자로 기본값 지정하기
```swift
문제 설명
Nil-Coalescing 연산자를 활용해서 기본값을 지정한 다음 r 접두어가 붙어있는 상수에 저장해 주세요.

제한
기본값은 0, 0.0, "no value"로 제한합니다.

import Foundation

let a: Int? = nil
let b: Double? = 12.3
let c: String? = "Hello"

// 아래 상수에 값을 저장해 주세요.
let ra: Int = a ?? 0
let rb: Double = b ?? 0.0
let rc: String = c ?? "no value"

print(ra, rb, rc)
```



### 8-8. Optional Chaining ***
- 하나의 표현식 내에서 다수의 옵셔널 형식 멤버에 접근하는 방법
- 옵셔널 체이닝의 결과는 항상 옵셔널이다


### 8-9. Optional Pattern ***
- 옵셔널은 열거형(enum)이다
- case none
- case some(Wrapped)
- Generic type이기 때문에 어떤 타입도 사용 가능하다

```swift
let a: Int? = 0
let b: Optional<Int> = 0

if a == nil {

}

if a == .none {

}

if a == 0 {

}

if a == .some(0) {

}

if let x = a {
  print(x) // 0
}

// enum case로 출력(위 코드와 같은 내용)
if case .some(let x) = a {
  print(x) // 0
}
if case let x? = a {
  print(x) // 0
}

let list: [Int?] = [0, nil, nil, 3, nil, 5]

for item in list {
  guard let x = item else { continue }
  print(x) // 0, 3, 5
}

for case let x? in list {
  print(x) // 0, 3, 5
}
```

### 8-10. 옵셔널 패턴을 활용해서 유효한 값만 처리하기
```swift
문제 설명
list 배열에는 숫자와 nil이 저장되어 있습니다.
for-in 반복문으로 배열에 있는 숫자만 더해야 합니다.
옵셔널 패턴을 활용해서 올바른 결과를 얻을 수 있도록 수정해 주세요.

제한
if문과 옵셔널 바인딩은 사용할 수 없습니다.

import Foundation

let list: [Int?] = [0, nil, nil, 3, nil, 5, 9]
var sum = 0

for case let num? in list {
    sum += num
}

print(sum)
```


## Functions
- 자주 사용하는 기능을 함수로 만들고 재사용하는 방법

### 9-1. Functions
- 코드 조각(함수는 특정 기능을 수행하는 코드 조각이다)을 반복적으로 사용하는 방법
  - 함수의 장점
  - 함수 선언 문법
  - 함수 호출 문법

```swift
func sayHello() {
  print("hello, Swift")
}

sayHello() // hello, Swift
```

### 9-2. Return Values
- 함수가 계산한 결과를 리턴하고 실행을 종료하는 방법
```swift
func add() -> Int {
  return 1 + 2
}

let r = add() // 3

if add() == 3 {
  print("Three") // Three
}

func doSomething() {
  let rnd = Int.random(in: 1...10)
  
  if rnd % 2 == 1 {
    return // return value가 없으니까 함수의 실행을 중지
  }
  
  print(rnd) // 2, 4, 6, 8, 10
}
```


### 9-3. Parameters
- 파라미터를 통해 함수로 값을 전달하는 방법
- 파라미터는 바디에서 사용할 수 있는 임시 상수이다 -> 별도의 값을 저장할 수 없다
```swift
// 함수 선언에서의 파라미터를 formal parameter라고 함
func add(a: Int, b: Int) -> Int {
  a = 12 // 불가능함 -> 별도의 값을 저장할 수 없음
  return a + b
}

// 실제 사용되는 곳에서의 함수 파라미터는 Actual parameter 또는 Argument라고 함. 우리 말로는 '인자'라고 함
add(a: 12, b: 34) // 46


// Default Value
func sayHello(to: String = "Stranger") {
  print("Hello, \(to)")
}

sayHello(to: "Swift") // Hello, Swift
sayHello() // Hello, Stranger
```

### 9-4. Argument Label
```swift
func sayHello(name: String) { // 함수의 형식을 지정할 때 들어가는 파라미터 name은 Formal Parameter라고 한다
  print("Hello, \(name)")
}

sayHello(name: "Swift") // 함수를 호출할 때 들어가는 파라미터 name은 Actual Parameter 또는 Argument라고 한다

// case 1
sayHello(name: Type) // 이 때 name은 Parameter Name이면서 동시에 Argument Label임
// case 2
sayHello(label name: Type) // 이 때는 label이 Argument Label이고, name이 Parameter Name임


==================================================
// sayHello(name:)
func sayHello(name: String) {
  print("Hello, \(name)")
}

sayHello(name: "Swift")

// sayHello(to:)
func sayHello(to name: String) {
  // print("Hellom \(to)") // 함수 내부에서 Argument Label을 사용할 수는 없다
  print("Hello, \(name)")
}

sayHello(to: "Swift") // 함수를 호출할 때는 Argument Label을 사용한다

// Wild Card Pattern
func sayHello(_ name: String) {
  print("Hello, \(name)")
}

sayHello("Swift")
```
- Argument Label을 사용하는 이유는 함수의 가독성을 높이기 위함이다
- 함수를 호출할 때 쓰는 게 Argument Label이다

## Functions - 고급

### 9-5. Variadic Parameters ***
- 하나의 파라미터를 통해 두 개 이상의 값을 전달하는 가변 파라미터
```Swift
print("Hello") // Hello
print("Hello", "Swift") // Hello Swift

func printSum(of nums: Int...) { // 이러면 [Int]를 파라미터로 받을 수 있다
  var sum = 0
  for num in nums {
    sum += num
  }
  print(sum)
}

printSum(of: 1, 2, 3)
printSum(of: 1, 2, 3, 4, 5)

// 가변 파라미터는 함수에서 하나만 사용할 수 있다.
func printSum(of nums: Int..., double: Double...) { // 이렇게 쓰면 에러 발생함

}

```

### 9-6. In-Out Paramters
- 입출력 파라미터
- 파라미터로 전달된 변수의 값을 함수 내부에서 직접 변경하는 방법에 대해 공부합니다.
- Copy-In Copy-Out Memory Model

```swift
var num1 = 12
var num2 = 34

func swapNumber(_ a: inout Int, with b: inout Int) {
  // var tmp = a // inout 쓸 때는 var 쓰면 안 된다
  let tmp = a
  a = b
  b = tmp
}

num1 // 12
num2 // 34

// inout parameter를 가진 함수를 호출할 때는 Argument Parameter앞에 &(앰퍼샌드)를 붙여줘야 한다 
swapNumber(&num1, with: &num2)

num1 // 34
num2 // 12
```


### 9-7. 전달된 숫자의 합을 리턴하는 함수 구현하기
```swift
import Foundation

// 여기에서 함수를 구현해 주세요.

var count = 0
func sumNums(_ nums: Int...) -> Int {
    count += nums.count
    var sum = 0
    for num in nums {
        sum += num
    }
    return sum
}

// 여기에서 구현한 함수를 호출하고 결과를 저장해 주세요.
let result = sumNums(1, 2, 3, 4, 5)

print(count, result)
```


### 9-8. Function Notation
- 함수를 읽는 법과 코드에서 표기하는 방법


### 9-9. Function Types ***
- Swift 함수는 First-class Citizen이다
  - 변수나 상수에 저장할 수 있다
  - 파라미터로 전달할 수 있다
  - 함수에서 리턴할 수 있다
- function type에서 빈 괄호()는 비어있는 튜플(Empty Tuple)을 의미한다
- Void는 리턴형이 없다는 것을 나타내는 특별한 키워드이다. Void는 ()와 같다

```swift
func sayHello() {
  print("Hello, Swift")
}

let f1 = sayHello
f1 // f1의 type은 () -> ()임
f1() // Hello, Swift

func printHello(with name: String) {
  print("hello, \(name)")
}

let f2: (String) -> () = printHello(with:) // 자료형: (String) -> ()
let f3 = printHello(with:) // 자료형: (String) -> ()
f3("World) // Hello, World
f3(with: "Hello") // 이렇게 쓰면 에러 발생함. Argument Label 쓰면 안 됨

func add(a: Int, b: Int) -> Int {
  return a + b
}

var f4: (Int, Int) -> Int = add(a:b:)
f4(1, 2) // 3

func add(_ a: Int, with b: Int) -> Int {
  return a + b
}

f4 = add(_:with:)

func swapNumbers(_ a: inout Int, _ b: inout Int) {

}

let f5 = swapNumbers(_:_:)
f5

func sum(of numbers: Int...) {
}
let f6 = sum(of:)
f6

func add(_ a: Int, _ b: Int) -> Int {
  return a + b
}

func subtract(_ a: Int, _ b: Int) -> Int {
  return a - b
}

func multiply(_ a: Int, _ b: Int) -> Int {
  return a * b
}

func divide(_ a: Int, _ b: Int) -> Int {
  return a / b
}

typealias ArithmeticFunction = (Int, Int) -> Int

func selectFunction(from op: String) -> ArithmeticFunction? {
  switch op {
   case "+":
    return add(_:_:)
   case "*":
    return multiply(_:_:)
   case "-":  
    return subtract(_:_:)
   case "/":
    return divide(_:_:)
   default:
    return nil
  }
}

let af = selectFunction(from: "+")
af?(1, 2) // 3
selectFunction(from: "*")?(12, 34)
```
- 


### 9-10. Function Type 이해하기
```swift
문제 설명
상수 f에 저장할 수 있는 add 함수를 구현해 주세요.

문법 설명
함수는 First-class Citizen입니다.
함수 형식은 자료형과 리턴형으로 구성됩니다.

import Foundation

// 여기에서 add 함수를 구현해 주세요.
func add(_ a: Int, _ b: Int) -> Int {
    return a + b
}
let f: (Int, Int) -> Int = add
let result = f(1, 2)

print(result)

```


### 9-11. Nested Functions ***
- 함수 내부에 새로운 함수를 구현하는 방법
- 내포된 함수
```swift
func outer() -> () -> () {
  func inner() {
    print("inner")
  }
  print("outer")
  
  return inner
}

let f = outer()
f() // inner

```




## Closures
- 익명 코드 블록을 구현하는 방법

### 10-1. Closures
- 클로저는 비교적 짧고 독립적인 코드 조각이다
- self-contained code blocks이다
- Objective-C에서는 block이라고 부르고, Java에서는 lambda라고 부른다
- Swift에서 클로저에 포함되는 것은 세 가지이다.
  - Named Closures
    - Function
    - Nested Function
  - Unnamed Closures
    - Anonymous Function


- 클로저 표현식 문법
```swift
{ (parameters) -> ReturnType in // Closure Head
  statements // Closure Body
}

{ statements } // 가장 단순한 클로저 형태

let c = { print("Hello, Swift") } // 자료형은 () -> ()
c() // Hello, Swift

let c2 = { (str: String) -> String in
  return "Hello, \(str)"
}

// 클로저에서는 argument label을 사용하지 않는다
let result = c2("Closure")
print(result) // Hello, Closure

typealias SimpleStringClosure = (String) -> String
func perform(closure: SimpleStringClosure) {
  print(closure("iOS"))
}

perform(closure: c2) // Hello, iOS
perform(closure: { (str: String) -> String in 
  return "Hi, \(str)"
})

let products = [
  "Macbook Air", "MacBook Pro", "iMac", "iMac Pro", "Mac Pro", "Mac mini", "iPad Pro", "iPad", "iPad mini",
  "iPhone Xs", "iPhone Xr", "iPhone 8", "iPhone 7", "AirPods", "Apple Watch Series 4", "Apple Watch Nike+"
]

var proModels = products.filter({ (name: String) -> Bool in
  return name.contains("Pro")
})

print(proModels) // ["MacBook Pro", "iMac Pro", "Mac Pro", "iPad Pro"]

proModels.sort(by: { (lhs: String, rhs: String) -> Bool in 
  return lhs.caseInsensitiveCompare(rhs) == .orderedAscending
})

print(proModels) // ["iMac Pro", "iPad Pro", "Mac Pro", "MacBook Pro"]

print("Start")

DispatchQueue.main.asyncAfter(deadline: .now() + 5, execute: { print("End") }) // 5초 뒤 End 출력

// 문법 최적화(Syntax Optimization)
DispatchQueue.main.asyncAfter(deadline: .now() + 5) {
  print("End")
}
```


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


## Collection 
- 다수의 데이터를 저장하는데 사용하는 Array, Dictionary, Set

### 13-1. Collection Overview
### 13-2. Array #1
### 13-3. Array #2
### 13-4. Array #3
### 13-5. 배열 정렬하기
### 13-6. 배열 검색하기
### 13-7. Dictionary#1
### 13-8. Dictionary#2
### 13-9. Dictionary#3
### 13-10. Set#1
### 13-11. Set#2
### 13-12. Set을 통한 집합 연산
### 13-13. Iterating Collections



## Enumeration
- 동일한 이름에 속한 상수 그룹을 선언하고 다양하게 매칭시키는 방법

### 14-1. Enumeration Types
### 14-2. Raw Values
### 14-3. 열거형으로 Http Status Code 처리하기

## Enumeration - 고급

### 14-4. Associated Values ***
### 14-5. Enumeration Case Pattern ***



## Structure and Class
- 새로운 형식을 직접 구현하는 방법

### 15-1. Structures and Classes
### 15-2. Initializer Syntax
### 15-3. 구조체를 선언하고 인스턴스 생성하기
### 15-4. 클래스를 선언하고 인스턴스 생성하기
### 15-5. Value Types vs Reference Types


## Structure and Class - 고급

### 15-6. Identity Operator ***
### 15-7. Nested Types



## Property
- 형식 내부에 값을 저장하고 처리하는 방법

### 16-1. Stored Property
### 16-2. 새로운 저장 속성 추가하기
### 16-3. Computed Property
### 16-4. 새로운 계산 속성 추가하기
### 16-5. Property Observer
### 16-6. Type Property 
### 16-7. 새로운 형식 속성 선언하기
### 16-8. self & super



## Method and Subscript
- 형식과 연관된 코드 블록을 구현하는 방법과 서브스크립트 문법과 함께 사용할 수 있도록 구현하는 방법

### 17-1. Instance Method
### 17-2. 새로운 인스턴스 메소드 추가하기
### 17-3. Type Method
### 17-4. 형식 메소드 구현하기
### 17-5. Subscript
### 17-6. 서브스크립트 구현하기



## Inheritance and Polymorphism
- 상속을 통해 코드 중복을 줄이는 방법과 OOP의 특징 중 하나인 다형성에 대한 공부

### 18-1. Inheritance
### 18-2. Overriding
### 18-3. 클래스 계층 구현하기
### 18-4. Upcasting and Downcasting
### 18-5. Type Casting
### 18-6. Any and AnyObject
### 18-7. Any 배열에 저장되어 있는 값 분류하기
### 18-8. Overloading



## Initializer and Deinitializer
- 인스턴스의 생성과 해제를 담당하는 코드를 구현하는 방법

### 19-1. Initializers
### 19-2. Class Initializers
### 19-3. Required Initializer
### 19-4. Initializer Delegation
### 19-5. 생성자 & 생성자 델리게이션 구현하기
### 19-6. Failable initializer
### 19-7. Deinitializer



## Extension
- 이미 존재하는 형식을 확장하는 방법

### 20-1. Extension - Syntax
### 20-2. Adding Properties
### 20-3. 어제 날짜를 리턴하는 속성과 월, 일을 리턴하는 속성 추가하기
### 20-4. Adding Methods
### 20-5. 문자열 앞, 뒤 공백을 제거하는 메소드 추가하기
### 20-6. Adding Initializers
### 20-7. 년, 월, 일로 날짜를 초기화하는 생성자 추가하기
### 20-8. Adding Subscripts
### 20-9. 문자열에 정수 인덱스로 접근하는 Subscript 추가하기



## Protocol
- 프로토콜을 통해 형식이 구현해야 하는 요구사항을 선언하고 이 요구사항을 충족하도록 형식을 구현하는 방법

### 21-1. Protocol Syntax
### 21-2. Property Requirements
### 21-3. Method Requirements
### 21-4. Initializer Requirements
### 21-5. Subscript Requirements
### 21-6. Custom Type을 비교 연산자로 비교하기


## Protocol - 고급

### 21-7. Protocol Types ***
### 21-8. Protocol composition ***
### 21-9. Optional Requirements ***
### 21-10. Protocol Extension ***



## Memory, Value Typeand Reference Type
- 메모리가 값을 저장하는 방법을 공부하고, 값 형식과 참조 형식의 차이점을 비교

### 22-1. Memory Basics
### 22-2. Value Type vs Reference Type
### 22-3. ARC(Automatic Reference Counting)
### 22-4. Strong Reference Cycle
### 22-5. Closure Capture List



## Generics
- 형식에 독립적인 코드를 구현

### 23-1. Generic Function
### 23-2. 두 값을 비교하는 제네릭 함수 구현하기
### 23-3. Generic Types
### 23-4. Associated Types



## Error Handling
- 코드에서 발생할 수 있는 다양한 오류를 크래시 없이 처리하는 방법

### 24-1. Error Handling
### 24-2. do-catch Statements
### 24-3. Optional Try
### 24-4. defer Statements
### 24-5. 오류 처리 패턴 구현하기
