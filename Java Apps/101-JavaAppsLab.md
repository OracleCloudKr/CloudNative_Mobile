# 오라클 클라우드 테스트 드라이브 #
-----
## 101 : 초기 GitHub 저장소를 사용하여 Oracle Developer Cloud Service 로열티 관리 애플리케이션 프로젝트 생성 ##


### 소개 ###
이 자습서에서는 다음 작업을 수행하는 방법을 보여줍니다. 
- 기존 외부 Git 저장소를 사용하여 Oracle Developer Cloud Service 프로젝트 생성 - GitHub 

### 오늘 Practice에 대하여 ###
이 연습에서는 다음을 수행합니다. 
- 로열티 관리 시스템을위한 새로운 개발자 클라우드 서비스 프로젝트 만들기 
충성도 관리 Java 응용 프로그램 소스 코드를 저장할 새로운 Developer Cloud Service Git 저장소 만들기 
- Gitub에 저장된 외부 Git 저장소를 위에서 작성한 Developer Cloud Service Git 저장소에 복제합니다. 

### 선수 과목 ###

- 개발자 클라우드 서비스를 포함한 Oracle Public Cloud Service 계정 (없는 경우 강사와 확인) 

----


#### Oracle Cloud에 로그인하십시오. 

1. 브라우저를 열고 [cloud.oracle.com](https://cloud.oracle.com)으로 이동하십시오.**로그인**을 클릭하십시오. 

![cloud.oracle.com](images/sign-in/sign.01.cloud.oracle.com.png)


2. 기존 클라우드 계정을 선택한 다음 환경의 데이터 센터에 따라 &#39;Public Cloud Service - EMEA` 또는&#39;Public Cloud Servce - US &#39;를 선택하십시오.**내 서비스**버튼을 클릭하십시오. 
![](images/sign-in/sign.02.select.datacenter1.png)


3. **Developer Cloud Service \ (DevCS \)**ID 도메인을 입력하고**Go**를 클릭하십시오. ID 도메인 및 관련 자격 증명은 강사가 제공해야합니다. 
![](images/sign-in/sign.03.identity.domain.png)


4. 서비스 관리자 역할이있는 사용자의 DevCS 사용자 이름과 암호를 입력하십시오.**로그인**을 클릭하십시오. 
![](images/sign-in/sign.04.credentials.png)


5. 로그인이 성공하면 대시 보드가 표시됩니다. 대시 보드에는 서비스별로 미리 정의 된 타일이 있습니다.**개발자 클라우드 서비스**타일이 표시되지 않으면**대시 보드 사용자 정의**를 클릭하고**개발자**서비스를 표시하여 대시 보드에 표시하십시오. 
![](images/sign-in/sign.05.dashboard.new.png)
![](images/sign-in/sign.06.customize.png)


#### Oracle Developer Cloud Service 프로젝트 생성 

6. 이제 개발자 서비스 타일을 찾아 햄버거 아이콘을 클릭하십시오. 드롭 다운 메뉴에서**서비스 콘솔 열기**를 클릭하십시오. 

![](images/101/01.dashboard.new.png)


7. Oracle Developer Cloud Service에 로그인하고 새 프로젝트를 작성하십시오. 

![alt text](images/101/02.new.project.png)


8. 프로젝트의 이름을 입력하고 원하는 속성을 설정하십시오. 
	**Name:** `APAC Cloud Test Drive`   
	**Description:** `APAC Cloud Test Drive project hub`   
	and click **Next**


![](images/101/02.new.project.detail.png)


9. 템플릿으로*빈 프로젝트*를 선택하고**다음을 클릭하십시오**

![](images/101/03.emptyproject.png)


10. Wiki Markup으로 MARKDOWN을 선택하고**Finish**를 클릭하십시오. 

![](images/101/04.finish.png)


11. **개발자 클라우드 서비스 프로젝트 준비가 대기 중입니다**. 

![](images/101/05.wait.png)


12. 프로젝트가 준비되면 프로젝트 기본 화면이 나타납니다. 오른쪽 창에서`저장소`탭에 있는지 확인하십시오. [**+ New Repository**] 버튼을 클릭하여 새로운 Git 저장소를 만듭니다. 

![](images/101/06.newrepo.png)


13. 새 저장소 이름에 대해 다음 정보를 입력하십시오 :`LoyaltyManagement` 
	 Initial content: select `Import existing repository`   
`https://github.com/APACTestDrive/LoyaltyManagement.git`를 저장소 주소로 입력하거나 복사하십시오. [**만들기**] 버튼을 클릭하십시오. 

![](images/101/07.repoinfo.png)


14. 이제 기존 저장소를 기반으로하는 개발자 클라우드 서비스에 저장된 소스 코드로 새로운 Git 저장소를 만들었습니다. 

![](images/101/08.repocreated.png)



이 Lab 섹션을 마쳤습니다. 

[Procced to Next - 102: Define Continuous Integration 'Build' and 'Deploy' Configuration in Oracle Developer Cloud Service](102-JavaAppsLab.md)

or

[Back to JavaAppsLab Home](README.md)
