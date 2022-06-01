# Network - HTTP
### HTTP 프로토콜
HTTP -> 서버에 저장되어 있는 웹 표준 데이터(HTML, CSS, JS 파일)를 받아오는 역할

HyperText Transfer Protocol
- www에서 쓰이는 핵심 프로토콜
- 문서의 전송을 위해 쓰임
- 거의 모든 웹 애플리케이션에서 사용됨
- 음성, 화상 등 여러 종류의 데이터를 전송가능
- Request / Response 동작에 기반하여 서비스 제공

- HTTP 1.0
3Way Handshake -> 요청 & 응답 -> 연결 종료의 구조
각 파일당 계속 3Way Handshake를 보내야하므로, 매우 비효율적

- HTTP 1.1
1.0의 비효율성을 개선하여 3Way Handshake를 한 번 했을 때, 여러 개의 파일들을 요청&응답을 통해 전송받을 수 있게 됨


### HTTP 요청 프로토콜
요청 프로토콜 구조 : Request line + Headers + 공백(1줄) + Body
<img width="998" alt="image" src="https://user-images.githubusercontent.com/88201041/171381047-1a2e88c3-6722-4a63-b101-fc35bffb949d.png">

#### Request line
요청 타입 + 공백 + URI + 공백 + HTTP 버전

주요 요청 방식 : GET, POST
GET - server로부터 client가 문서를 읽어오려 할 때
POST - server로 client가 어떤 정보를 전송할 때
-> 하지만 둘 다 전송과 수신이 가능

#### GET vs POST
- GET 방식은 서버로 정보를 보낼 때, URI 부분에 포함시켜서 보냄
- POST 방식은 body에 포함시켜서 보냄
<img width="789" alt="image" src="https://user-images.githubusercontent.com/88201041/171382526-86175e29-f756-45ca-9676-1c3343537074.png">

추가적 보안을 위해 보통 로그인에는 HTTPS 사용

### URI
인터넷 상에서 특정 자원(파일)을 나타내는 유일한 주소 - Uniform Resource Identifier

scheme - 프로토콜 :// host:port / path ? query
ex) http:// IP주소 : 포트 or 도메인 주소 / 폴더이름 / 파일이름 ? 쿼리
