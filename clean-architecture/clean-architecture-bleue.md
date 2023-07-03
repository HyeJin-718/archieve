# 클린 아키텍처

[클린아키텍처 이미지](../resources/CleanArchitecture-bleue.jpeg)

## 엔티티 😀

기업 규모의 비지니스 규칙
기업 규모가 아닌 하나의 어플리케이션이라면 엔티티는 어플리케이션의 비지니스 객체임
데이터 구조, 객체(함수/메소드)가 엔티티가 될 수 있음
제일 높은 레벨의 규칙으로 캡슐화 됨.
외부의 변화에 제일 변하지 않는다.

## 유즈 케이스

애플리케이션별 비지니스 규칙이 포함됨
시스템의 모든 사용 사례를 캡슐화 하고 구현
기업 전체의 비지니스 규칙을 사용하여 유즈 케이스의 목표 달성

## 인터페이스 어댑터

데이터를 유즈케이스 및 엔티티에 가장 편리한 형식에서 데이터베이스, 웹과 같은 외부와 편리한 형식으로 변환하는 어댑터

## 프레임워크 드라이버

가장 바깥쪽 계층
웹 프레임워크, 데이터베이스 등 도구
세부정보/세부사항

## Dependency Rule

소스코드의 종속성은 내부만 가리킬 수 있음
안쪽으로 갈 수 록 추상화의 수준이 높아짐
가장 밖의 원은 낮은 수준의 콘크리트 세부 사항
내부로 이동할 수록 더 추상적으로 변하고, 높은 수준의 정책을 캡슐화

## 외부 통신

컨트롤러/프레젠터가 다음 계층의 유즈케이스와 통신
컨트롤 흐름 기록 -> 컨트롤에서 시작 -> 사용사례 -> 프레젠터 실행

유즈케이스가 프레젠터를 호출할때 종속성 규칙을 위반할 수 있으므로 해당 호출은 직접적이면 안됨 => 외부의 원의 이름은 내부 원에서 언급 X => 유즈케이스를 이용하여 내부 원에 있는 인터페이스를 호출하고 외부 원에 있는 프레젠터가 해당 내용을 구현

## 추상화

복잡한, 자료, 모듈, 시스템등으로부터 핵심적인 개념 또는 기능을 간추리는 것
복잡한걸 단순하게 만들어서 더욱 복잡한 내용을 구현할 수 있음