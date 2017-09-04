# 오라클 클라우드 테스트 드라이브 #
-----
## 401 : 모바일 응용 프로그램 용 MBE (모바일 백 엔드) 만들기 ##


### 소개 ###
이 자습서에서는 모바일 응용 프로그램을 지원하기 위해 MBE (모바일 백 엔드)를 만드는 방법을 보여줍니다. 모바일 백엔드는 API (플랫폼 및 사용자 지정 API) 및 특정 응용 프로그램 집합을 지원하기 위해 만드는 기타 리소스의 서버 쪽 그룹입니다. 

![](../../common/images/mobile/long/mcsgs_dt_015_mobile_bkend.png)


### 오늘 Practice에 대하여 ###
이 연습에서는 Loyalty 관리 및 모바일 클라이언트 용 API를 지원하는 &quot;Cafe Supremo&quot;라는 모바일 응용 프로그램 용 MBE를 만듭니다. 이를 통해 Cafe Supremo 모바일 응용 프로그램은 생성 된 MBE와 상호 작용하여 제안 푸시, 쿼리 제공 세부 정보를 얻고 제안을 수락 또는 거부합니다. 

### 선수 과목 ###

- 모바일 클라우드 서비스를위한 Oracle Public Cloud Service 계정 (없는 경우 강사에게 확인하십시오) 
- 텍스트 편집기를 사용하여 &quot;mobile_App_Settings_Sample.json&quot;이라는 JSON 파일을 열어 아래의 &quot;6. 확인&quot;단계에서 &quot;baseUrl&quot;, &quot;backendId&quot;및 &quot;anonymousToken&quot;과 같은 일부 속성을 바꿉니다. 

----


#### Cafe Supremo 응용 프로그램을위한 MBE (Mobile Back End) 생성 

1. 제공되는**모바일 클라우드 서비스 \ (MCS \)**ID 도메인 ID 및 자격 증명을 사용하여 모바일 클라우드 서비스에 로그인하십시오. 대시 보드를 사용하여 Mobile Cloud Service Console을 엽니 다. 

2. 대시 보드 화면에서 &quot;모바일 환경 서비스&quot;를 클릭하십시오. 

![](../../common/images/mobile/long/400-MobileEnvService.png)


3. 서비스 세부 사항 화면에서 &quot;서비스 인스턴스 URL&quot;을 클릭하십시오. 

![](../../common/images/mobile/long/400-MCS_ServiceInstanceURL.png)


4. 서비스 소개 페이지의 왼쪽 위에있는 햄버거 아이콘을 클릭하십시오. 탐색 바에서 &quot;응용 프로그램&quot;-> &quot;모바일 백엔드&quot;를 선택하고 &quot;+ 새 모바일 백엔드&quot;녹색 버튼을 클릭하십시오. 

![](../../common/images/mobile/long/400-New_MBE.png)


5. 다음 매개 변수를 사용하여 MBE를 구성합니다. 
+ **이름**:`LoyaltyMgmt_MBE0X` (0X는 강사가 지정한 일련 번호입니다.) 
+ **설명**:`LoyaltyMgmt_MBE0X` (모든 값은 괜찮습니다.) 

![](../../common/images/mobile/long/400-New_MBE_name_desc.png)


6. 확인 

모바일 백엔드가 생성되고 MBE와 상호 작용할 때 사용해야하는 모바일 백엔드 ID 등이 표시되는 새로 생성 된 MBE의 &quot;설정&quot;탭으로 이동합니다. &quot;익명 키&quot;를 보려면 두 개의 &quot;표시&quot;링크를 클릭하십시오. 

![](../../common/images/mobile/long/400-MBE_settings.png)


텍스트 편집기를 사용하여 &quot;Mobile_App_Settings_Sample.json&quot;이라는 JSON 파일을 엽니 다.**&quot;Backend ID&quot;, &quot;Anonymous Key&quot;및 &quot;Base URL&quot;의 값을 복사하고 JSON 파일의 &quot;backendId&quot;, &quot;anonymousToken&quot;및 &quot;baseUrl&quot;과 같은 속성 값을 복사 된 값으로 바꿉니다.**그리고 나중에 사용할 수 있도록 JSON 파일을 저장하십시오. Cafe Supremo 모바일 응용 프로그램 설정을위한 QR 코드를 만들려면 &quot;404 : 모바일 앱에 푸시 알림 설정 및 푸시 알림 설정&quot;에서이 코드를 사용하십시오. 

```
{
      "baseUrl": "https://mcs-<YOUR_MCS_DOMAIN_NAME>.mobileenv.us2.oraclecloud.com:443",
            --> Replace the vaue inside double quotes with the value of "Base URL".
            --> Replace the value inside double quotes with the value of "Mobile Backend ID".
            --> Replace the value inside double quotes with the value of "Anonymous Key".
```


You have finished this lab section.

[Procced to Next - 402: Create Connectors for external services](402-MobileLab.md)

or

[Back to Mobile Serivce and Application Home](README.md)
