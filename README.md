# study-kafka

카프카 예제 작성 및 테스트

## 환경 구성

Kafka 2.3.0 버전 설치 및 환경 세팅
기본 설치 (포트: 9092)

## 카프카 스트림 

> `지속적`으로 `유입`되고 `나가는` 데이터에 대한 분석이나 질의를 수행하는 과정
> 데이터가 분석 시스템이나 프로그램에 도달하자마자 처리를 하기 때문에 스트림 프로세싱은 실시간 분석이라고 불린다.

#### 대비되는 개념: 배치(정적 데이터) 처리

- 배치에 비교한 장점
    - 이벤트에 즉각적으로 반응
    - 지속적인 데이터를 분석하는 것에 최적화

#### 상태 기반 & 무상태 스트림 처리

- 상태 기반 : 이전 스트림을 처리한 결과를 참조하는 경우
- 무상태 스트림 : 이전 처리와 관계없이 현재 스트림을 기준으로 처리하는 경우

### 카프카 스트림즈의 특징 & 개념

- 간단하고 가벼운 클라이언트 라이브러리
- 시스템이나 카프카에 대한 의존성이 없음
- 카프카 브로커나 클라이언트에 장애가 생겨도 스트림에 대해 1번만 처리 보장
- 한번에 한 레코드만 처리
- DSL 과 저수준의 API 제공

### 카프카 스트림 아키텍처

- 각 스트림 파티션은 토픽 파티션에 저장된 정렬된 메시지
- 스트림의 데이터 레코드는 카프카 해당 토픽의 메시지 (키 + 값)
- 데이터 레코드의 키를 통해 다음 스트림으로 전달

