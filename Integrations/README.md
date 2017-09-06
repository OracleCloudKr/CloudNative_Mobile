# 오라클 클라우드 테스트 드라이브 #
-----
## 3. Oracle Integration Cloud Service를 통한 빠른 시스템 통합 ##


**\* 길이가 45 ~ 60 분인 단순화 된 Lab 버전입니다. 관심이 있으시면 [HERE](long/README.md) 전체 버전을 살펴보십시오.

### 소개 ###
이 랩은 APAC 클라우드 테스트 드라이브의 일부로 CRM 응용 프로그램을 빠르게 연결하고 통합하는 세 번째 실습입니다. 이 섹션에서는 웹 기반 대시 보드를 사용하여 Oracle Integration Cloud Service를 통한 애플리케이션 통합에 대해 설명합니다.

#### 본 Practice에 관하여

![](images/ics.scope.png)


이 연습에서는 Oracle Integration Cloud Service를 사용하여 백엔드 애플리케이션에 연결하고 프런트 엔드 모바일 소비자 요청을 처리합니다. ICS는 모바일 소비자로부터 요청을 받으면 제품 제안의 수락에 대한 고객 활동 로그를 CRM에 전달한 다음 사용자가 제안을 수락하면 QR 코드 이미지 URL을 반환합니다.

**Lab 가정**
+ 귀하는 CRM 시스템을 신속하게 통합하고자 원하는 `통합 설계자`입니다.
+ CRM 시스템 및 필수 서비스 엔드 포인트를 연결하고 사용할 준비가 되었습니다.
+ QR 코드 서비스는 두 번째 실습 후에 응용 프로그램 컨테이너 클라우드 서비스에서 준비됩니다.

**Oracle Integration Cloud Service (ICS)** 는 클라우드에서 응용 프로그램을 연결할 수 있는 완벽하고 안전하면서도 가벼운 통합 솔루션입니다. 응용 프로그램 간의 연결을 단순화하고 클라우드에 있는 응용 프로그램(SaaS)과 여전히 On-Premise에 있는 응용 프로그램을 모두 연결합니다. Oracle Integration Cloud Service는 연결하는 응용 프로그램 또는 해당 응용 프로그램이 상주하는 위치에 관계없이 안전한 엔터프라이즈 급 연결성을 제공합니다.

![](images/00.ics.png)


Oracle Integration Cloud Service는 Oracle Sales Cloud, Oracle RightNow Cloud 등과 같은 오라클 SaaS(Software as a Service) 응용 프로그램과 고유한 연결을 제공합니다. Oracle Integration Cloud Service 어댑터는 업계 최고의 모범 사례를 사용하여 애플리케이션에 연결하는 복잡성을 내부적으로 처리함으로써 사용자 입장에서는 연결을 단순화시킵니다. 여러분들안 각 시스템에 대한 최소 연결 정보를 제공하면 바로 연결됩니다. 마지막으로, 비주얼한 데이터 맵퍼를 제공하여 소스 데이터와 타겟 데이터를 UI 상에서 직접 매핑하여 맵핑을 신속하게 작성할 수 있습니다.
응용 프로그램을 통합하여 통합을 활성화하면 대시 보드는 실행중인 통합에 대한 정보를 표시하므로 각 통합에 대한 상태 및 처리 통계를 모니터 할 수 있습니다. 대시 보드는 주요 정보를 캡처 및 보고하여 거래 실적에 성능을 측정하고 추적할 수 있습니다. 거래를 추적하기 위해 메시지상의 주요 비즈니스 식별자를 관리하거나, 각 통합, 각 연결 또는 특정 거래에 대한 오류를 관리 할 수 ​​있습니다.
Oracle Integration Cloud Service의 주요 기능은 다음과 같습니다.

1. **Connect**
  - 함께 구매한 SaaS와 자동 연결
  - Native SaaS Adaptors
  - Secure On-Premises Integration
  - Open Adapter SDK
2. **디자인**
  - 직관적인 비주얼 디자이너 및 모바일 지원 - 풍부한 포인트 앤 클릭 브라우저 기반 디자이너로 컴퓨터 또는 원하는 태블릿에서 어디에서나 통합을 구축 가능
  - Oracle Recommended ™ - Smart Data Mapper는 Oracle Recommends ™를 사용하여 정확한 추천 매핑 항목을 제공합니다.
  - 비즈니스 사용자 친화적 - 사용하기 쉬운 비디오 및 튜토리얼와 결합 된 비즈니스 친화적 용어
  - API 지원 - 외부 클라이언트가 사용할 수 있게 API기반으로 호출가능합니다.

3. **모니터 및 관리**
  - End to End Visibility - 심플하지만 강력한 검색으로 관심있는 거래에 집중할 수 있습니다. 상세한 감사 및 분석을 위한 포괄적 인 드릴 다운 기능 제공
  - KPI 모니터링 - 고성능 시각적 대시 보드의 핵심 성과 지표에 대한 실시간 통찰력
  - 강력한 오류 관리 - 오류를 신속하게 감지하고 진단합니다.

4. **가속화**
  - 사전 구축 된 통합(Pre_built Integrations) - 즉시 사용 가능하며, 비즈니스 요구 사항에 따라 커스터마이징이 가능한 통합 포트폴리오
  - Cloud Marketplace - Oracle 및 Oracle 파트너가 게시한 사전 구축된 어댑터 및 통합

### 이 튜토리얼에서는 다음을 수행하는 방법을 보여줍니다. ###

+ CRM(Customer Relationship Management) 서비스를 SOAP(Simple Object Access Protocol) 아답터를 통해 연결하고 REST(Representational State Transfer) 기반 서비스로 노출
+ 대상 시스템(서비스)를 연결하고 요청 및 응답 메시지를 매핑하며 서비스를 조합하는 통합 플로우를 구성
+ 거래를 모니터링하고 엔드 포인트 상태, 성능 통계 및 비즈니스 식별자를 통한 거래 추적

### 준비사항 ###

+ 통합 클라우드 서비스를 포함한 Oracle Public Cloud Service 계정

# Lab 연습 : #

## 301 : Oracle Integration Cloud Service 둘러보기 ##

[Click Here.](301-IntegrationsLab.md)

## 302 : CRM 연동을 위한 선 통합(Pre-Built) 자산 임포트 및 연결 정보 수정하기 ##

[Click Here.](302-IntegrationsLab.md)

## 303 : 조정(Orchestration) 패턴을 이용하여 통합하기 ##

[Click Here.](303-IntegrationsLab.md)

## 304 : 서비스 테스트 및 ICS 대시 보드로 모니터링 ##

[Click Here.](304-IntegrationsLab.md)

또는

[Back to Cloud Test Drive Home](../README.md)
