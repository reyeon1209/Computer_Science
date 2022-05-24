## PART 07. 네트워크 정보보호

### 02. 패킷 필터링
- 네트워크 계층 & 전송 계층에서 동작


### 04. 포트번호
- IMAP: TCP 143
- POP3: TCP 110


### 07. 필터링
- egress 필터링: 라우터 내부에서 외부로 나가는 패킷의 소스 IP 검사
- ingress 필터링: 라우터 외부에서 내부로 유입되는 패킷 필터링
- black hole 필터링: null routing을 이용한 필터링, 특정한 IP 대역에 대해 가상의 null 인터페이스로 보냄 → 패킷 통신 X


### 09. 10. 방화벽
- 패킷 필터링: 트래픽 정보 수집 어려움, IP 스푸핑 공격 대응 어려움
- 상태 검사(stateful inspection): 패킷 필터링 기능을 사용, 현재 연결 세션의 트래픽 상태와 미리 저장된 상태와의 비교를 통해 접근 제어
- 응용 레벨 게이트웨이: 서비스별로 프록시 서버 데몬을 두어 사용자 인증 & 접근 제어 수행
- 회선 레벨 게이트웨이: 송수신자 간의 직접 연결 X, 프록시가 연결 판단, ex) SOCKS


### 25. 26. 방화벽 구축 형태
#### (1) 베스천 호스트 (Bastion Host)
- 베스천 호스트가 손상되면 내부 네트워크 보호 X
- 로그인 정보가 누출되면 내부 네트워크 보호 X
#### (2) 스크리닝 라우터 (Screening Router)
- 인증 기능 X
#### (3) 듀얼 홈드 게이트웨이 (Dual Homed Gateway)
#### (4) 스크린드 호스트 게이트웨이 (Screened Host Gateway)
- 외부 네트워크 - 스크린 라우터 - 베스천 호스트 - 내부 네트워크
#### (5) 스크린드 서브넷 게이트웨이 (Screened Subnt Gateway)
- DMZ: 보안 조치가 취해진 네트워크 영역, 웹/이메일/DNS서버와 같이 반드시 외부로 연결할 수 있어야 함(DB X), 내부 방화벽과 외부 방화벽 사이 위치


### 32. 42. IDS (Intrusion Detection System)
- 호스트기반 침입탐지시스템: 시스템의 로그에 대한 탐지가 우선
- 오용 탐지/시그니처 기반 감지: 상태전이 분석, 패턴 매칭, 전문가 시스템


### 44. 45. 46. NIDS / HIDS
#### (1) NIDS (Network-based Intrusion Detection System)
- 운영체제/하드웨어에 독립적
- 캡처된 트래픽에 대해 침입자가 흔적 제거 어려움
- 암호화된 패킷 분석 불가능
- 탐지된 침입의 실제 공격 성공 여부를 네트워크 단에서 모름
- 패킷이 라우터로 들어오기 전, 라우터 뒤, 방화벽 뒤, 내부 네트워크, DMZ 등 설치

#### (2) HIDS (Host-based Intrusion Detection System)
- 고부하/스위치 네트워크에서도 적용 가능
- 우회 가능성 X
- 중요한 곳에 설치


### 50. Snort
- 침입 탐지 & 방지 시스템 (IDS & IPS)
- Rule을 이용한 침입탐지 분석 기능
- 실시간 트래픽 분석, 프로토콜 분석 가능


### 57. DLP (Data Leak Prevention)


### 63. 65. 66. 71. VPN
- 터널링 프로토콜: 2계층-PPTP, L2F, L2TP 3계층-IPSec
- PPTP: MS에서 개발, PPP를 기반으로 함
- 서로 다른 통신 프로토콜의 패킷 안에 패킷을 캡슐화해 네트워크 사이에서 데이터 전송


### 74. 76. 78. 79. 80. 84. 88. 90. 92. 93. 95. 100. IPSec
- AH와 ESP 사용을 위해 Security Association(보안 연계)가 설정되어야 함 → ISAKMP 프로토콜
- SA는 양방향으로 통신하는 호스트 쌍에 송수신을 위해 사용할 키가 각 방향 상에서 필요하다 (2쌍)
- 일반적으로 호스트는 보안 연관 매개변수들을 보안 연관 데이터베이스에 저장하여 사용
- 상위 계층 보안이 필요한 VPN 제공 가능
- 재전송 공격을 막기 위해 IP 패킷별로 순서번호 부여
#### (1) 인증 (AH: Authentication Header)
- HMAC, 메시지인증코드 사용 → 재전송 공격 방지, 무결성, 개체 인증
- 터널모드: IP 패킷 전체에 적용, 새로운 헤더 추가, **New IP Header** - IPSec Header - Origin IP Header - TCP Header - TCP Data
- 전송모드: IP 헤더를 제외한 부분에 적용, Point-to-Point 연결 제공, 송신자와 수신자가 모두 호스트인 경우에 사용, IP Header - IPSec Header - TCP Header - TCP Data
#### (2) 캡슐화 보안 페이로드 (ESP: Encapsulating Security Payload)
- 기밀성 제공 (+ 선택적 인증, 선택적 무결성, 재전송 공격 방지)
- 암호화: 페이로드, ESP 트레일러(패딩, Next Header)
- 암호화 X: SPI(Security Parameter Index), Sequence Number 필드
- 터널모드 & 전송모드 둘 다 적용 가능
- 터널모드에서 AH와 ESP 동시 사용 불가
#### (3) 키 관리
- IKE(Internet Key Exchange) 사용 →  인증서 요청(Certificate Request) 페이로드 사용 가능
- 두 컴퓨터 간 보안 연결 설정

|서비스|사용 기술|
|---|---|
|암호화|DES, 3-DES|
|무결성|HMAC|
|보안 파라미터 협상 프로토콜|IKE|
|공유 비밀키 분배 프로토콜|Diffie-Hellman 알고리즘|


### 105. 107. NAC (Network Access Control)
- 사용자의 보안 상태와 보안 프로그램들의 상태 정보 확인 → 적절한 보안 기능을 갖추지 못한 경우 자동 격리 & 치료
- Endpoint가 처음 내부망 네트워크에 접근을 시도할 때, 내부망에 피해가 없도록 Endpoint에 일련의 보안정책 적용
- 802.1x방식, VLAN 방식 등으로 구현
- 네트워크 접근 시 인증을 위해 Active Directory, Kerberos, LDAP 등 사용


### 109. SIEM (Security Information Event Management)
- 보안 시스템의 로그를 실시간으로 수집 & 분석 & 대응방안 제공

