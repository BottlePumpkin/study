# final class

### 오버라이드 방지 (Preventing Overrides)

서브클래스에서 특정 메소드, 프로퍼티, 서브스크립트가 오버라이드 되는 것을 방지하려면 final키워드를 사용합니다. 다시말해, final로 선언되면 override되는 것을 막을 수 있습니다. (final func, final class func, final subscript) 만일 final로 선언된 메소드, 프로퍼티, 서브스크립트를 오버라이드 하려고 하면 컴파일 시간(compile-time)에 에러가 발생합니다. 클래스 전체를 final로 선언해서 클래스 안의 모든 메소드, 프로퍼티 등이 override가 되는 것을 막을 수 있습니다. (final class)

### final 키워드 적용이 성능에 미치는 영향?

공식 문서에서는 성능과 관련된 사항을 언급하고 있지는 않음. 

final로 선언된 요소들은 직접 호출 하는 반면, 그렇지 않은 요소들은 vtable을 통해 간접 호출되어 직접 호출되는 경우보다 느리게 작동.

### Vtable?

가상 메서드 테이블, 메서드 오버라이딩에 따라 실행 시점에 어떤 메서드를 결정할지 동적 디스패치를 지원하기 위해 프로그래밍 언어에서 사용하는 매커니즘

오버라이딩 메서드 : 실행 시점에서 어떤 메서드를 실행할지 결정

final 키워드 메서드: 컴파일 시점에 어떤 메서를 실행 할 지 결정 ⇒ 성능상 이점을 가짐

참조 문서:

 [https://www.hackingwithswift.com/sixty/8/4/final-classes](https://www.hackingwithswift.com/sixty/8/4/final-classes)

[https://velog.io/@ryan-son/Swift-final-키워드-왜-사용하는걸까](https://velog.io/@ryan-son/Swift-final-%ED%82%A4%EC%9B%8C%EB%93%9C-%EC%99%9C-%EC%82%AC%EC%9A%A9%ED%95%98%EB%8A%94%EA%B1%B8%EA%B9%8C)

[https://jusung.gitbook.io/the-swift-language-guide/language-guide/13-inheritance?q=](https://jusung.gitbook.io/the-swift-language-guide/language-guide/13-inheritance?q=)

[https://github.com/apple/swift/blob/main/docs/OptimizationTips.rst#advice-use-final-when-you-know-the-declaration-does-not-need-to-be-overridden](https://github.com/apple/swift/blob/main/docs/OptimizationTips.rst#advice-use-final-when-you-know-the-declaration-does-not-need-to-be-overridden)

[https://ko.wikipedia.org/wiki/가상_메소드_테이블](https://ko.wikipedia.org/wiki/%EA%B0%80%EC%83%81_%EB%A9%94%EC%86%8C%EB%93%9C_%ED%85%8C%EC%9D%B4%EB%B8%94)