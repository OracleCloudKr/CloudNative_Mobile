# 오라클 클라우드 테스트 드라이브 #
-----
## 1. DevOps - Oracle Developer Cloud Service에 의한 JEE의 지속적인 통합 및 연속성 ##


### 소개 ###
이 랩은 APAC 클라우드 테스트 드라이브의 일부로 애자일 프로젝트 수명주기 동안 JEE 응용 프로그램을 작성, 구축 및 배포하는 첫 번째 Lab입니다. 이 절에서는 WebLogic Server 관리 콘솔을 사용하여 Oracle Java Cloud Service 인스턴스에 응용 프로그램을 배포 및 배포 취소하는 방법에 대해 설명합니다. 

#### 오늘 Practice에 관하여 

![](images/jcs.scope.png)


이 연습에서는 향후 1 시간 내에 Developer Cloud Service를 사용하여 다음 작업을 수행합니다. 
+ JEE 애플리케이션 소스 코드를 얻고 Java Cloud Service에서 WebLogic Server에 배포 
+ 코드 변경에서부터 시작되는 간단한 `지속적인 통합 및 전달` 

**Lab 가정**
+ `충성도 관리`응용 프로그램은 마케팅 관리자가 선택한 고객 그룹을 기반으로 캠페인 제안을 작성하는 데 사용됩니다 
+ 당신은 최근에 사소한 코드 수정안을 작성하고 변경을 제공 한이 응용 프로그램을 소유 한 `응용 프로그램 설계자`입니다. 
+ 로열티 관리 데이터베이스, 테이블 및 데이터는 응용 프로그램에서 연결하고 사용할 준비가되었습니다. 
+ WebLogic Server 인스턴스가 Java Cloud Service에 프로비저닝 됨 

현대의 개발 팀은보다 나은 품질의 짧은 주기로 소프트웨어를 제공하고자합니다. 민첩한 개발 방법론은 변화하는 비즈니스 요구 사항을 신속하게 해결하고 작업 소프트웨어를 고객에게 제공하기위한 처리 시간을 단축시킵니다. 개발 단계를 통해 소프트웨어 제공을 간소화해야하는 필요성은 지속적인 통합 및 전달 자동화와 같은 대중화 된 기술을 필요로합니다. 이러한 기술은 전체 DevOps주기를 최적화하기 위해 자주 채택됩니다. 

![](images/business.value.png)


**Oracle Developer Cloud Service (DevCS)**는 이러한 최신 개발 및 운영 기술 구현을 단순화하는 통합 클라우드 기반 플랫폼을 제공합니다. DevCS는 클라우드 기반 소프트웨어 개발 플랫폼 (PaaS)이며 응용 프로그램 개발 인프라를위한 호스팅 환경입니다. Hudson, Git, Maven, 문제점 및 위키와의 통합을 통해 애플리케이션 개발 라이프 사이클을 효과적으로 관리하기위한 오픈 소스 표준 기반 솔루션을 제공합니다. Oracle Developer Cloud Service를 사용하면 애플리케이션 소스 코드를 Oracle Cloud의 Git 저장소에 커밋하고, 할당 된 문제와 온라인 결함을 추적하고, wiki 페이지를 사용하여 정보를 공유하고, 소스 코드를 검토하고 프로젝트 빌드를 모니터링 할 수 있습니다. 테스트를 성공적으로 마친 후에는 Oracle Java Cloud Service - SaaS 확장, 공개 된 Oracle Java Cloud Service 인스턴스, Oracle Application Container Cloud Service 인스턴스 또는 사내 구축 환경에 프로젝트를 배포 할 수 있습니다. 

![](images/00.dcs.png)


Oracle Developer Cloud Service의 주요 기능은 다음과 같습니다. 
+ 프로젝트 생성, 구성 및 사용자 관리 
Git으로 버전 관리 및 소스 코드 관리 
+ Maven으로 응용 프로그램 종속성 및 라이브러리 저장 
Hudson과의 지속적인 빌드 통합 
+ 문서 공동 작업을위한 Wiki 
+ 과제 추적 시스템으로 작업, 결함 및 기능 추적 
+ 코드 검토 후 저장소 분기 병합 
+ Oracle Java Cloud Service 로의 배포 - SaaS 확장, Oracle Java Cloud Service 및 Oracle Application Container Cloud Service 

Oracle Developer Cloud Service는 웹 브라우저 및 Brackets, Eclipse 용 Oracle Enterprise Pack (OEPE), Oracle JDeveloper 및 NetBeans IDE와 같은 통합 개발 환경 (IDE)에서 액세스 할 수있는 웹 인터페이스로 사용할 수 있습니다. DevCS는 Git, Hudson, Maven, 브라우저 기반 IDE, 이슈 트래커, 위키, 스 니펫, 코드 리뷰 등 다양한 구성 요소로 구성됩니다. 모든 구성 요소는 Oracle Developer Cloud Service에서 제공하는 기능 및 서비스 모음 인 프로젝트에서 사용할 수 있습니다. 

### 이 자습서에서는 다음을 수행하는 방법을 보여줍니다. ###

- 초기 [GitHub](https://github.com) 저장소를 사용하여 Oracle Developer Cloud Service (DevCS) 로열티 관리 애플리케이션 프로젝트 생성 

- Oracle Developer Cloud Service의 `Build`및 `Deploy`구성의 지속적인 통합 정의 

- CICD (Continuous Integration &amp; Delivery) : Oracle Developer Cloud Service에 Brackets 사용, 코드 변경 및 푸시 코드 변경 

### 선수 과목 ### <br>


- 다음 실습에서는 강사가 제공 할 Oracle Public Cloud 계정이 필요합니다. 
- 경량 IDE - [Brackets](http://brackets.io/). Brackets installer will be provided by instructor or you can download from [GitHub HERE](https://github.com/adobe/brackets/releases)도 설치해야합니다. 

- Git 클라이언트가 있어야합니다. 이미 Github Desktop, Eclipse 또는 다른 IDE를 사용하고 있다면, 이미 Git을 사용하고있을 것입니다. Git 설치 관리자는 강사가 제공하거나 [here](https://git-scm.com/downloads)에서 다운로드 할 수 있습니다. 

-*[Click HERE for Brackets installation detail](brackets.md)*

-*[Click HERE for Git installation details](gitclient.md)*

# 실험실 연습 : # <br>


## 101 : 초기 GitHub 저장소를 사용하여 Oracle Developer Cloud Service 로열티 관리 애플리케이션 프로젝트 생성 ##


[Click Here.](101-JavaAppsLab.md) 

## 102 : Oracle Developer Cloud Service에서 지속적인 통합 `빌드`및 `배포`구성 정의 ## <br>


[Click Here.](102-JavaAppsLab.md) 

## 103 : CICD (Continuous Integration &amp; Delivery) : Oracle Developer Cloud Service에 괄호 사용, 코드 변경 및 푸시 코드 변경 ## <br>


[Click Here.](103-JavaAppsLab.md) 

또는 

[Back to Cloud Test Drive Home](../README.md) 

