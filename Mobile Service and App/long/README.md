

# 오라클 클라우드 테스트 드라이브 #


## 소개 ##
우리는 일상 생활에서 모바일 서비스에 크게 의존하고 있습니다. 이러한 추세로 인해 기업은 더 나은 고객 경험, 탁월한 운영 및 비즈니스 가치 향상을 위해 점점 더 많은 모바일 응용 프로그램을 구축하고자합니다. 따라서 모바일이 디지털 전환의 핵심이라고 말할 수 있습니다. 비즈니스에서의 모바일 애플리케이션 개발은 훨씬 더 현실적입니다. 비즈니스 및 기술적 관점에서 모바일 애플리케이션 개발의 과제가 무엇인지 살펴 보겠습니다. 

### 모바일에서의 기술적 과제 ###
비즈니스 과제뿐만 아니라 기업은 모바일 애플리케이션 개발에 어려움을 겪고 있습니다. 모바일 애플리케이션을 개발하려면 다음과 같은 전문 지식이 필요합니다. 
+ 여러 플랫폼 (Android, iOS, Windows 등) 개발 및 지원 
개발, 테스트 및 생산 환경 준비 
+ 모바일 서비스 모니터링 및 분석 방법 
+ 다양한 백엔드에 대한 보안 및 신원 프로토콜 및 정책 
+ 다양한 백엔드와의 통합 
+ 그들을 만들기 위해 어떤 도구를 사용합니까?![](../../common/images/mobile/long/Technical_Challenges_in_Mobile.PNG)


## Oracle Mobile Solution Strategy ##
위의 과제를 극복하기 위해 오라클은 개발자가 iOS, Android의 기본 개발, Ionic, Angular, Sencha 및 Xamarin과 같은 타사 및 개방형 프레임 워크에 이르는 널리 사용되는 도구를 사용할 것을 권장합니다. 우리는 그것을 &quot;모바일 클라이언트 불가 지론 (Mobile Client Agnostic)&quot;이라고 부릅니다. 오라클은 데이터 싱크, 스토리지, 위치 서비스, 메시징, 카메라, 연락처, GPS 등과 같은 로컬 서비스에 대한 액세스를 제공하는 모바일 서비스를 통합합니다. 코드가 낮고 코드 개발이 필요하지 않은 추세가 있습니다 - 오라클은 MAX (모바일 Application Accelerator)를 모바일 클라우드 서비스 (MCS)의 일부로 사용합니다. 
![](../../common/images/mobile/long/Oracle_Mobile_Solution_Strategy.PNG)


요약하면 오라클은 귀사의 비즈니스 및 기술적 과제를 해결할 수있는 엔드 투 엔드 솔루션을 제공합니다. 

### Oracle Mobile Services ###
다음과 같이 Oracle MCS (Mobile Cloud Service)에 액세스하여 어떤 모바일 서비스가 준비되어 있는지 확인할 수 있습니다. 
+ 모바일 서비스 (플랫폼 API) : Google은 분석, 푸시 알림, 오프라인 데이터 동기화, 위치, 개체 저장소, 데이터베이스, 앱 정책, API 관리, 통합 관리, 보안 및 보안과 같은 사전 구축되고 테스트되고 최적화 된 모바일 서비스를 제공합니다. 사용자 관리 및 인텔리전트 봇과 같은 더 많은 기능이 제공됩니다. 
+ 플랫폼 API 외에도 사용자 정의 API 및 코드를 개발하여 모바일 서비스를 확장 할 수 있습니다. (예 : SNS 통합, Google지도 통합, 외부 시스템 통합 등) 즉, 모바일 애플리케이션은 맞춤 API를 플랫폼 API로 호출하여 다양한 데이터 소스를 상호 작용할 수 있습니다. 
+ 모바일 IDE 개발을위한 클라이언트 IDE의 경우 Oracle MAX (Low code development), JET (JavaScript 기반 Hybrid App Dev.) 및 MAF (Java 기반 Hybrid App Dev)와 같은 모바일 프레임 워크뿐 아니라 모든 IDE를 지원할 수 있습니다. 

![](../../common/images/mobile/long/Oracle_Mobile_Services.PNG)


위의 모바일 서비스에 대한 자세한 내용은 [the following link](https://docs.oracle.com/en/cloud/paas/mobile-cloud/index.html)을 참조하십시오. 

### 오늘 운동에 대하여 ### <br>
모바일 개발의 어려운 부분은 모든 서버 측 서비스를 통합하고 관리하는 것입니다. 이 연습에서는 푸시 알림, API 작성 및 외부 서비스와의 통합과 같은 모바일 서비스를 사용 / 개발하여 Oracle MCS (모바일 클라우드 서비스)를 사용하여 충성도 관리를위한 &quot;Cafe Supremo&quot;모바일 응용 프로그램을 구현하는 방법을 쉽게 알 수 있습니다. 

충성도 관리 모바일 응용 프로그램의 경우이 랩을 통해 아래 작업을 수행하여 플랫폼 API (외부 모바일 서비스) 및 외부 통합을위한 사용자 지정 API를 사용하여 모든 작업을 원활하게 진행할 수 있습니다. 
- MBE (Mobile Back End) 만 작성하여 특정 응용 프로그램 세트를 지원하기 위해 작성하는 API 및 기타 자원 그룹화를위한 서버 측 컨테이너를 제공하십시오. 
- QR 코드 생성과 같은 외부 서비스를 통합하고 ACCS에서 제공하는 정보 쿼리를 마이크로 서비스로 제공하기 위해 사용자 지정 API 용 커넥터를 만듭니다. 
- Cafe Supremo 모바일 응용 프로그램, 제공 요청을 받기위한 Java 응용 프로그램, QR 코드를 얻기위한 마이크로 서비스 등을위한 서비스 라이브러리를 구축하기 위해 사용자 정의 REST API 및 코드를 작성하십시오. 
- Cafe Supremo 모바일 애플리케이션의 사용자에게 쿠폰 정보를 보내고 푸시 알림을 테스트하도록 푸시 알림을 설정합니다. Lab에서는 Oracle MCS가 iOS 및 Windows를 지원할 수있을지라도 Lab 시간을 단축하기 위해 Android를 지원할 예정입니다. 
- 맞춤 분석 보고서를 사용하여 &quot;사용자가 승인 한 쿠폰&quot;과 같은 고객 행동을 추적합니다.**[참고]**이 섹션은 선택 사항입니다. 시간이 없으면이 부분을 건너 뛸 수 있습니다. 

![](../../common/images/mobile/long/CTD_About_Lab_Mobile.PNG)




### 선수 과목 ###

- 안드로이드 전화 가져와. 
-이 실습에서는 만들려는 키 값을 JSON 파일에 붙여 넣어야합니다. &quot;Mobile_App_Settings_Sample.json&quot;이라는 JSON 파일을 다운로드하십시오. [this link](../../common/assets/mobile/Mobile_App_Settings_Sample.json) and select "Save link as..." for your use in the lab. When you fill out all the information like "baseUrl", "applicationKey", "backendId" and "anonymousToken", you will create a QR code using [a QR code generator](http://www.qr-code-generator.com/)를 오른쪽 클릭하여 다운로드 할 수 있습니다. 지금은 로컬 PC에 저장하십시오. 

- Android 스마트 폰에서 &quot;Cafe_Supremo.apk&quot;라는 모바일 애플리케이션. 

[this link](../../common/assets/mobile/Cafe_Supremo.apk?raw=true)을 오른쪽 클릭하여 다운로드 할 수 있습니다. &quot;다른 이름으로 링크 저장 ...&quot;을 선택하여 로컬 PC에 다운로드하여 저장하십시오. 
휴대 전화에 QR 코드 스캐너가있는 경우 Android 휴대 전화에서 다음 QRcode를 스캔하여 모바일 응용 프로그램을 설치할 수 있습니다. 

! [](../../common/images/mobile/long/401-Install_App_QRcode.png) 

또는 아래 지침에 따라 모바일 응용 프로그램을 설치하십시오. 

1. 장치를 컴퓨터에 연결하고 &quot;Cafe_Supremo.apk&quot;라는 Android APK 파일을 장치의 SD 카드 또는 내부 저장소로 복사합니다. 

![](../../common/images/mobile/long/401-Install_App_1.png)


2. Android 기기에서 알 수없는 소스 사용 : &quot;설정&quot;>> &quot;보안&quot;>> &quot;알 수없는 소스&quot;상자를 선택하십시오. (참고로 Android 버전에 따라 메뉴가 약간 다를 수 있습니다.) 

![](../../common/images/mobile/long/401-Install_App_2.png)


3. Android 기기에서 파일 관리자를 엽니 다. 

![](../../common/images/mobile/long/401-Install_App_3.png)


4. &quot;Cafe_Supremo.apk&quot;파일을 넣은 위치로 이동하여 설치할 파일을 클릭하십시오. 아래 이미지는 Android APK 파일을 &#39;다운로드&#39;라는 폴더에 넣은 경우를 보여줍니다. 

![](../../common/images/mobile/long/401-Install_App_4.png)


5. &quot;설치&quot;버튼을 누릅니다. 

![](../../common/images/mobile/long/401-Install_App_5.png)



6. &quot;확인&quot;버튼을 클릭하여 &quot;Café Supremo&quot;모바일 애플리케이션에 필요한 모든 권한을 허용하십시오. 이제 모바일 응용 프로그램의 설치가 완료되었습니다. 

![](../../common/images/mobile/long/401-Install_App_6.png)




---
# 실험실 연습 : #
모바일 서비스 및 응용 프로그램 랩을 살펴 보겠습니다. Lab을 시작하려면 아래 링크를 클릭하십시오. 

## 401 : 모바일 응용 프로그램 용 MBE (모바일 백 엔드) 만들기 ##


[Click Here.](401-MobileLab.md) 

## 402 : 외부 서비스 용 커넥터 만들기 ## <br>


[Click Here.](402-MobileLab.md) 

## 403 : 모바일 서비스를 확장하기 위해 맞춤 API 및 맞춤 코드 개발 ## <br>


[Click Here.](403-MobileLab.md) 

## 404 : 푸시 알림 설정 및 모바일 앱에 푸시 알림 테스트 ## <br>


[Click Here.](404-MobileLab.md) 

## 405 : 고객 행동 추적 [선택 사항] ## <br>


[Click Here.](405-MobileLab.md) 

또는 

[Back to Cloud Test Drive Home](../../README.md) 

