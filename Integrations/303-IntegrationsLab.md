# 오라클 클라우드 테스트 드라이브 #
-----
## 303 : 통합 완료 - 오케스트레이션 통합 흐름 ##


### 소개 ###
이 자습서에서는 다음 작업을 수행하는 방법을 보여줍니다. 
- ICS (Integration Cloud Service)에 대한 통합 플로우 완성 

### 오늘 Practice에 대하여 ###
이 연습에서는 다음을 수행합니다. 
- REST 및 SOAP 끝점을 사용하여 ICS 통합 흐름을 탐색하고 통합 흐름에 따라 나머지 데이터 매핑을 완료합니다. 
- 웹 기반 클릭을 사용하여 통합 리소스 세부 정보를 탐색하고 ICS 대시 보드에서 데이터 매핑을 정의하는 기술을 구성, 끌어서 놓기 

### 선수 과목 ###

- 통합 클라우드 서비스를 포함한 Oracle Public Cloud Service 계정 
- 이미 구성된 ICS의 SOAP 및 REST 연결 (302- 통합 라이브러리 .md) 

#### Complete an 'Orchestration' 통합 ####

1. 탐색 창을 사용하여 왼쪽 상단에있는 햄버거 메뉴 아이콘을 클릭하여 탐색 창을 표시 한 다음 `통합`을 클릭하십시오. 

![](images/303/01.home_hamburger_integrations.png)


2. **통합**요약 페이지가 표시됩니다. 목록에서**XXX_ICS_INTMGT (1.0)**항목을 찾은 다음 오른쪽에있는 햄버거 메뉴 아이콘을 클릭하고 `편집`을 선택하십시오. 

![](images/303/02.integration_edit.png)


3. 이전에 가져온 통합 플로우**XXX_ICS_INTMGT (1.0)**의 통합 오 케스트 레이션 편집기가 표시됩니다. 이는 다음 단계가 나머지 부분을 완료하는 불완전한 흐름입니다. 

![](images/303/03.integration_existing.png)


4. 변경하기 전에 가져 오기 중에 사전 빌드 된 내용을 검토 합니다.**ProcessOrder**라는 첫 번째 노드를 클릭하여 선택하고 팝업 메뉴에서 `편집` `펜`버튼을 클릭하십시오. 

![](images/303/04.integration.processoffer.png)


5. **Oracle REST Endpoint 구성**대화 상자 창이 표시됩니다. 이 페이지는 임포트 된 통합 플로우의 인터페이스, 즉 적절한 JSON 형식으로 REST 요청 및 응답을 통해이 프로세스와 상호 작용하는 방법을 요약합니다. 나머지 세부 사항을 보려면 오른쪽 상단에있는 &lt;뒤로> 버튼을 클릭하십시오. 

![](images/303/05.integration.rest.summary.png)


6. 이 페이지는 응답 페이로드 세부 사항을 요약하여 변경하지 않고이 페이지의 세부 사항을 자유롭게 탐색 할 수 있습니다. 중간에 `<<< inline >>>`링크를 클릭하십시오. 

![](images/303/05.integration.rest.response.payload.png)


7. **Response Sample Json Payload**의 형식이 표시됩니다.`{"activityid": "elit aliqua aliquip", "imgurl": "minim ipsum"}` 아래에있는 `Cancel`버튼을 클릭하면 돌아갑니다. 

![](images/303/05.integration.rest.response.payload1.png)


8. 오른쪽 상단의 `&lt;뒤로`버튼을 클릭하여 나머지 세부 사항을 검토하십시오. 

![](images/303/05.integration.rest.response.png)


9. 이 페이지는 요청 페이로드 세부 사항을 요약하여 변경하지 않고이 페이지의 세부 사항을 자유롭게 탐색 할 수 있습니다. 
`{"customerid": 21767684, "offerid": 49531393, "productid": 28916305,   "accepted": true}`  
맨 위의`<뒤로` 버튼을 클릭하십시오. 남은 세부 사항을 검토 할 수 있습니다. 

![](images/303/05.integration.rest.request.png)


10. 마지막으로,**Oracle REST Endpoint Configuration Wizard 시작 페이지**가 표시되며이 REST Endpoint 인터페이스의 전체 설정을 요약합니다. 아무 것도 변경하지 않고 오른쪽 상단의 `취소`버튼을 클릭하여 오케스트레이션 흐름을 반환하십시오. 

![](images/303/05.integration.rest.endpoint.png)


11. **CustomerService ...로 맵핑 된 두 번째 노드를 클릭 한 다음, 팝업 메뉴에서 `편집` `펜`단추를 클릭하십시오. 

![](images/303/06.integration.map.png)


12. **CustomerServiceActivity**맵 페이지가 표시됩니다. 왼쪽에있는 **Source**트리의 일부 필드와 오른쪽에있는 **Target**트리의 일부 필드에는 녹색 틱 라디오 버튼이 있습니다. 이는 매핑이 구성되어 이러한 원본에서 대상 필드 엔터티 사이에서 사용됨을 의미합니다. (이미 가져 오기 중에 완료) 예를 들어**Target**트리 아래의 CustomerId는**Source**트리에서 같은 이름 필드 엔터티`customerId`로 매핑되었습니다. 이제**Target**아래의 두 번째 필드 인`activityName`을 살펴보고 아래의**Mapping**열 아래에서 `f (x), offerid, acceptance, accepted`라는 텍스트를 클릭하겠습니다. 

![](images/303/06.integration.map1.png)
<html>

13. **Build Mappings**대화 상자 창이 나타납니다. 매핑은 다음 매핑으로 가져 와서 완료되었습니다.`![](images/303/06.integration.map2.png)


14. **CustomerServiceActivity**페이지로 돌아 가기 화면에서 아래의**매핑**열 아래에있는 `f (x), productid`라는 텍스트를 클릭하십시오. 

![](images/303/06.integration.map3a.png)


15. **Build Mappings**대화 상자 창에 가져온 매핑이 표시됩니다 : <xsl:value-of select = 'concat("Offer for product ID: ", /nssrcmpr:execute/nsmpr0:request-wrapper/nsmpr0:productid)'> 일단 검토가 끝나면 오른쪽 하단에있는 `닫기`버튼을 클릭하십시오. 

![](images/303/06.integration.map3.png)


16. **CustomerServiceActivity**페이지로 돌아 가기 화면에서 아래의**매핑**열 아래에있는 마지막 필드 텍스트 인 f (x)를 클릭하십시오. 

![](images/303/06.integration.map4a.png)


17. 가져 오기 매핑과 함께**Build Mappings**대화 상자 창이 나타납니다 : <xsl:value-of select = 'fn:current-data()'> `이것은 통합 클라우드 서비스가 제공하는 즉시 사용할 수있는 기능으로, 왼쪽 하단의**매핑 구성 요소**트리를 확장하여이 기능 (기능 -> 날짜 범주 아래) 및 기타 많은 기능을 자유롭게 찾을 수 있습니다 모서리. 검토가 완료되면 오른쪽 하단에있는 `닫기`버튼을 클릭하십시오. 

![](images/303/06.integration.map4.png)


18. **CustomerServiceActivity**페이지 화면으로 돌아가서 오른쪽 상단에있는 `닫기`버튼을 클릭하십시오. 

![](images/303/06.integration.map5.png)


19. 오케스트레이션 흐름으로 돌아가서**CustomerServiceActivity**라는 세 번째 노드를 선택하고 팝업 메뉴에서 `편집` `펜`단추를 클릭하십시오. 

![](images/303/07.integration.soap.png)


20. **SOAP 엔드 포인트 구성 대화 상자가 표시됩니다. SOAP 기반 인터페이스의 특성으로 인해 구성 할 수있는 추가 페이지가 없습니다. 이 페이지를 검토하고 오른쪽 상단의 `취소`버튼을 클릭하기 만하면됩니다. 

![](images/303/07.integration.soap1.png)


21. 오케스트레이션 흐름으로 돌아가서**IF Accept Offer**라는 네 번째 노드를 선택하고 팝업 메뉴에서 `편집` `펜`단추를 클릭하십시오. 

![](images/303/08.integration.if.png)


22. **제안 수락**페이지가 표시됩니다. 텍스트 영역에 `lower-case (accepted) = &quot;true&quot;라는 논리 결정이 내려졌고 왼쪽의**Source**아래에있는`accepted` 필드 옆에 녹색 체크 표시가 있습니다. 이 함수는 `accepted`의 소문자 문자열 값에 따라 true 또는 false 결과를 반환하도록 평가합니다. 여기서 결과는**IF**또는**ELSE**경로를 향한 메시지 흐름을 결정하는 데 사용됩니다. 검토가 끝나면 오른쪽 상단의 `닫기`를 클릭하십시오. 

![](images/303/08.integration.logic.png)


23. *if*또는*otherwise*조건에서 다른 응답 데이터가 리턴됩니다. 이제 전체 통합 흐름을 완료하기 위해*if*경로에 남아있는 작업 하나가 있습니다. 

![](images/303/34.integration.if.difference.png)


24. 고객이 제안을 수락 할 때 적절한 응답을 처리하기 위해 응답 데이터의 누락 된**맵**을*if*경로에 구성해야합니다. 오른쪽 창에서`Actions`를 클릭하고`Map`을 드래그하여**IF Accept Offer**노드와`+`아이콘과 함께 나타나는 두 개의 스위치 라인의 연결 지점 사이의 통합 흐름으로 드롭하십시오 이하. 

![](images/303/35.integration.if.add1.png)


![](images/303/35.integration.if.add2.png)


25. `Map`이 제대로 삭제되면**Data Mapping**대화 상자 창이 열립니다. 왼쪽 창에서**Source**를 확장하고`$ CustomerServiceActivity` ->`addCustomerActivityResponse` 아래에`return` 필드를 드래그하고 오른쪽 창에있는`activityid`에 놓습니다. 
	Click `imgurl` to proceed advance data mapping.

![](images/303/36.integration.if.map.png)


26. **Build Mappings**대화 상자가 나타납니다. 왼쪽 된 창에서**Source**아래의**Mapping Components**를 확장 한 다음,`Functions` ->`String`을 확장하십시오. 
	Drag the function `fx concat` and drop it onto `- Drag and Drop or Type value here...` under **Mapping** in right pane.  
	
![](images/303/37.integration.if.map1.png)


27. `string1`을 클릭하고, ``sign, ie`'https://qrcodegenerator-<Your Application Container Cloud Identity Domain Hostname>/ctdqr/v1/offer/'` 작은 따옴표를 URL의 앞과 뒤에 넣어야합니다. ( `Microservices`랩에서 얻은 호스트 이름) 다음으로, 왼쪽 창에서`Source`를 확장하고`offerid` 필드를 드래그하여`string2`에 놓습니다. 문자열이 자동으로 삽입됩니다. \ ( `offerid`\의 XSLT 변수 표현입니다.) 
	Click `Save`, and then click `Close` button at the bottom to return previous screen.


![](images/303/38.integration.if.map2.png)


28. *데이터 맵핑*은 아래와 같아야합니다. `확인`을 클릭 한 다음 `닫기`를 클릭하십시오. 

![](images/303/39.integration.if.map3.png)


29. *프로세스 제안*통합 플로우 개발이 완료되었습니다. 

![](images/303/40.integration.flow.complete.png)


30. 햄버거 아이콘을 클릭 한 다음 오른쪽 상단 모서리에있는 `Tracking`을 선택하십시오. 

![](images/303/42.integration.tracking.png)


31. **Business Identifiers for Tracking** 대화 상자 창이 표시됩니다. 비즈니스 식별자는 메시지에 대한 런타임 트랜잭션 추적, 특히 ICS를 통해 실행되는 수십만 개의 메시지가 필요한 경우 필요합니다. `businessid`,`offerid` 및`productid`가 이미 매핑 된 Tracking 비즈니스 식별자에 주목하십시오. 화면은 다음과 같습니다. 
	Click `Cancel` button at the bottom on review completion of tracking setup to close the dialog.


![](images/303/43.integration.tracking.identifier1.png)


32. ICS 대시 보드 기본 화면으로 돌아가려면 각각 `저장`및 `닫기`버튼을 클릭하십시오. 

![](images/303/43.integration.edit.done.png)


33. **Integrations**Summary 페이지에서, 새로 생성 된`integration`의**Switch**버튼을 클릭하면,`Activate Integration? `대화 상자가 나타납니다. 프로덕션 트래픽을 처리 할 때 켜는 것은 좋지 않지만 나중에 테스트하기 위해 `Enable tracing`및 `Include payload`를 선택하십시오. 
	Click `Activate` button at the bottom.


![](images/303/44.integration.activate.png)


34. 통합 활성화를 위해 2 분 정도 기다리십시오. 완료되면 통합을 알리는 녹색 배너가 성공적으로 활성화되었으며 그 결과는 다음과 같습니다. 

![](images/303/45.integration.activate.done.png)


35. 브라우저에서 고유 한 URL을 클립 보드로 저장하거나 복사하십시오 :`https://integration-xxxxxxxxxxx.integration.xxx.oraclecloud.com:443/integration/flowapi/rest/XXX_ICS_INTMGT/`

36. 이제 통합 서비스가 테스트 준비가되었습니다. 

[Procced to Next - 304: Testing the service and Monitoring with ICS Dashboards](304-IntegrationsLab.md)

또는

[Back to Integrations Lab Home](README.md)
