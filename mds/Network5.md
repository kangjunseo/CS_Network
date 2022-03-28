# 네트워크 5강

### ARP 프로토콜



## ARP 프로토콜

#### ARP가 하는 일

LAN에서 통신을 하기 위해 필요한 MAC주소를 IP주소를 이용해서 알아옴

IP주소는 알고 MAC 주소는 모르더라도 ARP로 통신 할 수 있음



#### ARP 프로토콜의 구조

총 28 byte

Hardware type(2byte) : 2계층 프로토콜의 타입(대부분 0001 - 이더넷이 옴)

Protocol type(2byte) : 뒤에 나올 Protocol Address의 타입(대부분 0800 - IPv4이 옴)

Hardware/Protocol Address Length (2byte) : 각각 주소의 크기 (06,04 사실상 고정)

Opcode(2byte) : 요청인지 응답인지 표시 : 0001이면 요청, 0002이면 응답

Source/Destination Hardware Address(6byte) : 출발지/목적지 MAC 주소

Source/Destination Protocol Address(4byte) : 출발지/목적지 IP 주소



## ARP 프로토콜의 통신 과정

- 목적지 MAC 주소가 비어있는 상태(전부 0)로 목적지 IP주소로 보냄

- Ethernet 주소는 Broadcast로 설정 (전부 F) --> ARP 확인 안하고 같은 네트워크 대역의 모두에게 보냄

- 각 PC는 이더넷 부터 확인 - Broadcast 이므로 통과

- 그 후 3계층 ARP를 확인 - 본인의 IP주소와 목적지 IP주소가 일치하지 않으면 버림

- 일치하는 경우에는 다시 응답 프로토콜을 만들어서 줌 (이 때는 broadcast 할 필요 x)

- 다시 응답을 받은 PC에서는 APR 캐시 테이블에 상대방의 MAC 주소를 업데이트 함

  

## ARP 테이블

통신 했던 컴퓨터들의 주소를 일정 기간동안 저장해두는 곳



## 실습

1. ARP 테이블 확인해보기

   터미널에서 "arp -a"

2. ARP 프로토콜 분석하기

   Wireshark를 이용해서 ARP 프로토콜을 캡쳐하고 분석