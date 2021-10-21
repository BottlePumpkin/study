# Access Control 접근제어

## 접근제어

특정 코드의 접근을 다른 소스 파일이나 모듈에서 제한 하는 것.

특정 코드의 세부적인 구현을 감추고 딱 필요한 만큼 공개해 다른 곳에서 사용 할 수 있도록 함.

불필요한 접근으로 의도치 않은 결과를 초래하거나 꼭 필요한 이상의 코드가 노출될 위험이 있을때 사용

- 캡슐화, 은닉화를 이용한 것
- 은닉화?

클래스의 프로퍼티를 private로 만들어 클래스 밖에서 함부로 접근 할 수 없도록 하는 것을 말함

클래스를 사용할 때 프로퍼티에 직접 접근 하는 것은 데이터 무결성 오류에 치명적일 수 있기에 대신 연산 프로퍼티(get,set)를 통한 접근을 가능케 하는 것을 말함.

Class,Enum,Struct 등 개별 타입에서도 적용

Property,Method,Initializer,subscript에서도 적용 가능

Swift에서는 기본 접근레벨을 제공해 접근 레벨의 처리를 쉽게 할 수 있도록 돕는다!

## 모듈과 소스파일 (Modules and Source Files)

Swift의 접근제어는 모듈과 소스파일에 기반을 두고 있음.

모듈 → Library?

Xcode의 빌드 타겟은 Swift에서 분리된 단일 모듈로 취급 됨.

### 접근 레벨 (Access Levels)

- Open & Public : Open과 Public은 접근자 모두 선언한 모듈이 아닌 다른 모듈에서 사용 가능. 두 접근자의 차이점은 Open은 다른 모듈에서 오버라이드와 서브 클래싱이 가능하지만 Public접근자로 선언 된 것은 다른 모듈에서 오버라이드와 서브 클래싱이 불가능

Open : 다른 모듈에서 override, subclassing가능 

Public : 불가능

- Internal : 기본 접근 레벨로 아무 접근 레벨을 선언하지 않으면 Internal로 간주. 해당 모듈 전체 사용 가능 함.
- File-private: 특정 엔티티를 선언한 파일에서만 사용 가능 함.
- Private: 특정 엔티티가 선언된 괄호 ({}) 안에서만 사용 가능 함.

![접근 제어자 종류.png](Access%20Control%20%E1%84%8C%E1%85%A5%E1%86%B8%E1%84%80%E1%85%B3%E1%86%AB%E1%84%8C%E1%85%A6%E1%84%8B%E1%85%A5%204a4cbb5c0b174ce39da2e510e1b94cc3/%E1%84%8C%E1%85%A5%E1%86%B8%E1%84%80%E1%85%B3%E1%86%AB_%E1%84%8C%E1%85%A6%E1%84%8B%E1%85%A5%E1%84%8C%E1%85%A1_%E1%84%8C%E1%85%A9%E1%86%BC%E1%84%85%E1%85%B2.png)

### 접근 레벨 가이드 원칙

Swift에서 접근 레벨은 더 낮은 레벨을 갖고 있는 다른 엔티티를 특정 엔티티에서 사용할 수 없다.

- public 변수는 다른 internal,file-private,private 타입에서 정의 될 수 없음. 왜냐하면 그 타입은 public 변수가 사용되는 모든 곳에서 사용 할 수 없기 때문
- 함수는 그 함수의 파라미터 타입이나 리턴 값 타입보다 더 높은 접근 레벨을 갖을 수 없음.

### 기본 접근 레벨

- 아무 접근 레벨을 명시 하지 않은 경우 internal을 갖게 됨.

### 단일 타켓 앱을 위한 접근 레벨

- 필요에 다라 file-private, private등을 사용해 앱내에서 구현

### 프레임워크를 위한 접근 레벨

- public 또는 open으로 지정해서 다른 모듈에서 볼 수 있고 접근 가능하도록 만들어야 함

### 유닛 테스트 타겟을 위한 접근 레벨

- open , public만 접근 가능
- 유닛 테스트하는 모듈을 import할때 앞에 @testable 이라는 attribute를 붙여주면 테스트가 가능한 모듈로 가능.

### 커스텀 타입 (Custom Types)

특정 타입의 접근레벨의 지정은 그 타입의 멤버 (프로퍼티,메서드,초기자와 서브스크립트)에 기본 접근레벨에 영향을 미침.

```swift
public class SomePublicClass {                  // explicitly public class
    public var somePublicProperty = 0            // explicitly public class member
    (internal) var someInternalProperty = 0                 // implicitly internal class member
    fileprivate func someFilePrivateMethod() {}  // explicitly file-private class member
    private func somePrivateMethod() {}          // explicitly private class member
}

//public 타입은 기본적으로 internal 멤버를 갖고 public을 갖지 않음. public api를 만들 시에 노출 되지 말아야 할 api가 실수로 
//노출되는 것을 막기 위함.

class SomeInternalClass {                       // implicitly internal class
    (internal) var someInternalProperty = 0                 // implicitly internal class member
    fileprivate func someFilePrivateMethod() {}  // explicitly file-private class member
    private func somePrivateMethod() {}          // explicitly private class member
}

fileprivate class SomeFilePrivateClass {        // explicitly file-private class
    (fileprivate) func someFilePrivateMethod() {}              // implicitly file-private class member
    private func somePrivateMethod() {}          // explicitly private class member
}

private class SomePrivateClass {                // explicitly private class
   (private) func somePrivateMethod() {}                  // implicitly private class member
}
```

### 튜플 타입 (Tuple Types)

가장 제한 적인 접근 레벨

접근 권한이 2개라면 가장 낮은 레벨의 접근 레벨을 갖음

### 함수 타입 (Function Types)

함수 타입의 접근레벨은  리턴타입의 접근레벨 중 최소의 접근 레벨로 계산되어 사용

```swift
private func someFunction() -> (SomeInternalClass, SomePrivateClass) {
    // function implementation goes here
}

//private을 명시적으로 적어야 한다
// somePrivateClass가 있기 때문에 internal(기본) 에서 접근 할 수 없음
```

### 열거형 타입 (Enumeration Types)

열거형의 각 case는 enum의 접근 레벨을 따르고 개별적으로 다른 접근레벨을 지정 할 수 없음.

```swift
public enum CompassPoint {
    case north
    case south
    case east
    case west
}

//case 모두 enum의 접근 레벨인 public을 갖는다.
```

### 고유값과 연관 값 (Raw Values and Associated Values)

고유값과 연관값을 사용하는 타입의 경우 반드시 그 타입보다 높은 접근 레벨을 가져야 합니다. 즉, internal 접근 레벨을 갖고 있는 열거형 타입에서 private 접근레벨을 갖는 고유값을 사용 할 수 없음.

### 중첩 타입 (Nested Types)

선언 된 타입의 접근레벨을 가진다

### 서브 클래싱 (Subclassing)

서브 클래스는 수퍼클래스보다 더 높은 접근 레벨을 가질 수 없다.

메소드는 서브클래스에서 더 높은 접근 레벨을 갖는 메소드로 오버라이드 할 수 있음

⇒ 같은 소스파일에 선언 되어있어서 super.method 호출이 유효하기 때문

### 상수,변수,프로퍼티 그리고 서브스크립트

타입보다 더 높은 접근 레벨을 갖을 수 없다. 

필요에 따라서 세터의 접근레벨을 게터보다 낮게 정할 수 있다. 

```swift
struct TrackedString {
    private(set) var numberOfEdits = 0
    var value: String = "" {
        didSet {
            numberOfEdits += 1
        }
    }
}

numberOfEdits 변수가 private(set)로 설정해 TrackedString 내부에서만 변경되도록
지정한 코드. 설정하지 않았다면 internal로 취급돼 TrackedString밖에서도 접근이 가능 했음
```

세터 뿐 아니라 게터에도 접근레벨을 지정하고 싶다면 아래와 같이 설정

```swift
public struct TrackedString {
    public private(set) var numberOfEdits = 0
    public var value: String = "" {
        didSet {
            numberOfEdits += 1
        }
    }
    public init() {}
}
```

### 초기자

초기자의 접근레벨은 타입의 레벨과 같거나 낮다. 지정초기자 (required initializer)인데, 이 지정초기자는 반드시 이 초기자가 속한 타입과 접근레벨이 같아야 함.

### 프로토콜 (Protocols)

프로토콜의 접근레벨과 그 안의 요구사항의 접근레벨은 항상 동일 해야함.

- 프로토콜 상속 (Protocol Inheritance)

이미 존재하는 프로토콜을 상속받아 새로운 프로토콜을 선언하는 경우 새 프로토콜은 상속을 한 프로토콜과 같은 접근레벨을 갖음.

- 프로토콜 순응 (Protocol Conformance)

프로토콜 타입에 맞춰서 따르는 타입도 따라간다.

### 익스텐션 (Extensions)

새로 추가된 것은 기존에 타입이 선언된 접근레벨과 같은 레벨을 갖음.

명시적으로 접근레벨을 지정할 수 있으나 프로토콜로 사용하는 경우 명시적인 접근이 불가

### 제네릭 (Generics)

해당 접근레벨의 최소 접근 레벨을 갖음.

### 타입 별칭 (Type Aliases)

타입 별칭은 별칭을 붙인 타입보다 같거나 낮은 접근 레벨을 갖음.

참고문서 : [https://jusung.gitbook.io/the-swift-language-guide/language-guide/25-access-control](https://jusung.gitbook.io/the-swift-language-guide/language-guide/25-access-control)

,[https://velog.io/@hayeon/접근-제어자의-종류엔-어떤게-있는지-설명하시오](https://velog.io/@hayeon/%EC%A0%91%EA%B7%BC-%EC%A0%9C%EC%96%B4%EC%9E%90%EC%9D%98-%EC%A2%85%EB%A5%98%EC%97%94-%EC%96%B4%EB%96%A4%EA%B2%8C-%EC%9E%88%EB%8A%94%EC%A7%80-%EC%84%A4%EB%AA%85%ED%95%98%EC%8B%9C%EC%98%A4)