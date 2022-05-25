## PART 09. 운영체제 보안과 데이터베이스 보안

### 2. 시스템 메모리 기본구조 영역
#### (1) 스택(Stack)
- 지역변수, 함수 관련
#### (2) 힙(Heap)
- 동적 메모리
#### (3) 데이터(Data)
- 가상주소 공간
- 전역변수, 정적변수
#### (4) 코드(Code)
- 실행 명령을 포함하는 메모리, 목적 파일에 있는 프로그램 영역


### 4. 5. 망분리
#### (1) 물리적 망분리
- PC 2대 사용
#### (2) 논리적 망분리
- 가상화 기술 이용
- SBC(Server Based Computing): VDI(Virtual Desktop Infrastructure)
- CBC(Client Based Computing): OS 커널 분리


### 8. 운영체제 파일 보호 기법
- 접근제어 행렬
- 파일의 명명법(Naming): 접근하고자 하는 파일 이름을 모르는 사용자를 접근 대상에서 제외시킴
- 암호화


### 9. 참조 모니터(Reference Monitor)
- 항상 호출
- 분석과 시험이 용이하도록 충분히 작아야 함


### 12. 14. 윈도우즈 파일 시스템
#### (1) FAT16
- 2GB 저장 가능
#### (2) FAT32
- 테이블의 기본 크기: 32비트
#### (3) NTFS 파일 시스템
- 파일 정보를 MFT(Master File Table)에 저장


### 17. 윈도우 시스템의 레지스트리(Registery)
- HKEY_CLASSES_ROOT: 파일 확장자, 연결에 대한 맵핑 정보
- HKEY_CURRENT_CONFIG: 디스플레이와 프린터에 관한 정보


### 20. 윈도우 인증 구조
#### (1) 보안 참조 모니터(SRM: Security Reference Monitor)
- 접근 통제, 접근 권한 검사
- 커널모드에서 실행
- 사용자에게 고유의 SID 부여
#### (2) 로컬 보안 권한(LSA: Local Security Authority)
- 사용자 계정 검사, 시스템 접근 토큰 작성, 로그인
- 사용자 모드 컴포넌트
#### (3) 보안 계정 관리자(SAM: Security Accounts Manager)
- LSA가 사용하는 사용자 계정 DB 유지, LSA를 위한 사용자 인증 제공
- 사용자 모드 컴포넌트
#### (4) 로그인 프로세스(Login Process)
- 사용자 모드로 실행되는 로그인 시, 사용자 인증


### 27. 28. 윈도우즈 프로세스
- svchost.exe (service host process): dll에 의해 실행되는 기본 프로세스
- csrss.exe (client/server runtime system): 윈도우 콘솔 관장, 스레드 생성&삭제, 32비트 가상 MS-DOS 모드 지원
- service.exe: 시스템 서비스를 제어, 서비스 간 상호작용


### 30. MS Windows 운영체제 및 Internet Explorer의 보안 기능
- Windows 7의 각 파일과 폴더는 사용자에 따라 권한이 부여, 파일: 모든 권한/수정/읽기/쓰기/특정 권한, 폴더: 모든 권한/수정/읽기/쓰기/특정 권한/폴더 내용 보기
- BitLocker 기능: 디스크 볼륨 전체 암호화, Windows 비스타 부터 탑재
- Internet Explorer 10의 인터넷 옵션 - 개인정보 수준 '낮음': 압축된 개인정보 취급 방침이 없는 타사의 쿠키 차단
- Windows 7 운영체제의 고급 보안이 포함된 Windows 방화벽 - 인바운드 규칙 & 아웃바운드 규칙 모두 설정 가능


### 31. 윈도우 부팅 순서
- POST(Power On Self Test) 실행
- 기본 부팅 관련 설정사항 로드: CMOS
- MBR(Master Boot Record) 로드: 부팅 매체에 대한 기본 파일시스템 정보
- NTLDR(NT Loader) 실행: 간단한 파일시스템 실행
- NTDETECT.com 실행: 설치된 하드웨어 검사
- ntoskrnl.exe(NT OS Kernel) 실행: HAL.dll 로드


### 34. UNIX의 Kernel
- 주기억장치에 상주


### 38. 유닉스/리눅스 로그 파일
- loginlog: 사용자가 5번 이상 로그인 실패할 경우 접근 정보 기록
- wtmp 로그의 내용은 last 명령어로 확인 (계정명, 로그인 시간, 로그아웃 시간 등)


### 41. 유닉스/리눅스 명령어
- mesg: 타인이 본인의 터미널에 접근하는 권한 제어
- touch: 빈 파일 생성 or 기존 파일의 시간 변경


### 69. 파일 시스템
- EXT(Extended File System): 리눅스 고유의 파일 시스템


### 80. 리눅스 bash 셸
- 셸 변수 or 환경 변수로 설정된 SHELL에 저장된 값 출력?
```bash
echo "$SHELL"
```


### 83. 리눅스 패킷 필터링 (iptable)
```bash
iptables -A <체인> <매칭 옵션> -j <타겟>
```
- -p <프로토콜>: TCP/UDP/ICMP/ALL
- -d <도착지 주소>
- -s <출발지 주소>
- -dport <포트>: 도착지 포트
- -sport <포트>: 출발지 포트
- -i <인터페이스>: 패킷이 들어오는 네트워크 인터페이스 지정
- -o <인터페이스>: 패킷이 나가는 네트워크 인터페이스 지정
- -j <타겟>: ACCEPT/DROP/REJECT


### 85. 보안 관리 도구
- PAM(Pluggable Authentication Module): 사용자를 인증 & 해당 사용자의 서비스에 대한 접근 제어하는 모듈화된 방법
- SELinux: 관리자가 시스템 액세스 권한을 제어할 수 있게 하는 Linux 시스템용 보안 아키텍처


### 95. DB 암호화
||API|Plug-In/Filter|TDE(Transparent Data Encryption)|
|---|---|---|---|
|데이터 암복호화 위치|응용프로그램|DB|DB|
|접근제어|X|O|O|


### 99. CERT (Computer Emergency Response Team)
- 웜 사고에 대응하기 위해 만들어졌지만, 현재는 해커의 침입/대응/추적까지 맡음


### 107. 업무연속성 (BCP: Business Continuity Planning)
- 미러사이트, 핫사이트: 백업 센터에 주전산센터 장비와 동일한 장비를 구축


### 113. 디지털 포렌식의 원칙
- 연계보관성의 원칙: 증거는 획득/이송/분석/보관/법정제출 등의 과정이 명확해야 한다.


### 121. CAATs (Computer Assisted Auditing Techniques)
- 데이터베이스에 있는 대량의 숫자 정보의 무결성/정확성을 확인하기 위한 방법


### 122. 디지털 포렌식
- 슬랙(Slack): 물리적으로 파일에 할당되어있지만 논리적으로 사용할 수 없는 낭비 공간
- 카빙(Carving): 디스크 내 비구조화된 데이터 스트림을 식별 & 의미 있는 내용 추출

