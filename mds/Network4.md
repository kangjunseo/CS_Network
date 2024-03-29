# 네트워크 4강

### IP주소를 활용한 통신 : 3계층



## 3계층의 기능

#### 3계층 에서 하는 일

다른 네트워크 대역, 즉 서로 다른 LAN들을 연결시켜줌

2계층 장비인 스위치만으로는 안되고, 3계층 장비인 라우터가 필요



#### 3계층에서 쓰는 주소

**IP 주소** : WAN에서 통신할 때 사용하는 현재 PC의 주소

서브넷 마스크 : IP 주소에 대한 네트워크의 대역 규정

게이트웨이 : 외부와 통신할 때 사용하는 네트워크의 출입구



#### 3계층 프로토콜

ARP : IP주소를 이용해 MAC주소를 알아오는 프로토콜

IPv4 : WAN에서 통신할 때 사용하는 프로토콜

ICMP : 서로가 통신되는지 확인할 때 쓰는 프로토콜



## 일반적인 IP 주소

#### Classful IP 주소

Classful IP 주소 : 낭비가 심함

A Class : 0XXXXXXX / B Class : 10XXXXXX / C Class : 110XXXXX / D / E

<img width="674" alt="image" src="https://user-images.githubusercontent.com/88201041/159702686-30e2e407-2e2b-4214-905d-78b62a44e92c.png">



#### Classfulless IP 주소

**IP 주소** : 0.0.0.0 ~ 255.255.255.255

서브넷 마스크 : 네트워크 대역을 나눠주는데 사용, 1로 시작하고 1과1 사이에는 0이 올 수 없음

<img width="527" alt="image" src="https://user-images.githubusercontent.com/88201041/159703361-659101a2-153f-4b23-b4ff-1065b413ac44.png">


#### 사설 IP와 공인 IP

사설 IP : 같은 네트워크 대역에서만 사용하는 IP

공인 IP : 외부와 연결할 때 사용하는 IP

실제 인터넷에서는 공인 IP로만 통신하므로 외부 네트워크에서는 사설IP 대역이 보이지 않는다.



## 특수한 IP 주소

0.0.0.0 : wildcard, 나머지

127.0.0.1 : 내 컴퓨터

게이트웨이 주소 : 인터넷에 접속하기 위한 출입구를 알려주는 주고



### 실습

공인ip 사설ip 비교
