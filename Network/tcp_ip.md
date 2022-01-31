## TCP/IP 4계층

- Application Layer
  - 전송할 데이터를 생성, 사용자가 네트워크 서비스를 사용할 수 있도록 인터페이스를 제공
  - 프로토콜 : HTTP, FTP, Telnet, DNS 등
- Transport Layer
  - 통신 노드 간 연결을 제어, 신뢰성 있는 전송을 담당
  - 프로토콜 : TCP, UDP 등
- Internet Layer
  - 통신 노드 간 패킷 전송을 담당
  - 프로토콜 : IP, ARP, RARP 등
- Network Access Layer
  - 통신 노드 간 하드웨어 연결 담당
  - 프로토콜 : Ethernet, PPP, Token Ring 등

## IP

- 지정한 IP 주소에 패킷을 전달하는 역할
- IP 헤더는 출발지 IP, 목적지 IP 등을 포함

### 특징

1. 비연결성 : 전송 전 연결을 설정하지 않는 방식
2. 비신뢰성 : 패킷이 제대로 갔는지 보장하지 않음

## TCP

- 패킷이 중간에 유실되지 않고 정해진 목적지로 가도록 제어하는 역할
- TCP 헤더는 포트 번호, 패킷의 순서 등을 포함

### 특징

1. 신뢰성 : 패킷 손실, 중복, 순서 바뀜이 없도록 보장
2. 연결지향 : 3 way handshake
