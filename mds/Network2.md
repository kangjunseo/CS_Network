# 네트워크 2강

### 네트워크 모델



## 네트워크 계층 모델

TCP/IP 모델 : 1-네트워크 인터페이스/ 2-네트워크 / 3-전송 / 4-응용

**OSI 7계층** : 1-물리 / 2-데이터 링크 (이더넷) / 3-네트워크 (IP, ICMP, ARP) / 

4-전송(TCP,UDP) / 5-세션 / 6-표현 / 7-응용(HTTP)

<img width="398" alt="image" src="https://user-images.githubusercontent.com/88201041/159700264-1bc066e5-8bb0-4332-8041-96a4f245e2e3.png">



### 두 모델 비교

#### 공통점

- 계층적 네트워크 모델
- 계층간 역할 정의

#### 차이점

- 계층의 수 차이
- OSI는 역할 기반(논리적), TCP/IP는 프로토콜 기반(실무적)
- OSI는 통신 전반에 대한 표준
- TCP/IP는 데이터 전송기술 특화



## 패킷

네트워크 상에서 전달되는 데이터로, **블록** 단위로 존재함

패킷은 제어 정보와 사용자 데이터(페이로드)로 이루어져있음



#### 패킷의 구조

{헤더 + 페이로드 + (풋터)}의 구조가 재귀적으로 나타남

Ethernet(헤더) + {IPv4(헤더) + {TCP(헤더) + HTTP(페이로드)}(페이로드)}(페이로드)

--> 이것을 하는 과정 : 캡슐화(encapsulation)

상위 프로토콜에 하위 프로토콜을 붙임! (같은 계층까지는 가능)

<img width="642" alt="image" src="https://user-images.githubusercontent.com/88201041/159701088-226c696e-e8e2-4b9a-bac7-44e3b8789104.png">


디캡슐화 : 하위 계층부터 하나씩 확인

헤더 + 페이로드 구조에서 헤더를 확인



#### 계층별 패킷 이름 PDU(Protocol Data Unit)

4계층 PDU : 세그먼트

3계층 PDU : 패킷

2계층 PDU : 프레임



### 실습 : 프로토콜 캡쳐

1. ARP : ethernet+ARP+footer

2. ICMP : Ethernet + IPv4 + ICMP
