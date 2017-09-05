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


#### Complete an 'Orchestration' 통합 ####

1. 왼쪽 상단에있는 햄버거 메뉴 아이콘을 클릭하여 탐색 메뉴을 표시 한 다음 `통합(Integrations)`을 클릭하십시오.

![](images/303/01.home_hamburger_integrations.png)


2. **통합** 페이지가 표시됩니다. 목록에서 **XXX_ICS_INTMGT (1.0)** 항목을 찾은 다음 오른쪽에있는 햄버거 메뉴 아이콘을 클릭하고 `편집(Edit)`을 선택하십시오.

![](images/303/02.integration_edit.png)


3. 이전에 가져온 통합 플로우 **XXX_ICS_INTMGT (1.0)**의 통합 조정(Orchestration) 편집기가 표시됩니다. 앞서 임포트 한 것으로 일부가 완성되지 않은 상태입니다.

![](images/303/03.integration_existing.png)


4. 수정하기 전에 전에 임포트된 선 통합(Pre-Built) 내용을 살펴봅니다. **ProcessOffer**라는 첫 번째 노드를 클릭하여 선택하고 팝업 메뉴에서 `편집` `펜`버튼을 더블클릭하십시오.

![](images/303/04.integration.processoffer.png)


5. **Oracle REST Endpoint 구성** 대화 상자 창이 표시됩니다. 이 페이지는 임포트된 통합이 요청을 수신 및 응답하는 부분입니다. 즉 정의한 JSON 형식으로 REST 요청 및 응답을 통해 이 프로세스와 상호 작용하는 방법을 요약합니다. 나머지 세부 사항을 보려면 오른쪽 상단에있는 &lt;뒤로> 버튼을 클릭하십시오.

![](images/303/05.integration.rest.summary.png)


6. 이 페이지는 응답 페이로드 세부 사항을 요약화면입니다. 변경하지 않고 이 페이지의 세부 사항을 자유롭게 탐색 할 수 있습니다. 중간에 `<<< inline >>>`링크를 클릭하십시오.

![](images/303/05.integration.rest.response.payload.png)


7. **Response Sample JSON Payload**의 형식이 표시됩니다.`{"activityid": "elit aliqua aliquip", "imgurl": "minim ipsum"}` 아래에 있는 `취소(Cancel)`버튼을 클릭하면 돌아갑니다.

![](images/303/05.integration.rest.response.payload1.png)


8. 오른쪽 상단의 `<뒤로`버튼을 클릭하여 나머지 세부 사항을 검토하십시오.

![](images/303/05.integration.rest.response.png)


9. 이 페이지는 요청 페이로드 세부 사항을 요약화면이며, 변경하지 않고 이 페이지의 세부 사항을 자유롭게 탐색 할 수 있습니다.
`{"customerid": 21767684, "offerid": 49531393, "productid": 28916305,   "accepted": true}`  
맨 위의`<뒤로` 버튼을 클릭하십시오. 남은 세부 사항을 검토 할 수 있습니다.

![](images/303/05.integration.rest.request.png)


10. 마지막으로,**Oracle REST Endpoint Configuration Wizard 시작 페이지**가 표시되며 REST Endpoint 인터페이스의 기본 정보를 보여줍니다. 아무 것도 변경하지 않고 오른쪽 상단의 `취소(Cancel)`버튼을 클릭하여 캔버스 화면으로 돌아옵니다.

![](images/303/05.integration.rest.endpoint.png)


11. **매핑 대상 CustomerService...** 이란 이름의 두 번째 노드를 클릭 한 다음, 팝업 메뉴에서 `편집` `펜`단추를 더블클릭하십시오.

![](images/303/06.integration.map.png)


12. **CustomerServiceActivity** 매핑 페이지가 표시됩니다. 왼쪽에 있는 **Source**트리의 일부 필드와 오른쪽에있는 **Target**트리의 일부 필드에는 녹색 동그라미가 있습니다. 이는 매핑이 구성되어 이러한 소스에서 대상 필드사이에서 매핑되었음을 의미합니다. (이미 가져 오기 중에 완료) 예를 들어 **Target**트리 아래의 customerId는 **Source**트리에서 같은 이름 필드 `customerId`로 매핑되었습니다. 이제 **Target** 아래의 두 번째 필드 인 `activityName`을 살펴보고 아래의 **Mapping** 열 아래에서 `f (x), offerid, acceptance, accepted`라는 텍스트를 클릭하겠습니다.

![](images/303/06.integration.map1.png)


13. **매핑 생성(Build Mappings)**대화 상자 창이 나타납니다. 매핑은 다음 그림 처림 문자열과 변수 값이 concat한 것임을 확인할 수 있습니다. 확인 후 하단 `닫기(Close)`를 클릭합니다.
`![](images/303/06.integration.map2.png)


14. **CustomerServiceActivity** 매핑 페이지로 돌아가서, 화면에서 아래의 **매핑** 열 아래에 있는 `f (x), productid`라는 텍스트를 클릭하십시오.

![](images/303/06.integration.map3a.png)


15. **매핑 생성(Build Mappings)** 대화 상자 창에 가져온 매핑이 표시됩니다 : <xsl:value-of select = 'concat("Offer for product ID: ", /nssrcmpr:execute/nsmpr0:request-wrapper/nsmpr0:productid)'> 일단 검토가 끝나면 오른쪽 하단에있는 `닫기`버튼을 클릭하십시오.

![](images/303/06.integration.map3.png)


16. **CustomerServiceActivity** 매핑 페이지로 돌아가서, 화면에서 아래의 **매핑** 열 아래에있는 마지막 필드 텍스트 인 f(x)를 클릭하십시오.

![](images/303/06.integration.map4a.png)


17. **매핑 생성(Build Mappings)** 대화 상자 창이 나타납니다 : <xsl:value-of select = 'fn:current-data()'> `이것은 ICS가 기본 제공하는 함수로써, 왼쪽 하단의 **매핑 구성 요소(Mapping Components)** 트리를 확장하여 많은 함수들을 자유롭게 찾아서 쓸 수 있습니다. 검토가 완료되면 오른쪽 하단에있는 `닫기`버튼을 클릭하십시오.

![](images/303/06.integration.map4.png)


18. **CustomerServiceActivity** 페이지 화면으로 돌아가서 오른쪽 상단에있는 `닫기`버튼을 클릭하십시오.

![](images/303/06.integration.map5.png)


19. 캔버스 화면으로 돌아가서 **CustomerServiceActivity**라는 세 번째 노드를 선택하고 팝업 메뉴에서 `편집` `펜`단추를 더블 클릭하십시오.

![](images/303/07.integration.soap.png)


20. **SOAP 엔드 포인트** 구성 대화 상자가 표시됩니다. SOAP 기반 인터페이스는 WSDL기반으로 동작하기 때문에 별도 수정할 수 있는 여기서는 사항이 없습니다. 이 페이지를 검토하고 오른쪽 상단의 `취소`버튼을 클릭하기 만하면됩니다.

![](images/303/07.integration.soap1.png)


21. 캔버스 화면으로 돌아가서 **IF Accept Offer**라는 네 번째 노드를 선택하고 팝업 메뉴에서 `편집` `펜` 단추를 더블 클릭하십시오.

![](images/303/08.integration.if.png)


22. IF 조건문 표현식 페이지가 표시됩니다. 텍스트 영역에 `lower-case (accepted) = 'true'` 라는 조건이 설정되어 있고 왼쪽의 **Source** 아래에 있는 `accepted` 필드 옆에 녹색 체크 표시가 있습니다. 이 함수는 `accepted`의 소문자 문자열 값에 따라 true 또는 false 결과를 반환하도록 평가합니다. 여기서 결과는 **IF** 또는 **ELSE**경로를 향한 메시지 흐름을 결정하는 데 사용됩니다. 검토가 끝나면 오른쪽 상단의 `닫기`를 클릭하십시오.

![](images/303/08.integration.logic.png)


23. *If* 또는 *Otherwise* 조건에서 진행 경로가 결정됩니다. 이제 전체 통합 흐름을 완료하기 위해 *If* 경로에 추가해야 할 작업 하나가 있습니다.

![](images/303/34.integration.if.difference.png)


24. 고객이 제안을 수락 할 때, 즉 `lower-case (accepted) = 'true'` 일때 적절한 응답을 처리하기 위해 응답 데이터의 누락 된 **맵**을 *If* 경로에 구성해야 합니다. 오른쪽 창에서`작업(Actions)`를 클릭하고 `맵(Map)`을 드래그하여 **IF Accept Offer** 노드 다음의 `+` 위치에 드롭합니다.

![](images/303/35.integration.if.add1.png)

![](images/303/35.integration.if.add2.png)


25. `맵(Map)` 작업이 드랍되면, **Data Mapping** 대화 상자 창이 열립니다. 왼쪽 창에서**Source**를 확장하고`$ CustomerServiceActivity` ->`addCustomerActivityResponse` 아래에 `return` 필드를 드래그하여 오른쪽 창에있는`activityid`에 놓습니다.

![](images/303/36.integration.if.map.png)

26. 우측 대상 필드 중 `imgurl`을 클릭합니다.

27. 매핑 대화 상자가 나타납니다. 왼쪽 된 창에서 **Source**아래의 **매핑 구성요소(Mapping Components)**를 확장 한 다음,`함수(Functions)` ->`문자열(String)`을 확장하십시오. `concat` 함수를 드래그 하여 `끌어 놓기 또는 여기에 값 입력(Drag and Drop or Type value here...)`로 드랍합니다.

![](images/303/37.integration.if.map1.png)


28. concat 함수의 두 파라미터를 입력합니다.
  + string1: `string1`을 클릭하고, `'https://qrcodegenerator-<Your Application Container Cloud Identity Domain Hostname>/ctdqr/v1/offer/'`을 입력합니다. 작은 따옴표를 URL의 앞과 뒤에 넣어야합니다. (<Your Application Container Cloud Identity Domain Hostname>는 `Microservices`랩에서 얻은 호스트 이름입니다.)
	+ string2: 왼쪽 창에서 `Source`를 확장하고 `offerid` 필드를 드래그하여 `string2`에 놓습니다. 자동으로 XPath 형식으로 변경됩니다.

29. 저장후 닫기 버튼을 클릭합니다.


![](images/303/38.integration.if.map2.png)


30. 데이터 맵핑은 아래와 같아야합니다. `확인`을 클릭 한 다음 `닫기`를 클릭하십시오.

![](images/303/39.integration.if.map3.png)


31. 조정(Orchestration) 프로세스 개발이 완료되었습니다.

![](images/303/40.integration.flow.complete.png)


32. 햄버거 아이콘을 클릭 한 다음 오른쪽 상단 모서리에 있는 `추적(Tracking)`을 선택하십시오.

![](images/303/42.integration.tracking.png)


33. **Business Identifiers for Tracking** 대화 상자 창이 표시됩니다. 비즈니스 식별자는 메시지에 대한 런타임 트랜잭션 추적, 특히 ICS를 통해 실행되는 수십만 개의 메시지가 필요한 경우 필요합니다. `businessid`,`offerid` 및 `productid`가 이미 매핑 된 Tracking 비즈니스 식별자에 주목하십시오. 화면은 다음과 같습니다.

![](images/303/43.integration.tracking.identifier1.png)


34. ICS 대시 보드 기본 화면으로 돌아가려면 각각 `저장`및 `닫기`버튼을 클릭하십시오.

![](images/303/43.integration.edit.done.png)


35. **통합(Integrations)** 페이지에서, 새로 생성 된 `integration`의 **Switch**버튼을 클릭하면,`통합을 활성화하시겠습니까?(Activate Integration?)` 대화 상자가 나타납니다. 운영환경에서는 체크하는 것이 좋지 않지만 나중에 테스트하기 위해 `Enable tracing` 및 `Include payload`를 선택하십시오.

![](images/303/44.integration.activate.png)


36. 통합 활성화를 위해 2 분 정도 기다리십시오. 완료되면 통합을 알리는 녹색 배너가 성공적으로 활성화되었으며 그 결과는 다음과 같습니다.

![](images/303/45.integration.activate.done.png)


37. 브라우저에서 고유한 URL을 클립 보드로 저장하거나 복사하십시오 :`https://integration-xxxxxxxxxxx.integration.xxx.oraclecloud.com:443/integration/flowapi/rest/XXX_ICS_INTMGT/`

38. 이제 통합 서비스가 테스트 준비가 되었습니다.

[Proceed to Next - 304: Testing the service and Monitoring with ICS Dashboards](304-IntegrationsLab.md)

또는

[Back to Integrations Lab Home](README.md)
