# 오라클 클라우드 테스트 드라이브 #
-----
## 100 : 로열티 관리 응용 프로그램을위한 데이터베이스 연결 만들기 [TBD] ##


### 소개 ###
이 자습서에서는 다음 작업을 수행하는 방법을 보여줍니다. 
- 나중에 JEE 응용 프로그램에서 관련 테이블을 사용할 WebLogic Server에 충성도 관리 데이터베이스 연결을 생성합니다. 

### 선수 과목 ###

- Developer Cloud Service 및 Java Cloud Service를 포함한 Oracle Public Cloud Service 계정 (없는 경우 강사와 확인) 
- [Loyalty Management Database connectivity for WebLogic Server instance in Java Cloud Serivce](100-JavaAppsLab.md) 

----


#### WebLogic Server에서 데이터베이스 연결 만들기 

1. 액세스 문서의 [Sign in](sign.in.to.oracle.cloud.md) to [https://cloud.oracle.com/sign-in](https://cloud.oracle.com/sign-in) by provided **Java Cloud Service (JCS)**ID 도메인 ID 및 자격 증명. 대시 보드를 사용하여 Java Cloud Service Console을 엽니 다. 

![](images/100/00.png)


2. 서비스 요약의 오른쪽 위에있는 햄버거 아이콘을 클릭하십시오. 메뉴에서 WebLogic Server 콘솔 열기를 선택하십시오. 

![](images/100/01.png)


3. 새 브라우저가 열리고 선택한 콘솔의 로그인 페이지로 리디렉션됩니다. 서버가 자체 서명 된 인증서로 보호되는 경우이 인증서가 신뢰되지 않는다는 경고 메시지가 표시됩니다. 이것은 기본 구성이며 인증을 구성 할 수 있습니다. 위험 이해 및 예외 추가 (인증서 승인)를 선택합니다. 

![](images/100/02.png)


4. 대화 상자가 나타나면 보안 예외 확인을 선택하십시오. 

![](images/100/03.png)


5. 콘솔 로그인 페이지가 나타나면 WebLogic 관리자에 대해 입력 한 로그인 자격 증명을 입력하십시오. 예 : 
- **사용자 이름**:`weblogic` 
- **비밀번호**:`Welcome_1` 

![](images/100/04.png)


6. 로그인이 완료되면 WebLogic Server 관리 콘솔이 표시됩니다. 잠금 및 편집 및 서비스 -> 데이터 소스를 클릭하십시오. 새**일반 데이터 소스 만들기**

![](images/100/05.png)


7. 다음 매개 변수를 사용하여 데이터 소스를 구성합니다. 
+ **이름**: loyaltyDataSource 
+ **범위**: 전체 (기본값) 
+ **JNDI 이름**: jdbc / loyaltyDS 
+ **데이터베이스 유형**: Oracle (기본값) 

8. 다음을 클릭하십시오. 

![](images/100/06.png)


9. 기본 데이터베이스 드라이버를 그대로두고 다음을 클릭하십시오. 

![](images/100/07.png) 


10. 기본 트랜잭션 옵션을 그대로두고 다음을 클릭하십시오. 

![](images/100/08.png)


11. 데이터베이스 서비스 연결 설명자를 구성하십시오. 
+ **데이터베이스 이름**:`PDB1. <Your Identity Domain> .oraclecloud.internal` 
+ **호스트 이름**: 응용 프로그램을 실행할 데이터베이스 클라우드 서비스, 즉`apacctddb.compute- <Your Identity Domain> .oraclecloud.internal` 또는 (강사가 제공 한)` 
+ **포트**: 기본값 1521 남기기 
+ **데이터베이스 사용자 이름**: 충성도 
+ **비밀번호**: 데이터베이스 사용자의 `충성도`비밀번호, 즉 Welcome_1 또는 (intructor가 제공 한) 
+ **oracle.jdbc.DRCPConnectionClass**: 비워 두십시오. 

12. 다음을 클릭하십시오. 

![](images/100/09.png)


13. **Test Configuration**을 클릭하여 데이터 소스를 테스트합니다. 

![](images/100/10.png)


14. 응용 프로그램을 전개 할 서버 또는 클러스터를 선택하십시오. 이 자습서에서는 클러스터의 모든 서버에 응용 프로그램을 배포하도록 선택하고 마침을 클릭합니다. 

![](images/100/11.png)


15. **변경 사항을 활성화하고 확인을 확인하십시오 :`모든 변경 사항이 활성화되었습니다. 다시 시작할 필요 없음` 

![](images/100/12.png)


이 Lab 섹션을 마쳤습니다. 

[Procced to Next - 101: Create Oracle Developer Cloud Service Loyalty Management application project using initial GitHub repository](101-JavaAppsLab.md)

or

[Back to JavaAppsLab Home](README.md)
