# 오라클 클라우드 테스트 드라이브 #
-----
## 502 : End-to-End 테스트 ##


### 소개 ###
마지막으로 우리는 시스템, device(폰) 및 components 간의 메시지 흐름을 모니터링하기 위해 모니터를 통해 엔드 투 엔드 (end-to-end) 테스트를 실행하여 모든 것을 통합 할 수 있습니다. 

### 오늘 Practice에 대하여 ###
이 연습에서는 다음을 수행합니다. 
- 마케팅 관리자 및 최종 고객의 역할에 따라 로열티 관리 응용 프로그램 및 `Cafe Supremo`모바일 앱을 각각 테스트합니다. 
- 오늘 랩에서 사용된 구성 요소 전반의 메시지 흐름 파악 및 모니터링 

### 선수 과목 ###

+ 이전 Lab 연습 완료 : [501: Update Source Code for Sending Push Notification from JEE Application to Mobile Cloud Service](501-PuttingAllTogetherLab.md) 

----


#### 로열티 관리 응용 프로그램에서 쿠폰 생성 

1. 로열티 관리 응용 프로그램의 홈 페이지로 이동하십시오. 로열티 관리 애플리케이션 URL은 다음 형식이어야 합니다. 
https://**<JCS WLS instance IP Adress>**/loyalty/jsp/welcome.jsp
**Input Offer Criteria**에 정수 값으로, 이 예제에서 10000 포인트 이상의 고객을 나타내는 `10000`을 입력하십시오. **대상 제품(Target Product)**을 선택하십시오. 이 예에서는 `Festival Blend`이 선택합니다. 그런 다음 `검색`버튼을 클릭하십시오. 

![](images/502/01.offer.search.png)


2. 오퍼 기준과 일치하는 고객의 수가 표시되면 `다음`버튼을 클릭하십시오. 

![](images/502/02.offer.target.png)


3. 다음과 같은 예를 통해 새로운 제안에 대한 세부 정보를 제공하십시오. 
**Offer Name** : `Summer Festival Offer`  
**Offer Period** : `01-08-2017` To `31-08-2017`  
**Offer Message** : `Hot Summer means Hot Offer. Enjoy our discount today on Festival Blend. Valid from 1st to 31st Aug 2017, terms and conditions apply.`
이제 `Create Offer`버튼을 클릭하십시오. 

![](images/502/03.offer.create.png)


4. 오퍼가 성공적으로 생성되고 고객 푸시 알림이 표시되면 다음 결과가 표시되어야합니다. (제안된 오퍼에는 빨간색으로 강조 표시된 텍스트와 알림 JSON 메시지의 파란색으로 강조 표시된 텍스트가 표시됩니다.)

![](images/502/04.offer.sent.png)

**어떤 일이 일어 났습니까?** 
이전 Lab에서 : [501: Update Source Code for Sending Push Notification from JEE Application to Mobile Cloud Service](501-PuttingAllTogetherLab.md)에서 개발자와 Java Cloud Service를 활용 한 로열티 관리 JEE 애플리케이션에서 *confirm.jsp*의 일부 코드를 수정하여 애플리케이션이 모바일 클라우드 서비스 푸시 알림 REST API를 호출 할 수 있도록 했습니다. 이어서 MCS가 Google Firebase와 교환하여 등록된 Android 기기에 푸시 알림을 전달합니다. 

![](images/502/jcs2mcs.png)


#### 모바일 앱에서 쿠폰에 응답 

5. 몇 초 안에 이전에 제공 한 쿠폰 메시지와 함께 앱 푸시 알림이 Android 기기에 도착해야합니다. 

![](images/502/05.offer.receive.png)


6. Swipe/Click 하면 알림 메시지가 열리고 쿠폰 목록이있는 `Cafe Supremo`모바일 앱이 열립니다. 기존 쿠폰 목록에서 최신 또는 음료를 제공하려면 클릭하십시오. 

![](images/502/06.offer.open.png)


7. 음료 제품 이미지, 설명 및 제안 응답에 대한 오퍼 세부 사항이 표시됩니다. `수락`또는 `거절`버튼을 클릭하여 처리합니다. 

![](images/502/07.offer.accept.png)

**어떤 일이 일어 났습니까?** 
이전 Lab : [3. Rapid Connect Applications by Oracle Integration Cloud Service](../Integrations/README.md)에서 CRM 고객 활동 로그 SOAP API를 연결하고 통합 클라우드 서비스에 REST API로 공개되는 통합 흐름을 설정하여 모바일 사용자 작업을 기록 할 수 있습니다. 

![](images/502/mcs2ics.png)


8. QR 코드 이미지 및 음료 제품 설명과 함께 제공합니다. 원하는 경우 QR 스캐너를 사용하여 쿠폰 URL을 열 수 있습니다. 

![](images/502/08.offer.qr.png)


**어떤 일이 일어 났습니까?** 
이전 랩 [Microservice Lab](../Microservices/README.md)에서는 개발자 및 응용 프로그램 컨테이너 클라우드 서비스를 각각 활용하는 Offer 및 QR이라는 2 개의 마이크로 서비스를 배포했습니다. 고객이 `수락`을 하면 결과 제공 상세 및 QR 이미지가 모바일 장치에 표시됩니다. 

![](images/502/mcs2acc.png)


9. MCS 대시 보드에서 `Applications` ->`Mobile Backends` ->`Your Loyalty Management API`로 이동하면 모바일 및 평균 응답 시간으로부터 최근 API 호출을 찾을 수 있습니다. MCS 모니터링에 대한 자세한 내용은 [404: Track customer behaviors](../Mobile%20Service%20and%20App/404-MobileLab.md)을 참조하십시오. 

![](images/502/09.offer.mcs.png)


10. ICS 대시 보드에서 `Monitoring` ->`Tracking`으로 가면 최근 제안 응답 액션 메시지 트랙을 찾을 수 있습니다. ICS 모니터링에 대한 자세한 내용은 [304: Testing the service and Monitoring with ICS Dashboards](../Integrations/304-IntegrationsLab.md)을 참조하십시오. 

![](images/502/10.offer.ics.png)


11. 트랙 인스턴스 플로우에서 메시지 플로우의 승인 또는 거부 된 if-then 실행 경로를 찾을 수 있습니다. `활동 스트림`에서 허용 또는 거부 된 쿠폰의 QR 코드 이미지 URL을 찾을 수 있습니다. 

![](images/502/11.offer.flow.png)


12. 축하합니다! 이제 이 Lab과 모든 워크샵 연습을 마쳤습니다. 

[Back to Putting All Together Lab Home](README.md) 

