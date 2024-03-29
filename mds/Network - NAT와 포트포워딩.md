# Network - NAT와 포트포워딩

### NAT (Network Address Translation)
- IP패킷의 TCP/UDP 포트 숫자, 소스 및 목적지의 IP 주소 등을 **재기록** -> 3,4계층까지도 다시 만듦 -> 대신 NAT Table에 변화내용을 기록

- 특정 IP 주소의 특정 포트 번호로 가는 패킷 -> 다른 IP 주소의 다른 포트 번호로 바꾸어 줌
- 주로 사설 IP -> 공인 IP 변환에 쓰임 
<img width="1026" alt="image" src="https://user-images.githubusercontent.com/88201041/171349527-b787f480-4034-47ea-9b3f-04389a3efbf7.png">

<img width="886" alt="image" src="https://user-images.githubusercontent.com/88201041/171349320-6d64f508-2389-4116-bef3-2e196f57f207.png">
- 공유기가 통신하는 것처럼 보이지만, 실제로는 NAT Table에 세부 기록들을 모두 저장해놓은 채로 진행됨

### 포트포워딩
사설 IP를 사용하는 PC는 일반적으로 NAT 테이블을 통해 기록된 내용이 있을 때만 직접 통신이 가능
-> 패킷의 요청이 내부에서 외부로 나갔다가 응답이 들어오는 것은 가능하지만 애초에 외부에서의 요청 패킷이 직접 사설 네트워크 대역으로 들어오는 것은 불가능

특정 IP 주소, 포트 번호의 통신 요청 -> 다른 IP, 포트 번호로 넘겨주는 NAT 응용 기술
- NAT를 수행하는 장치에서 설정하며 특정 포트를 Open하고 해당 포트로 들어오는 모든 패킷을 내부의 사설 IP로 전달
- 서버가 사설 네트워크 대역에 있을 때, 해당 서버에서 서비스해주는 포트를 포트포워딩으로 접근 가능하게 함
- 미리 라우터(공유기)의 특정한 포트 번호와 사설 IP 주소를 매핑해 두어야 함

<img width="968" alt="image" src="https://user-images.githubusercontent.com/88201041/171350794-2ee1dd0b-18d8-4671-a5c0-6cd139739f63.png">
