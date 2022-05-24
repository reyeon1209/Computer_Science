## PART 05 네트워크 보안

### 01. 06. TCP/IP 보안 프로토콜
- 데이터링크계층: 물리 계층에서 발생할 수 있는 오류 발견
- 표현 계층: ASCII, JPEG, MPEG


### 09. SNMP (Simple Network Management Protocol)
- 에이전트는 비정상적인 상황을 관리자에게 경고하기 위하여 Trap 메시지를 관리자에게 보냄
- MIB(Management Information Base): 망 관리 자원 정보를 구조화시킨 관리객체들의 집합
- SMI(Structure of Management Infromation): SNMP에서 관리 정보의 구조로 MIB 객체를 정의하는 일반적 규칠들의 집합


### 11.91.  OSI 7계층 모델 프로토콜
- ARP 스푸핑: MAC 주소 위조 → MAC 주소는 데이터링크 계층에서 사용
- Ping of Death: ICMP 메시지 이용 → ICMP 메시지는 인터넷 계층에서 사용


### 19. TCP/IP 프로토콜 계층 & 보안기술
- Kerberos: 응용 계층 보안 기술


### 25. TCP의 3-Way Handshaking
|클라이언트|서버|
|---|---|
|closed|listen|
|SYN_sent|listen|
|SYN_sent|SYN_received|
|established|established|


### 26. TCP 연결 설정
- 연결 종료: 클라이언트가 FIN 보냄, 서버가 이에 대한 ACK 세그먼트 보냄, 서버가 FIN 보냄, 클라이언트가 이에 대한 ACK 세그먼트 보냄


### 27. TCP 헤더의 제어플래그
- URG ACK PSH RST SYN FIN


### 33. netstat 명령
- TIME_WAIT: 연결이 종료되었거나 다음 연결을 위해 대기


### 34. 네트워크 명령어
- ping: 지정한 IP 주소 통신 장비의 접속성 확인, RTT(Round Trip Time) 정보 제공
- tracert(traceroute): 거치는 구간의 정보 기록
- netstat: 연결 포트 등의 네트워크 상태 정보 확인
- nslookup: 호스트 이름을 입력하면 IP 주소 알려줌
- route: IP 라우팅 테이블을 보여줌
- nmap: 호스트, 포트, 운영체제 버전, 방화벽의 패킷 타입 등 네트워크의 특징 검사


### 42. net 명령어
- net view: 지정된 PC와 공유된 영역, 호스트 혹은 자원 정보
- net user: 시스템 계정 관련 정보
- net localgroup: 로컬 그룹에 속해져 있는 사용자 리스트
- net group: 특정 영역에 속해있는 사용자 리스트
- net use: 공유 폴더


### 43. 리눅스 네트워크 관리 도구 및 서비스
- tcpdump: 네트워크 모니터링 및 패킷 분석을 위해 사용되는 도구, 패킷 필터 기능으로 특정 침입자의 침입 경로 감시
- fping: 일정한 주소 범위에 ping을 보내기 위한 명령, 네트워크 스캐너로 사용


### 44. 윈도우즈 시스템 route PRINT -4 명령 결과
- destination: 목적지 주소
- gateway: 외부로 패킷을 포워딩하기 위한 장치의 IP 주소
- genmask: 라우팅 항목의 네트워크 마스크
- flags: U, H, G, D, M
- metric: 다음 라우터와의 거리


### 48. Wireshark
- 트래픽 수집을 위해 WinPcap 사용


### 53. IP주소
- InterNIC에서 관리하는 IP주소는 네트워크와 호스트(노드)로 구성
- IPv6: 네트워크 프래그멘테이션 증가로 인한 라우팅의 비효율성 문제 해결


### 60. 사설 IP
- A클래스: 10.0.0.0 - 10.255.255.255
- B클래스: 172.16.0.0 - 172.31.255.255
- C클래스: 192.168.0.0 - 192.168.255.255


### 62. 이더넷 물리 주소 == MAC 주소
- 6바이트 (48비트)


### 64. VLAN
- VLAN 멤버십 구성 정보: 포트번호, MAC주소, IP주소
- VLAN(IEEE 802.1Q): 그룹 단위 or 세그먼트 포트 단위의 유용성 보장을 위해 논리적 개별 스위칭 동작을 하게 하는 스위칭 LAN의 옵션 구성


### 70. 89. 스니핑
- ICMP 리다이렉트: ICMP redirect를 위조한 메시지를 만들어 호스트 패킷의 라우팅 경로 위조, 자신이 공격 대상자의 게이트웨이가 되게 함
- 전자메일: PGP(Pretty Good Privacy) 기술 이용해 방지


### 82. 84. ARP
- ARP 패킷은 데이터링크 프레임에 캡슐화
- ARP 요청 패킷은 브로드캐스트, ARP 응답 패킷은 유니캐스트
- ARP 스푸핑: 근거리 네트워크 환경에서 발생


### 86. DNSSEC
- 인증체인 형태로 확장되어 계층적 구조의 DNS 서버에도 적용


### 87. DNS 서버 레코드
- A (Address): 도메인 주소에 대해 IP 주소 맵핑
- PTR (Pointer): IP 주소에 대해 도메인 명 맵핑
- NS (Name Server): 각 도메인에 적어도 하나 이상 있어야 하는 DNS 서버
- MX (Mail Exchange): 도메인 이름으로 보낸 메일을 받는 호스트 목록 지정
- CNAME (Canonical Name): 호스트의 다른 이름 정의
- SOA (Start Of Authority): 도메인에 대한 권한 있는 서버 표시
- HINFO (Hardware Info): 해당 호스트의 하드웨어 사양 표시
- ANY (ALL): DNS 레코드 모두 표시


### 96. 107. DDoS 공격 기법
- Trin00: 미네소타 대학 사고의 주범, UDP 공격
- TFN
- Stacheldraht


### 98. Smurf 공격 == ICMP Flooding


### 106. 110. 137. DoS
- 대상 포트 번호를 확인하여 17, 135, 137번 UDP 포트 스캔이 아니면 UDP Flooding 공격으로 간주
- SYN Flooding: 다른 DoS 공격에 비해서 작은 수의 패킷으로 공격 가능
- Targa/NewTear/Nestea 공격


### 106. IP 스푸핑
- 신뢰 관계에 있는 두 시스템 사이에 공격자 호스트를 하나의 신뢰 관계처럼 속임


### 112 리눅스 커널 보안
- ping 요청을 응답하지 않게 설정


### 114. HTTP CC(Cache-control) 공격
- CC 헤더 옵션에서 캐시 기능을 사용하지 않게 하면 웹 서비스의 부하 증가


### 132. 공격기법
- Heap Spraying: 코드 삽입을 위한 사전 단계, 비정상적인 메모리 주소로 jump/call
- CSRF(크로스사이트 요청 위조): 사용자의 의도와 무관하게 공격자가 의도한 행위 요청


### 134. DRDoS
- TCP 프로토콜 및 라우팅 테이블 운영상의 취약성 이용
- 출발지 IP 주소 위조


### 139. TCP 세션 하이재킹
- ARP 스푸핑과 같은 추가적인 공격 기술 필요

