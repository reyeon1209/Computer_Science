## PART 08. 웹 보안과 전자상거래 보안

### 4.이메일/전자우편 보안성 향상
- PEM, S/MIME, PGP


#### 5. SMTP
- 실행 파일이나 2진 데이터를 텍스트 형태로 변환하여 전송
- SMTP 서버는 특정 크기 이상의 메일 메시지 처리 X


### 6. SMTP 명령어
- HELO: 클라이언트 호스트 인증
- VRFY: 클라이언트가 SMTP 서버에게 받는 쪽 주소를 확인


### 10. IMAP
- 사용자가 폴더를 생성하고 폴더에 메시지를 할당


### 11. 인터넷 메일 구조
- MTA(메세지 전송 에이전트): 메시지가 목적지 MDA에 도달할 때까지 중계 역할
- MAA(메세지 접근 에이전트): 메일 서버에 접근하여 사용자 메일박스로부터 메세지 가져옴 (IMAP, POP3)
- MUA(메세지 사용자 에이전트): 사용자 actor와 사용자 응용프로그램을 대신하여 동작
- MSA(메세지 제출 에이전트): MUA에 의해 제출된 메시지를 받아들임
- MDA(메세지 배달 에이전트): 메세지를 MHS에서 MS로 전달
- MS: 메세지 저장소

### 12. 13. 15. 19. 20. 23. PGP (Pretty Good Privacy)
- 필 짐머만 개발
- 대칭키를 이용한 암호화(기밀성) & 공개키를 이용한 전자서명(무결성, 부인방지, 인증)
- 플러그인 방식으로 확장 가능
- 특정 인증기관의 개입 X
- 데이터를 압축해서 암호화
- 공개키 취소 증명서 발행 가능
- 다수의 사람들에게 메시지 전송할 때, 키 링(Key Ring) 필요
- 공개키 인증을 위해 PGP 인증서 사용, 인증기관 X
- 대용량 이메일을 단편으로 쪼개 전송


### 24. 27. S/MIME (Secure/Multipurpose Internet Mail Extension)
- IETF 작업 그룹에서 RSADSI 기술 기반으로 개발
- 대칭키 암호화(RSA), 전자서명(DSS), MD 생성(SHA-1)
- X.509 형식의 공개키 인증서 사용


### 29. PEM
- IETF 에서 만듦
- 자동 암호화로 전송 중 유출되더라도 내용 확인 불가능


### 37. 54. SSL 프로토콜
- 단편화 - 압축 - MAC 추가 - 암호화 - SSL 레코드 헤더 추가
- 대칭키 암호 사용 but 클라이언트→서버 != 서버→클라이언트
- SSL 암호 사양 변경 프로토콜: 핸드셰이크 프로토콜에 의해 협상된 암호 규격과 암호키를 이용하여 레코드 계칭의 메시지를 보호할 것을 지시

|||||
|---|---|---|---|
|SSL 핸드쉐이크 프로토콜|SSL 암호 사양 변경 프로토콜|SSL 경고 프로토콜|상위 응용 프로토콜|
||SSL 레코드 프로토콜|||


### 42. SSL 핸드쉐이크 프로토콜
- 보안 능력 (프로토콜 버전, 암호화 방식 등) 협상
- 서버 인증 or 키 교환
- 클라이언트 인증 or 키 교환
- 협상된 보안 알고리즘에 따른 메시지 교환


### 45. 46. SSL 핸드쉐이크 프로토콜
#### (1) 보안설정 단계
- client_hello(필수): 버전, 랜덤 넘버, 세션ID, 암호도구, 압축방법 ... 포함된 메시지
- server_hello(필수): 서버가 선택한 버전, 서버가 생성한 랜덤 넘버, 서버가 선택한 암호도구, 압축방법 ... 포함한 메시지
#### (2) 서버 인증과 키 교환
- certificate(선택): 서버의 인증서 전달
- server_key_exchange(선택): 서버의 키 교환
- certificate_request(선택): 클라이언트 인증서 요청
- server_hello_done(필수)
#### (3) 클라이언트 인증과 키 교환
- certificate(선택): 클라이언트의 인증서 전달
- client_key_exchange(필수): 클라이언트의 키 교환
- certificate_verify(선택): 인증서 확인정보
#### (4) 종료
- change-cipher-spec(필수): 안전한 연결설정 완성
- finished(필수): 핸드셰이크 프로토콜 종료


### 58. 60. 64. TLS (Transport Layer Security)
- SSL을 기반으로 한 IETF 인터넷 표준
- FTPS: TLS 사용
- MQTT 응용 계층 프로토콜의 보안에 TLS 사용


### 61. WTLS (Wireless Transport Layer Security)
- 클라이언트(모바일 장비)와 WAP 게이트웨이 간 보안

|||||
|---|---|---|---|
|WTLS Handshake|WTLS Change-Cipher Spec|WTLS Alert|WTP|
||WTLS Record|||
||Datagram Protocal(WDP or UDP)|||


### 65. 66. 67. HTTPS
- HTTP over SSL/TLS/Secure
- 암호화 요소: 요청 문서 URL, 문서 내용, 입력한 브라우저 양식 내용, 브라우저-서버 사이 쿠키, HTTP 헤더 내용
- 200 OK
- 201 Created
- 400 Bad Request
- 403 Forbidden: 서버가 페이지 접근 허용 거부
- 500 Internal Server Error


### 70. HTTP ver 1.1
- 요청 메시지의 첫 줄인 요청 라인에는 메소드, URL, HTTP 버전 필드가 포함
- 기본: 지속 연결(요청과 그에 대한 응답이 같은 연결로), 지원: 비지속 연결(분리된 별도의 연결을 이용)


### 71. HTTP
- ver 1.0: RFC 1945
- ver 1.1: RFC 2616


### 74. SSH(Secure SHell) 프로토콜
- TCP 기반의 보안 프로토콜
- 터널링 지원 (SSH 클라이언트-서버 사이 연결)

|||
|---|---|
|SSH 사용자 인증 프로토콜|SSH 연결 프로토콜|
|SSH 전송 계층 프로토콜||
|TCP||
|IP||
- SSH 연결 프로토콜: 암호화된 터널을 여러 개의 논리적 채널로 다중화
- SSH 전송 계층 프로토콜: 서버 인증 & 기밀성 & 무결성 제공, 압축(옵션)


### 76. FTP 보안
- 임의의 계정으로 로그인 시도를 반복적으로 수행하여 사용자 계정의 패스워드를 유추할 수 있는 취약점
- 사용자 인증정보 유출 방지를 위한 보안 대책: SCP, SFTP, FTPS
- 익명 FTP: 암호 X


### 78. FTP 연결 방식
||능동 모드(Active Mode)|수동 모드(Passive Mode)|
|---|---|---|
|데이터 전송 시 |20번 포트 사용|임의의 번호로 할당한 포트 사용|


### 80. FTP 클라이언트 명령어
- lcd: 지역 호스트의 작업 디렉터리 변경
- hash: 파일이 전송되는 진행 상황을 알려줌
- mget: 여러 개의 파일을 원격 호스트에서 지역 호스트로


### 81. DTLS
- CoAP: DTLS 사용


### 84. SET(Secure Electronic Transaction)
- 대칭키 & 공개키 모두 사용


### 88. 89. 91. 블록체인
- 블록: 트랜잭션의 집합 + 헤더
- 하이퍼레저 패브릭(Hyperledger Fabric): 공개키 인증서를 이용하여 peer에 대한 identity 정보 제공
- 공개키의 해시값이 암호화폐를 주고 받는 주소값으로 사용


### 92. 93. 비트코인 블록헤더
- 6가지 필드 80 Byte
- 버전: 소프트웨어 버전, 4 Byte
- 비트: 4 Byte
- 이전 블록 해시: 32 Byte
- 시간: 블록 생성 시간, 4 Byte
- 머클해시: 거래 정보 해시, 32 Byte
- nonce: 4 Byte


### 94. 95. 블록체인 합의 알고리즘
#### (1) 작업증명 (PoW: Proof of Work)
- 컴퓨터의 연산 능력이 빠를수록 더 많은 기록 권한 부여
#### (2) 지분증명 (PoS: Proof of Stake)
- 지분이 많을수록 더 많은 기록 권한 부여
#### (3) 위임지분증명 (DPoS: Delegated Proof of Stake)


### 98. FDS (Fraud Detection System)
- 이상거래 탐지 시스템
- 거래 패턴을 분석하여 금융 사기 유형 거래를 사전에 탐지/차단


### 105. OWASP 웹 취약점 TOP 10

- 취약한 접근통제 (Broken Access Control)
- 암호화 오류 (Cryptographic Failures)
- 인젝션 (Injection)
- **안전하지 않은 설계 (Insecure Design)**
- 잘못된 보안 구성 (Security Misconfiguration)
- 취약하고 오래된 요소 (Vulnerable and Outdated Components)
- 식별 및 인증 오류 (Indentification and Authentication Failures)
- **소프트웨어 및 데이터 무결성 오류 (Software and Data Integrity Failures)**
- 보안 로깅 및 모니터링 오류 (Security Logging and Monitoring Failures)
- **서버 측 요청 위조 (Server-Side Request Forgery)**


### 136. SQL Injection 공격 보안 대책
- Prepared Statement 객체 등을 이용하여 DB에 컴파일된 퀴리문을 전달


### 138. 웹쉘 (Web Shell)
- 파일 업로드 취약점 이용
- 웹 서버에 명령을 실행하여 관리자 권한 획득


### 139. 리버스 텔넷 (Reverse Telnet)
- 웹 서버는 보통 방화벽 안에 존재
- 방화벽 내부에서 외부로 나가는 패킷에 대한 아웃바운드 필터링이 없는 취약점 이용


### 144. 인증 우회 공격
- XQuery를 사용하여 XML 데이터에 대한 동적 쿼리 생성 시 외부 입력에 대한 유효성 검증 누락


### 147. 비밀번호 설계
- 해시함수 실행은 서버에서


### 150. Injection 취약점 갖는 PHP 함수
- exec: 시스템 호출 시 결과 저장
- system: 시스템 호출 시 결과 출력
- eval: php 코드 평가


### 152. 웹 방화벽
- WebKnight, ModSecurity


### 160. SSID (Service Set ID)
- 무선 네트워크 access point 이름
- 무선 랜을 통해 전송되는 패킷들의 각 헤더에 붙는 고유 식별자


### 163. 무선랜 보호 기술
- WiFi Protected Access Enterprise
- WiFi Protected Access
- Wired Equivalent Privacy


### 169. 185. 무선 통신 보안 기술
- 인증 및 인가, 과금을 위해 RADIUS 프로토콜 사용
- RADIUS(Remote Authentication Dial-In User Services): AP와 인증서버 사이, 서버/클라이언트 방식으로 동작, 응용계층


### 182. 183. 무선 LAN 보안
- WEP: 64비트 WEP 키가 수분 내 노출되어 보안 취약
- WAP: 48비트 길이의 IV(초기벡터)를 사용해 인증


### 187.KRACK (Key Reinstallation Attacks)
- WPA2 공격
- 4-way handshake 과정에서 메시지 조작 & 재전송
- Diameter 프로토콜: RADIUS보다 세션관리, 보안 측면에서 개선/확장


### 191. IEEE 802.11i의 키 관리
- PSK(Pre-Shared Key): AP와 STA가 공유하는 비밀키
- MSK(Master Session Key): 인증 단계에서 생성
- PMK(Pairwise Master Key): PSK라면 PSK를 PMK로 사용, MSK라면 MSK 일부를 PMK로 사용
- PTK(Pairwise Transit Key): AP와 STA가 상호 인증을 끝내고 통신 시 사용, PMK를 사용하여 생성
- TK(Temporal Key): PTK의 일부


### 193. 194. 195. 196. 블루투스 취약점
- OPP(OBEX Push Profile): 블루투스 장치끼리 인증 없이 정보 교환
- 블루스나프: 주소록, 달력 등 저장된 데이터 내용 열람
- 블루프린팅: 블루투스 장치 검색 & 모델 확인
- 블루버그: 장치에 대한 접근권한 획득
- 블루재킹: 같은 메시지를 메일처럼 전송
- 블루본: 원격 제어 권한 획득


### 199. 안드로이드 보안 체계
- 응용 프로그램은 샌드박스 프로세스 내부에서 실행
- 시스템과 다른 응용 프로그램 접근 통제