## Management > Service Monitoring > 릴리스 노트

### 2020. 03. 24.

#### 기능 개선
* 웹 모니터링 데이터 검증 시 [JsonPath 메서드](/Management/Service%20Monitoring/ko/console-guide/#_9) 제공
* 이메일 장애 메시지에 _조직명_, _프로젝트명_ 추가
* [다중 배치 모니터링 검증 API](/Management/Service%20Monitoring/ko/api-guide/#_5) 지원
* 배치 모니터링 내용 검증 결과 중 실패한 내용 강조 표시

### 2020. 01. 21.

#### 기능 개선
* 웹/TCP 모니터링 US 리전 지원
* 모니터링 히스토리 검색 시 모니터링 리전 옵션 추가

### 2019. 12. 24.

#### 기능 개선
* 장애 전파 실패 시 히스토리 상세 내역 메시지 개선
* 웹 페이지 성능 향상

#### 버그 수정
* 전파 현황 페이지에서 서비스 전파 담당자가 아닌 사용자에게는 전파 내역이 보이지 않는 문제 수정

### 2019. 11. 26.

#### 기능 개선
* 전파 현황 페이지에서 전파 상태 정보 분리 노출.
* 사용자 언어가 영어일 경우 일부 UI가 깨지는 현상 수정.
* 웹 모니터링 시나리오 편집 기능 개선
  * 텍스트 검증 시 연산자에 따라서 placeholder 다르게 표시되도록 개선.
  * [시나리오 검증 타입]에 따라 텍스트 검증 연산자 노출 제한.
  * [시나리오 검증 타입]이 모듈일 경우에도 **스크립트 에러무시**, **이미지 다운로드 제외**, **CSS 활성화** 옵션을 사용할 수 있도록 개선.

#### 버그 수정
* [장애 전파 취소 안내] 메일 전송시 각 메일 내의 취소한 사용자 이름 대산 수신자 이름으로 전달되는 문제 수정.

### 2019. 08. 27.

#### 기능 개선
* 일본어 글꼴을 TOAST 공통 글꼴로 변경하였습니다.
* TCP 모니터링 시나리오 편집 화면에서 IP, PORT 입력 레이블을 분리해 가독성을 향상했습니다.

#### 버그 수정
* [전파 상세 보기] 화면에서 시간이 제대로 표시되지 않는 문제를 개선하였습니다.
* 모니터링 장애를 등록할 때, 시나리오 저장 시 설정한 언어로 전파 제목이 등록되도록 개선하였습니다.
* 장애 전파 메시지에서 장애 알림 페이지에 접속할 때, 만료되지 않았음에도 만료되었다고 나오는 현상을 개선하였습니다.
* 일본어 장애 전파 메시지의 제목이 잘못 추가되는 문제를 개선하였습니다.

### 2019. 07. 23.

#### 신규 서비스 출시
Service Monitoring은 안정적인 서비스 운영을 위한 서비스 장애 관리 플랫폼입니다. 
	* 서비스별 전파 담당자, 전파 채널 관리
	* 다양한 모니터링 방식 지원 - 웹 모니터링, TCP 모니터링, 배치 모니터링