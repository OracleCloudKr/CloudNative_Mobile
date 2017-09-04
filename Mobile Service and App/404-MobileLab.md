# 오라클 클라우드 테스트 드라이브 #
-----
## 404 : 고객 행동 추적 [선택 사항] ##


### 소개 ###
![](../common/images/mobile/404-Analytics_Overview.png)


Oracle Mobile Cloud Service (MCS)는 애플리케이션 성능 및 사용 패턴을 측정하는 데 도움이되는 Analytics API를 제공합니다. 비즈니스 개발 관리자 또는 모바일 프로그램 관리자는 분석을 사용하여 응용 프로그램을 향상시키는 방법을 찾을 수 있습니다. 

MCS는 사용자가 모바일 애플리케이션과 상호 작용하는 방식을 설명하는 이벤트로부터 분석 보고서를 작성합니다. 모바일 애플리케이션 개발자는 모바일 애플리케이션 코드의 이벤트를 발생시켜 모바일 애플리케이션의 전체 사용량을 추적 할 수 있습니다. 이 실습에서는 &quot;AcceptOffer&quot;및 &quot;RejectOffer&quot;와 같은 이벤트를 추적하는 방법을 살펴 보겠습니다. 모바일 백엔드는 모바일 응용 프로그램에서 작성한 REST 호출의 이벤트를 수신합니다. 모바일 애플리케이션은 사용자 위치, 사용자 세션의 시작 및 종료, 사용자 모바일 디바이스에 대한 세부 정보와 같은 컨텍스트 정보와 함께 이벤트를 설명하는 JSON 페이로드를 포함하는 단일 호출을 작성합니다. 직선적 인 REST 호출을 사용하는 경우 페이로드를 직접 조작하거나 모바일 클라이언트 SDK를 사용하여 직접 구조 작업을 수행 할 수 있습니다. 

![](../common/images/mobile/404-Analytics_Mechanism.png)




### 오늘 Practice에 대하여 ###
이 연습에서는 다음을 수행합니다. 
- 모바일 응용 프로그램의 소스 코드 스 니펫을보고 이벤트 발생 
- MCS (모바일 클라우드 서비스)에서 제기 된 이벤트를 확인하는 방법보기 

### 선수 과목 ###

- 충성도 관리 MBE는 이전 Lab에서 만들었습니다. 
- 귀하의 안드로이드 장치에 카페 Supremo 모바일 응용 프로그램 설치 

----


#### 모바일 응용 프로그램에서 이벤트를 발생시키는 방법이 실습에서는 모바일 응용 프로그램을 작성하여 이벤트를 만들지 않습니다. 그러나 맞춤 이벤트를 만들기 위해 모바일 애플리케이션을 개발하는 방법에 대한 아이디어를 제공하고자합니다. 오라클은 클라이언트 SDK의 일부로 이벤트 API를 제공하여 오퍼를 수용 / 거부하여 이벤트를 발생시킵니다. 이벤트 이름은 원하는 문자열 일 수 있으며 사용자 정의 속성을 MCS의 보고서 생성 마법사에서 볼 수있는 &quot;속성&quot;필드에 추가 할 수 있습니다. 모바일 애플리케이션에서 이벤트를 발생시키는 방법에 대한 아이디어를 얻으려면 아래 모바일 클라이언트 코드 스 니펫을 참조하십시오. 

    ```
    service.post('/mobile/custom/LoyaltyMgmt0X/offer/:id/accept', function (req, res) {
        var events = [];
        events.push({
            name: 'context',
            type: 'system',
            timestamp: timestamp()
        });
        events.push({
            name: 'AcceptOffer',
            type: 'custom',
            component: 'Offers',
            timestamp: timestamp(),
            properties: {
                userName: "jimSmith",
                  offerId: "10001"
            }
        });
        req.oracleMobile.analytics.postEvent(events)
        var events = [];
        events.push({
            name: 'context',
            type: 'system',
            timestamp: timestamp()
        });
        events.push({
            name: 'RejectOffer',
            type: 'custom',
            component: 'Offers',
            timestamp: timestamp(),
            properties: {
                userName: "jimSmith",
                  offerId: "10001"
            }
        });
        req.oracleMobile.analytics.postEvent(events).then(function () {
            var rejectReq = {
                "offerid": req.params.id,
                "productid": req.body.productid,
                "accepted": false
            };
            processoffer(rejectReq, req, res);
        });
    ```

---
![](../common/images/mobile/404-Analytics_Event_Check.png)
![](../common/images/mobile/404-Analytics_Event_Count.png)
![](../common/images/mobile/404-Analytics_Event_Report_Creation.png)
