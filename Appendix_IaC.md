[ENG](#iac---infra-as-code) / [KOR](#iac란)

# IaC - Infra as Code

# IaC란?

애플리케이션 개발과 운영에 필요한 인프라를 코드로 자동 생성·배치·관리하는 것

#


## IaC 작동 방식

인프라에 대한 정보가 담긴 코드들을 하나의 스크립트에 작성하면, IaC 툴이 스크립트에 맞춰 다양한 CSP(Cloud Service Provider)의 클라우드 서비스와 연동해 인프라를 생성한다.


### [테라폼으로 s3 버킷 만들기 예제](https://frozenpond.tistory.com/189)


#


## IaC의 장점

IaC를 이용해 개발하기 전 수행해야 했던 번거로운 클라우드 인프라 설정 작업을 줄이고, 개발과 운영을 유기적으로 만들 수 있다.


- ### **참고 용어**
    - "인프라 프로비저닝(설정과정: Provisioning)"

        : IT 환경에서 운영 담당자가 개발자가 사용할 컴퓨터에 필요한 컴퓨팅 자원과 저장소 또는 기타 서비스를 설치한다는 의미



## **핵심은 IaC를 통해 인프라 프로비저닝을 자동화하는 것**

    -> 개발자가 애플리케이션을 개발하거나 배포할 때마다 서버, 운영체제(OS), 스토리지 및 기타 인프라 구성 요소를 수동으로 설치하고 관리할 필요가 없어짐


#

## IaC - 명령형 vs. 선언형

### 2가지 코드 작성 방식

IaC를 위해서 인프라 구성을 코드형태로 스크립트에 씀

작성 방식은 크게
1. 명령형(Imperative) : 순차적인 명령을 내림
2. 선언형(Declarative) : 최종 결과물을 구성

<명령형>
- 스크립트에 인프라에 대한 자원과 구성에 대한 코드가 모두 포함돼어야 함
- 하나씩 주어진 명령을 수행하며 인프라를 생성하므로 스크립트 코드 작성 순서가 중요

<선언형>
- 최종 결과물이 어떻게 나올지 구상한 후 모듈 형식으로 작성
- 인프라의 최종 상태를 지정하면 IaC 툴이 나머지를 알아서 처리해 줌

    -> 순차적 코드 작성을 해야하는 '명령형'과 달리
     생성하고자 하는 서비스 별로 '선언'하기만 하면 됨


## [Infrastructure as Code: Imperative vs Declarative](https://tech.ovoenergy.com/imperative-vs-declarative/)

    -> IaC는 대부분 '선언형'을 채택함.
    CSP: "A", 리전: "B", 스토리지: "C"처럼 작성하면 IaC 툴이 알아서 인프라 생성해줌.

# IaC Tools

## 1. Terraform
- 하시코프(HarsiCorp)에서 오픈 소스로 개발
- Go 언어 기반
- 자체 언어인 (HCL, Hashicorp Configuration Language)를 사용해 클라우드 리소스를 생성

- AWS, GCP, Azure, Heroku 등등 다양한 클라우드 서비스 생성 가능

    -> 복수의 클라우드 리소스 관리 가능.  
    ex) 컴퓨팅 자원은 AWS,   
        DNS(Domain Name System)는 클라우드플레어에서,   
        DB는 히로쿠(Heroku)에서 등등


## [Terraform_Official_Tutorial](https://learn.hashicorp.com/terraform?utm_source=terraform_io)


#


## 2. Pulumi

- Infrastructure as Code (IaC) "플랫폼"
    - Pulumi SDK + 웹 대시보드 등 부가기능
- 다양한 프로그래밍 언어를 가지고 바로 IaC 구현 가능
    - TypeScript
    - JavaScript
    - Python
    - Go
    - .NET
- Terraform에 비해 클라우드 플랫폼 지원은 빈약 (현재 4개만)
    - AWS
    - Google Cloud Platform (GCP)
    - Azure
    - Kubernetes

## [Pulumi_Officail_Tutorial](https://www.pulumi.com/docs/get-started/aws/)
### [Pulumi_Dashbord](https://app.pulumi.com/Ridealist)


#


## 3. AWS CloudFormation
- AWS의 자체 개발 IaC 툴
- AWS의 클라우드 서비스만 지원한다는 한계
- 멀티 클라우드 환경을 구현하고자 하는 기업들에게는 ‘테라폼’이나 ‘앤서블’과 같은 IaC 툴이 각광받는다고...

## [AWS CloudFormation으로 인프라 자동화 시작하기](https://medium.com/pplink/aws-cloudformation%EC%9C%BC%EB%A1%9C-%EC%9D%B8%ED%94%84%EB%9D%BC-%EC%9E%90%EB%8F%99%ED%99%94-%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-9fe13cdf08c9)
