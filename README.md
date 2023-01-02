# SpringBoot Study

## thymeleaf_basic

- Thymeleaf 기본 기능 예제
- Controller에서 HTML 페이지로 객체 송,수신 방법
- HTML 페이지에서 Thymeleaf를 사용해 객체 접근 방법
- Thymeleaf의 조건문, 반복문, 연산, layout 등에 대해 정리

## thymeleaf_form

- Thymeleaf 폼 관련 예제
- 학생 추가 Form을 통해 학생에 대한 정보를 입력받고 리스트로 출력하는 예제
  - HTML, Thymeleaf를 활용한 Form 생성 (th:field 활용)
  - Form 입력 값을 Controller로 수신 방법
  - input 태그 외에도 radio, checkbox, select 등의 태그 입력 방법
  - properites 파일을 활용한 메세지, 국제화 기능 추가 

![](https://blog.kakaocdn.net/dn/b3vfCQ/btrQtRLvUpf/zq3xSmMGiZ3hHKU6YoGbJ0/img.png)

## basic_board

- DB를 사용하지 않은 게시판 구현 예제
  - 게시물 CRUD 기능 구현
  - 파일 첨부 기능 및 다운로드 기능 구현
  - 이미지 업로드 및 미리보기 기능 구현

![](https://blog.kakaocdn.net/dn/3ICS3/btrP7NJztSf/jUO3ejt0zFotaNTSOtGFQ1/img.png)
![](https://blog.kakaocdn.net/dn/bSLJJs/btrRd62noh4/rcTeBCKJJHCe7FkVz4n63K/img.png)

## validation_example

- Thymeleaf로 만든 Form을 활용해 Validation(검증)하는 예제
  - field error, global error 사용
  - error.properties를 활용한 에러 메세지 설정

## entityManager_example

- Entity Manager을 주입 받아 MySQL DB에 Data CRUD 예제

## jparepository_example

- Jpa Repository를 사용해(상속 받아) MySQL DB에 Data CRUD 예제

## jpa_mapping_example

- Jpa Repository를 사용한 1:1, 1:N, N:M 연관관계 매핑 예제
- 1:N 연관관계 매핑 => Team : Player = 1 : N 관계
  - Team 등록, Player 등록 구현
  - Team 조회 시 해당 Team에 속한 Player들의 이름도 return
  - Player 조회 시 해당 Player가 속한 Team의 이름도 return
- 1:1 연관관계 매핑 => Customer : Seat = 1 : 1 관계
  - @PostConstruct를 사용해 초기 데이터 생성
  - customerId와 seatId를 입력받아 좌석 예약 기능 구현
  - Seat의 rowId, colId를 입력받아 해당 좌석의 예약 상황 조회 기능 구현
- N:M 연관관계 매핑 => Examinee : Academy = N : M 관계
  - 수험생 학원 등록 기능 구현 + 등록 날짜 추가
  - 모든 등록 조회 기능 구현
  - 수험생 조회 기능 구현 => 수험생이 등록한 모든 학원 이름 리스트도 출력
  - 학원 조회 기능 구현 => 학원에 등록한 모든 수험생 이름 리스트도 출력

## circular_referance_example

- Jpa 연관관계 매핑 시 순환 참조 문제를 해결하는 방법
  1. @JsonIgnore 어노테이션 사용
  2. @JsonManagedReference, @JsonBackReference 어노테이션 사용
  3. **DTO 활용**
  4. 단방향 매핑으로 수정

## filter_interceptor_example

- Filter와 Interceptor 사용 예제
- LogFilter와 LogInterceptor을 생성, 등록하여 모든 요청에 대한 로그를 찍는 예제
- AuthFilter와 AuthInterceptor을 생성, 등록하여 특정 요청에 대해 인증을 진행하여 통과시키거나 통과시키지 않는 예제
- Filter와 Interceptor을 동시에 적용하는 요청을 만들어 테스트 => Filter, Interceptor의 실행 순서 확인