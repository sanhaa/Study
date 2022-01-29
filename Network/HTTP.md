# HTTP


- [ ] CORS (Cross-Origin Resource Sharing) 공부


## 1. HTTP
``` text
HyperText Transfer Protocol
```
- 웹(www)의 기본이 되는 통신 규약(프로토콜)
- HTML, TEXT, 이미지 등의 여러 데이터를 주고 받는 규칙

<br>  

> HTTP/1.1(1997): 가장 많이 사용, TCP  
> HTTP/2(2015): 성능 개선, TCP  
> HTTP/3: 현재 진행형, UDP  

<br> 

### HTTP 특징
- client-server 구조
- 요청-응답 구조
- stateless, connectionless
- HTTP 메세지

----
## 2. Stateless (무상태)
``` text
서버는 클라이언트의 이전 상태를 저장하지 않는다.
```
> ex. ```Stateful```  
> **손님**: 아메리카노 얼마인가요?  
> **카페사장님**: 2000원입니다. 아이스로 드릴까요, 핫으로 드릴까요? ```메뉴에 대한 상태유지```  <br>  
> **손님**: 아이스로 한 잔 주세요.  
> **카페사장님**: 카드로 결제하시나요?  <br>  
> **손님**: 아니요, 현금으로 할게요. ```메뉴, 결제수단에 대한 상태 유지```  
> **카페사장님**: 결제 완료되었습니다. 아이스 아메리카노 한 잔 나왔습니다.

> ex. ```Stateless```  
> **손님**: 아메리카노 얼마인가요?  
> **카페사장님**: 2000원입니다. <br>  
> **손님**: 아이스로 한 잔 주세요.  
> **카페사장님**: 네??????? 무슨 메뉴로요??  <br>  
> **손님**: 아까 말했잖아요! 아메리카노 아이스로요!   
> **카페사장님**: 저는 기억이 안납니다:( 정확한 메뉴와 결제 수단을 한 번에 말씀해주시라구요~

- 클라이언트가 서버에 요청을 보낼 때, 한 번에 모든 정보를 포함하도록 해야 한다.
- 서버는 클라이언트의 이전 상태 ```state```를 저장하지 않기 ```less``` 때문이다.
- *ex. 아메리카노 아이스로 주세요. 결제는 카드로 할거에요*

<br>

---- 

## 3. Connectionless (비연결성)
```
한 번 요청을 하고 응답을 받을 때마다 새로운 TCP/IP 연결을 생성, 삭제함 (연결 유지 X)
```
**한계**
- 연결을 생성하고 끊음에 따라 TPC/IP 연결 방식이 3-way handshake에 따른 오버헤드

**해결**
- HTTP 지속 연결(PErsistent Connections)로 문제 해결
- HTTP/2, HTTP/3에서 최적화

<br>  

---- 

## 4. HTTP 메세지

![](https://mdn.mozillademos.org/files/13827/HTTPMsgStructure2.png)

### 메세지 구성

1. start-line
    1) HTTP Method (GET, PUT, POST 등)  
    2) request URL  
    3) HTTP version  
2. HTTP header  
    - Request headers (request message에서만 사용)
    - General headers
    - Entity headers
![](https://mdn.mozillademos.org/files/13821/HTTP_Request_Headers2.png)
3. empty line (CRLF)
4. message body

### 1) Request Message  
![](https://documentation.help/DogeTool-HTTP-Requests-vt/http_requestmessageexample.png)

### 2) Response Message  
![](https://documentation.help/DogeTool-HTTP-Requests-vt/http_responsemessageexample.png)  


### Request Header
- Host  
    요청하는 호스트에 대한 `호스트 이름` + 포트번호 (필수)  
- User-Agent  
    클라이언트 소프트웨어(브라우저, OS, `device`) 명칭 및 버전 정보
- From  
    클라이언트 사용자 메일 주소
- Cookie
    서버에 의해 Set-Cookie로 클라이언트에게 설정된 쿠키 정보
    주로 검색엔진 웹 로봇의 연락처 메일 주소
- Referer
- If-Modified-Since
- Authorization  
    ```인증토큰```(JWT 토큰 등)을 서버로 보낼 때 사용  
- Origin   
    서버로 ```POST``` 요청을 보낼 때, 요청이 어느 주소에서 시작되었는지 나타낸다.  
    요청을 보낸 주소와 받는 주소가 다르면 ```CORS``` 에러가 발생한다.

### Response Header
- Server  
    서버 소프트웨어 정보  
- Accpet-Range  
- Set-Cookie  
    서버측에서 클라이언트에게 세션 쿠키 정보를 설정
- Expires
- Age
- Allow
- Access-Control-Allow-Origin  
    요청을 보내는 프론트 주소와 받는 백엔드 주소가 다르면 CORS 에러 발생  
    프로토콜, 서브도메인, 도메인, 포트 모두 같아야 CORS 에러 발생하지 않음  



<br>  
<br>  


----
### Reference
https://velog.io/@duarufp06/HTTP-Stateless-Connectionless-HTTP-%EB%A9%94%EC%8B%9C%EC%A7%80-%EA%B0%9C%EB%85%90  
https://developer.mozilla.org/ko/docs/Web/HTTP/Messages  
https://documentation.help/DogeTool-HTTP-Requests-vt/http_request.htm  
https://gmlwjd9405.github.io/2019/01/28/http-header-types.html  