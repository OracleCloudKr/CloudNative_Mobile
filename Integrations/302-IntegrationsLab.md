# 오라클 클라우드 테스트 드라이브 #
-----
## 302 : CRM 고객 활동 서비스 및 REST 서비스 노출에 대한 연결 임포트 및 정의 ##


### 소개 ###
이 튜토리얼에서는 다음 작업을 수행하는 방법을 보여줍니다. 
- REST 트리거 서비스 노출에 대한 ICS 연결 임포트 및 정의 및 외부 SOAP 서비스 호출 

### 오늘 Practice에 대하여 ###
이 연습에서는 다음을 수행합니다. 
- 웹 기반 클릭 및 구성 기술을 사용하여 ICS 연결 리소스를 가져오고 정의합니다.**SOAP**및**REST**. 

### 선수 과목 ###

- 통합 클라우드 서비스를 포함한 Oracle Public Cloud Service 계정 
- 강사가 배포 한 `XXX_ICS_INTMGT_01_lab.iar`의 통합 아카이브 파일 (IAR) 이름 

#### 임포트 통합 클라우드 서비스 프로젝트 아티팩트 

1. `Integrations` 파란색 아이콘을 클릭하여**Integrations**Summary 페이지로 이동하십시오. 

![](images/302/01.home_integrate.png)


또는 왼쪽 상단 모서리에있는 햄버거 아이콘을 클릭하고 `설계자`를 클릭 한 다음 `통합`을 클릭하여 **통합**요약 페이지로 이동할 수 있습니다. 

![](images/302/02.home_hamburger.png)


![](images/302/03.home_hamburger_designer.png)


![](images/302/01.home_hamburger_integrate.png)


2. 오른쪽 상단의 `임포트`를 클릭하면 **임포트 통합**대화 상자 창이 나타납니다. `찾아보기 `버튼을 클릭하십시오. 

![](images/302/02.integration_import.png)


3. 컴퓨터 로컬 디렉토리를 찾아서 열어 이전에 강사가 제공 한*IAR*파일을 선택한 다음`임포트 `버튼을 클릭하십시오. 

![](images/302/02.integration_import1.png)


4. 통합 목록에**통합이 성공적으로 임포트**및 새로 가져온 엔티티**XXX_ICS_INTMGT (1.0)**에 대한 녹색 대화 상자 텍스트 영역이 있어야합니다. 

![](images/302/02.integration_import2.png)


부분적으로 사전 빌드 된 아티팩트 세트를 가져 왔습니다. 우리는 건설 된 것을 걷고 나머지 부분을 완성 할 것입니다. 

#### CRM 고객 활동 서비스를위한 SOAP 연결 정의 

5. 왼쪽 상단 모서리에있는 햄버거 아이콘을 클릭하여 **접속**요약 페이지로 이동하여 `설계자`와 `접속`을 차례로 클릭하십시오. 

![](images/302/04.home_hamburger_connections.png)


6. **Connections**홈 페이지에서 **XXX_CRM_CustomerService**및 **XXX_ICSINTMGT_ProcessOffer**라는 새로 가져온 연결 엔터티를 각각 찾을 수 있어야 합니다. 

![](images/302/05.connection_import.png)


7. 그런 다음**XXX_CRM_CustomerService** Connection 행에서 오른쪽에 있는 햄버거 메뉴 아이콘을 클릭하고 아래의 `편집`을 선택하십시오. 

![](images/302/05.connection_import1.png)


8. **XXX_CRM_CustomerService**연결 세부 사항 페이지가 표시됩니다. 명시된 바와 같이, 이것은*서비스 엔드 포인트를 호출*SOAP*프로토콜 기반 연결입니다. 이 연결 세부 사항을 정의 할 것입니다. 

![](images/302/07.connection_initial.png)


9. 아래로 스크롤하여 **접속 속성**섹션을 열고 `접속 구성`버튼을 클릭하십시오. 

![](images/302/05.connection_import2.png)


10. **연결 등록 정보**대화 상자 창이 표시됩니다.**WSDL URL**에 **Property Value**를 다음 형식으로 제공하여 채웁니다. 
	* **http://\<Your Java Cloud Service Instance IP Address\>/crm/CustomerServicePort?WSDL** 
	*\*If you forget your JCS instance IP address, [Click Here!](../../Java%20Apps/java.cloud.md)*  
	Leave other properties **empty** as they are optional and not required in this lab exercise.
	
![](images/302/08.connection_properties.png)


11. 다른 속성 설정은 변경하지 마십시오. 변경 사항을 저장하려면 `확인`버튼을 클릭하십시오. 엔드 포인트 인터페이스에서 필요하기 때문에 `보안 정책 없음`이 선택됩니다. 

12. **SOAP Connection**페이지의 맨 위에서 오른쪽 상단의 `테스트`를 클릭하면 테스트**확인**대화 상자 창이 표시됩니다. 
	Click `Validate and Test` button.


![](images/302/10.connection_test.png)


13. **연결 테스트가 성공적으로 완료되었음을 나타내는 녹색 대화 상자 텍스트 영역을 찾아야합니다**. 

![](images/302/11.connection_testresult.png)


14. 그런 다음 오른쪽 상단에서 `저장`을 클릭하십시오. 

![](images/302/12.connection_save.png)


15. **변경 사항을 저장 하시겠습니까?** 대화 상자 창이 나타납니다. 대화 상자를 닫으려면 대화 상자를 닫고 `저장`을 클릭하십시오. 

![](images/302/12.connection_save1.png)


16. **연결이 성공적으로 저장되었습니다**에 대한 녹색 대화 상자 텍스트 영역을 찾아야합니다. `닫기`를 클릭하여 종료하고 **연결**요약 페이지로 돌아갑니다. 

![](images/302/13.connection_saveresult.png)


17. CRM 고객 서비스에 대한*SOAP 연결이 업데이트되었고 \*호출 할 준비가되었습니다*. 

#### ICS 서비스 노출에 대한 REST 연결 정의 

18. 이제 우리는**XXX_ICSINTMGT_ProcessOffer**연결을 업데이트 할 것입니다. 그러나 이번에*Connection*은 모든 엔드 포인트 서비스를 \*invoke \**하는 것이 아니라 대신 프론트 클라이언트, 즉 모바일 클라이언트에 의해 호출되는*\*트리거 \**입니다. 이*REST*연결 서비스로*트리거합니다. 
	
	Make sure you are still on **Connections** Summary Page. If not, follow step 1 previously.  
	On the row of **XXX_ICSINTMGT_ProcessOffer** Connection, click the hamburger menu icon at the right side and select `Edit` like below.
	
![](images/302/14.connection_rest.png)


19. 이번에**XXX_ICSINTMGT_ProcessOffer**연결 세부 정보 페이지가 표시되며*REST 트리거*유형 연결로 인해 더 간단합니다. 

![](images/302/16.connection_initial1.png)


20. **REST Connection**페이지에서 오른쪽 상단 모서리에있는 `Test`를 클릭하십시오.**연결 테스트가 성공적으로 완료되었습니다**에 대한 녹색 대화 상자 텍스트 영역을 찾아야합니다. 

![](images/302/18.connection_test1.png)


21. 그런 다음 오른쪽 상단에서 `저장`을 클릭하십시오. 마찬가지로**변경 사항 저장?**대화 상자가 나타나 통합을 다시 활성화하는 방법에 대해 경고하고 `저장`을 클릭하여 확인한 다음 대화 상자를 다시 닫습니다. 

![](images/302/20.connection_save2.png)


22. **연결이 성공적으로 저장되었습니다**에 대한 녹색 대화 상자 텍스트 영역을 찾아야합니다. `닫기`를 클릭하여 종료하고**연결**요약 페이지로 돌아갑니다. 

![](images/302/19.connection_save1.png)


23. 두 개의*연결*이 준비됩니다.**SOAP 연결 - \*CRM 고객 서비스로의***및**REST 연결 - \*트리거**에서 프로세스 제안**에 대한 ICS로 각각 연결됩니다. 

[Procced to Next - 303: Complete an Integration - An Orchestration Integration Flow](303-IntegrationsLab.md)

or

[Back to Integrations Lab Home](README.md)
