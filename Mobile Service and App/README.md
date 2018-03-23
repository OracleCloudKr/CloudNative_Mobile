
# ORACLE Cloud Test Drive #

## Introduction ##
우리는 일상 생활에서 모바일 서비스에 크게 의존하고 있습니다. 이러한 추세로 인해 기업은 더 나은 고객 경험, 탁월한 운영 및 비즈니스 가치 향상을 위해 더 많은 모바일 애플리케이션을 구축하고자 합니다. 따라서 모바일은 디지털 전환의 핵심이라고 말할 수 있습니다. 비즈니스에서의 모바일 애플리케이션 개발은 훨씬 더 현실적입니다. 비즈니스 및 기술적 관점에서 모바일 애플리케이션 개발의 문제점을 파악해 봅시다.

### Technical Challenges in Mobile ###
비즈니스 과제뿐만 아니라 기업은 모바일 애플리케이션 개발에 어려움을 겪고 있습니다. 모바일 응용 프로그램을 개발하려면 전문 지식이 필요합니다.
+ 여러 플랫폼 (Android, iOS, Windows 등) 개발 및 지원
개발, 테스트 및 생산 환경 준비
+ 모바일 서비스 모니터링 및 분석 방법
+ 다양한 백엔드에 대한 보안 및 신원 프로토콜 및 정책
+ 다양한 백엔드와의 통합
+ 그들을 만들기 위해 어떤 도구를 사용합니까?
![](../common/images/mobile/Technical_Challenges_in_Mobile.PNG)

## Oracle Mobile Solution Strategy ##
위의 과제를 극복하기 위해 오라클은 개발자가 iOS, Android를 사용한 기본 개발, Ionic, Angular, Sencha 및 Xamarin과 같은 타사 및 개방형 프레임 워크에 대해 널리 사용되는 도구를 사용할 것을 권장합니다. 우리는 이것을 "모바일 클라이언트 불가지론 자"라고 부릅니다. 오라클은 데이터 동기화, 스토리지, 위치 서비스, 메시징, 카메라, 연락처, GPS 등과 같은 로컬 서비스에 대한 액세스를 제공하는 모바일 서비스를 통합합니다. 코드가 낮고 코드 개발이 필요하지 않은 추세가 있습니다 - 오라클은 MAX (모바일 Application Accelerator)를 Oracle Mobile Cloud, Enterprise (OMCe)의 일부로 포함합니다.
![](../common/images/mobile/Oracle_Mobile_Solution_Strategy.PNG)

요약하면 Oracle은 귀사의 비즈니스 및 기술적 과제를 극복 할 수있는 엔드 투 엔드 솔루션을 제공합니다.

### Oracle Mobile Services ###
다음과 같이 OMCe (Oracle Mobile Cloud, Enterprise)에 액세스하여 어떤 모바일 서비스가 준비되어 있는지 확인할 수 있습니다.
+ 모바일 서비스 (플랫폼 API) : Google은 분석, 푸시 알림, 오프라인 데이터 동기화, 위치, 개체 저장소, 데이터베이스, 앱 정책, API 관리, 통합 관리, 보안 및 보안 기능과 같은 사전 구축되고 테스트되고 최적화 된 모바일 서비스를 제공합니다. 사용자 관리 및 인텔리전트 봇과 같은 더 많은 기능이 제공됩니다.
+ 플랫폼 API 외에도 사용자 정의 API 및 코드를 개발하여 모바일 서비스를 확장 할 수 있습니다. (예 : SNS 통합, Google지도 통합, 외부 시스템 통합 등) 즉, 모바일 애플리케이션은 맞춤 API를 플랫폼 API로 호출하여 다양한 데이터 소스를 상호 작용할 수 있습니다.
+ 모바일 IDE 개발을위한 클라이언트 IDE의 경우 Oracle MAX (Low code development), JET (JavaScript 기반 Hybrid App Dev.) 및 MAF (Java 기반 Hybrid App Dev)와 같은 모바일 프레임 워크뿐 아니라 모든 IDE를 지원할 수 있습니다.

![](../common/images/mobile/Oracle_Mobile_Services.PNG)

위의 모바일 서비스에 대한 자세한 내용은 다음을 참조하십시오.[the following link](https://docs.oracle.com/en/cloud/paas/mobile-cloud/index.html).

### About the Exercise Today ###
모바일 개발의 어려운 부분은 모든 서버 측 서비스를 통합하고 관리하는 것입니다. 이 연습에서는 OMCe (Oracle Mobile Cloud, Enterprise)를 사용하여 충성도 관리를 위해 "Cafe Supremo"라는 모바일 응용 프로그램을 구현하기 위해 푸시 알림, API 작성 및 외부 서비스와의 통합과 같은 모바일 서비스를 얼마나 쉽게 활성화 / 개발할 수 있는지 보여줍니다.

로열티 관리 모바일 애플리케이션의 경우이 랩을 통해 아래 작업을 수행하여 플랫폼 API (외부 모바일 서비스) 및 외부 통합을위한 사용자 정의 API를 사용하여 모든 작업을 원활하게 진행할 수 있습니다.
- MBE (Mobile BackEnd) 패키지를 가져오고 커넥터를 구성하여 ACS의 마이크로 서비스를 비롯하여 QR 코드를 생성하는 외부 서비스와 ICS의 서비스를 수락 또는 거부하여 기존 CRM을 업데이트합니다.
- 엔드 포인트 W 사용자 정의 API의 구현을 검증하십시오. 사용자 지정 API는 MBE 패키지로 가져오고 커넥터를 활용하여 외부 서비스와 상호 작용합니다.
- 푸시 알림을 설정하고 가져온 MBE에서 작동하도록 Cafe Supremo 모바일 앱을 구성합니다.
- 맞춤 분석 보고서를 사용하여 '사용자가 승인 한 쿠폰'과 같은 고객 행동을 추적합니다. **[참고]** 이 섹션은 선택 사항입니다. 먼저이 섹션을 건너 뛸 수 있으며 다른 모든 섹션을 완료 한 후에 다시 돌아올 수 있습니다.

![](../common/images/mobile/CTD_About_Lab_Mobile.PNG)

### Prerequsite ###

- 안드로이드 폰이 필요합니다. 
- 강사로부터 MBE 패키지 파일 &quot;package-LoyaltyMgmt_MBE0X.zip&quot;을 받았는지 확인하십시오. 파일 이름의 &quot;0X&quot;는 각 사용자에게 지정된 액세스 문서의 접미사와 일치해야합니다. MBE 패키지 파일이 없거나 파일 이름이 할당 된 접미사와 일치하지 않으면 강사에게 문의하여 올바른 파일을 얻으십시오. 
-이 실습의 끝에서 직접 만든 MBE로 작동하도록 모바일 애플리케이션을 구성 할 것입니다. &quot;Mobile_App_Settings_Sample.json&quot;파일에서 모든 설정을 수집합니다. 이 파일의 샘플은 [여기](../common/assets/mobile/Mobile_App_Settings_Sample.json)를 클릭한후, "Save link as..."를 눌러서 받을 수 있습니다. 이 파일로 통해 모든 설정을 받은 후에, 이 링크[online QR code generator](http://www.qr-code-generator.com/)를 통해서 settings에 대한 QR코드를 만들 수 있습니다. 

- Android 스마트 폰에 &quot;Cafe Supremo&quot;모바일 응용 프로그램을 설치하십시오. QR 코드 스캐너를 휴대 전화에 설치 한 경우 휴대 전화에서 다음 QR 코드를 스캔하여 모바일 응용 프로그램을 설치하십시오. 

![](../common/images/mobile/400-Install_App_QRcode.png) 

또는, [이 링크](../common/assets/mobile/Cafe_Supremo.apk?raw=true)를 마우스 오른쪽 버튼으로 클릭하여 앱 파일을 다운로드하십시오. 다운로드하려면 &quot;다른 이름으로 링크 저장 ...&quot;을 선택하십시오. 아래 지침에 따라 모바일 응용 프로그램을 설치하십시오. 

1. Andorid 기기를 컴퓨터에 연결하고 &quot;Cafe_Supremo.apk&quot;라는 Android APK 파일을 기기의 SD 카드 또는 내부 저장소로 복사합니다. 

![](../common/images/mobile/401-Install_App_1.png) 

2. Android 기기에서 Unknown Sources를 enable하기 : &quot;설정&quot;>> &quot;보안&quot;>> &quot;Unknown Sources&quot;체크박스를 선택하십시오. (참고로 Android 버전에 따라 메뉴가 약간 다를 수 있습니다.) 

![](../common/images/mobile/401-Install_App_2.png) 

3. Android 기기에서 파일 관리자를 엽니다. 

![](../common/images/mobile/401-Install_App_3.png) 

4. &quot;Cafe_Supremo.apk&quot;파일이 있는 위치로 이동하여 설치를 위해 파일을 클릭하십시오. 아래 이미지는 Android APK 파일을 `다운로드`라는 폴더에 넣은 상태를 보여주고 있습니다. 

![](../common/images/mobile/401-Install_App_4.png) 

5. &quot;설치&quot;버튼을 누릅니다. 

![](../common/images/mobile/401-Install_App_5.png) 

6. &quot;확인&quot;버튼을 클릭하여 &quot;Café Supremo&quot;모바일 애플리케이션에 필요한 모든 권한을 허용하십시오. 이제 모바일 응용 프로그램의 설치가 완료되었습니다. 

![](../common/images/mobile/401-Install_App_6.png) 


---
# Lab 연습 : #
모바일 서비스 및 응용 프로그램 랩을 살펴 보겠습니다. Lab을 시작하려면 아래 링크를 클릭하십시오. 

## 401 : MBE 패키지 가져 오기 및 외부 서비스 용 커넥터 구성하기


[Click Here.](401-MobileLab.md) 

## 402 : 사용자 지정 API 및 구현 확인 및 테스트하기 ## 


[Click Here.](402-MobileLab.md) 

## 403 : 푸시 알림 설정 및 모바일 앱 구성하기 ## 


[Click Here.](403-MobileLab.md) 

[Back to Cloud Test Drive Home](../README.md) 

