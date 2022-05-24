## AWS 활용하여 3-tier architecture 구축하기

### 3-tier Architecture  

1. Client Tier - Presentation Layer
    - html/css 등 정적 데이터 
    - front-end
2. Application Tier - Business Logic Layer
    - middleware or backe-end
3. Data Tier - Data Access Layer
    - DB, DB서버
    - DB 또는 파일 시스템 접근 및 관리

**계층(Tier) vs. 층(Layer)**  
  - `Tier`: 컴포넌트들의 물리적인 분리
  - `Layer`: 컴포넌트들의 논리적인 분리

- 세가지 계층이 분리된 구조
- 각각 다른 플랫폼 상에 구현된 구조
- 계층 별로 역할을 분담 - 효율적
- 계층 간 독립성 - 문제 해결 편리


### Web server vs. Web Application Server (WAS) --> 따로 정리
- 

### 대충 알겠는 것
- what is bastion: private subnet에 접근 가능하게 프록시 설정
- web instance: apache 설치
- was instance: tomcat 설치
- 가용영역 2개에 각각 Web instance, WAS instance 생성, RDS는 read-replica 사용
- Load Balancer: External ELB, internal ELB() 필요
- 보안 그룹은 서비스 별로: web, was, db, ... in-LB, ex-LB, bastion

### 모르겠는 것
- 프록시
- bastion host 사용 이유: public subnet 안에 NAT가 있나?
- 라우팅 테이블: public rt와 pivate rt ??
- VPC ipv4 CIDR 주소에서 subnet 나누기 (/16 -> 8개 서브넷 생성을 위해 -> /19 prefix 사용)


<br>

---

## Reference
- https://prinha.tistory.com/entry/WEB-3-Tier-Architecture-3%EA%B3%84%EC%B8%B5-%EA%B5%AC%EC%A1%B0
- https://bkjeon1614.tistory.com/27
