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
- 문법 최적화를 통해서 클로저 코드를 단축시키는 방법
```swift
var proModels = products.filter({ (name: String) -> Bool in 
  return name.contains("Pro")
})

products.filter({ 
  return $0.contains("Pro") // $0, $1 같은 것들을 'Shorthand Argument Name'이라고 부른다.
})

products.filter({ 
  $0.contains("Pro") // return을 생략한 것을 Implicit Returns라고 한다
})

products.filter() { 
  $0.contains("Pro") // closure 부분만 따로 떼어내서 뒤에 붙이는 것을 Trailing Closure라고 한다
}

products.filter { // 다른 파라미터가 없으면 Argument 넣는 부분까지 생략한다 
  $0.contains("Pro")
}

// 또 다른 예시
// (1) 기본 표현
proModels.sort(by: { (lhs: String, rhs: String) -> Bool in
  return lhs.caseInsensitiveCompare(rhs) == .orderedAscending
})

// (2) 파라미터 형식과 리턴형 생략
proModels.sort(by: { (lhs, rhs) in
  return lhs.caseInsensitiveCompare(rhs) == .orderedAscending
})

// (3) 파라미터 이름을 생략하고 shorthand argument로 대체
proModels.sort(by: {
  return $0.caseInsensitiveCompare($1) == .orderedAscending
})

// (4) 단일 return문이라면 return을 생략(Implicit return)
proModels.sort(by: { 
  $0.caseInsensitiveCompare($1) == .orderedAscending
})

// (5) 클로저가 마지막 파라미터라면 Trailing Closure로 작성한다
proModels.sort() {
  $0.caseInsensitiveCompare($1) == .orderedAscending
}

// (6) 괄호 사이에 더 이상 파라미터가 없다면 괄호를 생략한다
proModels.sort {
  $0.caseInsensitiveCompare($1) == .orderedAscending
}
```

### 10-3. 클로저와 문법 최적화
```swift

containt(where:)은 배열에서 파라미터로 전달한 클로저를 통해 검색을 실행합니다.
이 클로저는 문자열 파라미터를 받아서 불린값을 리턴합니다.

다음 조건을 만족하도록 코드를 작성해 주세요.

where 파라미터에 클로저를 전달하고 A 접두어가 포함된 문자열을 검색해 주세요. 접두어 검색 코드는 아래의 코드를 사용해 주세요. name.hasPrefix("A")
(1)에서는 문법 최적화 없이 전체 문법으로 작성해 주세요.
(2)에서는 문법 최적화를 활용해서 최대한 단순하게 작성해 주세요.
a와 b에는 모두 true가 저장되어야 합니다.

import Foundation

let list = ["Apple", "Google", "Samsung", "Microsoft"]

// where 파라미터로 인라인 클로저를 전달해 주세요. 문법 최적화를 적용하지 않은 전체 문법으로 작성해 주세요.
let a = list.contains(where: { (name: String) -> Bool in
    return name.hasPrefix("A")
}) // (1)

// 여기에서 contains(where:)를 호출하고 문법 최적화를 적용해 주세요.
let b = list.contains() {
    $0.hasPrefix("A")
} // (2)

print(a && b)
```

## Closures - 고급

### 10-4. Capturing Values
- 클로저 내부에서 클로저 외부에 있는 값에 접근할 때 값이 처리되는 방식
- Swift의 Closures는 Named Closures와 Unnamed Closures로 구분된다
- Named Closures는 Function과 Nested Function으로 나뉜다
- Unnamed Closures는 Anonymous Function이 있다
- 세 가지 Closures는 값을 캡처하는 방식이 다르다
- Function(Global Function)은 값을 캡처하지 않는다
- Nested Function은 값을 캡처한다
  - 자신을 포함하고 있는 함수 바디에 있는 값에 접근할 때 이 값을 캡처한다
  - 클로저 표현식으로 작성한 클로저는 클로저 외부에 있는 값을 접근할 때 값을 캡처한다
- 값을 캡처한다(Capturing Values)는 것은 무슨 의미일까? -> '값을 가져와서 쓴다'고 생각하면 쉽다
```swift
// Capturing Values
var num = 0
let c = { print("check point #1: \(num)") }
c() // check point #1: 0 -> num의 값을 가져와서 썼다

num += 1
print("check point #2: \(num)") // check point #2: 1
```
- 값을 캡처하는 방식은 2가지이다.
  - 첫 번째는 복사본을 캡처하는 방식이다 -> Objective-C가 이 방법을 사용한다
  - 두 번째는 참조를 캡처하는 방식인데, Swift가 이 방법을 사용한다. 그냥 원본을 그대로 가져온다고 생각하면 된다.
    - 클로저에서 캡처한 값을 바꾸면, 원래 값도 함께 바뀐다.

```swift
var num = 0
let c = {
  num += 1 // 클로저에서 캡처한 값을 바꾸고 있다 -> 원래 값도 함께 바뀜
  print("check point #1: \(num)")
}
c() // check point #1: 1

print("check point #2: \(num)") // check point #2: 1 -> Swift가 참조를 캡처하는 방식인데, 클로저 내부에서 num의 값을 1 증가 시켰으므로 원래 값도 바뀐다
```
- 클로저 내부에서 외부에 있는 값에 접근하면 값에 대한 참조를 획득한다
- 클로저 내부에서 값을 바꾼다면, 원래 값도 함께 바뀐다
- 클로저에 값을 캡처할 때 메모리 관리를 하지 않는다면, 참조 사이클 문제가 발생한다



### 10-5. Escaping Closure ***
- Escaping과 Non escaping 방식으로 클로저를 실행했을 때 어떤 차이가 있는지 비교
- Escaping Closure는 '무엇으로부터 탈출하는가'를 아는 것이 핵심이다
- Escaping Closure는 함수의 실행이 종료된 후에도 실행될 수 있다
- 함수의 정상적인 흐름을 탈출하는 것이다.
- Escaping Closure는 함수의 시작 시점과 종료 시점이 특정되지 않는다

```swift
func performNonEscaping(closure: () -> ()) {
  print("start")
  closure()
  print("end")
}

performNonEscaping {
  print("closure")
}

/* 
Non-Escaping Closure 실행 결과 -> 실행 흐름을 탈출하지 않는다
start
closure
end
*/


func performEscaping(closure: @escaping () -> ()) {
  print("start")
  
  DispatchQueue.main.asyncAfter(deadline: .now() + 3) {
    closure()
  }
  
  print("end")
}

performEscaping {
  print("closure")
}

/* 
Escaping Closure 실행 결과 -> 실행 흐름을 탈출
start
end
closure
*/
```



## Tuples
- 튜플을 통해 두 개 이상의 값을 하나로 묶어서 처리하는 방법

### 11-1. Tuples
- 두 개 이상의 값을 저장하는 Compound Type인 튜플
```swift
let i = 12, 34 // 'Expected pattern' 에러 발생 -> Int의 경우 하나의 값만 저장할 수 있는 Scalar Type이기 때문
let i = (12, 34) // 이렇게 하면 문제 없음 -> Tuple은 Compound Type이기 때문에 두 개 이상을 저장할 수 있다

let data = ("<html>", 200, "OK", 12.34)
// data의 자료형 -> (String, Int, String, Double)
data.0 // "<html>"
data.1 // 200
data.2 // "OK"
data.3 // 12.34

data.1 = 404 // 'Cannot assign to property: 'data' is a 'let' constant' 에러 발생

var mutableTuple = data
mutableTuple.1 = 404
mutableTuple.1 // 404
```
- 튜플에 저장된 값을 사용할 때는 점문법'.(dot) Syntax'을 사용한다
- 점문법을 보통 Explicit Member Expression이라고 부른다



### 11-2. Named Tuples
- 튜플 멤버에 이름을 붙여서 가독성을 높이는 방법
```swift
let data = ("<html>", 200, "ok", 12.34)
data.0 // <html>

let named = (body: "<html>", statudCode: 200, statusMessage: "OK", dataSize: 12.34)
named.1 // 200
named.statusCode // 200
```



### 11-3. Tuple Decomposition
- 튜플에 저장된 멤버를 개별 상수나 개별 변수에 저장하는 방법
- Decomposition은 우리말로 '분해'를 의미한다
```swift
let data = ("<html>", 200, "OK", 12.34)

let (body, code, message, size) = data
let (body, code, message, _) = data // wild card 문법 사용 가능

```


### 11-4. Tuple Matching
- switch문을 활용해서 튜플에 저장된 값을 매칭시키는 방법
```swift
let resolution = (3840.0, 1080.0)

if resolution.0 == 3840 && resolution.1 == 2160 {
  print("4K")
}

switch resolution {
  case let(w, h) where w / h == 16.0 / 9.0:
    print("16:9")
  case (_, 1080): // 넓이는 신경쓰지 않고, 높이만 신경 쓰는 경우
    print("1080p")
  case (3840...4096, 2160):
    print("4K")
  default:
    break
}
```



### 11-5. 튜플을 리턴하는 함수 구현하기
```swift
문제 설명
코드가 정상적으로 실행되도록 함수를 구현하고 결과를 출력해 주세요.

제한
함수는 name, age, address 상수를 튜플로 리턴해야 합니다.
Named Tuple로 리턴해야 합니다.

import Foundation

// 여기에서 함수를 구현해 주세요.
func convertToTuple(name: String, age: Int, address: String) -> (name: String, age: Int, address: String) {
    return (name, age, address)
}

let name = "John doe"
let age = 34
let address = "Seoul"

let t = convertToTuple(name: name, age: age, address: address)

// 여기에서 튜플에 저장된 이름, 나이, 주소를 순서대로 출력해 주세요.
print(t.name, t.age, t.address) // John doe 34 Seoul

```

## String and Character
- 가장 기초적인 형식인 문자열과 문자를 다루는 방법

### 12-1. Strings and Characters
```swift
var nsstr: NSString = "str"
let swiftStr: String = nsstr as String
nsstr = swiftStr as NSString
// NSString과 String을 Toll-Free Bridged라고 표현한다 -> 서로 타입 캐스팅을 하는 것이 가능
```



### 12-2. Multiline String Literals
### 12-3. String Interpolation
- 문자열을 동적으로 구성하는 두 가지 방법
  - String Interpolation
  - 문자열 포멧 생성자
  - 포멧 지정자
  - 다국어 포멧 문자열
  - Escape Sequence

```swift
// 포멧 지정자(Format Specifier)
str = String(format: "%.1fKB", size) // 12.3KB
String(format: "Hello, %@", "Swift") // Hello, Swift
String(format: "%d", 12) // 12
String(format: "%f", 12.34) // 12.3400000
String(format: "%.3f", 12.34) // 12.340
String(format: "%010.3f", 12.34) // 000012.340

String(format: "[%d]", 123) // [123]
String(format: "[%10d]", 123) // [   123] -> 오른쪽 정렬
String(format: "[%-10d]]", 123) // [123   ]] -> 왼쪽 정렬

let firstName = "Yoon-ah"
let lastName = "Lim"

let korFormat = "그녀의 이름은 %2$@ %1$@ 입니다." // 두 번째로 들어오는 인자가 먼저 나오도록 설정
let engFormat = "Her name is %1$@ %2$@."

String(format: korFormat, firstName, lastName) // 그녀의 이름은 Lim Yoon-ah 입니다.
String(format: engFormat, firstName, lastName) // Her name is Yoon-ah Lim.


print("A\tB") // A  B
print("C\nD") 
/* 
C
D
*/
```

### 12-4. 원하는 포멧으로 문자열 출력하기
```swift
아래와 같이 출력되도록 코드를 구현해 주세요.

오늘은 2019년 10월 14일 입니다. 날씨는 '맑음', 온도는 10.2도 입니다.

import Foundation

let year = 2019
let month = 10
let day = 14

// 오늘은 2019년 10월 14일 입니다.
let dateStr = String(format: "오늘은 %d년 %d월 %d일 입니다.", year, month, day)

let weather = "맑음"
let temperature = 10.23456

// 날씨는 '맑음', 온도는 10.2도 입니다.
let weatherStr = String(format: "날씨는 '\(weather)', 온도는 %.1f도 입니다.", temperature)

// String Interpolation 문법으로 dateStr, weatherStr을 공백 하나로 연결해 주세요.
let finalStr = "\(dateStr) \(weatherStr)"
print(finalStr)
```



### 12-5. String Indices
- 문자열 인덱스로 특정 문자의 위치를 표현하는 방법
```swift
let str = "Swift"
str.startIndex // String.Index 타입
let firstCh = str[str.startIndex]
print(firstCh) // S

let lastCh = str[str.endIndex] // String.Index 타입.
print(lastCh) // 이 상태라면 String index is out of bounds 에러 발생

// 정상적으로 문자열의 마지막 인덱스에 접근하는 방법
let lastCharIndex = str.index(before: str.endIndex)
let lastCh = str[lastCharIndex]
print(lastCh) // t

let secondCharIndex = str.index(after: str.startIndex)
let secondCh = str[secondCharIndex]
print(secondCh) // w

var thirdCharIndex = str.index(str.startIndex, offsetBy: 2) // 첫 번째 인덱스에서 두 번째 만큼 떨어진 인덱스(세 번째)
var thirdCh = str[thirdCharIndex]
print(thirdCh) // i

thirdIndex = str.index(str.endIndex, offsetBy: -3) // 마지막 인덱스에서 끝에서 세 번째 인덱스
thirdCh = str[thirdCharIndex]
print(thirdCh) // i

// 안전하게 사용하기
if thirdCharIndex < str.endIndex && thirdCharIndex >= str.startIndex {

}

```



### 12-6. 문자열에서 원하는 범위 추출하기
```swift
import Foundation

let str = "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."

// range(of:)를 활용해서 시작 인덱스를 구해주세요.
let startIndex = str.range(of: "nisi ut aliquip")?.lowerBound ?? str.startIndex

// index(_:offsetBy:)를 활용해서 종료 인덱스를 구해주세요.
let endIndex = str.index(startIndex, offsetBy: 14)

// 서브스크립트 문법으로 범위를 추출해 주세요.
let result = str[startIndex...endIndex]
print(result == "nisi ut aliquip")
```

### 12-7. String Basics
- 문자열 조작에 필요한 기초 테크닉
```swift
var str = "Hello, Swift String"
var emptyStr = ""
emptyStr = String()

let a = String(true) // "true"
let b = String(12) // "12"
let c = String(12.34) // "12.34"

let hex = String(123, radix: 16) // "7b" -> 16진수 123
let octal = String(123, radix: 8) // "173" -> 8진수 123
let binary = String(123, radix: 2) // "1111011" -> 2진수 123

let repeatStr = String(repeating: "G", count: 7) // "GGGGGGG"
let unicode = "\u{1f44f}" // 박수문자

let e = "\(a) \(b)" // "true 12"
let f = a + " " + b // "true 12"
str += "!!" // "Hello, Swift String!!"

str.count // 21
str.isEmpty // false
str == "Apple" // false
"apple" != "Apple" // true -> 대소문자 구분 한다
"apple" < "Apple" // false -> 소문자 apple이 대문자 Apple보다 크다고 판단

str.lowercased() // 모든 문자들을 소문자로 변경 -> 원본은 건드리지 않는다
str.uppercased() // 모든 문자들을 대문자로 변경

"apple ipad".capitalized() // 첫 글자를 대문자로 변경 -> "Apple Ipad"

for char in "Hello" {
  print(char)
}
/* 
H
e
l
l
o
*/

let num = "1234567890"
num.randomElement()

num.shuffled() // 문자열을 임의로 섞음
```



### 12-8. Substring
```swift
let str = "Hello, Swift"
let l = str.lowercased() // hello, swift

var first = str.prefix(1) // 새로운 메모리 공간을 사용하지 않는다
// 핵심: substring은 원본 문자열의 메모리를 공유한다
first.insert("!", at: first.endIndex)
str // "Hello, Swift"
first // "H!" -> Copy on Write Optimization(Swift의 메모리 최적화 기법)

let s = str.[..<str.index(str.startIndex, offsetBy: 2)] // "He"

str[str.index(str.startIndex, offsetBy: 2)...] // "llo, Swift"

let lower = str.index(str.startIndex, offsetBy: 2) // String.Index
let upper = str.index(str.startIndex, offsetBy: 5) // String.Index
str[lower ... upper] // "llo,"
```



### 12-9. String Editing #1
- 메소드를 활용해서 문자열을 편집하는 방법
```swift
var str = "Hello"
str.append(", ")
print(str) // "Hello, "

let s = str.appending
// append 메소드는 리턴형이 Void, appending 메소드는 리턴형이 String

let s = str.appending("Swift")
str // "Hello, "
s // "Hello, Swift"

"File size is ".appendingFormat("%.1f", 12.3456) // "File size is 12.3"

var str = "Hello, Swift"
str.insert(",", at: str.index(str.startIndex, offsetBy: 5)) // "Hello, Swift"

if let sIndex = str.firstIndex(of: "S") {
  str.insert(contentsOf: "Awesome", at: sIndex)
}
print(str) // "Hello, AwesomeSwift"
```



### 12-10. String Editing #2
- 메소드를 활용해서 문자열을 편집하는 방법
```swift
var str = "Hello, Objective-C"
if let range = str.range(of: "Objective-C") {
  str.replaceSubrange(range, with: "Swift")
}
str // Hello, Swift

if let range = str.range(of: "Hello") {
  let s = str.replacingCharacters(in: range, with: "Hi") // replacing은 원본을 변경시키지 않는다
  s // Hi, Swift
  str // Hello, Swift
}


var s = str.replacingOccurences(of: "Swift", with: "Awesome Swift")
s // "Hello, Awesome Swift"
s = str.replacingOccurences(of: "swift", with: "AwesomeSwift") // str에는 Swift만 있지 swift는 없으니까 검색에 실패함 -> 원본을 그대로 돌려줌
s // "Hello, Swift"
s = str.replacingOccurrences(of: "Swift", with: "Awesome Swift", options: [.caseInsensitive]) 
s // "Hello, Awesome Swift"

// Removing Substrings
var str = "Hello, Awesome Swift!!!"

let lastCharIndex = str.index(before: str.endIndex)

var removed = str.remove(at: lastCharIndex) // "!"

str // "Hello, Awesome Swift!!"

removed = str.removeFirst()
str // "ello, Awesome Swift!!"
str.removeFirst(2) // "lo, Awesome Swift!!"
str // "lo, Awesome Swift!!"

str.removeLast // !
str // "lo, Awesome Swift!"

str.removeLast(2) // "lo, Awesome Swif"
str // "lo, Awesome Swif"

if let range - str.range(of: "Awesome") {
  str.removeSubrange(range)
  str // "lo, Swif"
}

str.removeAll()
str // ""

str.removeAll(keepingCapacity: true) // 이렇게 하면 다 지우더라도 메모리 공간에는 남아 있다 -> 불필요한 메모리 오버헤드가 줄어들 수 있음
str = "Hello, Awesome Swift!!!"

var substr = str.dropLast() // "Hello, Awesome Swift!!"

substr = str.dropLast(3) // "Hello, Awesome Swift" -> 새로운 메모리 공간이 생성된 건 아님(str과 메모리 공유)
substr = str.drop(while: { (ch) -> Bool in 
  return ch != ","
})
substr // ",Awesome Swift!!!"
```



### 12-11. 문자열에서 원하는 부분 편집하기
```swift
// 문자열에서 i를 모두 삭제하고 소문자 o는 대문자 O로 바꿔 주세요.

import Foundation

let str = "Lorem ipsum dolor sit amet"

var result = str.replacingOccurrences(of: "o", with: "O")
result = result.replacingOccurrences(of: "i", with: "")

print(result == "LOrem psum dOlOr st amet")
```


### 12-12. String Comparison
- 문자열을 비교하는 방법
```swift
let largeA = "Apple"
let smallA = "apple"
let b = "Banana"

largeA == smallA // false
largeA != small! // true

largeA < smallA // true -> 대문자 A에 할당된 아스키코드가 소문자 a보다 작기 때문에 true가 나온다
largeA < b // true -> 대문자 A가 소문자 b보다 작기 때문
smallA < b // false -> 아스키코드에서는 소문자 a가 소문자 b보다 크다

largeA.compare(smallA) // NSComparisonResult 타입
largeA.compare(smallA) == .orderedSame // false
largeA.caseInsensitiveCompare(smallA) == .orderedSame // true -> 대소문자 구분 안함
largeA.compare(smallA, options: [.caseInsensitive]) == .orderedSame // true

let str = "Hello, Swift Programming!"
let prefix = "Hello"
let suffix = "Programming" // suffix는 '접미사'를 의미한다

str.hasPrefix(prefix) // true -> 둘 다 Hello로 시작하니까
str.hasSuffix(suffix) // false -> str은 Programming!으로 끝나는데 suffix는 Programming으로 끝나니까 false임
```

### 12-13. String Searching
- 문자열에서 원하는 부분만 검색하는 방법
```swift
let str = "Hello, Swift"
str.contains("swift") // false -> 대소문자 구분 함
str.lowercased().contains("swift") // true
str.range(of: "Swift") // 범위 검색 -> 대소문자 구분 함
str.range(of: "swift", options: [.caseInsensitive]) // 범위 검색 -> 대소문자 구분 안 함

let str2 = "Hello, Programming" // "Hello, Programming" 
let str3 = str2.lowercased() // "hello, programming"

var common = str.commonPrefix(with: str2) // "Hello,"
common = str.commonPrefix(with: str3) // "" -> 대소문자 구분 함
str.commonPrefix(with: str3, options: [.caseInsensitive]) // "Hello," -> .caseInsensitive 옵션으로 대소문자 구분 안 함

str3.commonPrefix(with: str, options: [.caseInsensitive]) // "hello," -> str3이 hello로 쓰여 있으니까

```
### 12-14. 문자열에서 문자 검색하기
```swift
import Foundation

let str = "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."

var count = 0
for char in str {
    if char == "i" {
        count += 1
    }
}

// 여기에서 i 문자의 수를 구한 후 count 변수에 저장해 주세요.

print(count)
```



## String and Character - 고급

### 12-15. String Options #1
- 문자열 옵션을 통해 다양한 비교//검색 조건을 지정하는 방법
```swift
"A" == "a" // false
"A".caseInsensitiveCompare("a") == .orderedSame // true
"A".compare("a", options: [.caseInsensitive]) == .orderedSame // true
NSString.CompareOptions.caseInsensitive

let a = "\u{D55C}" // "한"이라는 글자의 유니코드
let b = "\u{1112}\u{1161}\u{11AB}" // "ㅎ", "ㅏ", "ㄴ" 유니코드 -> "한"

a == b // true
a.compare(b) == .orderedSame // true
a.compare(b, options: [.literal]) == .orderedSame // false

let korean = "행복하세요"
let english = "Be happy"

if let range = english.range(of: "p") {
  english.distance(from: english.startIndex, to: range.lowerBound) // 5
}

if let range = english.range(of: "p", options: [.backwards]) {
  english.distance(from: english.startIndex, to: range.lowerBound) // 6
}

// Anchored Option: 검색 범위를 문장의 시작이나 끝부분으로 설정하고 시작
let str = "Swift Programming"

if let result = str.range(of: "Swift") {
  print(str.distance(from: str.startIndex, to: result.lowerbound)) // 0 -> "Swift"의 인덱스는 0
} else {
  print("not found")
}

if let result = str.rrange(of: "Swift", options: [.backwards]) {
  print(str.distance(from: str.startIndex, to: result.lowerbound)) // 0 -> "Swift"의 인덱스는 0(backwards)
} else {
  print("not found")
}

if let result = str.rrange(of: "Swift", options: [.anchored]) {
  print(str.distance(from: str.startIndex, to: result.lowerbound)) // 0 -> "Swift"의 인덱스는 0(anchored)
} else {
  print("not found")
}

if let result = str.rrange(of: "Swift", options: [.anchored, .backwards]) { // 이렇게 옵션에 .anchored, .backwards 순서로 넣으면 trailing에서 leading 방향으로 검색한다
  print(str.distance(from: str.startIndex, to: result.lowerbound))
} else {
  print("not found") // 이게 출력됨 -> anchored 옵션을 사용하면 문자열 전체를 검색하지 않는다.
                     // 문자열 중에서 시작 부분이나 마지막 부분만 검색을 한다. backwards 옵션이 포함되어 마지막 부분만 검색해서 이런 결과가 나온다
}
// anchored 옵션은 단독으로 사용되는 경우가 없다. 자주 사용하지도 않는다.
str.hasPrefix("swift") // false
if let _ = str.range(of: "swift", options: [.anchored, caseInsensitive]) {
  print("same prefix") // "same prefix" 
}
str.hasSuffix("swift") // false
```

### 12-16. String Options #2
- 문자열 옵션을 통해 다양한 비교/검색 조건을 지정하는 방법
```swift
// Numeric Option
"A" < "B" // true
"a" < "B" // false -> Swift는 사전 순서로 문자를 배열하지 않는다. 아스키 테이블에서는 소문자 a가 대문자 B보다 더 크다.

let file9 = "file9.txt"
let file10 = "file10.txt"

file9 < file10 // false
file9.compare(file10) == .oredredAscending // false

// numeric 옵션을 사용하면 문자열에 포함된 숫자를 숫자 자체로 비교한다(numeric은 '숫자'를 의미).
file9.compare(file10, options: [.numeric]) == .orderedAscending // true

// Diacritic(발음기호) Insensitive
let a = "Cafe"
let b = "Cafe"(발음기호 추가됨)

a == b // false
a.compare(b) == .orderedSame // false
a.compare(b, options: [.diacriticInsensitive]) == .orderedSame // true

// Forced Ordering Option -> 강제 정렬
let upper = "STRING"
let lower = "string"

upper == lower // false
upper.compare(lower, options: [.caseInsensitive]) == .orderedSame // true
upper.compare(lower, options: [.caseInsensitive, .forcedOrdering]) == .orderedSame // false -> forcedOrdering을 적용하면 caseInsensitive가 무시됨

// Regular Expression(정규식 표현)
let emailPattern = "([0-9a-zA-Z_-]+)@(0-9a-zA-Z_-]+)(\\.[0-9a-zA-Z_-]+){1,2}"
let emailAddress = "user@example.com"

if let _ = emailAddress.range(of: emailPattern) {
  print("found")
} else {
  print("not found") // 이게 출력됨
}

if let _ = emailAddress.range(of: emailPattern, options: [.regularExpression]) {
  print("found") // 이게 출력됨
} else {
  print("not found")
}
// 하지만 위 방법만으로는 사용자가 email 형식을 제대로 사용하였는지 확인할 수 없으므로 다음의 방법을 사용해야함

if let range = emailAddress.range(of: emailPattern, options: [.regularExpression]), (range.lowerBound, range.upperBound) == (emailAddress.startIndex, emailAddress.endIndex) {
  print("found") 
} else {
  print("not found")// 이게 출력됨
}

```
### 12-17. 올바른 문자열 옵션 사용하기
```swift
두 문자열을 동일한 문자열로 판단하도록 적절한 문자열 옵션을 채워주세요.
import Foundation

let a = "cafè"
let b = "Cafe"

let result = a.compare(b, options: 
[.caseInsensitive, .diacriticInsensitive]
) == 
.orderedSame

print(result)
```



### 12-18. Character Set ***
- 문자 집합(Character Set)을 만들고 활용하는 방법
```swift
let a = CharacterSet.uppercaseLetters
let b = a.inverted

// 캐릭터셋을 활용한 검색 코드
let str = "loRem Ipsum"
var charSet = CharacerSet.uppercaseLetters

if let range = str.rangeOfcharacter(from: charSet) {
  print(str.distance(from: str.startIndex, to: range.lowerBound)) // 2 (세번째 인덱스)
}

if let range = str.rangeOfcharacter(from: charSet, options: [.backwards]) {
  print(str.distance(from: str.startIndex, to: range.lowerBound)) // 뒤에서 검색했을 때 첫 번째가 "I"이므로, "I"의 인덱스인 6이 출력됨 
}

str " A p p l e "
charSet = .whiteSpaces
let trimmed = str.trimmingCharacters(in: charSet)
print(trimmed) // A p p l e

var editTarget = CharacterSet.uppercaseLetters
editTarget.insert("#") // # 문자가 추가됨
editTarget.insert(charactersIn: "~!@") // 여러개를 추가할 때는 charactestIn

editTarget.remove("A") // A문자 하나를 삭제
editTarget.remove("charactersIn: "BCD") // 세 문자를 삭제

let customCharSet = CharacterSet(charactersIn: "@.")
let email = "userId@example.com"
let components = email.components(separatedBy: customCharSet) // "userId", "example", "com" -> @와 .으로 구분된 내용들

```


### 12-19. 문자열에서 불필요한 문자 제거하기
```swift
문제 설명
CharacterSet을 활용해서 [ ] 문자와 앞 뒤 공백을 제거해 주세요.

import Foundation

var str = "[  http://www.programmers.co.kr  ]"

// 여기에서 CharacterSet을 생성해 주세요.
var charSet = CharacterSet.whitespaces

// 여기에 결과를 저장해 주세요.
var result = str.trimmingCharacters(in: ["[", "]"])
result = result.trimmingCharacters(in: charSet)

print(result)

```

## Collection 
- 다수의 데이터를 저장하는데 사용하는 Array, Dictionary, Set

### 13-1. Collection Overview
- Foundation Collection: 객체(Object) 형식의 데이터만 저장할 수 있다
  - NSArray
  - NSDictionary
  - NSSet

- Swift Collection: 객체(Object) 형식과 값(Value) 형식 모두 저장할 수 있다
  - Array
  - Dictionary
  - Set

- 컬렉션이 변경되지 않는다면, 메모리 최적화를 위해 항상 동일한 데이터를 사용한다(Copy-on-write)



### 13-2. Array #1
- 배열의 특징과 기초적인 조작 방법
  - 배열의 일반적인 특징
  - 배열 리터럴과 배열 자료형
  - 요소의 수 확인
  - 서브스크립트 문법
  - 
```swift
let fruits = ["Apple", "Banana", "Melon"]

fruits[0] // Apple

fruits[2] // Melon

fruits[0...1] // ["Apple", "Banana"]

fruits[fruits.startIndex] // Apple

fruits[fruits.index(before: fruits.endIndex)] // Melon

fruits.first // Apple
fruits.last // Melon

```


### 13-3. Array #2
- 배열에 새로운 요소를 추가하고 삭제하는 방법
  - 배열 마지막에 새로운 요소 추가
  - 특정 위치에 새로운 요소 추가
  - 특정 범위 교체
  - 요소 삭제
  - 범위 삭제

```swift
Adding Elements

var alphabet = ["A", "B", "C"]

alphabet.append("E") // ["A", "B", "C", "E"]
alphabet.append(contentsOf: ["F", "G"]) // ["A", "B", "C", "E", "F", "G"]
alphabet.insert("D", at: 3) // ["A", "B", "C", "D", "E", "F", "G"]
alphabet.insert(contentsOf: ["a", "b", "c"], at: 0) // ["a", "b", "c", "A", "B", "C", "D", "E", "F", "G"]

특정 범위 교체
alphabet[0...2] = ["x", "y", "z"]
alphabet // ["x", "y", "z", "A", "B", "C", "D", "E", "F", "G"]

alphabet.replaceSubrange(0...2, with: ["a", "b", "c"])
alphabet // ["a", "b", "c", "A", "B", "C", "D", "E", "F", "G"]

alphabet[0...2] = ["z"]
alphabet // ["z", "A", "B", "C", "D", "E", "F", "G"]

특정 범위 삭제
alphabet[0..<1] = []
alphabet // ["A", "B", "C", "D", "E", "F", "G"] 

Removing Elements
alphabet = ["A", "B", "C", "D", "E", "F", "G"]
alphabet.remove(at: 2) // "C"
alphabet // ["A", "B", "D", "E", "F", "G"]

alphabet.removeFirst() // "A"
alphabet // ["B", "D", "E", "F", "G"]

alphabet.removeFirst(2)
alphabet // ["E", "F", "G"]

alphabet.removeAll() // []

alphabet.popLast() // nil -> 비어있으니까 (에러 발생 안하므로 안전하게 사용 가능)
alphabet = ["A", "B", "C", "D", "E", "F", "G"]
alphabet.popLast() // ["A", "B", "C", "D", "E", "F"]
alphabet

alphabet.removeSubrange(0...2) // ["D", "E", "F"]
alphabet // ["D", "E", "F"]

```

### 13-4. Array #3
- 배열을 비교하고, 원하는 요소를 검색하고, 요소를 원하는 순서로 정렬하는 방법
  - 배열 비교
  - 요소 검색
  - 첫 번째 인덱스 검색
  - 첫 번째 요소 검색
  - 배열 정렬과 역순 정렬
  - 특정 위치의 요소 교체
  - 랜덤 섞기

```swift
let a = ["A", "B", "C"]
let b = ["a", "b", "c"]

a == b // false
a != b // true

a.elementsEqual(b) // false

a.elementsEqual(b) { (lhs, rhs) -> Bool in
  return lhs.caseInsensitiveCompare(rhs) == .orderedSame
} // true

Finding Elements
let nums = [1, 2, 3, 1, 4, 5, 2, 6, 7, 5, 0]
nums.contains(1) // true
nums.contains(8) // false

nums.contains { (n) -> Bool in
  return n % 2 == 0
} // true

nums.first { (n) -> Bool in
  return n % 2 == 0
} // 2 -> 가장 첫 번째 짝수

nums.firstIndex { (n) -> Bool in
  return n % 2 == 0
} // 1 -> 2가 두 번째(1번 인덱스)에 있으니까

nums.firstIndex(of: 1) // 0 -> 첫 번째 1은 0번 인덱스에 있으니까 
nums.lastIndex(of: 1) // 3 -> 마지막 1은 3번 인덱스에 있으니까

Sorting on Array
sort -> 배열을 직접 정렬
sorted -> 정렬된 새로운 배열을 리턴

nums.sorted() // [0, 1, 1, 2, 2, 3, 4, 5, 5, 6, 7] 
nums // [1, 2, 3, 1, 4, 5, 2, 6, 7, 5, 0]

nums.sorted { (a, b) -> Bool in
  return a > b
} // [7, 6, 5, 5, 4, 3, 2, 2, 1, 1, 0]

nums.sorted().reversed() // ReversedCollection<Array<Int>>
[Int](nums.sorted().reversed()) // [7, 6, 5, 5, 4, 3, 2, 2, 1, 1, 0]

가변배열 정렬
var mutableNums = nums
mutableNums.sort() // [0, 1, 1, 2, 2, 3, 4, 5, 5, 6, 7]
mutableNums.reverse() // [7, 6, 5, 5, 4, 3, 2, 2, 1, 1, 0]

mutableNums // [7, 6, 5, 5, 4, 3, 2, 2, 1, 1, 0]
mutableNums.swapAt(0, 1) // [6, 7, 5, 5, 4, 3, 2, 2, 1, 1, 0]

랜덤 섞기
mutableNums.shuffle()
```

### 13-5. 배열 정렬하기
```swift
import Foundation

var list = [9, 5, 4, 2, 7, 1, 0, 3, 6, 8]

// 여기에서 list 배열을 내림차순으로 정렬해 주세요.
list.sort {
    $0 > $1
}

// 여기에서 list 배열을 오름차순으로 정렬한 새로운 배열을 저장해 주세요.
let a = list.sorted()
print(list == [9, 8, 7, 6, 5, 4, 3, 2, 1, 0] && list.reversed() == a)
```



### 13-6. 배열 검색하기
```swift
import Foundation

let list = ["iPad Pro", "iPhone Xs", "MacBook", "iPhone Xs MAX", "iPad", "MacBook Air", "iPhone Xr", "iPad Mini", "iPhone 8", "MacBook Pro", "iPhone 8 Plus", "iMac", "AirPods", "iMac Pro", "Magic Mouse 2", "Mac Pro", "Magic Keyboard", "Mac mini"]

// 여기에서 필터링 코드를 구현해 주세요.
var filtered = list.filter { $0.contains("iPhone") }

filtered.sort()
print(filtered == ["iPhone 8", "iPhone 8 Plus", "iPhone Xr", "iPhone Xs", "iPhone Xs MAX"])
```


### 13-7. Dictionary#1
- 딕셔너리의 특징 및 기초적인 사용법
  - 딕셔너리의 특징
  - 딕셔너리 리터럴
  - 딕셔너리 자료형
  - 딕셔너리 생성
  - 요소의 수 확인
  - 서브스크립트 문법

```swift
Creating a Dictionary
let words = ["A": "Apple", "B": "Banana", "C": "City"]
let emptyDict: [String: String] = [:]
let emptyDict2 = [String: String]()
let emptyDict3 = Dictionary<String, String>()

Inspecting a Dictionary
words.count // 3
words.isEmpty // false


Accessing Keys and Values

words["A"] // "Apple"
words["Apple"] // nil

let a = words["E"] // nil -> 해당 키에 맞는 밸류가 없으니까 nil
let b = words["E", default: "Empty"] // "Empty"

for k in words.keys {
  print(k)
}
/* 
B
A
C
*/

for v in words.values {
  print(v)
}
/* 
Banana
Apple
City
*/

// 정렬해서 출력하기
for k in words.keys.sorted() {
  print(k)
}
/* 
A
B
C
*/


// Dictionary를 배열로 바꾸기
let keys = Array(words.keys) // ["B", "C", "A"]
let values = Array(words.values) // ["Banana", "City", "Apple"]
```



### 13-8. Dictionary#2
- 새로운 요소를 추가하고 삭제하는 방법
  - 새로운 요소 추가
  - 개별 요소 삭제
  - 전체 요소 삭제
```swift
Adding Keys and Values

var words = [String: String]()
words["A"] = "Apple"
words["B"] = "Banana"

words.count // 2
words // ["A": "Apple", "B": "Banana"]

words["B"] = "Ball"
words // ["A": "Apple", "B": "Ball"]

words.updateValue("City", forKey: "C") // nil
words.updateValue("Circle", forKey: "C") // "City"

Removing Keys and Values

words // ["C": "Circle", "A": "Apple", "B": "Ball"]
words["B"] = nil

words // ["C": "Circle", "A": "Apple"]

words["Z"] = nil // nil -> 존재하지 않는 키를 삭제한다고 해서 크래시가 발생하진 않는다

words.removeValue(forKey: "A") // "Apple"
words.removeValue(forKey: "A") // nil

words.removeAll() // 전체 삭제

```



### 13-9. Dictionary#3
- 딕셔너리를 비교하고 검색하는 방법
  - 딕셔너리 비교
  - 요소 검색

```swift
Comparing Dictionaries

let a = ["A": "Apple", "B": "Banana", "C": "City"]
let b = ["A": "Apple", "C": "City", "B": "Banana"]

a == b // true -> 순서는 신경쓰지 않는다
a != b // false

let a = ["A": "Apple", "B": "Banana", "C": "City"]
let b = ["A": "Apple", "C": "City", "B": "banana"]

a == b // false -> 대소문자는 신경 쓴다
a != b // true

// 대소문자 무시하고 비교하기(caseInsensitiveCompare) -> 잘못된 코드
a.elementsEqual(b) { (lhs, rhs) -> Bool in
  return lhs.key.caseInsensitiveCompare(rhs.key) == .orderedSame &&
         lhs.value.caseInsensitiveCompare(rhs.value) == .orderedSame
} // true 또는 false가 나옴 -> 같은 키를 비교하는 경우와 서로 다른 키를 비교하는 경우가 둘 다 생긴다 -> 딕셔너리는 정렬되어 있지 않으니까

// 대소문자 무시하고 비교하기(caseInsensitiveCompare) -> 제대로 된 코드
let aKeys = a.keys.sorted()
let bKeys = b.keys.sorted()

aKeys.elementsEqual(bKeys) { (lhs, rhs) -> Bool in
  guard lhs.caseInsensitiveCompare(rhs) == .orderedSame else { return false }
  guard let lv = a[lhs], let rv = b[rhs],
    lv.caseInsensitiveCompare(rv) == .orederedSame else { return false }
    return true
} // 이렇게 하면 항상 true -> 정렬 돼 있으니까



Finding Elements

words = ["A": "Apple", "B": "Banana", "C": "City"]

let c: ((String, String)) -> Bool = {
  $0.0 == "B" || $0.1.contains("i") // Key에 대문자 B가 있거나, 밸류에 "i"가 있는 경우 true
}

words.contains(where: c) // true
let r = words.first(where: c) // (key: "B", value: "Banana") 검색된 첫 번째 요소(tuple)를 return
r?.key // "C" -> 순서 달라지니까
r?.value // "City" -> 순서 달라지니까

words.filter(c) // ["C": "City", "B": "Banana"]

```



### 13-10. Set#1
- 집합 연산을 구현한 셋
  - 셋의 특징
  - 셋 자료형
  - 요소의 수 확인
  - 요소 검색
  - 요소 추가
  - 요소 삭제
  - 해싱


```swift
let set: Set<Int> = [1, 2, 2, 3, 3, 3] // {1, 2, 3} -> 중복이 허용되지 않는다
set.count // 3

Inspecting a Set

set.count // 3
set.isEmpty // false

Testing for Membership

set.contains(1) // true


Adding and Removing Elements

var words = Set<String>()

var insertResult = words.insert("Swift") // inserted true
insertResult.inserted // true
insertResult.memeberAfterInsert // "Swift"

var insertResult = words.insert("Swift") // inserted false
insertResult.inserted // false
insertResult.memeberAfterInsert // "Swift"

var updateResult = words.update(with: "Swift") // "Swift" -> 기존에 있던 내용을 update
updateResult // "Swift"

updateResult = words.update(with: "Apple") // nil -> 기존에 없던 내용을 insert
updateResult // nil


var value = "Swift" // "Swift"
value.hashValue // -375957790865175...

updateResult = words.update(with: value) // "Swift"
updateResult // "Swift"

value = "Hello" // "Hello"
value.hashValue // -301532757027695...

updateResult = words.update(with: value) // nil
updateResult // nil


struct SampleData: Hashable {
  var hashValue: Int = 123
  var data: String
  
  init(_ data: String) {
    self.data = data
  }
  
  static func == (lhs: SampleData, rhs: SampleData) -> Bool {
    return lhs.hashValue == rhs.hashValue // 두 데이터를 비교할 때 해시값을 비교
  }
}

var sampleSet = Set<SampleData>()
var data = SampleData("Swift")
data.hashValue // 123

var r = sampleSet.insert(data) // inserted true, {hashValue 123, data "Swift"}
r.inserted // true
r.memberAfterInsert // SampleData
sampleSet {{hashValue 123, data "Swift"}}

data.data = "Hello"
data.hashValue // 123

r = sampleSet.insert(data) // inserted false, {hashValue 123, data "Hello"} -> 해시 값이 똑같이 123이기 때문에 "Hello"는 추가되지 못했음
r.inserted // false
r.memberAfterInsert
sampleSet // {{hashValue 123, data "Swift"}}

sampleSet.update(with: data)
sampleSet // {{hashValue 123, data "Hello"}} -> "Hello"가 새롭게 추가(insert)되진 않았지만, 기존의 "Swift"를 대체했다(update)

words.remove("Swift") // "Swift"
words // {"Apple", "Hello"}

words.remove("Ghost"} // nil -> 없는 존재를 삭제하면 nil을 리턴

words.removeAll()

```



### 13-11. Set#2
- 셋에서 집합 비교와 집합 연산을 구현
  - 셋 비교
  - 합집합
  - 교집합
  - 여집합
  - 차집합

```swift
Comparing Sets

var a: Set = [1, 2, 3, 4, 5, 6, 7, 8, 9]
var b: Set = [1, 3, 5, 7, 9]
var c: Set = [2, 4, 6, 8, 10]
var d: Set = [1, 7, 5, 9, 3]

a == b // false
a != b // true

b == d // true -> 원소의 순서는 고려하지 않는다

b.elementsEqual(d) // false -> elementsEqual은 두 Set에 들어있는 원소를 순서대로 배열하기 때문
// 두 Set의 원소를 제대로 비교하고 싶다면, 우선 Set을 배열로 바꾸고 그 후에 비교해야 한다

a.isSubset(of: a) // 부분집합 여부 -> true
a.isStrictSubset(of: a) // 진부분집합 여부 -> false -> a의 원소는 모두 a에 속하지만 a == a이니까(진부분집합)

b.isSubset(of: a) // 부분집합 여부 -> true
b.isStrictSubset(of: a) // 진부분집합 여부 -> true -> b의 원소는 모두 a에 속하지만 b != a이니까(진부분집합)


// 상위집합여부 확인
a.isSuperset(of: a) // true
a.isStrictSuperset(of: a) // false

a.isSuperset(of: b) // true
a.isStrictSuperset(of: b) // true

a.isSuperset(of: c) // false
a.isStrictSuperset(of: c) // false

// 교집합여부 확인
a.isDisjoint(with: b) // false
a.isDisjoint(with: c) // false
b.isDisjoint(with: c) // true -> b는 홀수이고, c는 짝수이기 때문에 서로소집합이 성립된다


Combining Sets

a = [1, 2, 3, 4, 5, 6, 7, 8, 9]
b = [1, 3, 5, 7, 9]
c = [2, 4, 6, 8, 10]

// 합집합 만들기
var result = b.union(c) // {1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
result = b.union(a) // {1, 2, 3, 4, 5, 6, 7, 8, 9}

// 원본 직접 변경
b.formUnion(c) // {1, 2, 3, 4, 5, 6, 7, 8, 9, 10}

a = [1, 2, 3, 4, 5, 6, 7, 8, 9]
b = [1, 3, 5, 7, 9]
c = [2, 4, 6, 8, 10]

// 교집합
result = a.intersection(b) // {1, 3, 5, 7, 9}
result = c.intersection(b) // Set([])

a.formIntersection(b) // {1, 3, 5, 7, 9}
a // {1, 3, 5, 7, 9}

b.formIntersection(c) // Set([]) -> b는 빈 set이 되어버린다

a = [1, 2, 3, 4, 5, 6, 7, 8, 9]
b = [1, 3, 5, 7, 9]
c = [2, 4, 6, 8, 10]

// 여집합
result = a.symmetricDifference(b) // {2, 4, 6, 8}
result = c.symmetricDifference(b) // {1, 2, 3, 4, 5, 6, 7, 8, 9, 10}

a.formSymmetricDifference(b) // {2, 4, 6, 8}


a = [1, 2, 3, 4, 5, 6, 7, 8, 9]
b = [1, 3, 5, 7, 9]
c = [2, 4, 6, 8, 10]

// 차집합
result = a.subtracting(b) // {2, 4, 6, 8}
a.subtract(b) // {2, 4, 6, 8} -> b에 저장돼 있는 모든 홀수를 제거시킴

```


### 13-12. Set을 통한 집합 연산
```swift
import Foundation

var a: Set = [16, 8, 3, 13, 4, 2, 7, 14, 4, 17, 6, 7, 4, 26, 3, 19, 2, 15, 19, 25]
var b: Set = [11, 9, 20, 22, 30, 6, 14, 20, 20, 19, 7, 12, 2, 12, 19, 4, 13, 11, 24, 20]

// 여기에 합집합을 저장해 주세요.
let unionSet = a.union(b)

// 여기에 교집합을 저장해 주세요.
let intersectionSet = a.intersection(b)

// 여기에 차집합을 저장해 주세요.
let subtractingSet = a.subtracting(b)

print(unionSet.count, intersectionSet.count, subtractingSet.count)
```


### 13-13. Iterating Collections
- 컬렉션에 포함된 모든 요소를 대상으로 원하는 작업을 실행하는 방법
```swift
Iterating Collections

(1) for-in
for element in collection {
  statements
}

(1-1) Array 열거
let arr = [1, 2, 3]
for num in arr {
  print(num)
}
/* 
1
2
3
*/


(1-2) Set 열거
let set: Set = [1, 2, 3]
for num in set {
  print(num)
}
/*
2
3
1
*/ -> Set은 정렬되지 않은 상태임을 잊지 마라


(1-3) Dictionary 열거
let dict = ["A": 1, "B": 2, "C": 3]
for (key, value) in dict {
  print(key, value)
}
/* 
C 3
A 1
B 2
*/


(2) forEach

(2-1) Array
let arr = [1, 2, 3]
arr.forEach { (num) in
  print(num)
}
/* 
1
2
3
*/

(2-2) Set
let set: Set = [1, 2, 3]
set.forEach { (num) in
  print(num)
}
/* 
3
1
2
*/

(2-3) Dictionary
let dict = ["A": 1, "B": 2, "C": 3]
dict.forEach { (elem) in
  print(elem.key, elem.value)
}
/* 
A 1
B 2
C 3
*/

// for는 반복문이기 때문에 break나 continue를 사용할 수 있다
func withForIn() {
  print(#function)
  let arr = [1, 2, 3]
  for num in arr {
    print(num)
    return
  }
}

// forEach는 반복문이 아니기 때문에 break나 continue를 사용할 수 없다
func withForEach() {
  print(#function)
  let arr = [1, 2, 3]
  arr.ForEach { (num) in
    print(num)
    return
  }
}

withForIn()
/* 
withForIn()
1
*/ -> for문에서는 바로 return이 실행됨 -> 반복 횟수에 영향을 줌
withForEach()
/* 
1
2
3
*/ -> forEach문에서는 return이 실행되는 시점이 함수 종료 시점 -> 반복 횟수에 영향을 주지 않음
```


## Enumeration
- 동일한 이름에 속한 상수 그룹을 선언하고 다양하게 매칭시키는 방법

### 14-1. Enumeration Types
- 제한된 경우의 수를 표현하는 자료형
  - 열거형 선언 문법
  - 열거형 사용 이유 -> 코드의 가독성과 안정성(오타 가능성 감소)이 높아진다

```swift
enum TypeName {
  case caseName
  case caseName, caseName
}

enum Alignment {
  case left
  case right
  case center
}

Alignment.center // center

var textAlignment = Alignment.center
textAlignment = .left // 열거형 이름은 생략해도 되지만, 점(.)은 생략하면 안 된다

if textAlignment == .center {

}

switch textAlignment {
case .left:
  print("left")
case .right:
  print("right")
case .center:
  print("center")
}
// left
```



### 14-2. Raw Values(원시값)
- case에 값을 저장하고 읽는 방법
- 원시값이 필수는 아니다

```swift
Raw Values
enum TypeName: RawValueType {
  case caseName = Value
}

enum Alignment: Int {
  case left
  case right = 100
  case center
}

Alignment.left.rawValue // 0
Alignment.right.rawValue // 100
Alignment.center.rawValue // 101

Alignment.left.rawValue = 10 // Cannot assign to property: 'rawValue' is immutable 에러 발생

Alignment(rawValue: 0) // left
Alignment(rawValue: 200) // nil

enum Weekday: String {
  case sunday
  case monday = "MON"
  case tuesday
  case wednesday
  case thursday
  case friday
  case saturday
}

Weekday.sunday.rawValue // "sunday"
Weekday.monday.rawValue // "MON"


```


### 14-3. 열거형으로 Http Status Code 처리하기
```swift
import Foundation

// 여기에서 열거형을 선언해 주세요.
enum HttpStatusCode: String {
    case ok = "OK"
    case badReqeust = "Bad Request"
    case unauthorized = "Unauthorized"
    case notFound = "Not Found"
    case internalSeverError = "Internal Server Error"
    case badGateway = "Bad Gateway"
}

func solution(_ statusCode:Int) -> String {
   // 여기에서 인스턴스를 생성하고 메시지를 리턴해 주세요.
    switch statusCode {
        case 200:
            return HttpStatusCode.ok.rawValue
        case 400:
            return HttpStatusCode.badReqeust.rawValue
        case 401:
            return HttpStatusCode.unauthorized.rawValue
        case 404:
            return HttpStatusCode.notFound.rawValue
        case 500:
            return HttpStatusCode.internalSeverError.rawValue
        case 502:
            return HttpStatusCode.badGateway.rawValue
        default:
            return "Unknown Error"
    }
}
```

## Enumeration - 고급

### 14-4. Associated Values ***
- case에 연관 값을 저장하는 방법
```swift
enum TypeName {
  case caseName(Type)
  case caseName(Type, Type, ...)
}

enum VideoInterface {
  case dvi(width: Int, height: Int)
  case hdmi(Int, Int, Double, Bool)
  case displayPort(CGSize)
}

var input = VideoInterface.dvi(width: 2048, height: 1536)

switch input {
case .dvi(2048, 1536):
  print("dvi 2048 * 1536")
case .dvi(2048, _):
  print("dvi 2047 * Any)
case .dvi:
  print("dvi")
case .hdmi(let width, let height, let version, let audioEnabled):
  print("hdmi \(width) * \(height))
case let .displayPort(size):
  print("dp")
}

input = .hdmi(3840, 2160, 2.1, true)
```


### 14-5. Enumeration Case Pattern ***
- 조건문과 반복문에서 연관 값을 매칭시키는 방법
```swift
Enumeration Case
Pattern

case Enum.case(let name):
case Enum.case(var name):

case let Enum.case(name):
case var Enum.case(name):

enum Transporation {
  case bus(number: Int)
  case taxi(company: String, number: String)
  case subway(lineNumber: Int, express: Bool)
}

var tpt = Transportation.bus(number: 7) // bus(number: 7)

switch tpt {
case .bus(let n):
  print(n)
case .taxi(let c, var n):
  print(c, n)
case let .subway(l, e):
  print(l, e)
}

tpt = Transportation.subway(lineNumber: 2, express: false)

// 2호선(line)인지 먼저 확인하고, 그 다음 급행 여부(express) 확인
if case let .subway(2, express) = tpt {
  if express {
  
  } else {
  
  }
}

if case .subway(_, true) = tpt {
  print("express")
}

let list = [
  Transportation.subway(lineNumber: 2, express: false),
  Transportation.bus(number: 4412),
  Transportation.subway(lineNumber: 7, express: true),
  Transportation.taxi(company: "SeoulTaxi", number: "1234")
]

for case let .subway(n, _) in list {
  print("subway \(n)")
}
/* 
subway 2
subway 7
*/

for case let .subway(n, true) in list {
  print("subway \(n)")
}
// subway 7

for case let .subway(n, true) in list where n == 2 {
  print("subway \(n)")
}
// 아무것도 출력되지 않음 -> 2호선이면서 급행인 건 없으니까
```



## Structure and Class
- 새로운 형식을 직접 구현하는 방법

### 15-1. Structures and Classes
- 구조체와 클래스에 대한 기초적인 내용과 구현 문법
  - 프로그래밍 패러다임
    - Object-Oriented Programming
      - 애플이 제공하는 프레임워크는 객체지향으로 구성되어 있다
      - 따라서 보통 iOS 개발을 시작할 때 객체지향으로 개발하게 되는 경우가 많다
      - 객체지향에 대한 이해를 기초로 깔고 그 위에 다른 패러다임을 얹는 게 좋다
    - Protocol-Oriented Programming
    - Functional Programming

  - 객체와 추상화
  - 클래스 선언 문법
  - 구조체 선언 문법
  - 인스턴스 생성
  - 클래스와 구조체 비교

- 이름만으로 호출할 수 있으면 함수이고, 인스턴스를 통해서 호출할 수 있으면 메소드이다.
- 구조체는 메모리 공간으로 스택을 사용하고, 스택에 값을 저장한다. 그리고 값을 전달할 때마다 복사본을 생성한다. -> 값 형식(열거형)
- 클래스는 메모리 공간으로 힙을 사용하고, 힙에 값을 저장한다. 스택에는 힙에 저장되어 있는 값의 주소를 저장한다. 값을 전달하면 복사본은 생성하지 않고, 주소만 전달한다. -> 참조 형식(클래스, 클로저)
- 소멸자(deinitializer)와 상속(Inheritance)은 클래스에서만 지원한다.
- 메모리 관리 방식에도 차이가 있다
  - 값 형식에서는 인스턴스가 속한 스코프가 종료되면 메모리에서 자동으로 제거된다
  - 참조 형식에서는 스코프에 관계 없이 레퍼러스 카운팅을 통해 메모리를 관리한다



### 15-2. Initializer Syntax
- 가장 기본적인 형태의 생성자를 구현하고 호출하는 방법
  - 생성자 구현
  - 생성자 호출

```swift
Initializer Syntax
init(parameters) {
  statements
}
*** 중요 ***
- 생성자는 속성 초기화가 가장 중요하고 유일한 목적이다
- 생성자 실행이 종료되는 시점에는 모든 속성의 초기값이 저장되어 있어야 한다

class Position {
  var x: Double
  var y: Double
  
  init() {
    x = 0.0
    y = 0.0
  }
  
  init(value: Double) {
    x = value
    y = value
  }
}

let a = Position() // 인스턴스가 생성됨
a.x // 0
a.y // 0

let b = Position(vlaue: 100)
b.x // 100
b.y // 100

```


### 15-3. 구조체를 선언하고 인스턴스 생성하기
```swift

파라미터로 r, g, b 세 값이 전달됩니다.
컬러를 저장하는 새로운 구조체를 선언하고 전달된 값으로 인스턴스를 생성해 주세요.
생성된 인스턴스 속성으로 아래와 같은 문자열을 구성해서 리턴해 주세요.

R:95 G:199 B:205

import Foundation

// 여기에서 새로운 Color 구조체를 선언해 주세요.
struct Color {
    var r:Int
    var g:Int
    var b:Int
    
    var rgb: String

    init(r: String, g: String, b: String) {
        self.r = Int(r) ?? 0
        self.g = Int(g) ?? 0
        self.b = Int(b) ?? 0
        
        self.rgb = "R:\(self.r) G:\(self.g) B:\(self.b)"
    }
}

func solution(_ r:Int, _ g:Int, _ b:Int) -> String {
    // 여기에서 새로운 인스턴스를 생성해 주세요.
    let color = Color(r: String(r), g: String(g), b: String(b))
    // 여기에서 문자열을 리턴해 주세요.
    return color.rgb
}
```



### 15-4. 클래스를 선언하고 인스턴스 생성하기
```swift

파라미터로 r, g, b 세 값이 전달됩니다.
컬러를 저장하는 새로운 클래스를 선언하고 전달된 값으로 인스턴스를 생성해 주세요.
생성된 인스턴스 속성으로 아래와 같은 문자열을 구성해서 리턴해 주세요.

R:95 G:199 B:205
import Foundation

// 여기에서 새로운 Color 클래스를 선언해 주세요.
class Color {
    var r: Int
    var g: Int
    var b: Int
    
    var rgb: String
    
    init(r: Int, g: Int, b: Int) {
        self.r = r
        self.g = g
        self.b = b
        
        self.rgb = "R:\(self.r) G:\(self.g) B:\(self.b)"
    }
}


func solution(_ r:Int, _ g:Int, _ b:Int) -> String {
    // 여기에서 새로운 인스턴스를 생성해 주세요.
    let color = Color(r: r, g: g, b: b)
   
    // 여기에서 문자열을 리턴해 주세요.
    return color.rgb
}
```



### 15-5. Value Types vs Reference Types
- 값 형식과 참조 형식의 차이점
  - 값 형식의 메모리 처리 방식
  - 참조 형식의 메모리 처리 방식
  - 일반적인 구현 지침

- Value Types and Reference Types
  - Value Type
    - Structure(Int나 String, Swift Collection 등등 포함)
    - Enumeration
    - Tuple
  - Reference Type
    - Class
    - Closure

```swift
struct PositionValue {
  var x = 0.0
  var y = 0.0
}

class PositionObject {
  var x = 0.0
  var y = 0.0
}

// 선언과 동시에 기본값을 저장하면 파라미터가 없는 생성자가 자동으로 제공되는데, 이를 기본 생성자(Default Initializer)라고 한다
var v = PositionValue() // x0 y0
var o = PositionObject() // x0 y0

var v2 = v // x0 y0
var o2 = o // x0 y0

v2.x = 12
v2.y = 34

v // x0 y0 -> 복사본이기 때문에 v에는 변화가 없다
v2 // x12 y34

o2.x = 12
o2.y = 34

o // x12 y34 -> 클래스는 새로운 복사본을 생성하지 않고, 참조를 전달(인스턴스가 저장되어 있는 메모리 주소)하기 때문에(원본을 전달) 어떤 변수를 통해 속성을 바꾸더라도 항상 같은 속성을 변경하게 된다
o2 // x12 y34
```

- 값 형식과 참조 형식 중 어떤 것을 선택할지는 본인 선택이지만, 객체 지향 프로그래밍에서는 대부분 참조 형식인 클래스로 구현한다.
- 상대적으로 적은 데이터를 필요로 하고 상속이 필요 없다면 값 형식을 생성한다
- 값이 전달되는 시점마다 복사본이 생성되어야 하는 경우에도 값 형식을 사용한다
- 연관된 상수 그룹을 표현할 때는 열거형으로 구현하고, 코드 내에서 한 번만 사용되는 형식은 튜플로 구현한다.
- 나머지 값형식은 모두 구조체로 구현한다
- 함수형 프로그래밍과 프로토콜 지향 프로그래밍에서는 주로 구조체로 구현한다
- 상속을 구현하거나, 참조를 전달해야 하는 경우에만 클래스로 구현한다




## Structure and Class - 고급

### 15-6. Identity Operator ***
- 항등 연산자를 통해 참조를 비교하는 방법
  - 동일성 비교
  - Identical To Operator
  - Not Identical To Operator
  - Identical과 Equal의 차이

- 값 형식과 참조 형식은 동일성을 비교하는 데 차이가 있다
  - 값 형식
    - 값 형식이 저장되는 메모리 공간은 스택이다
    - 하나의 공간에 저장되기 때문에, 값을 비교를 위해서는 비교연산자 하나로 충분하다


  - 참조 형식
    - 참조형식은 값을 힙에 저장하고, 메모리 주소를 스택에 저장한다
    - 두 개의 공간에 저장되기 때문에, 비교하는 방법도 두 가지가 필요하다
    - 값을 비교할 때는 비교 연산자를 사용하고, 메모리 주소를 비교할 때는 항등 연산자를 사용한다

```swift
Identity Operator

class A {

}

let a = A()
let b = a
let c = A()

a === b // true -> 동일한 주소
a !== b // false

a !== c // true -> 서로 다른 주소

같은 메모리 주소를 갖고 있으면 Identical 하다고 하고, 
같은 값을 갖고 있으면 Equal 하다고 한다.
```


### 15-7. Nested Types(포함된 형식, 내포된 형식 -> 형식 내부에 선언된 형식)
- 하나의 형식 내부에 다른 형식을 선언하고 새로운 인스턴스를 생성하는 방법
  - Nested Type 선언 문법
  - Nested Type 표기법

```swift
class One {
  struct Two {
    enum Three {
      case a
      
      class Four {
      
      }
    }
  }
  
  var a = Two()
}

// let two: Two = Two() // Use of undeclared type 'Two' 에러 발생
let two: One.Two = One.Two() // Use of undeclared type 'Two' 에러 발생
```
- Nested Type의 가장 큰 장점은 가독성이다




## Property
- 형식 내부에 값을 저장하고 처리하는 방법

### 16-1. Stored Property
- 저장 속성과 지연 저장 속성
  - 변수 저장 속성
  - 상수 저장 속성
  - 지연 저장 속성
  - 구조체의 가변성과 속성의 관계
  - 지연 저장 속성
  - 속성 초기화 패턴

- 저장속성은 클래스와 구조체에서 선언할 수 있다
- 저장속성은 인스턴스에 속한 속성이다
- 그래서 인스턴스가 새로 생성될 때마다 새로운 메모리 공간이 생성된다
- 속성에 저장되는 값은 인스턴스마다 달라진다

```swift
Explicit Member Expression(명시적 멤버 표현식) -> Dot Syntax(점 문법)
class Person {
  let name = "John Doe"
  var age = 33
}
let p = Person()
p.name // "John Doe"
p.age // 33

p.age = 30
p.name = "New Name" // Cannot assign to property: 'name' is a 'let' constant 에러 발생

struct Person {
  let name = "John Doe"
  var age = 33
}

let p = Person()
p.age = 30 // Cannot assign to property: 'p' is a 'let' constant 문제 발생 -> 구조체 인스턴스 p가 let 타입으로 선언되어 있으니까

var p = Person()
p.age = 30 // 문제 없음



Lazy Stored Property(지연 저장 속성)

- 저장 속성이 초기화 되는 시점: 인스턴스 초기화 시점과 동일
- 지연 저장 속성은 초기화를 지연시킨다 -> 인스턴스가 초기화 되는 시점이 아니라, 속성에 처음 접근하는 시점에 초기화 된다
- 항상 변수 저장 속성(lazy var)으로 선언한다
- 생성자에서 초기화하지 않기 때문에, 선언 시점에 기본값을 저장해야 한다

struct Image {
  init() {
    print("new image")
  }
}

struct BlogPost {
  let title: String = "Title"
  let content: String = "Content"
  let attachment: Image = Image()
}

let post = BlogPost() // 이 때 바로 "new Image"가 출력됨

struct BlogPost {
  let title: String = "Title"
  let content: String = "Content"
  lazy var attachment: Image = Image()
  
  let date: Date = Date()
  
  lazy var formattedDate: String = {
    let f = DateFormatter()
    f.dateStyle = .long
    f.timeStyle = .medium
    return f.string(from: date)
  }() // 괄호를 붙여주면 클로저가 초기화 시점에 호출된다
}

var post = BlogPost()
post.attachment // 이 때가 돼야 "new Image"가 출력됨
```


### 16-2. 새로운 저장 속성 추가하기
```swift
import Foundation

class Color {
   let red: Int
   let green: Int
   let blue: Int
   
var alpha: Double = 1.0


   init(red: Int, green: Int, blue: Int) {
      self.red = red
      self.green = green
      self.blue = blue
   }
}

let c = Color(red: 255, green: 0, blue: 0)
if c.alpha == 1.0 {
   c.alpha = 0.5
}

print("OK")

```

### 16-3. Computed Property(계산된 속성, 계산 속성)
- 다른 속성을 기반으로 동작하는 계산 속성
  - get 블록과 set 블록
  - 읽기 전용 계산 속성

- Computed의 의미는 '다른 속성을 기반으로 속성값이 결정된다'는 의미
- 계산 속성은 메모리 공간을 가지지 않는다.
- 다만 다른 속성의 값을 읽어 계산해서 리턴하거나 저장한다
- 속성에 접근할 때마다 다른 값이 리턴할 수 있으므로, 항상 let이 아닌 var로 선언해야 한다
- 계산 속성은 클래스 뿐만 아니라, 열거형에도 추가할 수 있다.

```swift
Computed Properties

var name: Type {

  // get block, getter
  get {
    statements
    return expr
  }
  
  // set block, setter
  set(name) {
    statements
  }
}

class Person {
  var name: String
  var yearOfBirth: Int
  
  init(name: String, yaer: Int) {
    self.name = name 
    self.yearOfBirth = year
  }
  
  var age: Int {
    get {
      let calendar = Calendar.current
      let now = Date()
      let year = calendar.component(.year, from: now)
      return year - yearOfBirth
    }
    
    set {
      let calendar = Calendar.current
      let now = Date()
      let year = calendar.component(.year, from: now)
      yearOfBirth = year - newValue
    }
  }
}

let p = Person(name: "John Doe", year: 2002)
p.age
p.age = 50 // set block 실행
p.yearOfBirth // 1969

Read-only Computed Properties(읽기 전용 계산 속성)

var name: Type {
  get {
    statements
    return expr
  }
}

var name: Type {
  statements
  return expr
}
```
- 읽기 전용 계산 속성은 있지만 쓰기 전용 계산 속성은 없다




### 16-4. 새로운 계산 속성 추가하기
```swift
문제 설명
코드가 정상적으로 동작하도록 계산 속성을 추가해 주세요.
계산 속성에서는 현재 색상의 보색을 리턴해 주세요.

참고
보색 계산 공식 255 - currentValue

import Foundation

class Color {
   let red: Int
   let green: Int
   let blue: Int
   
   init(red: Int, green: Int, blue: Int) {
      self.red = red
      self.green = green
      self.blue = blue
   }
   
   // 여기에 계산 속성을 추가해 주세요.
    var complementary: Color {
        get {
            return Color(red: (255 - self.red), green: (255 - self.green), blue: (255 - self.blue))
        }
    }
}

let color = Color(red: 95, green: 199, blue: 205)
let complementaryColor = color.complementary

print(complementaryColor.red, complementaryColor.green, complementaryColor.blue)
```



### 16-5. Property Observer(속성 감시자)
- 속성 감시자를 통해 속성 값이 변경될 때 실행할 코드를 구현하는 방법
  - willSet 블록과 didSet 블록
  - 문법적 제약

```swift
var name: Type = DefaultValue {
  willSet(name) {
    statements
  }
  didSet(name) {
    statements
  }
}

class Size {
  var width = 0.0 {
    willSet {
      print(width, "=>", newValue)
    }
    didSet {
      print(oldValue, "=>", width)
    }
  }
}

let s = Size()
s.width = 123
/* 
0.0 => 123.0
0.0 => 123.0
*/
```




### 16-6. Type Property(형식 속성)
- 형식과 관련된 메소드를 선언하고 접근하는 방법
  - 저장 형식 속성
  - 계산 형식 속성
  - 속성 초기화 시점

```swift
class Math {
  static let pi = 3.14
}

let m = Math()
// m.pi -> 이렇게 쓰면 안 됨
Math.pi // 3.14 -> 형식 속성은 이런 식으로 호출해야 함

enum Weekday: Int {
  case sunday = 1, monday, tuesday, wednesday, thursday, friday, saturday
  
  static var today: Weekday {
    let cal = Calendar.current
    let today = Date()
    let weekday = cal.component(.weekday, from: today)
    
    return Weekday(rawValue: weekday)!
  }
}

Weekday.today // friday

```


### 16-7. 새로운 형식 속성 선언하기
```swift
import Foundation

class Color {
   let red: Int
   let green: Int
   let blue: Int
   
   init(red: Int, green: Int, blue: Int) {
      self.red = red
      self.green = green
      self.blue = blue
   }
   
   // 여기에서 형식 속성을 추가해 주세요.
    static var white: Color {
        Color(red: 255, green: 255, blue: 255)
    }
    
    static var black: Color {
        Color(red: 0, green: 0, blue: 0)
    }
}


let white = Color.white
let black = Color.black

print(white.red == 255 && white.green == 255 && white.blue == 255 && black.red == 0 && black.green == 0 && black.blue == 0)
```



### 16-8. self & super
- 자동으로 제공되는 특별한 속성인 self와 super
  - self expression
  - super expression

- self는 인스턴스에 자동으로 추가된다

```swift
class Size {
  var width = 0.0
  var height = 0.0
  
  func calcArea() -> Double {
    // return self.width * self.height
    return width * height
  }
  
  var area: Double {
    // return self.calcArea()
    return calcArea()
  }
  
  func update(width: Double, height: Double) {
    // 이 경우에는 속성과 파라미터를 구분하기 위해 반드시 self를 붙여줘야 한다
    self.width = width
    self.height = height
  }
  
  func doSomething() {
    // let c = { width * height } -> 이렇게 하면 안 된다.
    let c = { self.width * self.height }
  }
  
  static let unit = ""
  
  // 형식 메소드
  static func doSomething() {
    // self.width // 형식 메소드에서 인스턴스에 직접 접근하는 것은 불가능
    self.unit // unit의 경우에는 역시 타입 멤버(static)이므로 사용 가능함
    unit // 앞에 self 안 붙이고도 사용 가능
  }
}

struct Size {
  var width = 0.0
  var height = 0.0
  
  mutating func reset(value: Double) {
    // width = value
    // height = value
    self = Size(width: value, height: value)
  }
}
```

- super 속성은 상속과 관련 있기 때문에, 클래스에서만 사용된다


## Method and Subscript
- 형식과 연관된 코드 블록을 구현하는 방법과 서브스크립트 문법과 함께 사용할 수 있도록 구현하는 방법

### 17-1. Instance Method
- 인스턴스와 연관된 메소드를 구현하고 호출하는 방법
  - 인스턴스 메소드 선언 문법
  - 인스턴스 메소드 호출 문법
  - 값 형식의 인스턴스 메소드 구현 방식

- 메소드는 특정 형식에 속하는 함수를 의미함

```swift
Instance Method

func name(parameters) -> ReturnType {
  code
}

instance.method(parameters)

class Sample {
  var data = 0
  static var sharedData = 123
  
  func doSomething() {
    print(data)
    Sample.sharedData // static으로 선언된 Type Member이므로
  }
  
  func call() {
    doSomething()
  }
}

let a = Sample()
a.data
a.doSomething()
a.call()

class Size {
  var width = 0.0
  var height = 0.0
  
  func enlarge() {
    width += 1.0
    height += 1.0
  }
}

let s = Size()
s.enlarge()


struct Size {
  var width = 0.0
  var height = 0.0
  
  mutating func enlarge() {
    width += 1.0
    height += 1.0
  }
}

var s = Size() // 인스턴스를 let으로 선언되면 안 된다 -> 값 복사니까
s.enlarge()
```


### 17-2. 새로운 인스턴스 메소드 추가하기
```swift
문제 설명
코드가 정상적으로 실행되도록 인스턴스 메소드를 추가해 주세요.
일부 초기 코드는 수정이 필요할 수 있습니다.

제한
extend(by:) 메소드는 width, height 속성에 파라미터로 전달된 값을 곱한 새로운 인스턴스를 리턴해야 합니다.
reset() 메소드는 모든 속성을 0으로 초기화 해야 합니다.

import Foundation

struct Area {
   var x: Int
   var y: Int
   var width: Int
   var height: Int
   
   // 여기에서 인스턴스 메소드를 추가해 주세요.
    mutating func extend(by: Int) -> Area {
        return Area(x: 0, y: 0, width: self.width * by, height: self.height * by)
    }
    
    mutating func reset() {
        self.x = 0
        self.y = 0
        self.width = 0
        self.height = 0
    }
}

// 아래 코드는 let 또는 var 키워드만 수정할 수 있습니다.
var a = Area(x: 0, y: 0, width: 100, height: 100)
let b = a.extend(by: 3)
a.reset() 

// 아래 코드는 수정하지 마세요.
let isExtended = b.width == 300 && b.height == 300
let isZeroArea = a.x == 0 && a.y == 0 && a.width == 0 && a.height == 0

print(isExtended && isZeroArea)

```



### 17-3. Type Method
- 형식과 연관된 메소드를 구현하고 호출하는 방법
  - 타입 메소드 선언 문법
  - 타입 메소드 호출 문법
  - 메소드 오버라이딩

```swift
Type Methods

static func name(parameters) -> ReturnType {
  statements
}

class func name(parameters) -> ReturnType {
  statements
}

Type.method(parameters)


class Circle {
  static let pi = 3.14
  var radius = 0.0
  
  func getArea() -> Double {
    return radius * radius * Circle.pi
  }
  
  static func printPi() {
    print(pi)
  }
  
  class func printPi2() {
    print(pi)
  }
}

Circle.printPi() // 3.14

class StrokeCircle: Circle {
//  override static func printPi() { // Cannot override static method 오류 발생: 수퍼 클래스에서 static 키워드로 선언한 메소드는 서브클래스에서 오버라이드 할 수 없다!
//    print(pi)
//  }

    override static func printPi2() { // class 메소드는 서브클래스에서 static 오버라이드 가능
      print(pi)
    }
}
```



### 17-4. 형식 메소드 구현하기
```swift
문제 설명
코드가 정상적으로 실행되도록 새로운 자료형을 선언하고 형식 메소드를 구현해 주세요.

제한
string(from:) 메소드는 정수를 문자열로 변환합니다.
integer(from:) 메소드는 문자열을 정수로 변환합니다.
형식 메소드는 오버라이딩이 가능하도록 선언해야 합니다.

import Foundation

// 여기에서 새로운 자료형을 선언하고 형식 메소드를 구현해 주세요.
class StringConverter {
    static func string(from: Int) -> String {
        return String(from)
    }
    
    static func integer(from: String) -> Int? {
        return Int(from)
    }
}

// 아래에 있는 코드는 수정하지 마세요.
let a = 123
let b = "456"

let str = StringConverter.string(from: a)
if let num = StringConverter.integer(from: b) {
   print(str == "123" && num == 456)
} else {
   print(false)
}
```



### 17-5. Subscript
- 서브스크립트를 직접 구현하는 방법
  - 서브스크립트 호출 문법
  - 서브스크립트 선언 문법

```swift
Subscripts
  instance[index]
  instance[key]
  instance[range]
  
let list = ["A", "B", "C"]
list[0] // "A" -> 스퀘어브라켓을 통해 index를 넣어 값을 추출하는 것이 바로 서브스크립트다


서브스크립트 문법 -> 메소드와 달리 리턴형을 생략할 수 없다
subscript(parameters) -> ReturnType {
  get {
    return expression
  }
  set(name) {
    statements
  }
}

class List {
  var data = [1, 2, 3]
  
  subscript(index: Int) -> Int {
    get {
      return data[index]
    }
    set {
      data[index] = newValue
    }
  }
}

var l = List()
l[0] // 1
l[1] = 123


struct Matrix {
  var data = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
  
  subscript(row: Int, col: Int) -> Int {
    return data[row][col]
  }
}

let m = Matrix()
// m[0][0] // -> 이렇게 쓰면 작동 안 됨
m[0, 0]
```



### 17-6. 서브스크립트 구현하기
```swift
문제 설명
Player 구조체는 선수의 이름과 번호를 저장합니다.
Team 구조체는 팀 이름과 선수 목록을 저장합니다.
선수 번호와 이름으로 선수를 검색할 수 있도록 서브스크립트를 추가해 주세요.

문법 설명
서브스크립트 선언 문법 ``` subscript(파라미터_목록) -> 리턴형 { get { return 표현식 } set(상수) {
}
}

import Foundation

struct Player {
   let number: Int
   let name: String
}

struct Team {
   let name: String
   let squad: [Player]
   
   // 여기에서 서브스크립트를 구현해 주세요.
    subscript(num: Int) -> Player? {
        for i in 0..<squad.count {
            if squad[i].number == num {
                return squad[i]
            }
        }
        return nil
    }
        
    subscript(name: String) -> Player? {
        for i in 0..<squad.count {
            if squad[i].name == name {
                return squad[i]
            }
        }
        return nil
    }
}

// 아래에 있는 코드는 수정하지 마세요.
let firstTeam = [
   Player(number: 1, name: "Hugo Lloris"),
   Player(number: 3, name: "Danny Rose"),
   Player(number: 4, name: "Toby Alderweireld"),
   Player(number: 5, name: "Jan Vertonghen"),
   Player(number: 7, name: "Heung-Min Son"),
   Player(number: 10, name: "Harry Kane"),
   Player(number: 12, name: "Victor Wanyama"),
   Player(number: 20, name: "Dele Alli"),
   Player(number: 23, name: "Christian Eriksen"),
   Player(number: 33, name: "Ben Davies")
]
let tot = Team(name: "Tottenham Hotspur", squad: firstTeam)

var name: String?
var number: Int?

if let player = tot[7] {
   name = player.name
}

if let player = tot["David de Gea"] {
   number = player.number
}
print(name == .some("Heung-Min Son") && number == nil)

```



## Inheritance and Polymorphism
- 상속을 통해 코드 중복을 줄이는 방법과 OOP의 특징 중 하나인 다형성에 대한 공부

### 18-1. Inheritance
- 클래스에서 상속을 통해 Super Class로부터 멤버를 상속하는 방법
  - 클래스 계층
  - Base Class, Super Class, Subclass
  - 클래스 상속 문법
  - Final Class

- 스위프트에서는 다중 상속(Multiple Inheritance)이 불가능하다
- 다중상속과 유사한 기능을 구현하고 싶다면 프로토콜을 사용하면 된다

```swift
class Figure {
  var name = "Unknown"
  
  init(name: String) {
    self.name = name
  }
  
  func draw() {
    print("draw \(name)")
  }
}

class Circle: Figure {
  var radius = 0.0
}

let c = Circle(name: "Circle")
c.radius
c.name
c.draw() // draw Circle

final class Rectangle: Figure { // final 키워드를 붙이면 더 이상 상속할 수 없다
  var width = 0.0
  var height = 0.0
}

// class Square: Rectangle {
// }
```



### 18-2. Overriding(재정의)
- Super Class로부터 상속한 멤버를 재정의하는 방법
  - 오버라이딩 구현 패턴
  - 메소드 오버라이딩
  - 속성 오버라이딩
  - 멤버 오버라이딩 금지 문법

```swift
class Figure {
  var name = "Unknown"
  
  init(name: String) {
    self.name = name
  }
  
  func draw() {
    print("draw \(name)")
  }
}

class Circle: Figure {
  var radius = 0.0
  
  var diameter: Double {
    return radius * 2
  }
  
  override func draw() {
    super.draw()
    print("Override Circle")
  }
}

let c = Circle(name: "Circle")
c.draw() 
/* 
draw Circle 
Circle
*/

class Oval: Circle {
  // 속성을 오버라이드 할 때는 반드시 슈퍼클래스의 속성을 따라가야(읽기, 쓰기 상태) 한다
  override var diameter: Double {
    get {
      return super.diameter
    }
    set {
      super.radius = newValue / 2
    }
  }
}

- final 키워드를 앞에 붙이면 상속받은 클래스에서 오버라이드가 불가능하다
```

### 18-3. 클래스 계층 구현하기
### 18-4. Upcasting and Downcasting
- 인스턴스를 동일한 클래스 계층에 존재하는 다른 클래스 형식으로 처리하는 방법
  - 업캐스팅
  - 다운캐스팅

```swift
class Figure {
  let name: String
  
  init(name: String) {
    self.name = name
  }
  
  func draw() {
    print("draw \(name)")
  }
}

class Rectangle: Figure {
  var width = 0.0
  var height = 0.0
  
  override func draw() {
    super.draw()
    print("rectangle \(width) * \(height)")
  }
}

class Square: Rectangle {

}

let f = Figure(name: "Unknown")
f.name // "Unknown"

let r = Rectangle(name: "Rect")
r.width // 0
r.height // 0
r.name // "Rect"

let s = Squre(name: "Square")
s.width // 0
s.height // 0
s.name // "Square"

// Upcasting: 서브클래스 인스턴스를 슈퍼클래스 형식으로 저장
let s: Figure = Squre(name: "Square")
// s.width
// s.height
// s.name

// 업캐스팅은 항상 성공한다(안전하다)

let downcastedS = s as! Square // 다운캐스팅 -> 상대적으로 위험(크래시 발생 가능)
downcastedS.name // Square
downcasetdS.width // 0
downcastedS.height // 0

class Rhombus: Square {
  var angle = 45.0
}

let dr = s as! Rhombus // 에러 발생 -> 인스턴스의 원래 형식인 Square보다 아래쪽에 있기 때문에
```



### 18-5. Type Casting
- Type Casting을 통해 인스턴스의 형식을 확인하고 다른 형식으로 캐스팅하는 방법
  - Type Check Operator
  - Type Casting Operator
  - 다형성

```swift
Type Check Operator

let num = 123

num is Int // true
num is Double // false
num is String // false

let t = Triangle(name: "Triangle")
let r = Rectangle(name: "Rect")
let s = Square(name: "Square")
let c = Circle(name: "Circle")

r is Rectangle // true
r is Figure // true
r is Squre // false


Type Casting Operator

(1) Compile Time Case
- expression as Type

(2) Runtime Cast
- expression as? Type -> Conditional Cast
- expression as! Type -> Forced Cast

let nsstr = "str" as NSString

//"str" as Int -> 에러 발생

t as? Triangle
t as! Triangle

var upcasted: Figure = s
upcasted = s as Figure

upcasted as? Square
upcasted as! Square
upcasted as? Rectangle
upcasted as! Rectangle

upcasted as? Circle // nil
// upcasted as! Circle // 크래시 발생 -> forced casting은 되도록 사용하지 않는 것이 좋다

if let c = upcasted as? Circle {

}

let list = [t, r, s, c] // 배열에 서로 다른 형식을 넣었는데 문제가 없다 -> 가장 인접한 슈퍼 클래스 형식(Figure)으로 업캐스팅 되었기에 가능함

for item in list {
  item.draw()
}
/* 
Rectangle 0.0 * 0.0
draw Square
Rectangle 0.0 * 0.0
draw Circle
Circle
*/ -> 형식은 슈퍼클래스인 Figure로 됐지만, 막상 출력할 때는 자식 클래스에 있는 내용들이 출력 됨 -> 다형성(Polymorphism)

for item in list {
  if let c = item as? Circle {
    c.radius
  }
}
```



### 18-6. Any and AnyObject
- Swift가 제공하는 범용 자료형
  - Any와 AnyObject
  - Type-Erasing Wrapper
  - 타입 캐스팅 패턴 활용

```swift
Any, AnyObject
Any는 모든 형식을 저장할 수 있고, AnyObject는 모든 클래스 형식을 저장할 수 있다

var data: Any = 1
data = 2.3 // Any로 선언하면 형식에 관계없이 모두 저장 가능
data = "str"
data = [1, 2, 3]
data = NSString()

var obj: AnyObject = NSString()
// obj = 1 // 에러 발생

if let str = data as? String {
  print(str.count)
} else if let list = data as? [Int] {
  
}

Type Casting Pattern

switch data {
case let str as String:
  print(str.count)
case let list as [Int]:
  print(list.count)
case is Double:
  print("Double Value")
default:
  break
}
```
  
  
  
### 18-7. Any 배열에 저장되어 있는 값 분류하기
```swift
list 배열에 저장되어 있는 값을 형식에 맞는 배열에 추가해 주세요.

import Foundation

let list: [Any] = [1, "2", 3.5, "Hello", -123]

var intList = [Int]()
var doubleList = [Double]()
var strList = [String]()

// 여기에서 구현해 주세요.
for i in 0..<list.count {
    if let intValue = list[i] as? Int {
        intList.append(intValue)
    } else if let doubleValue = list[i] as? Double {
        doubleList.append(doubleValue)
    } else if let strValue = list[i] as? String {
        strList.append(strValue)
    }
}

print(intList.count, doubleList.count, strList.count)
```



### 18-8. Overloading
- 오버로딩을 통해 동일한 이름을 가진 멤버를 구현하는 방법
  - 함수 오버로딩
  - 메소드 오버로딩
  - 네 가지 오버로딩 규칙

```swift

func process(value: Int) {
  print("process Int")
}

func process(value: String) {
  print("process String")
}

func process(value: String, anotherValue: String) {
  
}

func process(_ value: String) {

}

func process(value: Double) -> Int {
  return Int(value)
}

func process(value: Double) -> String? {
  return String(value)
}

let result = process(value: 12.34) as Int


process(value: 0) // process Int
process(value: "str") // process String
process("str")

struct Rectangle {
  func area() -> Double {
    return 0.0
  }
  
  static func area() -> Double {
    return 0.0
  }
}

let r = Rectangle()
r.area()
Rectangle.area()

Overloading 
Rule #1
- 함수 이름이 동일하면 파라미터 수로 식별
Rule #2
- 함수 이름, 파라미터가 수가 동일하면 파라미터 자료형으로 식별
Rule #3
- 함수 이름, 파라미터 수, 파라미터 자료형이 동일하면 Argument Label로 식별
Rule #4
- 함수 이름, 파라미터 수, 파라미터 자료형, Argument Label이 동일하면 리턴형으로 식별
```



## Initializer and Deinitializer
- 인스턴스의 생성과 해제를 담당하는 코드를 구현하는 방법

### 19-1. Initializers(생성자)
- 생성자와 인스턴스 초기화
  - 인스턴스 초기화
  - Default Initializer
  - Memberwise Initializer -> memberwise는 '회원'이라는 의미

```swift
Initialization
Default Initializer

class Position {
  var x = 0.0
  var y = 0.0
  var z: Double? = nil
  
}

let p = Position() // 이렇게 하면 Default Initializer가 호출된다


Initializer Syntax

init(parameters) {
  initialization
}

TypeName(parameters)

class SizeObj {
  var width = 0.0
  var height = 0.0
  
  init(width: Double, height: Double) {
    self.width = width
    self.height = height
  }
  
  // Convenience Initializer
  convenience init(value: Double) {
    // width = value
    // height = value
    self.init(width: value, height: value) // 이런 식으로 다른 이니셜라이저를 사용하는 것을 Initializer Delegation 이라고 한다
  }
}


Memberwise Initializer

struct SizeValue {
  var width = 0.0
  var height = 0.0
}

let s = SizeValue()
SizeValue(width: 1.2, height: 3.4)
```


### 19-2. Class Initializers
- 클래스에서 구현하는 특별한 생성자
  - Designated Initializer
  - Convenience Initializer
  - Automatic Initializer Inheritance


- 클래스에서 구현하는 이니셜라이저는 Designated Initializer와 Convenience Initializer로 구분된다
```swift
Designated Initializer(지정 생성자)

init(parameters) {
  initialization
}



Convenience Initializer(간편 생성자)

convenience init(parameters) {
  initialization
}



class Position {
  var x: Double
  var y: Double
  
  init(x: Double, y: Double) {
    self.x = x
    self.y = y
  }
  
  convenience init(x: Double) {
    self.init(x: x, y: 0.0)
  }
}

Initializer Inheritance

class Figure {
  var name: String
  
  init(name: String) {
    self.name = name
  }
  
  func draw() {
    print("draw \(name)")
  }
  
  convenience init() {
    self.init(name: "unknown")
  }
}

class Rectangle: Figure {
  var width: Double = 0.0
  var height: Double = 0.0
  
  init(name: String, width: Double, height: Double) {
    self.width = width
    self.height = height
    // 현재 클래스의 속성을 초기화 한 후 상위 구현을 호출한다
    super.init(name: name)
  }
  
  override init(name: String) {
    width = 0
    height = 0
    super.init(name: name)
  }
  
  convenience init() {
    self.init(name: "unknown")
  }
}
```


### 19-3. Required Initializer(필수 생성자)
- 모든 서브클래스에서 구현해야 하는 필수 생성자
```swift
Required Initializer

required init(parameters) {
  initialization
}

class Figure {
  var name: String
  
  required init(name: String) {
    self.name = name
  }
  
  func draw() {
    print("draw \(name)")
  }
}

class Rectangle: Figure {
  var width = 0.0
  var height = 0.0
  
  init() {
    width = 0.0
    height = 0.0
    super.init(name: "unknown")
  }
  
  required init(name: String) {
    width = 0.0
    height = 0.0
    super.init(name: name)
  }
}
```



### 19-4. Initializer Delegation
- 생성자 델리게이션을 통해 인스턴스가 초기화 되는 과정
  - 값 형식의 생성자 델리게이션
  - 참조 형식의 생성자 델리게이션
  - 생성자 델리게이션 규칙
  - 클래스 초기화 방식

```swift
Initializer Delegation -> 이니셜라이저가 다른 이니셜라이저를 호출하는 방식으로 구현됨

Value Type일 때

struct Size {
  var width: Double
  var height: Double
  
  init(w: Double, h: Double) {
    width = w
    height = h
  }
  
  init(value: Double) {
    // width = value
    // height = value
    self.init(w: value, h: value)
  }
}


Class일 때
Rule 1
- A designated initializer must call a designated initializer from its immediate superclass.
-> 데지그네이티드 이니셜라이저는 반드시 슈퍼클래스의 데지그네이티드 이니셜라이저를 호출해야 한다 -> Delegate Up이라고 한다


Rule 2
- A convenience initializer must call another initializer from the same class.
-> 컨비년스 이니셜라이저는 동일한 클래스에 있는 다른 이니셜라이저를 호출해야 한다 -> Delegate Across라고 한다
-> 호출할 이니셜라이저의 종류(데지그네이티드, 컨비년스)는 상관이 없다


Rule 3
- A convenience initializer must ultimately call a designated initializer
-> 컨비년스 이니셜라이저를 호출했을 때 최종적으로 동일한 클래스에 있는 데지그네이티드 이니셜라이저가 호출되어야 한다

class Figure {
  let name: String
  
  init(name: String) {
    self.name = name
  }
  
  convenience init() {
    self.init(name: "unknown") // Delegate Across (Rule 2)
  }
}

class Rectangle: Figure {
  var width = 0.0
  var height = 0.0
  
  init(n: String, w: Double, h: Double) {
    width = w
    height = h
    super.init(name: n) // Delegate Up
  }
  
  convenience init(value: Double) {
    self.init(n: "rect", w: value, h: value) 
  }
}

class Square: Rectangle {
  // convenience initializer는 어떤 경우에도 Delegate Up이 불가능하다
  convenience init(value: Double) {
    self.init(n: "square", w: value, h: value)
  }
  
  convenience init() {
    self.init(value: 0.0) // Rule 3
  }
}
```



### 19-5. 생성자 & 생성자 델리게이션 구현하기



### 19-6. Failable initializer
- 초기화 실패를 옵셔널로 처리하는 방법
  - 초기화 성공과 실패
  - 오버로딩 규칙
  - 생성자 델리게이션 규칙
  - 재정의 규칙


```swift
Failable Initializer

init?(parameters) {
  initialization
}

init!(parameters) {
  initialization
}

struct Position {
  let x: Double
  let y: Double
  
  init?(x: Double, y: Double) {
    guard x >= 0.0, y >= 0.0 else { return nil }
    
    self.x = x
    self.y = y
  }
  
  init!(value: Double) {
    guard value >= 0.0 else { return nil }
    
    // self.x = value
    // self.y = value
    
    self.init(x: value, y: value)
  }
}

var a = Position(x: 12, y: 34) // Position -> 정상 초기화
a = Position(x: -12, y: 0) // nil -> 음수여서 nil

var b = Position(value: 12) // Position

b = Position(value: -12) // nil

```


### 19-7. Deinitializer(소멸자)
- 인스턴스가 해제되기 전에 호출되는 소멸자
  - 메모리 정리 방식
  - 일반적인 구현 패턴

```swift
class Size {
  var width = ./0
  var height = 0.0
}

class Position {
  var x = 0.0
  var y = 0.0
}

class Rect {
  var origin = Position()
  var size = Size()
  
  deinit {
    print("deinit \(self)")
  }
}

var r: Rect? = Rect()
r = nil
```



## Extension
- 이미 존재하는 형식을 확장하는 방법

### 20-1. Extension - Syntax
- 익스텐션으로 형식을 확장하는 방법
  - 익스텐션 문법
  - 확장 가능한 멤버 종류
  - 구조체 확장
  - 프로토콜 구현 추가

```swift
struct Size {
  var width = 0.0
  var height = 0.0
}

extension Size {
  var area: Double {
    return width * height
  }
}

let s = Size()
s.width
s.height
s.area

extension Size: Equatable {
  public static func == (lhs: Size, rhs: Size) -> Bool {
    return lhs.width == rhs.width && lhs.height == rhs.height
  }
}
```



### 20-2. Adding Properties
- 익스텐션으로 계산 속성을 추가하는 코드
  - Date 형식에 년도를 리턴하는 속성 추가
  - Double 형식에 라디안/디그리 변환 속성 추가

```swift
Adding Properties

extension Date {
  var year: Int {
    let cal = Calendar.current
    return cal.component(.year, from: self)
  }
  
  var month: Int {
    let cal = Calendar.current
    return cal.component(.month, from: self)
  }
}

let today = Date()
today.year
today.month

extension Double {
  var radianValue: Double {
    return (Double.pi * self) / 180.0
  }
  
  var degreeValue: Double {
    return self * 180.0 / Double.pi
  }
}

let dv = 45.0
dv.radianValue // 0.785398163...
```



### 20-3. 어제 날짜를 리턴하는 속성과 월, 일을 리턴하는 속성 추가하기
```swift
코드가 정상적으로 동작하도록 Extension을 구현해 주세요.

yesterday 속성은 24시간 이전 날짜를 리턴합니다.
month 속성은 "월"을 리턴합니다.
day 속성은 "일"을 리턴합니다.

import Foundation

// 여기에서 구현
extension Date {
    var yesterday: Date {
        return Calendar.current.date(byAdding: .day, value: -1, to: Date())!
    }
    
    var month: Int {
        return Calendar.current.component(.month, from: self)
    }
    
    var day: Int {
        return Calendar.current.component(.day, from: self)
    }

}

func solution(_ year:Int, _ month:Int, _ day:Int) -> [Int] {
    let calendar = Calendar.current
    var comps = DateComponents()
    comps.year = year
    comps.month = month
    comps.day = day

    let date = calendar.date(from: comps)!
    
    let m = date.yesterday.month
    let d = date.yesterday.day
    
    return [m, d]
}

```



### 20-4. Adding Methods
- 익스텐션으로 메소드를 추가하는 코드
  - Double 형식에 화씨/섭씨 온도 변환 메소드 추가
  - Date 형식에 문자열 포멧팅 메소드 추가
  - String 형식에 랜덤 문자열 생성 메소드 추가

```swift
Adding Methods

extension Double {
  func toFahrenheit() -> Double {
    return self * 9 / 5 + 32
  }
  
  func toCelsius() -> Double {
    return (self - 32) * 5 / 9
  }
  
  static func convertToFahrenheit(from celsius: Double) -> Double {
    return celsius.toFahrenheit()
  }
}

let c = 30.0 // 30
c.toFahrenheit() // 86

Double.converToFahrenheit(from: 30.0) // 86

extension Date {
  func toString(format: String = "yyyyMMdd") -> String {
    let privateFormatter = DateFormatter()
    privateFormatter.dateFormat = format
    return privateFormatter.string(from: self)
  }
}

let today = Date()
today.toString()

today.toString(format: "MM/dd/yyyy")
```


### 20-5. 문자열 앞, 뒤 공백을 제거하는 메소드 추가하기
```swift
Extension으로 문자열 앞, 뒤 공백을 제거하는 메소드를 추가해 주세요.

import Foundation

extension String {
    func trimmed() -> String {
        let charSet = CharacterSet.whitespaces
        return self.trimmingCharacters(in: charSet)
    }
}

func solution(_ source:String) -> String {
    return source.trimmed()
}
```



### 20-6. Adding Initializers
- 익스텐션으로 생성자를 추가하는 코드 작성
  - Date 형식에 년,월,일로 초기화 하는 생성자 추가
  - UIColor 클래스에 RGB 파라미터를 받는 생성자 추가
  - 익스텐션으로 생성자를 구현할 때의 장점

```swift
extension Date {
  init?(year: Int, month: Int, day: Int) {
    let cal = Calendar.current
    var comp = DateComponents()
    comp.year = year
    comp.month = month
    comp.day = day
    
    guard let date = cal.date(from: comp) else { return nil }
    
    self = date
  }
}

Date(year: 2021, month: 7, day: 12)


extension UIColor {
  convenience init(red: Int, green: Int, blue: Int) {
    self.init(red: CGFloat(red) / 255, green: CGFloat(green) / 255, blue: CGFloat(blue) / 255, alpha: 1.0)
  }
}

UIColor(red: 0, green: 0, blue: 255)

struct Size {
  var width = 0.0
  var height = 0.0
  
}

extension Size {
  init(value: Double) {
    width = value
    height = value
  }
}

Size()
Size(width: 12, height: 34)
```



### 20-7. 년, 월, 일로 날짜를 초기화하는 생성자 추가하기
```swift
Extension으로 년, 월, 일로 날짜를 초기화 하는 생성자를 구현해 주세요.

import Foundation

extension Date {
    init?(year: Int, month: Int, day: Int) {
        let cal = Calendar.current
        var component = DateComponents()
        component.year = year
        component.month = month
        component.day = day
        
        guard let date = cal.date(from: component) else { return nil }
        
        self = date
    }
}

let date = Date(year: 2011, month: 10, day: 5)

func solution(_ year:Int, _ month:Int, _ day:Int) -> String {
   let formatter = DateFormatter()
   formatter.dateFormat = "yyyyMMdd"
   
   guard let date = Date(year: year, month: month, day: day) else {
      return "error"
   }
   
   return formatter.string(from: date)
}
```



### 20-8. Adding Subscripts
- 익스텐션으로 서브스크립트를 추가하는 코드 작성
  - String 형식에 정수 인덱스를 처리하는 서브스크립트 추가
  - Date 형식에 컴포넌트를 리턴하는 서브스크립트 추가

```swift
extension String {
  subscript(idx: Int) -> String? {
    guard (0..<count).contains(idx) else { return nil }
    
    let target = index(startIndex, offsetBy: idx)
    return String(self[target])
  }
}

let str = "Swift"
str[1] // "w"
str[100] // nil

extension Date {
  subscript(component: Calendar.Component) -> Int? {
    let cal = Calendar.current
    return cal.component(component, from: self)
  }
}

let today = Date()
today[.year]
today[.month]
today[.day]
```

### 20-9. 문자열에 정수 인덱스로 접근하는 Subscript 추가하기
```swift
문제 설명
문자열에서 특정 문자에 접근할 때 [ ] 사이에 String.Index 형식의 인덱스를 전달해야 합니다.
Int 형식의 인덱스를 지원하는 Subscript를 문자열에 형식에 추가해 주세요

import Foundation

func solution(_ source:String, _ index:Int) -> String {
    return source[index]
}

extension String {
  subscript(idx: Int) -> String {
    let targetIndex = index(startIndex, offsetBy: idx)
    return String(self[targetIndex])
  }
}

```


## Protocol
- 프로토콜을 통해 형식이 구현해야 하는 요구사항을 선언하고 이 요구사항을 충족하도록 형식을 구현하는 방법

### 21-1. Protocol Syntax
- 프로토콜 선언 문법과 프로토콜 채용 문법
  - 프로토콜 선언 문법
  - 프로토콜 채용 문법
  - 요구사항 구현
  - AnyObject 프로토콜
  - 클래스 프로토콜

```swift
프로토콜 정의(Defining Protocols)

protocol ProtocolName {
  propertyRequirements
  methodRequirements
  initializerRequirements
  subscriptRequirements
}

protocol ProtocolName: Protocol, ... {

}

protocol Something {
  func doSomething()
}

프로토콜 채용(Adopting Protocols)

struct Size: Something {
  func doSomething() {
    
  }
}

Class-Only Protocols

protocol SomethingObject: AnyObject, Something { // AnyObject를 채용하면 클래스에서만 채용 가능하다

}

// struct Value: SomethingObject { // SomethingObject의 경우 AnyObject 타입이기 때문에 구조체에서는 채용할 수 없다
// 
// }

class Object: SomethingObject {
  func doSomething() {
  
  }
}

```



### 21-2. Property Requirements
- 프로토콜에서 속성을 선언하고 형식에서 요구사항을 구현
  - var 키워드 용법
  - 가변성 선언
  - static 키워드와 class 키워드

```swift
Property Requirements

protocol ProtocolName {
  var name: Type { get set }
  static var name: Type { get set }
}


protocol Figure {
  static var name: String { get set }
}

struct Rectangle: Figure {
  static var name = "Rect"
}

struct Triangle: Figure {
  static var name = "Triangle"
}

class Circle: Figure {
  static var name: String {
    get {
      return "Circle"    
    }
    set {
    
    }
  }
}
```



### 21-3. Method Requirements
- 프로토콜에서 메소드를 선언하고 형식에서 요구사항을 구현
  - mutating 메소드 선언
  - static 키워드와 class 키워드

```swift
Method Requirements

protocol ProtocolName {
  func name(param) -> ReturnType
  static func name(param) -> ReturnType
  mutating func name(param) -> ReturnType
}

protocol Resettable {
  static func reset()
}

class Size: Resettable {
  var width = 0.0
  var height = 0.0
  
  func reset() {
    width = 0.0
    height = 0.0
  }
  
  static func reset() {
  
  }
}

```



### 21-4. Initializer Requirements
- 프로토콜에서 생성자를 선언하고 형식에서 요구사항을 구현
  - 구조체와 클래스에서 생성자 구현의 차이
  - final 클래스에서 프로토콜 구현
  - 상속과 중복 선언 오류
  - Non-failble Initializer와 Failable Initializer

```swift
Initializer Requirements

protocol ProtocolName {
  init(param)
  init?(param)
  init!(param)
}

protocol Figure {
  var name: String { get }
  init(n: String)
}

struct Rectangle: Figure {
  var name: String
  init(n: String) {
    name = n
  }
}

class Circle: Figure {
  var name: String
  
  required init(n: String) { // required 안 붙이면 에러 발생함
    name = n
  }
}

final class Triangle: Figure {
  var name: String
  
  init(n: String) { // final class이므로 required 안 붙여도 에러 없음
    name = n
  }
}

class Oval: Circle {
  var prop: Int
  
  init() {
    prop = 0
    super.init(n: "Oval")
  }
  
  required convenience init(n: String) {
    self.init()
  }
}

protocol Grayscale {
  init?(white: Double)
}

struct Color: Grayscale {
  init?(white: Double) {
  
  }
}
```



### 21-5. Subscript Requirements
- 프로토콜에서 서브스크립트를 선언하고 형식에서 요구사항을 구현

```swift
Subscript Requirements

protocol ProtocolName {
  subscript(param) -> ReturnType { get set }
}

protocol List {
  subscript(idx: Int) -> Int { get set } 
}

struct DataStore: List {
  subscript(idx: Int) -> Int {
    get {
      return 0
    }
    set {
    
    }
  }
}
```

### 21-6. Custom Type을 비교 연산자로 비교하기
```swift
Color 인스턴스를 == 연산자와 != 연산자로 비교할 수 있도록 구현해 주세요.

import Foundation

struct Color: Equatable {
   let red: Int
   let green: Int
   let blue: Int
   
   static var black: Color {
      return Color(red: 0, green: 0, blue: 0)
   }
   
   static var white: Color {
      return Color(red: 255, green: 255, blue: 255)
   }
    
    static func ==(lhs: Color, rhs: Color) -> Bool {
        return (lhs.red == rhs.red) && (lhs.green == rhs.green) && (lhs.blue == rhs.blue)
    }
    
}

// 아래에 있는 코드는 수정하지 마세요.
let b = Color.black
let w = Color.white

print(b == w)
```


## Protocol - 고급

### 21-7. Protocol Types ***
- 프로토콜 타입과 프로토콜 적합성
  - 프로토콜 타입
  - 프로토콜과 타입 캐스팅
  - 프로토콜 적합성
  - 상속과 유사한 패턴 구현

```swift
Protocol Types

protocol Resettable {
  func reset()
}

class Size: Resettable {
  var width = 0.0
  var height = 0.0
  
  func reset() {
    width = 0.0
    height = 0.0
  }
}

let s = Size()
let r: Resettable = Size()
r.reset() // 프로토콜을 활용하면 상속과 유사한 기능을 할 수 있다


Protocol Conformance(프로토콜 적합성)

instance is ProtocolName

instance as ProtocolName
instance as? ProtocolName
instance as! ProtocolName

protocl Resettable {
  func reset()
}

class Size: Resettable {
  var width = 0.0
  var height = 0.0
  
  func reset() {
    width = 0.0
    height = 0.0
  }
}

let s = Size()

s is Resettable // true

let r = Size() as Resettable // Size

r as? Size // Size


```



### 21-8. Protocol composition ***
- 다수의 프로토콜을 병합해서 하나의 임시 프로토콜을 만드는 방법




### 21-9. Optional Requirements ***
- 이 제목에서의 Optional은 말 그대로 '선택적'을 의미함, 기존 Swift의 옵셔널을 의미하는 것이 아님
- 선택적 요구사항을 선언하는 방법
  - @objc Attribute
  - optional Modifier
  - 선택적 요구사항과 옵셔널 체이닝

```swift
Optional Protocol Requirements

@objc protocol ProtocolName {
  @objc optional requirements
}

@objc protocol Drawable {
  @objc optional var strokeWidth: Double { get set }
  @objc optional var strokeColor: UIColor { get set }
  func draw()
  @objc optional func reset()
}

class Rectangle: Drawable {
  func draw() {
    
  }
}

let r: Drawable = Rectangle()
r.draw()
r.strokeWidth // nil -> 형식에 해당 속성이 선언되어 있지 않다는 의미
r.strokeColor // nil -> 형식에 해당 속성이 선언되어 있지 않다는 의미
r.reset?() // nil -> 호출한 메소드가 구현되어 있지 않다는 의미
```



### 21-10. Protocol Extension ***
- 프로토콜 익스텐션을 통해 공통 구현을 제공하는 방법
  - 프로토콜 확장
  - 멤버 우선순위
  - 멤버 추가 형식 제한

```swift
Protocol Extension

protocol Figure {
  var name: String { get }
  func draw()
}

extension Figure where Self: Equatable {
  func draw() {
    print("draw figure")
  }
}

struct Rectangle: Figure, Equatable {
  var name = ""
  
  func draw() {
    print("draw rectangle")
  }
}

let r = Rectangle()
r.draw()

```


## Memory, Value Typeand Reference Type
- 메모리가 값을 저장하는 방법을 공부하고, 값 형식과 참조 형식의 차이점을 비교

### 22-1. Memory Basics
- 메모리에 대한 기초적 내용
  - 비트와 바이트
  - 데이터 저장 방식
  - 메모리 주소
  - 메모리 공간 분류(스택과 힙)




### 22-2. Value Type vs Reference Type
- 값 형식과 참조 형식이 메모리에 저장되는 방식

- Value Type
  - Structure
  - Enumeration
  - Tuple

- Reference Type
  - Class
  - Closure

```swift
struct SizeValue {
  var width = 0.0
  var height = 0.0
}

var value = SizeValue()
var value2 = value
value2.width = 1.0
value2.height = 2.0

value // width 0, height 0
value2 // width 1, height 2



class SizeObject {
  var width = 0.0
  var height = 0.0
}

var object = SizeObject()

var object2 = object

object2.width = 1.0
object2.height = 2.0

object // width 1, height 2
object2 // width 1, height 2 


let v = SizeValue()
let o = SizeObject()
o.width = 1.0 
o.height = 2.0

값 형식
==
!=

참조 형식
==
!=
=== (항등연산자)
!==
```



### 22-3. ARC(Automatic Reference Counting)
- Swift의 메모리 관리 모델인 ARC
  - 메모리 관리 모델
  - 소유 정책
  - 참조 카운트
  - 강한 참조

- Automatic Reference Counting
  - Strong Reference
  - Weak Reference
  - Unowned Reference



### 22-4. Strong Reference Cycle
- 강한 참조 사이클이 발생하는 원인과 해결 방법
  - 강한 참조 사이클
  - 약한(weak) 참조
  - 비소유(unowned) 참조

```swift
Strong Reference Cycle

class Person {
  var name = "John Doe"
  car car: Car?
  
  deinit {
    print("person deinit")
  }
}

class Car {
  var model: String
  var lessee: Person?
  
  init(model: String) {
    self.model = model
  }
  
  deinit {
    print("car deinit")
  }
}

var person: Person? = Person()
var rentedCar: Car? = Car(model: "Porsche")

person?.car = rentedCar
rentedCar?.lessee = person

// 강한 참조 사이클 문제 
person = nil // 여전히 Person Instance의 카운트는 1
rentedCar = nil // 여전히 Car Instance의 카운트는 1

Strong Reference Cycle 문제를 해결하는 두 가지 방법
- Weak Reference
- Unowned Reference

(1) Weak Reference
class Person {
  var name = "John Doe"
  var car: Car?
  
  deinit {
    print("person deinit")
  }
}

class Car {
  var model: String
  weak var lessee: Person?
  
  init(model: String) {
    self.model = model
  }
  
  deinit {
    print("car deinit")
  }
}

var person: Person? = Person()
var retnedCar: Car? = Car(model: "Porsche")

person?.car = rentedCar
rentedCar?.lessee = person

person = nil // person deinit -> 참조 카운팅이 0이 된다
rentedCar = nil // car deinit -> 참조 카운팅이 0이 된다



(2) Unowned Reference
class Person {
  var name = "John Doe"
  var car: Car?
  
  deinit {
    print("person deinit")
  }
}

class Car {
  var model: String
  unowned var lessee: Person
  
  init(model: String, lessee: Person) {
    self.model = model
    self.lessee = lessee
  }
  
  deinit {
    print("car deinit")
  }
}

var person: Person? = Person()
var retnedCar: Car? = Car(model: "Porsche"m lessee: person!)

person?.car = rentedCar
rentedCar?.lessee = person

person = nil // person deinit -> nil
rentedCar = nil // car deinit -> nil
```


### 22-5. Closure Capture List
- Closure Capture List를 통해 클로저에서 발생하는 강한 참조 사이클을 해결하는 방법

```swift
Closure Capture List

class Car {
  var totalDrivingDistance = 0.0
  var totalUsedGas = 0.0
  
  lazy var gasMileage: () -> Double = {
    return self.totalDrivingDistance / self.totalUsedGas
  }
  
  func drive() {
    self.totalDrivingDistance = 1200.0
    self.totalUsedGas = 73.0
  }
  
  deinit {
    print("car deinit")
  }
}

var myCar: Car? = Car()
myCar?.drive()

myCar = nil // car deinit -> 정상적 해제

myCar?.gasMileage() // 16.43835616...


클로저 캡처리스트 문법

{ [list] (parameters) -> ReturnType in
  Code
}

{ [list] in
  Code
}

Value Type(값 형식)

{ [valueName] in
  Code
}

var a = 0
var b = 0
let c = { [a] in print(a, b) } // 값 형식을 클로저 캡처리스트에 추가하면 참조 대신 복사본을 캡처한다

a = 1
b = 2
c()


Reference Type(참조 형식)

{ [weak instanceName, unowned instanceName] in
  statements
}

// Weak
class Car {
  var totalDrivingDistance = 0.0
  var totalUsedGas = 0.0
  
  lazy var gasMileage: () -> Double = { [weak self] in
    guard let strongSelf = self else { return 0.0 }
    return strongSelf.totalDrivingDistance / strongSelf.totalUsedGas
  }
  
  func drive() {
    self.totalDrivingDistance = 1200.0
    self.totalUsedGas = 73.0
  }
  
  deinit {
    print("car deinit")
  }
}

var myCar: Car? = Car()
myCar?.drive()
myCar?.gasMileage()
myCar = nil

// Unowned
class Car {
  var totalDrivingDistance = 0.0
  var totalUsedGas = 0.0
  
  lazy var gasMileage: () -> Double = { [unowned self] in
    return self.totalDrivingDistance / self.totalUsedGas
  }
  
  func drive() {
    self.totalDrivingDistance = 1200.0
    self.totalUsedGas = 73.0
  }
  
  deinit {
    print("car deinit")
  }
}

var myCar: Car? = Car()
myCar?.drive()
myCar?.gasMileage()
myCar = nil
```



## Generics
- 형식에 독립적인 코드를 구현

### 23-1. Generic Function
- 특정 형식과 연관되지 않은 함수를 구현하는 방법
  - 제네릭 함수
  - Type Parameters
  - Type Constraints
  - Specialization

```swift
Generics

func swapInteger(lhs: inout Int, rhs: inout Int) {
  let tmp = lhs
  lhs = rhs
  rhs = tmp
}

var a = 10
var b = 20
swapInteger(lhs: &a, rhs: &b)
a
b


Generic Function
func name<T>(parameters) -> Type { // 여기에서 <T>의 T는 Type Parameter를 의미
  code
}

func swapValue<T>(lhs: inout T, rhs: inout T) {
  let tmp = lhs
  lhs = rhs
  rhs = tmp
}

a = 1
b = 2
swapValue(lhs: &a, rhs: &b)
a // 2
b // 1

var c = 1.2
var d = 3.4
swapValue(lhs: &c, rhs: &d)
c // 3.4
d // 1.2



Type Constraints(형식 제약)

func swapValue<T: Equatable>(lhs: inout T, rhs: inout T) { // Equtable일 때만 사용 가능
  print("generic version")
  if lhs == rhs { return }
  
  let tmp = lhs
  lhs = rhs
  rhs = tmp
}

Specialization

func swapValue<T: Equatable>(lhs: inout T, rhs: inout T) { // Equtable일 때만 사용 가능
  print("specialized version")
  if lhs == rhs { return }
  
  let tmp = lhs
  lhs = rhs
  rhs = tmp
}

var a = 1
var b = 2
swapValue(lhs: &a, rhs: &b) // generic version

var c = "Swift"
var d = "Programming"
swapValue(lhs: &c, rhs: &d) // specialized version

```


### 23-2. 두 값을 비교하는 제네릭 함수 구현하기
```swift
a, b, c, d에 모두 true가 저장되도록 제네릭 함수를 구현하고 Color 구조체를 수정해 주세요.

import Foundation

// 여기에서 제네릭 함수를 구현해 주세요.
func equal<T: Equatable>(lhs: T, rhs: T) -> Bool {
    if lhs == rhs { 
        return true
    } else {
        return false
    }
}

// Color 값을 비교할 수 있도록 구현해 주세요.
struct Color: Equatable {
   let r: Double
   let g: Double
   let b: Double   
}

let a = equal(lhs: 1, rhs: 1)
let b = equal(lhs: 12.34, rhs: 12.34)
let c = equal(lhs: "Hello", rhs: "Hello")
let d = equal(lhs: Color(r: 0, g: 0, b: 0), rhs: Color(r: 0, g: 0, b: 0))

print(a && b && c && d)
```



### 23-3. Generic Types
- 제네릭 타입을 선언하고 형식 내부에서 사용하는 다양한 형식을 타입 파라미터로 대체하는 방법
  - 제네릭 타입
  - 형식 표기 방식
  - 익스텐션으로 제네릭 타입 확장
  - 확장 대상 제한

```swift
Generic Types

class Name<T> {
  code
}

struct Name<T> {
  code
}

enum Name<T> {
  code
}

struct Color<T> {
  var red: T
  var green: T
  var blue: T
}

var c = Color(red: 128, green: 80, blue: 200) // 타입: Color<Int>

var d = Color(red: 128.0, green: 80.0, blue: 200.0) // 타입: Color<Double>

extension Color where T == Int { // Int일 때만 가능하게 조건 추가
  func getComponents() -> [T] {
    return [red, green, blue]
  }
}

let intColor = Color(red: 1, green: 2, blue: 3)
intColor.getComponents() // [1, 2, 3]

let dblColor = Color(red: 1.0, green: 2.0, blue: 3.0)
dblColor.getComponents()

```



### 23-4. Associated Types
- 프로토콜 내에서 실제 형식으로 대체되는 연관 형식을 선언하는 방법
  - 제네릭 프로토콜
  - Associated Types
  - typealias를 통한 실제 형식 선언
  - 연관 형식에 제약 추가

```swift
Associated Types(연관 형식)

associatedtype Name

protocol QueueCompatible {
  associatedType Element: Equatable // 연관형식 선언
  func enqueue(value: Element)
  func dequeue() -> Element?
}

class IntegerQueue: QueueCompatible {
  typealias Element = Int
  
  func enqueue(value: Int) {
  
  }
  
  func dequeue() -> Int? {
    return 0
  }
}

class DoubleQueue: QueueCompatible {
  func enqueue(value: Double) {
  
  }
  
  func dequeue() -> Double? {
    return 0
  }
}

```



## Error Handling
- 코드에서 발생할 수 있는 다양한 오류를 크래시 없이 처리하는 방법

### 24-1. Error Handling
- Swift의 에러 처리 패턴
  - Error 프로토콜
  - 컴파일 타임 에러와 런타임 에러
  - throw와 throws
  - Throwing function 구현
  - 오류 처리 패턴
  - try 표현식

```swift
Error Handling

throw expression

func name(parameters) throws -> ReturnType { // Throwing Function(Method)
  statements
}

init(parameters) throws { // Throwing Initializer
  statements
}

{ (parameters) throws -> ReturnType in // Throwing Closure
  statements
}


enum DataParsingError: Error {
  case invalidType
  case invalidField
  case missingRequiredField(String)
}

func parsing(data: [String: Any]) throws {
  guard let _ = data["name"] else {
    throw DataparsingError.missingRequiredField("name")
  }
  
  guard let _ = data["age] as? Int else {
    throw DataParsingError.invalidType
  }
  
  // Parsing
}
```



### 24-2. do-catch Statements
### 24-3. Optional Try
### 24-4. defer Statements
### 24-5. 오류 처리 패턴 구현하기
