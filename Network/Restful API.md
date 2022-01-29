# RESTful API
> *인터넷이 그물망처럼 연결되어 있는 웹에서, 데이터를 어떻게 주고 받을까. => 요청 - 응답 프로토콜인 HTTP를 따라 리소스를 요청하는 인터페이스 ```RESTful API``` 이용*

``` text
REST 아키텍처의 제약 조건을 준수하는 애플리케이션 프로그래밍 인터페이스
```

## API

``` text
Application Programming Interface
```
- 애플리케이션 소프트웨어를 구축하고 통합하는 정의 및 프로토콜 세트
- 호출 - 응답 사이의 계약
- 클라이언트 - 리소스 사이의 인터페이스 (주고 받음을 관리)


## REST

``` text
Representational State Transfer
```
**표현상태 전송**
= 자원의 표현에 의한 상태 전달

- 프로토콜 X, 표준 X → 아키텍처 원칙 세트
    > 반면 RESTful API가 널리 사용되기 이전에 사용되었던 ```SOAP```는 애플리케이션 프로토콜이었다. REST는 프로토콜이라기 보다는 추천되는 구조였다는 말이다  

    - ```SOAP```
        + distributed-computing protocol  
        + XML-based
    
- ```client-server``` 통신 방식 중 하나
- 아키텍처 스타일, 아키텍처 원칙 princip
- HTTP 1.0부터 PUT, GET의 개념은 있었다. 이를 활용하여 자원을 주고 받도록 설계한 구조

```HTTP URI(Uniform Resource Identifier)```를 통해 자원(Resource)를 명시하고 ```HTTP method```(POST, GET, PUT, DELETE)를 통해 해당 자원에 대한 ```CRUD``` operation을 적용

- 웹사이트의 모든 자원에 고유한 ID인 URI를 부여하고
- HTTP Method를 통해
- 자원을 CRUD operation 할 수 있도록 함

### REST 장점
- HTTP 프로토콜의 인프라를 그대로 사용하므로, 별도의 인프라가 필요 X
- HTTP 프로토콜의 표준을 최대한 활용
- REST API 메세지의 의도를 파악하기 쉽다.
- data source와 백엔드를 분리

### REST 단점
- 표준이 존재하지 않음
- HTTP method 기반이므로 4가지 메소드로 제한됨


### REST 구성 요소
1. **자원(Resource)**: URI
    - 자원을 구별하기 위한 ID
    - ```ex. /gourps/:group_id```
2. **메소드**: HTTP Method
    - HTTP protocol의 메소드를 사용
    - GET, POST, PUT, DELETE
3. **표현**: Representation of resource
    - Client: 자원의 상태에 대한 CRUD 요청
    - Server: 이에 적절한 응답을 보냄
    - JSON, XML, TEXT 등으로 표현됨

### REST 특징
1. **Server-Client** 구조
    - Server: 자원을 가지고 있음, API를 제공
    - Client: 사용자 인증이나 session을 관리, 자원을 요청
2. **Stateless** (무상태)
    - HTTP 프로토콜은 **Stateless** -> REST도 마찬가지
    - Client의 context (세션, 쿠키 등)을 server에 저장하지 않음
    - Server는 각 요청을 완전히 별개의 것으로 인식
        > 여러 요청 사이의 연관성 없음, 한번의 요청에 서버가 필요로 하는 정보를 모두 담아야 함. 
3. Cacheable (캐시 처리 가능)
4. Layered System (계층화)
    - Client는 REST API만 호출
    - API server를 다중 계층으로 구성할 수 있음

-----
## REST API
``` text
REST 기반으로 서비스 API를 구현한 것
```
- ```restful```은 REST라는 아키텍처를 구현하는 웹서비스를 나타내는 용어
- REST API를 제공하는 웹 서비스는 RESTful 하다.

------
 
### Reference
https://gmlwjd9405.github.io/2018/09/21/rest-and-restful.html
https://www.quora.com/What-was-the-web-like-before-REST-principles-were-in-wide-use
