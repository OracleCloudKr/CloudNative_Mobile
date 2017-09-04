![](common/images/CTD_introduction_Kr_Seoul.png)
---
# 오라클 클라우드 테스트 드라이브 #


## 소개 ##


이 Oracle Cloud 프로젝트에는 다양한 위치에 구성된 Cloud Native Apps 및 Mobile 용 Oracle Cloud Test Drive 이벤트 용 Lab 자료가 포함되어 있습니다. 참가자들은 JCS (자바 클라우드 서비스), DevCS (개발자 클라우드 서비스), ACCS (애플리케이션 컨테이너 클라우드 서비스), ICS (통합 클라우드 서비스) 및 MCS (모바일 클라우드 서비스)와 같은 일련의 Oracle 클라우드 서비스로이 랩을 Lab 할 수 있습니다. 이 클라우드 기본 및 모바일 테스트 드라이브를 통해 참가자는 클라우드 네이티브 앱, 마이크로 서비스, 통합 및 모바일 서비스를 구현하는 데 Oracle Cloud Services를 어떻게 사용할 수 있는지 알 수 있습니다. 기업이 언제 어떻게 Oracle Cloud Services를 사용할 수 있는지 더 잘 이해하기 위해 &quot;[loyalty management](https://github.com/APACTestDrive/CloudNative_Mobile/blob/master/common/scenario/README.md)&quot;이라는 서비스 시나리오 (비즈니스 사례)를 사용할 것입니다. 

보다 구체적으로이 프로젝트에는 현재 다음 주제가 포함되어 있습니다. 

## Java Apps Lab ##
[Java Apps lab](./Java%20Apps)는 다음으로 구성됩니다. 

+ DevOps Tooling의 배경 - DevOps의 비즈니스 가치, CI / CD와 같은 DevOps 툴용 DevCS (개발자 CS)는 무엇입니까? 
+ 초기 GitHub 저장소를 사용하여 Oracle 개발자 클라우드 서비스 (DevCS) 로열티 관리 애플리케이션 프로젝트를 생성합니다. 
+ Oracle Developer Cloud Service의 `Build`및 `Deploy`구성을 지속적으로 정의하십시오. 
+ CICD (Continuous Integration &amp; Delivery) : Eclipse IDE를 사용하여 코드 변경을 Oracle Developer Cloud Service에 적용 및 푸시합니다. 

## 마이크로 서비스 ##
[Microservices lab](./Microservices)는 Microservices 환경을 준비하고 Oracle ACCS를 사용하여 Microservices를 개발하는 방법을 보여줍니다. 이 Lab은 다음과 같이 구성됩니다. 

+ 마이크로 서비스에 대한 배경 - 마이크로 서비스 란 무엇입니까?, 왜 마이크로 서비스가 필요한가?, 마이크로 서비스의 예, ACCS 정보 
+ 제공 정보 쿼리 및 QR 코드 생성과 같은 마이크로 서비스 생성을 위해 외부 Git 저장소에서 코드를 가져옵니다. 
+ Developer Cloud Service 및 Oracle Application Container Cloud Services를 사용하여 프로젝트를 빌드하고 배포합니다. 

## 통합 ##
[Integrations lab](./Integrations)는 Oracle Integration Cloud Services를 사용하여 백엔드 애플리케이션에 연결하고 프론트 엔드 모바일 소비자 요청을 처리하는 방법을 보여줍니다. 이 Lab은 다음과 같이 구성됩니다. 

+ 통합 배경 - Oracle Integration Cloud Service (ICS) 정보 
+ SOAP (Simple Object Access Protocol) 기반 CRM (Customer Relationship Management) 서비스에 대한 연결 정의를 구성하고 REST (Representational State Transfer) 기반 서비스에 제공하여 오퍼 결과를 처리합니다. 
+ 서비스 엔드 포인트를 상호 연결하고 요청 및 응답 데이터 속성을 매핑하며 결정 논리를 조율하는 통합 플로우를 구성합니다. 
+ 통합 플로우 트랜잭션 및 엔드 포인트 상태, 성능 통계 및 비즈니스 식별자를 모니터링합니다. 

## 모바일 서비스 및 응용 프로그램 ##
[Mobile Service and Application lab](./Mobile%20Service%20and%20App)는 모바일 애플리케이션 용 모바일 서비스를 생성하고 Oracle Mobile Cloud Service를 사용하여 백엔드 서비스를 연결하는 방법을 보여줍니다. 이 Lab은 다음과 같이 구성됩니다. 

+ 모바일 서비스 관련 배경 - 과제 및 솔루션, Oracle Mobile Cloud Service (MCS) 등에 관한 정보 
+ 모바일 백엔드 패키지를 Oracle Mobile Cloud Service (MCS)로 가져옵니다. 
+ 제안 정보 쿼리, QR 코드 생성 등을 위해 외부 서비스와 통합 할 커넥터를 만듭니다. 
+ 맞춤형 API 및 맞춤 코드를 만들어 외부 서비스와 통합하십시오. 
+ 푸시 알림 설정 및 알림을 모바일 앱에 보냅니다. 
+ 사용자 별 애널리틱스 보고서를 작성하여 `사용자 별 완료 제안`을 추적합니다.이 Lab이 끝나면 완료 한 모든 Lab을 기반으로 충성도 관리에 대한 엔드 투 엔드 데모를 제공합니다. 

## 모두 합치면 ##
[Putting All Together lab](./Putting%20All%20Together)은 전선에 관한 최종 Lab이며 모든 기본 클라우드 및 모바일 구성 요소를 엔드 투 엔드로 테스트합니다. 이 섹션에서는 모바일 클라우드 서비스 푸시 알림 API를 통해 모바일과 상호 작용하고 워크샵 시나리오를 통해 테스트하는 방법에 대해 설명합니다. 이 Lab은 다음과 같이 구성됩니다. 

+ 충성도 관리 JEE 신청서 작성 
현재 구축 된 모든 것에 대한 엔드 투 엔드 테스트. 


워크샵은 이벤트 기간 동안 귀하에게 제공되는 Oracle Cloud 계정 정보로 작업하기위한 것입니다. 이 연습 문제를 시작하려면 다음 정보가 필요합니다. 

+ Oracle Cloud 계정**사용자 이름**및**비밀번호**
+ Oracle Cloud**ID 도메인**

위의 정보를 포함하여 &quot;액세스 문서&quot;를 배포하여 클라우드 테스트 드라이브의 각 클라우드 서비스에 액세스하는 방법에 대한 정보를 제공합니다. 
