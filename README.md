# java-racingcar-precourse

## 자동차 경주

### 기능 요구 사항

> 초간단 자동차 경주 게임을 구현한다.

- 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.
- 각 자동차에 이름을 부여할 수 있다. 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다.
- 자동차 이름은 쉼표(,)를 기준으로 구분하며 이름은 5자 이하만 가능하다.
- 사용자는 몇 번의 이동을 할 것인지를 입력할 수 있어야 한다.
- 전진하는 조건은 0에서 9 사이에서 무작위 값을 구한 후 무작위 값이 4 이상일 경우이다.
- 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한 명 이상일 수 있다.
- 우승자가 여러 명일 경우 쉼표(,)를 이용하여 구분한다.
- 사용자가 잘못된 값을 입력할 경우 IllegalArgumentException을 발생시킨 후 애플리케이션은 종료되어야 한다.

### 입출력 요구 사항

- 입력
    - 경주할 자동차 이름(이름은 쉼표(,) 기준으로 구분)
  > pobi,woni,jun
    - 시도할 횟수
  > 5
- 출력
    - 차수별 실행 결과
  > pobi : --
  >
  >woni : ----
  >
  >jun : ---
    - 단독 우승자 안내 문구
  > 최종 우승자 : pobi
    - 공동 우승자 안내 문구
  > 최종 우승자 : pobi, jun

### 구현할 기능 목록

#### 입출력 파트

##### 입력

- [x] 사용자 자동차 이름 입력
- [x] 사용자 시도할 횟수 입력

##### 출력

- [x] 차수별 실행 결과 출력
- [x] 단독 우승자 or 공동 우승자 안내 문구 출력

#### 기능 파트

- [x] 입력된 문자열 파싱 기능
- [x] 자동차 저장 기능
- [x] 자동차 전진 기능
    - [x] 자동차 전진 여부 선정 기능(랜덤값 기준)
- [x] 레이스 기록 저장 기능
- [x] 우승자 선정 기능

#### 예외 처리 파트

- [x] 사용자가 잘못된 값을 입력하면 예외 발생 기능

### 프로젝트 패키지 구조

```
.
└── java
    └── racingcar
        ├── Application.java
        ├── config
        │   └── AppConfig.java
        ├── controller
        │   ├── RacingCarController.java
        │   └── RacingCarControllerImpl.java
        ├── converter
        │   └── RacingHistoryConverter.java
        ├── dto
        │   ├── CarDto.java
        │   └── RacingHistoryDto.java
        ├── model
        │   └── domain
        │       ├── Car.java
        │       ├── RacingHistory.java
        │       ├── comparator
        │       │   └── CarMovedDistanceComparator.java
        │       └── vo
        │           ├── CarName.java
        │           └── Distance.java
        ├── repository
        │   ├── CarRepository.java
        │   ├── InMemoryCarRepository.java
        │   ├── InMemoryRacingHistoryRepository.java
        │   └── RacingHistoryRepository.java
        ├── service
        │   ├── CarService.java
        │   ├── CarServiceImpl.java
        │   ├── InputParsingService.java
        │   ├── InputParsingServiceImpl.java
        │   ├── RacingHistoryService.java
        │   ├── RacingHistoryServiceImpl.java
        │   ├── RacingService.java
        │   └── RacingServiceImpl.java
        └── view
            ├── ConsoleInputView.java
            ├── ConsoleOutputView.java
            ├── InputView.java
            └── OutputView.java
```
