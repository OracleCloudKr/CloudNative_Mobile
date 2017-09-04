# 오라클 클라우드 테스트 드라이브 #
-----
## 404 : 푸시 알림 설정 및 모바일 앱에 푸시 알림 테스트 ##


### 소개 ###
알림 서비스 (MCS 플랫폼 API의 일부)를 사용하여 모바일 백엔드에 등록 된 앱 사용자에게 알림을 보낼 수 있습니다. 모바일 백엔드에서 알림을 설정하면 iOS, Android 및 Windows 앱에서 알림을 보내는 프로세스가 동일합니다. 적절한 공급 업체 인증서를 획득하고 앱의 모바일 백엔드에 등록하여 알림을 설정합니다. 또한 알림을 수신 할 수 있도록 앱에 일부 코드가 포함되어 있습니다. 알림 자체는 타사 서버를 통해 전송되거나 사용자 정의 API의 로직에 의해 트리거 될 수 있습니다. 
![](../../common/images/mobile/long/mcsgs_dt_006_notifications.png)


### 오늘 Practice에 대하여 ###
이 연습에서는 다음을 수행합니다. 
- 알림 프로필을 만들고 Cafe Supremo 앱을 등록하십시오. 
- Cafe Supremo 응용 프로그램에서 알림 수신 준비 
- 시험 알림 

### 선수 과목 ###

- Cafe Supremo 응용 프로그램 바이너리 (강사가 제공) 
- Cafe Supremo 응용 프로그램을 설치하는 안드로이드 장치 

----
#### 알림 프로필 만들기 및 Cafe Supremo 앱 등록이 실습에서는 알림 프로필을 만들고 Google Apps 자격 증명을 연결하는 클라이언트 애플리케이션 (Cafe Supremo 모바일 애플리케이션)을 등록합니다. 

1. 알림을 받으려면 클라이언트를 만듭니다 (클라이언트로 MCS에 앱 등록). 
- &quot;응용 프로그램&quot;-> &quot;모바일 백엔드&quot;를 탐색하고 모바일 백엔드를 선택한 다음 &quot;열기&quot;를 클릭하여 MBE를 엽니 다.![](../../common/images/mobile/long/401-Select_MBE.png)




- &quot;클라이언트&quot;탭으로 전환하고 &quot;새 클라이언트&quot;를 클릭하십시오. 

![](../../common/images/mobile/long/401-Create_Client.png)




- &quot;Client Display Name&quot;으로`MyAndroidClient0X` (강사가 지정한 후위에 0X를 변경하십시오. 예 : 01), &quot;App Version&quot;으로는 1.0.0, com.oraclecorp.internal.ent3 .apacTestDrv`를 &quot;패키지 이름&quot;으로 사용하십시오. &quot;만들기&quot;를 클릭하십시오. 그러면 클라이언트 설정 화면이 나타납니다. 

![](../../common/images/mobile/long/401-Client_Settings.png)



2. &quot;설정&quot;화면에서 &quot;응용 프로그램 키&quot;의 값을 복사하고 랩 401의 &quot;Mobile_App_Settings_Sample.json&quot;파일에서 &quot;applicationKey&quot;라는 속성 값을 복사 된 값으로 바꿉니다.**JSON 저장 나중에 사용하기 위해 파일. 

```
{
      "baseUrl": "https://mcs-<YOUR_MCS_DOMAIN_NAME>.mobileenv.us2.oraclecloud.com:443",
      "applicationKey": "9722de7f-4ecf-443f-8e0e-714b2f6e0f9c",
            --> Replce the value inside double quotes with the value of "Application Key" in you JSON file.
```

![](../../common/images/mobile/long/401-Client_Setting_Tab.png)
![](../../common/images/mobile/long/401-Create_New_Profile.png)
![](../../common/images/mobile/long/401-Profile_Setting.png)
![](../../common/images/mobile/long/401-Selected_Profile.png)
![](../../common/images/mobile/long/401-Review_MobileApp_Profile.png)
---
```
{
      "baseUrl": "https://mcs-<YOUR_MCS_DOMAIN_NAME>.mobileenv.us2.oraclecloud.com:443",
      "applicationKey": "9722de7f-4ecf-443f-8e0e-714b2f6e0f9c",
      "backendId": "4a9d0d32-8aad-48fb-b803-5315459dce9f",
      "anonymousToken": "R1NFMDAwMTE2NzhfTUNTX01PQklMRV9BTk9OWU1PVVNfQVBQSUQ6Smk3cXBld3lrczlfbmI=",
      "API":"LoyaltyManagementAPI0X",
      "senderID":"925757644219"
}
```
우리는 곧 그것을 사용할 것입니다. 

2. 웹 브라우저에서`http : // www.qr-code-generator.com /`로 가서 `텍스트`버튼을 클릭하면**자유 텍스트**텍스트 영역이 나타납니다. 

![](../../common/images/mobile/long/01.qr.site.png)


3. 위의 2 단계에서 작성한**JSON 파일 내용을**자유 텍스트**텍스트 영역에 붙여넣고 QR 코드 만들기 버튼을 클릭하십시오. 창의 오른쪽에 QR 코드 이미지가 생성됩니다. 

![](../../common/images/mobile/long/02.qr.result.png)



이 브라우저를 열어 두거나 나중에 사용할 수 있도록 이미지를 저장할 수 있습니다. 

4. 휴대 기기에서 `Cafe Supremo`앱을 엽니 다. 

![](../../common/images/mobile/long/03.mobile.app.png)


5. 앱이 시작되고 로그인 페이지가 표시되면 왼쪽 상단에있는 햄버거 메뉴를 클릭하십시오. 

![](../../common/images/mobile/long/04.mobile.menu.png)


6. 확장 메뉴에서 `설정`을 클릭하십시오. 

![](../../common/images/mobile/long/05.mobile.settings.png)


7. 설정 페이지가 열리면 중간에 QRCode에서 설정 읽기 버튼을 클릭하십시오. 

![](../../common/images/mobile/long/06.mobile.qr.png)


8. QR 스캐너가 실행 중일 때 모바일 장치가 QR 코드 이미지를 향하게합니다 (4 단계에서). 스캐너 카메라가 QR 이미지를 인식 할 때까지 모바일 장치와 화면 사이의 거리를 조정해야 할 수도 있습니다. 

![](../../common/images/mobile/long/07.mobile.cam.png)


성공적으로 QR을 검색하면 JSON 파일의 모든 속성 설정이 아래와 같이 모바일 앱 설정 페이지에 자동으로 채워집니다. (`MCS Mobile Backend Preferences`를 확장해야 할 수도 있습니다) 

![](../../common/images/mobile/long/08.mobile.qr.result.png)


`Save settings and logout` 버튼을 클릭하십시오. 그런 다음 홈 화면으로 돌아갑니다. 

10. 강사가 제공 한 모바일 앱**사용자 이름**및**비밀번호**를 입력하고 `로그인`버튼을 클릭하십시오. 

![](../../common/images/mobile/long/09.mobile.login.png)


11. 로그인에 성공하면 환영 페이지가 표시됩니다. 휴대 기기에서 캠페인 쿠폰에 대한 푸시 알림을받을 준비가되었습니다. 

![](../../common/images/mobile/long/10.mobile.welcome.png)


---
#### 테스트 알림 1. &quot;알림&quot;탭으로 전환하고 &quot;4 테스트&quot;아래의 아이콘을 클릭하십시오. 

![](../../common/images/mobile/long/401-Test_Notification.png)



2. &quot;장치 관리&quot;를 클릭하십시오. 

![](../../common/images/mobile/long/401-Test_Manage_Devices.png)



3. 이 모바일 백엔드에 등록 된 장치를 확인해야합니다. &quot;닫기&quot;를 클릭하고 &quot;테스트&quot;화면으로 돌아갑니다. 

![](../../common/images/mobile/long/401-Manage_Devices.png)



4. 알림을 입력하십시오. `귀하는 포인트를 사용하여 제품을 구입할 수 있습니다! - 10001`을 선택하고 &quot;보내기&quot;를 클릭하십시오. 아직 등록 된 기기가 없으면 오류가 발생합니다. 

![](../../common/images/mobile/long/401-Notification_Test_Screen.png)



5. 등록 된 장치가 하나있는 경우 페이지 상단에 성공 메시지 팝업이 표시되고 알림은 장치의 알림 영역에 나타납니다. 

![](../../common/images/mobile/long/401-MCS_Notification_Result.png)




![](../../common/images/mobile/long/401-MobileApp_Notification_Result.png)



[Procced to Next - 405: Track customer behaviors](405-MobileLab.md)

or

[Back to Mobile Service and Application Home](README.md)
