## TCP/IP 4계층

- 각 계층을 거칠 때 해당 계층에 필요한 정보를 담고 있는 헤더를 추가
- Application Layer
  - 전송할 데이터를 생성, 사용자가 네트워크 서비스를 사용할 수 있도록 인터페이스를 제공
  - 프로토콜 : HTTP, FTP, Telnet, DNS 등
- Transport Layer
  - 통신 노드 간 연결을 제어, 신뢰성 있는 전송을 담당
  - 프로토콜 : TCP, UDP 등
  - 헤더에 포함된 정보 : 송신 포트, 수신 포트, sequence number, check sum 등
- Internet Layer
  - 통신 노드 간 패킷 전송을 담당
  - 프로토콜 : IP, ARP, RARP 등
  - 헤더에 포함된 정보 : 송신 IP 주소, 수신 IP 주소 등
- Network Access Layer
  - 통신 노드 간 하드웨어 연결 담당
  - 프로토콜 : Ethernet, PPP, Token Ring 등
  - 헤더에 포함된 정보 : 송신 MAC 주소, 수신 MAC 주소 등

## IP 특징

- 비연결성 : 전송 전 연결을 설정하지 않는 방식
- 비신뢰성 : 패킷이 제대로 갔는지 보장하지 않음

## TCP 특징

- 신뢰성 : 패킷 손실, 중복, 순서 바뀜이 없도록 보장
- 연결지향 : 3 way handshake

## UDP

- User Datagram Protocol
- 비연결형
- 비신뢰성
- 속도 빠름
