# 네트워크 3강

### 근거리 통신 : 2계층



## 2계층에서 하는 일

#### 기능

같은 네트워크 상에 존재하는 장비들에 대한 **흐름 제어**와 **오류 제어** 실행



#### 네트워크 크기

하나의 네트워크 대역 LAN

다른 네트워크와 통신 할때는 3계층의 도움이 필요함



## 2계층에서 사용하는 주소

**MAC 주소** : 물리적인 주소

12개의 16진수로 구성, OUI(회사 ID)와 고유번호로 구성

<img width="508" alt="image" src="https://user-images.githubusercontent.com/88201041/159701592-348457d3-a571-4519-8153-6ce29c9715d2.png">


## 2계층 프로토콜

**Ethernet** 프로토콜 : LAN에서 통신할 때 사용

Destination Address(6byte, MAC 주소) + Source Address(6byte, MAC 주소) + Ethernet Type(2btye)가 중요

- Destination Address : 목적지 MAC 주소

- Source Address : 출발지 MAC 주소

- Ethernet Type : DATA(페이로드)에 대한 정보를 미리 알려주는 역할

<img width="691" alt="image" src="https://user-images.githubusercontent.com/88201041/159702069-45814daa-3213-4202-ad5e-60a68a38f3ff.png">


## 실습

#### 1. 내 PC MAC주소 확인해보기

Mac OS에서는 윈도우와 방법이 달라서 따로 구글링해서 정리해보았다.

- 터미널에서 "sudo ifconfig"를 치고, 결과 중 "en0"의 "ether" 항목 확인

- 또는, 맥 메뉴의 시스템 리포트 - 네트워크에서 찾을 수 있다



#### 2. Ethernet 프로토콜 캡쳐 및 분석

실제 프로토콜을 확인해보면, Destination MAC Address와 Source MAC Address를 확인할 수 있음

Ethernet(14byte) : Dest Add(6byte) + Src Add(6byte) + protocol type(2byte)

상위 프로토콜 타입 : IPv4(0x0800), ARP(0x0806)
