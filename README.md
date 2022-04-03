# Effective Swift 한글 요약본

# 시작하기 앞서

---

> 이 페이지는 저자분의 허락하에 작성된 Effective Swift (일본어) 책의 한글 요약본 입니다. 

보다 자세한 정보는 책을 직접 구매하시는걸 추천드립니다. (저자 분의 부탁)

페이지에 대한 피드백은 언제든지 환영합니다. 출처를 꼭 밝혀주시면 감사합니다.
> 

 

✉️ 476c656e@gmail.com

😺 [476c656e](https://github.com/476C656E) #Github

---

## 도와주세요 🙇‍♂️

공부하면서 번역과 요약을 동시에 진행하고 있습니다. (제 실력이 부족한 탓에 늦는점 죄송합니다.)

생각보다 책에 나와 있는 예시가 많이 부족하다고 느끼실 수 있습니다.

적극적인 피드백을 주시면 꼭 반영하도록 하겠습니다. 

(도움 주신 분들 리스트에 추가할 예정입니다.)

# 저자에 관련된 정보

*저자의 Github*

[yimajo - Overview](https://github.com/yimajo)

*책 구매처*

[Effective Swift - キュリオシティソフトウェア書店 - BOOTH](https://booth.pm/ko/items/3755447)

저자분의 다른 책

[RxSwift研究読本1 入門編 - キュリオシティソフトウェア書店 - BOOTH](https://swift.booth.pm/items/1076262)

---

## 💡 읽기전에 권장하는 지식

## 📖 학습 전에 보기 좋은 책

- 클로저는 무엇인가?
- Dispatch Queue를 이용한 비동기 처리에 대한 코드를 보고 어떠한 순서대로 처리되는지
- Optional을 실현하고 있는 Optional 타입

---

- RxSwift 관련된 책
- VIPER 관련된 책
- Combine framework 가이드 북

---

# 목차

### 머릿말

### 책에 관해

> 책이 커버하는 범위
책의 구성
예상되는 독자
책 내용의 표기에 대해서
책 읽는 방법
면책 사항 (책에 관련된 사항)
> 

### [서막](Effective%20%20b5759/%E1%84%89%E1%85%A5%E1%84%86%E1%85%A1%E1%86%A8%20152fe.md)

> 책에서 사용하는 용어
함수 (메서드 및 Free Function)
인스턴스
순수 함수 (pure functions) 및 **side-effect**
기타 용어
> 

### [제 1장 - Swift에 익숙해지자](Effective%20%20b5759/%E1%84%8C%E1%85%A6%201%E1%84%8C%E1%85%A1%E1%86%BC%20-%20%20b50a9.md)

1. 되도록 타입 추론을 하자.
2. guard 구문은 조건을 반전하여 생각하지 않도록 하자.
3. 조건을 필요로하는 분기에는 그 조건을 명확히하자.
4. 가능한 let을 사용하자.
5. Array를 let으로 선언함으로써 요소 조작을 못하게 하자.
6. 가능한 self를 생략하자.
    1. 칼럼: 프로퍼티에 대한 접근을 명확하게 하기 위해 self를 생략하자.
7. ID를 가진 엔티티 (Entity)는 Identifiable을 적극적으로 사용하자.
8. 배열을 반환하는 메서드로 0일 경우 nil을 반환하는 것이 아닌 빈 배열을 반환하자.
9. Optional 할 필요가 없는 중요한 매개변수는 Optional을 하지 않는다.
10. nonmutation 및 복잡도가 $O(1)$이면 프로퍼티를 검토한다.
11. 범용적이고 확립된 도메인에는 Free Functions을 사용하자.
12. 함수에서 디폴트 매개변수를 이용한다.
13. 디폴트를 동작하기 위해 디폴트 매개변수를 이용하자.
14. Optional에서 빈 클로저를 이용하자.
    1. 클로저의 이스케이핑에 대해 이해하자.
    2. 클로저를 Optional하면 이스케이핑이 되는지를 이해하자.

### 제 2장 - 참조 카운트 방식을 이용하여 메모리릭을 피하자

1. 참조에 대한 기초 이해
    1. 값 타입과 참조 타입을 이해하자.
    2. 참조 카운터를 이해하자.
    3. ARC 이해하기
    4. 참조형과 참조 방식 이해하자.
        
        강한 참조
        약한 참조
        비소유 참조
        참조 카운트는 1종류만 있는게 아니다.
        
2. 순환 참조의 이해
    1. 클래스끼리의 순환 참조를 이해하자.
    2. 약한 참조로 순환 참조를 해결하자.
    3. 클로저에 의한 순환 참조를 이해하자.
    4. 캡처 리스트를 이해하자.
    캡처 리스트가 캡처되는 타이밍
    참조형의 캡처
3. 클로저에 의한 순환 참조가 강한 참조로도 해결되는 패턴을 이해하자.
4. 착각하기 쉬운 점을 이해하자.
    1. 이스케이프된 클로저에서 강한 참조를 해도 반드시 순환 참조하는 것은 아니다.
5. 강한 참조의 참조 카운터를 출력하여 확인하기.
6. 정리
    
    칼럼: unowned의 사용
    

### 제 3장 - 타입 명명법

1. enum에 의한 네임 스페이스를 검토
2. 능력을 나타내는 프로토콜은 동사의 접미사에 able, ible을 붙인다.
3. 프로토콜 이름이 추상적 개념으로 해석할 수 있다면 명사로도 좋다.

### 제 4장

1. 네이밍에는 역할을 나타낸다.
2. 가능하면 uuid라는 변수명은 피하자.
3. 변수명이나 상수명은 lowerCamelCase로 한다.
4. strongSelf 등 하지않고 self를 섀도잉해도 된다.

### 제 5장 - 함수의 명명법

1. 이니셜라이저 및 Factory 메소드
    1. 가역성 변환의 이니셜라이저에서는 레이블을 생략할 수 있다.
    2. narrowing 변환은 라벨을 생략하지 않고 
    * 絞りこみ方法(**narrowing method**) 을 라벨로 한다.
    3. Factory 메소드의 명명은 “make”로 시작하자.
    4. Factory 메소드의 명명은 라벨에 전치사를 포함하지 않는다.
2. * 함수의 호출원을 의식한 함수의 명명
    1. Bool을 리턴하는 함수는 호출원이 검증하는 이름으로 짓는다.
3. 라벨에 전치사를 사용하는 것을 검토한다.
    1. 명확한 함수명을 위해 모호함을 피하고 필요한 전치사를 포함한다.
    2. 전치사만으로는 프로퍼티의 의도가 명확하지 않은 경우 전치사구를 사용한다.
    3. 영문법으로서 정확하더라도 프로퍼티가 하는 의미를 라벨로 전달해줄 필요가 있다.
4. 타입에 의한 제약과 표현력을 고려하자.
    1. 명확한 함수명을 위해 불필요한 정보는 생략한다.
    2. 형태가 약한 프로퍼티인 경우 명확하기 위해 보충한다.
5. 여러 매개변수를 가진 함수
    1. 매개변수를 구별할 필요가 있으면 라벨을 생략하지 않고 표현하자.
    2. 매개변수를가 함수의 중심이 아닌 경우에 자연스러움을 포기하자.
    3. 매개변수를를 구별할 수 없으면 모든 라벨을 생략하자.
    4. 여러 매개변수를가 하나의 전치사에 필요한 경우 전치사를 메서드에 포함시킨다.
6. side-effect를 가진 함수
    1. nonmutating 함수는 명사구와 같이 한다.
    2. mutating 함수는 명령형의 동사구로 한다.
    3. mutating과 nonmutating의 함수를 가지는 경우에 동사로 통일한다면 ed / ing를 붙인다.
    4. mutating과 nonmutating의 함수를 가지는 경우 명사로 표현하면 form 메소드명에 붙인다.
7. 생략한 내용

### 제 6장 - Foundation을 이용한 실용적인 기술

1. 단위를 취급할 때는 준비된 형태가 있어야 하는 것을 알아 두자.
2. Codable을 이용 시, CodingKeys로 lowerCamelCase로 한다.

### 부록 A 개발을 위한 문서

1. 공식 문서
    1. [Language Guide](https://www.swift.org/)
    2. [API Design Guidline](https://www.swift.org/documentation/api-design-guidelines/)
    3. [Swift Fourms](https://forums.swift.org/)
    4. [Xcode](https://developer.apple.com/kr/xcode/)
2. Swift 정보 사이트
    1. [HACKGING WITH SWFIT](https://www.hackingwithswift.com/)
    2. [Swift By Sundell](https://www.swiftbysundell.com/)
    3. [SwiftLee](https://www.avanderlee.com/)
    4. [ASCIIwwdc / wwdc-session-transcripts](https://github.com/ASCIIwwdc/wwdc-session-transcripts)

---

## 도움주신 분들

베타판 컨트리뷰터 & 리뷰어
 - 제 1장을 읽었습니다. 매우 알기 쉽게 접근할 수 있었습니다. 감사합니다 ! ! (shin-usu)

[Swift Developer Japan Discord](https://swiftdevelopers.jp/)

Twitter

 - 정말 즐겁게 읽었습니다. Swift에서 사용되는 방법이 설명되어있고 저에게 딱 맞는 책이었습니다.
후배에게 추천하고 싶을 정도입니다. (@MobileAppDevEwa)

## 피드백

> 본 책에 대한 피드백은 하단 페이지에 문의해주시기 바랍니다.
> 
> 
> [Discussions · CSBooks/EffectiveSwiftBookSamples](https://github.com/CSBooks/EffectiveSwiftBookSamples/discussions)
> 

## 무료 샘플

> 샘플 PDF를 다운로드 할 수 있습니다. 본 문을 단편적으로 수록하고 있으므로 내용은 최신이 아닐 수 있습니다.
> 
> 
> [ログイン](https://booth.pm/downloadables/2421542)
> 

## 샘플 코드

> Xcode 13.2.1 버전에서 코드를 작성하였습니다.
수정이 필요한대로 깃허브 레포지토리에 추가할 예정입니다.
> 
> 
> [https://github.com/CSBooks/EffectiveSwiftBookSamples](https://github.com/CSBooks/EffectiveSwiftBookSamples)
> 

## 책의 업데이트 내역

### 2022.03.30

- 그림 2.5 Swift의 참조 타입 인스턴스의 라이플 사이클로 약한 참조를 typo 수정

### 2022.03.29

- 출시

### 요약에 도움주신 분들

Kakao Open Chat - iOS 개발 Q&A func7님

## 페이지의 업데이트 내역

### 2022.04.02

> 1차 번역 및 요약
> 
> 
> [서막](Effective%20%20b5759/%E1%84%89%E1%85%A5%E1%84%86%E1%85%A1%E1%86%A8%20152fe.md)
> 
> [제 1장 - Swift에 익숙해지자.](Effective%20%20b5759/%E1%84%8C%E1%85%A6%201%E1%84%8C%E1%85%A1%E1%86%BC%20-%20%20b50a9.md)
> 

### 2022.04.03

> **서막, 제 1장 (오타 및 내용 개선)**
주작용 → pure functions
부작용 → side-effect
플로우 차트 변경.
>
t
