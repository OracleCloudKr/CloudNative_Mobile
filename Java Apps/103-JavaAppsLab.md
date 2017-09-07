# 오라클 클라우드 테스트 드라이브 #
-----
## 103 : CICD (Continuous Integration &amp; Delivery) : Oracle Developer Cloud Service에 Brackets 사용, 코드 변경 및 푸시 코드 변경 ##


### 소개 ###
Oracle Developer Cloud Service 프로젝트는 IDE (Integrated Development Environments) 또는 Eclipse 용 Oracle Enterprise Pack (OEPE), Oracle JDeveloper 및 NetBeans IDE와 같은 텍스트 편집기에서 액세스 할 수 있습니다. 브래킷은 Oracle Developer Cloud Service와 바로 연결하여 소스를 변경할 수 있는 편리한 환경을 제공합니다. 

이 튜토리얼에서는 다음 작업을 수행하는 방법을 보여줍니다. 
- Oracle Developer Cloud Service (Brackets 포함)를 사용하여 간단하게 지속적인 통합 및 배포(CI/CD) 수행 

### 오늘 Practice에 대하여 ###
이 Lab에서는 다음을 수행합니다. 
- Brackets에서 Oracle Developer Cloud Service를 연결하고 프로젝트 소스 코드를 체크 아웃 및 업데이트합니다. 
- 업데이트 된 소스 코드를 Brackets에서 개발자 클라우드 서비스로 다시 보냅니다. 
- Developer Cloud Service의 지속적인 통합 및 배포(CI/CD) 결과 확인 

### 선수 과목 ###
+ [Create Oracle Developer Cloud Service project for Loyalty Management JEE application and deployed to Java Cloud Service WebLogic Server Container](102-JavaAppsLab.md)
+ [Installed Brackets and Git extension](brackets.md)

----


#### 개발자 클라우드 서비스에서 소스 코드 연결 및 가져 오기 

1. Brackets 텍스트 편집기를 시작하고, `파일` 풀다운 메뉴에서 `폴더 열기`를 선택하십시오. 

![](images/103/02.openfolder.png)


2. JEE 소스 코드를 저장할 대상 디렉토리를 선택하십시오 (예 :`D:\oracle`). 새 폴더를 작성한 후 새 폴더의 이름을 LoyaltyManagement로 지정하십시오. `LoyaltyManagement` 폴더를 선택한 상태에서 `Select Folder` 버튼을 클릭하십시오. 

![](images/103/03.selectfolder.png)


3. 개발자 클라우드 서비스 대시 보드로 돌아가서 **LoyaltyManagement** Git 저장소에 있습니다. HTTP를 클릭하여 Git HTTP URL을 표시하고 오른쪽에 있는 `Copy`버튼을 클릭하여 URL을 복사하십시오. 

![](images/103/04.devcs.git.png)


4. 브라켓 편집기로 돌아가서 편집기의 오른쪽에 있는 GIT 아이콘을 클릭하십시오. 

![](images/103/05.brackets.git.png)


5. Git 패널에서 Clone을 클릭하십시오. 

![](images/103/06.brackets.clone.png)


6. 개발자 클라우드 서비스에서 복사 한 GIT URL을 붙여 넣습니다. 사용자 이름은 자동으로 채워 져야합니다. 비밀번호를 입력하고 `원격 URL에 자격증 명 저장`을 선택하십시오. 하단의 `확인`버튼을 클릭하십시오. 

![](images/103/07.brackets.clone1.png)


7. 브래킷이 원격 프로젝트를 로컬 폴더에 복제 할 때까지 기다립니다. 

![](images/103/08.brackets.clone2.png)


8. 이제 Git 저장소의 로컬 사본이 있습니다. 

![](images/103/09.brackets.clone3.png)


#### 코드 변경 사항 적용 및 푸시 

9. 좌측 네비게이션 트리를 확장하고 `welcome.jsp` 파일을 엽니다 (loyalty-> src-> main-> webapp-> jsp). 기본 창에서 welcome.jsp 소스 코드 73 행을 찾으십시오. 

![](images/103/10.brackets.change.png)


14. 다음 부분을 수정하십시오. 

  	<h2>Welcome to the Loyalty Manager !!</h2>


당신이 페이지에서보고 싶은 것. 예 : 

	<h2><font color="red">APAC Test Drive</font> - Welcome to the Loyalty Manager !!</h2>


![](images/103/11.brackets.change1.png)


15. 파일을 저장하십시오. ( `Ctrl-S`누르거나 `File`>`Save` 풀다운 메뉴에서 선택하십시오) 

![](images/103/12.brackets.save.png)


16. Commit 옆에있는 상자를 선택하여 수정 된 모든 파일을 선택하십시오. 이는 아래의 체크 박스 (welcome.jsp)가 자동으로 선택되었음을 의미합니다. `Commit` 버튼을 클릭하십시오. 

![](images/103/13.brackets.commit.png)


17. 팝업창에 `변경된 헤더`를 입력하고 `확인`버튼을 클릭하십시오. 이것은 여러분의 LOCAL GIT REPOSITORY에 변경 사항을 적용합니다. 

![](images/103/14.brackets.commit1.png)


18. `Git Push`아이콘을 클릭하십시오. 

![](images/103/15.brackets.commit2.png)


19. 팝업 창에서 기본값을 모두 그대로 두고 하단의 `확인`버튼을 누릅니다. 

![](images/103/15.brackets.commit3.png)


20. Git Push가 완료되면 `OK`버튼을 클릭하십시오. 

![](images/103/16.brackets.done.png)


#### CICD (Continuous Integration &amp; Delivery) 

18. 이제 브라우저로 돌아가서 Oracle Developer Cloud Service 프로젝트의 Build 페이지를 확인하십시오. 새로운 빌드 (여기서는 :*LoyaltyManagementBuild*)가 Git 변경을 감지하여 자동으로 실행 되었음을 알 수 있습니다. 

![](images/103/21.png)


19. 작업이 완료되면 배포 탭으로 변경하여 새 배포가 시작되었는지 확인할 수 있습니다. 새로운 성공적인 빌드 결과물이 준비 될 때마다 배포가 다시 수행되도록 구성되었습니다. 

![](images/103/22.png)


20. 이제 '로열티 관리' 응용 프로그램의 변경 사항을 확인하십시오. 응용 프로그램의 페이지에서 변경 사항 (빨간색 텍스트)을 확인해야 합니다. 로열티 관리 애플리케이션 URL은 다음 형식이어야 합니다. 
	`https://**<JCS WLS instance IP Adress>**/loyalty/jsp/welcome.jsp`, the JCS WLS instance IP address is the same as **Deploy to JCS** target in DevCS.


![](images/103/23.png)


이 Lab 섹션을 마쳤습니다. 

[Back to JavaAppsLab Home](README.md) 

