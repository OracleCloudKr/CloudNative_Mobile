# 오라클 클라우드 테스트 드라이브 #
-----
## 303 : 조정(Orchestration) 패턴을 이용하여 통합하기 ##


### 소개 ###
이번 실습에서는 다음 작업을 수행해 보는 과정입니다.
- ICS (Integration Cloud Service)에 대한 통합 플로우 완성


### 본 실습은... ###
이번 실습에서는 다음을 수행합니다.
- REST 및 SOAP 끝점을 사용하여 ICS 통합 흐름을 탐색하고 통합 흐름에 따라 나머지 데이터 매핑을 완료합니다.
- 웹 기반 클릭을 사용하여 통합 리소스 세부 정보를 탐색하고 ICS 대시 보드에서 데이터 매핑을 정의하는 기술을 구성, 끌어서 놓기


### 준비사항 ###

- 통합 클라우드 서비스를 포함한 Oracle Public Cloud Service 계정 (없는 경우 강사와 확인)
- 이미 구성된 ICS의 SOAP 및 REST 연결


#### 'Orchestration' 통합 ####

1. 왼쪽 상단에있는 햄버거 메뉴 아이콘을 클릭하여 탐색 메뉴을 표시 한 다음 `통합(Integrations)`을 클릭하십시오.

![](images/303/01.home_hamburger_integrations.png)


2. **통합** 페이지가 표시됩니다. 목록에서 **XXX_ICS_INTMGT (1.0)** 항목을 찾은 다음 오른쪽에있는 햄버거 메뉴 아이콘을 클릭하고 `편집(Edit)`을 선택하십시오.

![](images/303/02.integration_edit.png)


3. 이전에 가져온 통합 플로우 **XXX_ICS_INTMGT (1.0)** 의 통합 조정(Orchestration) 편집기가 표시됩니다. 앞서 임포트 한 것으로 일부가 완성되지 않은 상태입니다.

![](images/303/03.integration_existing.png)


4. 캔버스 화면으로 돌아가서 **IF Accept Offer**라는 네 번째 노드를 선택하고 팝업 메뉴에서 `편집` `펜` 단추를 더블 클릭합니다.
![](images/303/08.integration.if.png)


5. IF 조건문 표현식 페이지가 표시됩니다. 텍스트 영역에 `lower-case (accepted) = 'true'` 라는 조건이 설정되어 있고 왼쪽의 **Source** 아래에 있는 `accepted` 필드 옆에 녹색 체크 표시가 있습니다. 이 함수는 `accepted`의 소문자 문자열 값에 따라 true 또는 false 결과를 반환하도록 평가합니다. 여기서 결과는 **IF** 또는 **ELSE** 경로를 향한 메시지 흐름을 결정하는 데 사용됩니다. 검토가 끝나면 오른쪽 상단의 `닫기`를 클릭하십시오.

![](images/303/08.integration.logic.png)


6. *If* 또는 *Otherwise* 조건에서 진행 경로가 결정됩니다. 이제 전체 통합 흐름을 완료하기 위해 *If* 경로에 추가해야 할 작업 하나가 있습니다.

![](images/303/34.integration.if.difference.png)


7. 고객이 제안을 수락 할 때, 즉 `lower-case (accepted) = 'true'` 일때 적절한 응답을 처리하기 위해 응답 데이터의 누락 된 **맵**을 *If* 경로에 구성해야 합니다. 오른쪽 창에서`작업(Actions)`를 클릭하고 `맵(Map)`을 드래그하여 **IF Accept Offer** 노드 다음의 `+` 위치에 드롭합니다.

![](images/303/35.integration.if.add1.png)

![](images/303/35.integration.if.add2.png)


8. `맵(Map)` 작업이 드랍되면, **Data Mapping** 대화 상자 창이 열립니다. 왼쪽  **Source** 를 확장하고`$ CustomerServiceActivity` ->`addCustomerActivityResponse` 아래에 `return` 필드를 드래그하여 오른쪽 창에있는`activityid`에 놓습니다.

![](images/303/36.integration.if.map.png)

9. 우측 대상 필드 중 `imgurl`을 클릭합니다.

10. 매핑 대화 상자가 나타납니다. 왼쪽 된 창에서 **Source**아래의 **매핑 구성요소(Mapping Components)** 를 확장 한 다음,`함수(Functions)` ->`문자열(String)`을 확장하십시오. `concat` 함수를 드래그 하여 `끌어 놓기 또는 여기에 값 입력(Drag and Drop or Type value here...)`로 드랍합니다.

![](images/303/37.integration.if.map1.png)


11. concat 함수의 두 파라미터를 입력합니다.
- string1: `string1`을 클릭하고, `'https://qrcodegenerator-<Your Application Container Cloud Identity Domain Hostname>/ctdqr/v1/offer/'`을 입력합니다. 작은 따옴표를 URL의 앞과 뒤에 넣어야합니다. (`<Your Application Container Cloud Identity Domain Hostname>`는 `Microservices`랩에서 얻은 호스트 이름입니다.)
- string2: 왼쪽 창에서 `Source`를 확장하고 `offerid` 필드를 드래그하여 `string2`에 놓습니다. 자동으로 XPath 형식으로 변경됩니다.

12. 저장후 닫기 버튼을 클릭합니다.

![](images/303/38.integration.if.map2.png)


13. 데이터 맵핑은 아래와 같아야합니다. `확인`을 클릭 한 다음 `닫기`를 클릭하십시오.

![](images/303/39.integration.if.map3.png)


14. 조정(Orchestration) 프로세스 개발이 완료되었습니다.

![](images/303/40.integration.flow.complete.png)


15. 햄버거 아이콘을 클릭 한 다음 오른쪽 상단 모서리에 있는 `추적(Tracking)`을 선택하십시오.

![](images/303/42.integration.tracking.png)


16. **Business Identifiers for Tracking** 대화 상자 창이 표시됩니다. 비즈니스 식별자는 메시지에 대한 런타임 트랜잭션 추적, 특히 ICS를 통해 실행되는 수많은 요청 메시지 중에 특정 메시지를 구분하기 위해 필요합니다. `businessid`,`offerid` 및 `productid`가 이미 매핑 된 Tracking 비즈니스 식별자에 주목하십시오. 화면은 다음과 같습니다.

![](images/303/43.integration.tracking.identifier1.png)


17. ICS 대시 보드 기본 화면으로 돌아가려면 각각 `저장`및 `닫기`버튼을 클릭하십시오.

![](images/303/43.integration.edit.done.png)


18. **통합(Integrations)** 페이지에서, 새로 생성 된 `integration`의 **Switch**버튼을 클릭하면,`통합을 활성화하시겠습니까?(Activate Integration?)` 대화 상자가 나타납니다. 운영환경에서는 체크하는 것이 좋지 않지만 나중에 테스트하기 위해 `Enable tracing` 및 `Include payload`를 선택하십시오.

![](images/303/44.integration.activate.png)


19. 통합 활성화를 위해 2 분 정도 기다리십시오. 완료되면 통합을 알리는 녹색 배너가 성공적으로 활성화되었으며 그 결과는 다음과 같습니다.

![](images/303/45.integration.activate.done.png)


20. 브라우저에서 고유한 URL을 클립 보드로 저장하거나 복사하십시오
- `https://integration-xxxxxxxxxxx.integration.xxx.oraclecloud.com:443/integration/flowapi/rest/XXX_ICS_INTMGT/`

21. 이제 통합 서비스가 테스트 준비가 되었습니다.

[Proceed to Next - 304 : 서비스 테스트 및 ICS 대시 보드로 모니터링](304-IntegrationsLab.md)

또는

[Back to Integrations Lab Home](README.md)
