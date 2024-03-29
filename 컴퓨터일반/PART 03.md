## PART 03 데이터 통신론

### 03. 동기식 전송
- 정해진 숫자만큼의 문자열을 묶어 일시에 전송
- 24000bps 이상 속도의 전송과 원거리 전송에 이용
- 블록과 블록 사이에 유휴시간이 없어 전송효율이 높음
- 데이터 블록의 앞쪽에 동기문자 추가


### 04. 신호해석
- 80baud의 변조속도와 2위상 편이 변조 방식으로 데이터 전송, 1분 동안 전송할 수 있는 full word의 수?
- BPS = Baud * 주기 당 전송 비트 수
- 2위상 = 1비트
- 80baud * 1bit = 8bps
- 1초에 80bit → 1분은 80*60=4800bit
- full word는 4Byte = 32bit
- 48000 / 32 = 150


### 13. 14. 18. LAN의 토폴로지
- 버스형: 터미네이터(신호가 케이블로 돌아오는 것 방지), 연결 노드 수나 트래픽이 증가하면 네트워크 성능이 크게 저하됨
- 링형: 하나의 패킷씩만 전송하므로 충돌X, FDDI
- 트리형: 허브 장비 필요, 네트워크 관리 용이


### 19. 20. 21. 다중화 방식
#### (1)  주파수분할 다중화 방식(FDMA)
#### (2)  시분할 다중화 방식(TDMA)
- 동기 시분할 다중화 방식(STDMA)
- 비동기 시분할 다중화 방식(ATDMA)
#### (3) 코드분할 다중화 방식(CDMA)
- 정보의 압축과 에러의 복구에 용이
- 디지털 방식의 데이터 송수신 기술
- 한국이 세계 최초로 상용화


### 23. 통신망
#### (1) 회선 교환방식
- 메시지 저장 불가능
#### (2) 메시지 교환방식
#### (3) 패킷 교환방식
- 가상회선: 전체의 전송을 위해 경로 설정, 연결 지향 서비스
- 데이터그램: 각 패킷마다 경로 설정, 비연결 지향 서비스


### 32. 네트워크 통신 장치
- 브리지: MAC 주소를 이용하여 패킷을 적절히 중계하고 필터링(자신의 MAC 주소인 경우에만 받고 아니면 다음 노드로 전달)


### 37.프로토콜
- 단편화, 재합성, 캡슐화, 연결제어, 흐름제어, 에러제어, 순서제어, 동기화, 주소설정


### 44. 데이터링크계층 2-way 핸드쉐이킹
- 송신측이 정보 프레임 전송
- 수신측 에러 검사 수행, 에러 없으면 긍정 응답 프레임(ACK), 에러 있으면 부정 응답 프레임(NAK)
- ex) stop and wait ARQ


### 49. 50. 51. 52. OSI 7계층
- 수신측에서 패킷 수신: 하위 → 상위
- 물리 계층: 전송 매체의 종류, 송수신되는 신호의 전압 레벨 등 정의
- 데이터링크 계층
- 네트워크 계층: 데이터를 패킷 단위로 분할하여 전송 후 재결합, 최적의 경로 선택
- 전송 계층
- 세션 계층: 프로세스 연결/유지/해제
- 표현 계층: 데이터 압축 및 암호화
- 응용 계층


### 55. OSI 7계층과 관련된 표준의 연결
- 물리 계층: RS-232C
- 데이터링크 게층: HDLC
- 네트워크 계층: X.25
- 전송 계층: TCP, UDP


### 58. TCP/IP 프로토콜의 계층 관련 요소
- 네트워크 접속 계층(물리 계층 + 데이터링크 계층): 이더넷, IEEE 802, MAC/LLC, SLIP, PPP, HDLC
- 인터넷 계층(네트워크 계층): IGMP


### 64. 전자우편
- 송신자(메일 클라이언트) -SMTP→ 메일서버 -SMTP→ 메일서버 -IMAP/POP3→ 수신자(메일 클라이언트)


### 67. WWW
- DNS 간의 질의는 재귀형(recursive) 또는 반복형(iterative)으로 연계
- HTTP 요청 메시지를 보내기 전에 TCP 3-way 핸드셰이크 수행


### 75. FTP
- FTP 서버의 데이터 포트 20번을 사용하는 능동 전송 모드
- FTP 클라이언트의 임의의 포트를 데이터 포트로 사용하는 수동 전송 모드


### 76. ICMP
- 네트워크를 통한 데이터 전송 시, 데이터의 전송 경로를 파악하기 위해 사용하는 도구들(traceroute/tracert)은 ICMP 기반으로 동작


### 78. 81. 96. 101. 105. TCP
- 슬라이딩 윈도우 기법 사용
- 일정 시간동안 수신지로부터 확인응답(ACK)이 오지 않으면 해당 패킷 재전송
- 패킷 손실을 이용하여 혼잡 정도를 측정하여 제어
- 전이중 연결 서비스 제공
- 확인 응답 번호: 성공적으로 수신한 데이터의 **마지막** 바이트
- 패킷의 송신순서와 동일하도록 수신순서를 맞춰 재조립
- 패킷 다중화 기능 제공

### 79. 81. 83. 91. TCP/IP 프로토콜
- 인터넷에 연결된 다른 기종의 컴퓨터 간에 데이터를 서로 주고받을 수 있도록 한 통신 규약
- 이더넷/ATM 등 다양한 링크 지원
- HTTP, FTP, SMTP와 같은 프로토콜은 전송 계층 위에서 동작
- IP: 라우팅 테이블을 이용하여 패킷 전달 수행 (라우팅 테이블 갱신은 라우팅 프로토콜로)


### 84. 109. 133. 네트워크 기술
- IPv6: 호스트 자동 설정 기능 제공, QoS 보장을 위해 흐름 레이블링 기능 지원
- 광대역통합망: 응용 서비스별로 약속된 서비스 레벨 보증 품질 수준 보장
- IPv4: 라우터는 IPv4 주소를 사용하여 해당 패킷이 어느 경로로 이동해야 할지 결정


### 85. 통신 프로토콜
- Telnet: 가상 터미널 연결을 위한 응용 계층 프로토콜, 텍스트 기반 양방향 통신 기능 제공


### 100. UDP
- DNS, DHCP


### 138. IETF(Internet Engineering Task Force)
- 인터넷 표준규격을 개발하고 검토하는 역할을 하는 국제 인터넷 작업그룹


### 146. 네트워크의 전송 데이터 오류 검출
- 체크섬: 1의 보수 방법 사용
- 순환중복검사(CRC): 모듈러-2 연산 주로 사용
- 전송할 데이터에 대한 중복 정보를 활용하여 오류 검출
- 단일 패리티 비트: 홀수 개 비트 오류 검출 가능, 짝수 개 비트 오류 검출 불가능


### 147. 순환중복검사 (CRC: Cyclic Redundancy Check)
- 다항식 코드 사용
- 집단 오류 검출에 적합


### 149. ARQ (Automatic Repeat reQuest)
- 부가 정보를 프레임에 첨가하여 전송
- 수신측이 오류 검출 시 재전송 요구


### 155. 슬라이딩 윈도우
- 송신측 윈도우: 전송 시 -1, 응답 수신 시 +1
- 수신측 윈도우: 수신 시 -1, 응답 전송 시 +1


### 157. 158. 159. CSMA/CD(Carrier Sense Multiple Access with Collision Detection)
- 이더넷(Ethernet) 매체 접근 제어(MAC) 방식
- IEEE 802.3
- 버스형 토폴로지에 많이 사용
- 데이터 전송 시간 및 충돌에 의한 데이터 지연 시간 예측 힘들다
- 모든 스테이션에 보내고자 하는 메시지 브로드캐스트
- 충돌 검출을 위해 전송 프레임의 길이를 일정 크기 이상으로 유지


### 160. 
- 프레임 릴레이: 프레임 길이를 가변적으로 사용


### 161. CSMA/CA(Carrier Sense Multiple Access with Collision Avoidance)
- IEEE 802.11
- 예비 신호를 먼저 보내 데이터 전송 중 패킷 충돌을 피한다.
- 채널이 사용되지 않는 상태임을 감지하더라도 스테이션은 임의의 백오프 값을 선택하여 전송 지연시킴
- 수신 노드는 오류 없이 프레임을 수신하면 수신 확인 ACK 프레임 전송


### 165. 무선 통신 기술
- 통신 범위: Wi-Fi < 셀룰러 통신망
- Wi-Fi: IEEE 802.11b
- WiBro: 국내에서 개발한 무선 인터넷 서비스, 3G에 해당
- 무선 단말기 이동성의 한계 극복을 위해 IMT-2000 표준 기술 사용


### 166. 167. 168. IEEE 802.11 무선랜
- AP: 무선랜 기술
- 종류에 따라 최대 전송속도가 달라지고 최대 1Gbps 이상 전송할 수 있는 표준도 존대
- 대부분의 경우 다수의 사용 가능 채널 존재, 근접한 거리에 있는 서로 다른 두 쌍의 컴퓨터가 서로 간섭을 받지 않고 동시에 통신 가능
- AP 없이도 서로 다른 두 컴퓨터가 통신 가능
- 3GPP LTE 표준보다 전송속도가 빠를 수 있다.
- 특정 기기가 사용하는 채널의 대역폭은 가변적

|||||
|---|---|---|---|
|IEEE 802.11a|5GHz 대역|OFDM 기술|최대 54Mbps 전송|
|IEEE 802.11b||CSMA/CA 기술|최대 11Mpbs 전송|
|IEEE 802.11g|2.4GHz 대역||54Mbps 전송|
|IEEE 802.11n|2.4GHz, 5GHz|여러 안테나를 사용하는 MIMO 기술||


### 170. LTE (Long-Term Evolution)
- 다중입력 다중출력(MIMO) 안테나 기술 사용
- 음성 및 데이터 네트워크를 통합한 All-IP 네트워크 구조
- 다운스트림에 주파수 분할 멀티플렉싱과 시간 분할 멀티플렉싱 결합


### 171. 무선 PAN 기술
- ZigBee: IEEE 802.15.4, 낮은 전력 & 저가의 센서 네트워크 구현


### 172. 무선 네트워크 방식
- NFC 방식은 AC 없이 두 장치 간의 통신 가능
- 최대 통신 가능 거리: NFC < bluetooth < Wi-Fi < LTE


### 173. 이동 애드혹 네트워크 (MANET)
- 전송 거리와 전송 대역폭에 제약
- 노드: 호스트 기능 & 라우팅 기능
- 보안 및 라우팅 지원이 여러 노드 간의 협력에 의해 분산 운영


### 174. 적외선파
- 주파수가 300GHz-400THz로 높기 떄문에 벽을 통과할 수 없어 폐쇠된 공간에서 사용


### 175. 안드로이드
- 구성요소: 액티비티, 방송 수신자, 서비스, 콘텐츠 제공자


### 187. 웜
- 자기복제 가능, 다른 파일 감염 X


### 199. NIDS (Network Intrusion Detection System)
- 네트워크 트래픽을 감시하여 DoS 공격, 포트 스캔, 크랙 시도 등과 같은 악의적 동작 탐지


### 203. SET (Secure Electronic Transaction)
- 카드 소지자는 전자 지갑 소프트웨어 필요


### 216. IT 기술
- ITS: 기존 교통체계의 구성 요소에 첨단 기술들을 적용시켜 보다 안전하고 편리한 통행과 전체 교통체계의 효율성을 높임


### 230. 서버 가상화, 하이퍼바이저
- Type-2 하이퍼바이저: 특정 OS 상에서 응용 프로그램처럼 동작
- KVM(Kernel-based Virtual Machine): Type-1 하이퍼바이저로 분류


### 235. 데이터
- 정형 데이터: 관계형 DB, 스프레드 시트
- 반정형 데이터: 스키마, 메타데이터로 연산이 불가능한 데이터(XML, HTML, JSON)
- 비정형 데이터: 소셜 데이터, 영상, 이미지, 음성 등 형태도 없고 연산도 불가능한 데이터


### 249. 디지털 워터마킹/워터마크
- 비가시성
- 강인성/견고성
- 권리 정보 추출성

