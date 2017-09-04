# 오라클 클라우드 테스트 드라이브 #
-----
## 302 : CRM 고객 활동 서비스 및 REST 서비스 노출에 대한 연결 정의 ##


### 소개 ###
이 자습서에서는 다음 작업을 수행하는 방법을 보여줍니다. 
- REST 트리거 서비스 노출에 대한 ICS 연결 정의 및 외부 SOAP 서비스 호출 

### 오늘 Practice에 대하여 ###
이 연습에서는 다음을 수행합니다. 
- 웹 기반 클릭 및 구성 기술을 사용하여 ICS 연결 리소스를 정의합니다.**SOAP**및**REST**. 

### 선수 과목 ###

- 통합 클라우드 서비스를 포함한 Oracle Public Cloud Service 계정 

#### CRM 고객 활동 서비스를위한 SOAP 연결 정의 

1. 연결**녹색 아이콘을 클릭하여**연결**요약 페이지로 이동하십시오. 

![](images/302/01.home_conn.png)


또는 왼쪽 상단의 햄버거 아이콘을 클릭하고 &#39;디자이너&#39;, &#39;연결&#39;을 차례로 클릭하여**연결**요약 페이지로 이동할 수 있습니다. 

![](images/302/02.home_hamburger.png)


![](images/302/03.home_hamburger_designer.png)


![](images/302/04.home_hamburger_connections.png)


2. **Connections**홈페이지에서 왼쪽 상단의 Create 버튼을 클릭하면**Create Connection - Select Adapter**대화 상자가 나타납니다.*Sales Cloud, E-Business Suite, Twitter, Salesforce 등과 같은 다양한 종류의 연결 어댑터를 사용할 수 있습니다. 그러나 이번 실습에서는 CRM 고객 활동 서비스 인터페이스에 연결하기 위해 간단한*SOAP*연결을 생성 할 것입니다. 이제 검색 텍스트 상자에 &#39;SOAP&#39;을 입력하여 검색을 수행 한 다음 아래 SOAP**어댑터 연결 상자에서 &#39;선택&#39;버튼을 클릭하십시오. 

![](images/302/05.connection_create.png)


3. 새 대화 상자 창**새 연결 작성**이 표시되면 다음 정보를 입력하여 첫 번째*SOAP 연결*을 작성하십시오.***이름 :** 고유하고 쉽게 식별 된*연결*이름을 제공하십시오 <Your Short Name\_<System_Name> \ _ <Service_Name> . 이 예에서는**KD_CRM_CustomerService**이고*KD*는 Kelvin Durant*의 약식 이름입니다. 
	* **Identifier:** The **Identifier** will be automatically filled-in while you type the **Name** above, however you can provide another unique identifier, suggest include your short name as prefix.
	* **Role:** Select **Invoke** from the drop-down list. (We are going to *Invoke* this service only)
	* **Description (Optional):** You can leave it empty or enter any meaningful text to describe this *SOAP Connection*.


![](images/302/06.connection_new.png)


4. &#39;생성&#39;버튼을 클릭하면 제공된**Name**이있는**SOAP Connection**페이지가 표시됩니다. 

![](images/302/07.connection_initial.png)


5. **연결 속성**섹션으로 스크롤하고 &#39;연결 구성&#39;버튼을 클릭하면**연결 속성**대화 상자 창이 표시됩니다.**WSDL URL**에**Property Value**를 다음 형식으로 제공하여 채 웁니다.***http : // \ <Your Java Cloud Service Instance IP Address\> / crm / CustomerServicePort? WSDL**
	*\*If you forget your JCS instance IP address, [Click Here!](../Java%20Apps/java.cloud.md)*  
	Leave other properties **empty** as they are optional and not required in this lab exercise.
	
![](images/302/08.connection_properties.png)


6. &#39;확인&#39;버튼을 클릭하여 변경 사항을 저장하십시오.**보안**섹션으로 스크롤하고 &#39;보안 구성&#39;버튼을 클릭하면**자격 증명**대화 상자 창이 표시됩니다.**보안 정책**에서 드롭 다운 목록에서 &#39;보안 정책 없음&#39;을 선택하십시오.*Basic Authentication*및*Username Password Token*이 지원되지만 실습에서 사용되는 보안 정책은 사용하지 않습니다. 

![](images/302/09.connection_security.png)


7. &#39;확인&#39;버튼을 클릭하여 변경 사항을 저장하십시오.**SOAP Connection**페이지에서 오른쪽 상단의 &#39;Test&#39;를 클릭하면 테스트**확인**대화 상자 창이 표시됩니다. 
	Click `Validate and Test` button.


![](images/302/10.connection_test.png)


8. **연결 테스트가 성공적으로 완료되었음을 나타내는 녹색 대화 상자 텍스트 영역이 있어야합니다. 

![](images/302/11.connection_testresult.png)


9. 그런 다음 오른쪽 상단에서 &#39;저장&#39;을 클릭하십시오. 

![](images/302/12.connection_save.png)


10. 마찬가지로**연결이 성공적으로 저장되었습니다**에 대한 녹색 대화 상자 텍스트 영역을 찾아야합니다. &#39;닫기&#39;를 클릭하여 종료하고**연결**요약 페이지로 돌아갑니다. 

![](images/302/13.connection_saveresult.png)


11. CRM 고객 서비스에 대한 SOAP 연결*이 만들어졌으며 \*호출 할 준비가되었습니다*. 

#### ICS 서비스 노출에 대한 REST 연결 정의 

이제 우리는 다른*REST*연결을 만들려고합니다. 그러나 이번에*Connection*은 모든 엔드 포인트 서비스를 \*invoke \**하는 것이 아니라 대신 프론트 클라이언트, 즉 모바일 클라이언트에 의해 호출되는*\*트리거 \**입니다. 이*REST*연결 서비스로*트리거합니다. 
	
	Make sure you are still on **Connections** Summary Page. If not, follow step 1 previously.  
	
	Click `Create` button on the top left corner, the **Create Connection - Select Adapter** dialog window is shown.  
	Enter search text `REST` in the search text box, then click `Select` button in the **REST** adapter connection box like below.
	
![](images/302/14.connection_create1.png)


12. 새 대화 상자 창**새 연결 작성**이 표시되면 다음 정보를 입력하여*REST 연결*을 작성하십시오.***이름 :** 고유하고 쉽게 식별 된*연결*이름을 제공하십시오 <Your Short Name> \ _ <System_Name> \ _ <Service_Name> . 이 예에서는**KD_ICSINTMGT_ProcessOffer**이며*KD*는 Kelvin Durant*의 약식 이름입니다. 
	* **Identifier:** The **Identifier** will be automatically filled-in while you type the **Name** above, however you can provide another unique identifier, suggest include your short name as prefix.
	* **Role:** Select **Trigger** from the drop-down list. (We are going to *Trigger* this service only)
	* **Description (Optional):** You can leave it empty or enter any meaningful text to describe this *REST Connection*.


![](images/302/15.connection_new1.png)


13. &#39;생성&#39;버튼을 클릭하면 제공된**이름**이있는**REST 연결**페이지가 표시됩니다. 이번에는*Trigger*유형 연결로 인해 페이지가 더 간단 해졌습니다. 

![](images/302/16.connection_initial1.png)


14. **보안**섹션에서 &#39;보안 구성&#39;버튼을 클릭하면**자격 증명**대화 상자 창이 열립니다.**보안 정책**에서 기본 옵션은 드롭 다운 목록에서 &#39;기본 인증&#39;입니다. 이것은 ICS가 요구하는 최소한의 보안 정책입니다. 
	Click `OK` button to save changes made.

![](images/302/17.connection_security1.png)


15. **REST 연결**페이지에서 오른쪽 상단 모서리에있는 &#39;테스트&#39;를 클릭하십시오.**연결 테스트가 성공적으로 완료되었습니다**에 대한 녹색 대화 상자 텍스트 영역을 찾아야합니다. 

![](images/302/18.connection_test1.png)


16. 그런 다음 오른쪽 상단에서 &#39;저장&#39;을 클릭하십시오.**연결이 성공적으로 저장되었습니다**에 대한 녹색 대화 상자 텍스트 영역을 찾아야합니다. &#39;닫기&#39;를 클릭하여 종료하고**연결**요약 페이지로 돌아갑니다. 

[Back to Integrations Lab Home](README.md) 

17. 2 개의 연결*이 준비됩니다.**SOAP 연결 - \*CRM 고객 서비스**에 대한**및**REST 연결 - \*Trigger \*는 Process Offer**에 대한 ICS로 각각 연결됩니다. 

[Procced to Next - 303: Create an Integration - An Orchestration Integration Flow](L303-IntegrationsLab.md)

or

[Back to Integrations Lab Home](README.md)
