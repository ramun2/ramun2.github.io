---
layout: single
title:  "아키텍처"
---
## 아키텍처
**애플리케이션 아키텍처**

- 애플리케이션 전체의 아키텍처를 다루는걸로 애플리케이션을 설계하고 구축하는데 사용하는 패턴과 기술을 설명한다.

**소프트웨어 아키텍처**

- UI와 비즈니스 로직 간의 관계를 다룬다.
- 소프트웨어 아키텍처는 ****뼈대나 고수준의 기반을 담당하는 반면 소프트웨어 디자인은 각각의 모듈들이 어떤것을 하는지, 클래스의 범위 등 코드 수준의 디자인을 담당한다.

→ 한마디로 SW 아키텍쳐 패턴은 더 큰 범주, 디자인 패턴은 더 작은 범주를 의미한다

EX) MVP의 구현 시 빌더패턴으로 Model을 옵저버 패턴으로, View를 팩토리 패턴으로 구현 할 수 있다.

- MVC, MVP, MVVM 등이 있고 이 패턴들은 따로 정리해둘 예정이다.

**애플리케이션 아키텍처엔 뭐가 있을까?**

- MA (Monolithic Archtecture)
    - UI와 비지니스 레이어, 데이터 레이어가 하나의 덩어리고 구성되있으며 하나의 데베를 여러 서비스에서 공유한다.
    - 예를 들어 위치 추적 시스템, 결제 시스템이 있으면 하나의 데이터베이스에서 운영하는거다.
    - 테스트와 개발이 간편하여 소규모 애플리케이션에서 사용한다.
- MA의 한계점
    - 프로젝트의 규모가 커질수록 빌드, 배포 시간이 길어지며 어려워져 유지보수가 어려워진다.
    - 내부 요소간의 의존성이 강하며 구조적으로 강력하게 결합되어 수평적으로 확장하기 어렵다.
    - 트래픽이 증가하면 대응하기 어렵고, 유저가 줄어들면 남는 메모리가 많아진다.
    - 특정 부분에 문제가 발생하면 전체 시스템에 영향을 미칠수 있다.
- MSA (Microservice Architecture)
    - MA처럼 하나의 단일 애플리케이션이 아닌 여러 독립적인 마이크로서비스로 구성된 아키텍처이다.
    - 각 마이크로서비스는 자신의 비즈니스 도메인에 최적화된 데베를 가질수 있다.
    - 예를 들어 위치 추적 시스템, 결제 시스템이 있으면 각자 별도의 데베를 운영한다.
    - 서비스가 잘 정의된 API를 사용하여 서로 통신하고, 각 서비스의 세부 내부 구현 정보는 다른 서비스에서 볼 수 없다. API를 통해서만 상호작용할 수 있다.
    - 한마디로 마이크로서비스는 작고, 독립적이며, 느슨하게 결합되어 있다.

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/cb105539-9547-43d0-8766-be86f9c17fb6/5d01f3fd-4a86-4ed3-920c-148cbffe26de/image.png)