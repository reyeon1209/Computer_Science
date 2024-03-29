## PART 02. 운영체제론


### 4. 운영체제
- Symbian: 심비안사가 휴대폰용으로 개발한 실시간 처리의 32비트 멀티태스킹 운영체제
- Solaris: 마이크로시스템즈사의 유닉스 운영체제, 주로 웹서버용


### 10. 운영체제가 프로세스를 생성하는 과정
- 프로세스 식별자 할당
- 주소공간, 프로세스 제어블록(PCB) 할당
- 프로세스 제어블록(PCB) 초기화
- 스케줄링 큐의 준비 or 준비/보류 리스트에 연결


### 12. 프로세스 상태 변이
- block: 현재 실행 중이던 프로세스가 지정된 시간 이전에 입출력 요구에 의하여 스스로 CPU를 반납하고 대기 상태로 전이하는 것


### 25. 프로세스 메모리 영역
- 데이터 영역: 프로그램의 가상주소 공간, 전역변수나 정적변수 할당


### 27. 28. 스레드
- Pthread: 스레드 생성과 동기화를 위해 POSIX가 제정한 표준 API
- 공유 영역: 코드, 데이터, 파일
- 비공유 영역: 레지스터, 스택


### 47. 49. 프로세스 스케줄링
- 다단계 피드백 큐(MFQ): CPU 위주 프로세스보다 입출력 위주 프로세스를 선호, 실시간 OS에 적합
- FCFS: 일괄처리 시스템에 적합, 대화형 시스템 X


### 66. 스풀링 (Spooling)
- CPU와 입출력 장치의 속도 차이를 줄이기 위해 디스크의 일부분을 버퍼처럼 사용하는 것


### 83. 교착상태
- 은행원 알고리즘: 교착상태 회피


### 101. TLB (Translation Lookaside Buffer)
- 가상기억장치에서 가상주소와 실주소를 저장해주는 일종의 캐시기억장치


### 130. 스레싱 (Thrashing)
- 작업 집합 기법과 페이지 부재 빈도 기법은 한 프로세스를 중단시팀으로써 다른 프로세스들의 스레싱을 감소시킬 수 있다.


### 138. 디스크 스케줄링
- 섹터 큐잉(Sector Queuing): 고정 헤드 장치에 사용되는 기법, 디스크 회전 지연 시간 고려
- SSTF: 대화형 시스템 X
- C-SCAN: 대기시간 균등화, SCAN 알고리즘 개선


### 148. 유닉스 운영체제의 커널
- 스케줄러
- 파일 관리자
- 메모리 관리자


### 149. 유닉스 프로세스 간 통신 (Interprocess Communication)
- 공유메모리에 대한 상호배제는 운영체제가 보장 X


### 150. 유닉스 명령어
- df: 파일시스템 디스크 공간의 사용량 출력
- diff: 파일을 줄 단위로 비교하여 출력
- ps: 프로세스 상태 확인
- ln: 파일 링크 생성
- touch: 빈 파일 생성 or 기존 파일의 시간 변경
- uname: 시스템 정보 출력


### 152. 유닉스 명령어
- ls 명령어: 하드링크 계수
- 직접 블록 포인터와 단일/이중/삼중 간접 블록 포인터로 구성된 인덱스 정보는 i-node 내에 포함


### 156. fork() 함수
- 부모 프로세스에게 자식프로세스의 PID 반환
- 자식 프로세스에게 0 반환


### 158. 윈도우 명령어
- dxdiag: DirectX 진단 도구를 이용하여 컴퓨터 사양 확인

