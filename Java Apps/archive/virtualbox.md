# 오라클 클라우드 테스트 드라이브 #
-----
## 클라우드 테스트 드라이브 ## 용 Oracle VM VirtualBox 설치 및 사용


VirtualBox는 교차 플랫폼 가상화 응용 프로그램입니다. 그게 무슨 뜻 이죠? 한 가지 예로 Windows, Mac, Linux 또는 Solaris 운영 체제를 실행하는 기존 Intel 또는 AMD 기반 컴퓨터에 설치됩니다. 둘째, 기존 컴퓨터의 기능을 확장하여 동시에 여러 운영 체제 (여러 가상 컴퓨터 내부)를 실행할 수 있습니다. 예를 들어 Mac에서 Windows 및 Linux를 실행하고 Linux 서버에서 Windows Server 2008을 실행하고 Windows PC에서 Linux를 실행하는 등의 작업을 기존 응용 프로그램과 함께 수행 할 수 있습니다. 실제로 사용할 수있는 가상 컴퓨터는 디스크 공간과 메모리뿐입니다. VirtualBox는 믿을 수 없을만큼 간단하면서도 매우 강력합니다. 소형 임베디드 시스템 또는 데스크탑 클래스 컴퓨터에서부터 데이터 센터 배포 및 심지어 클라우드 환경까지 모든 곳에서 실행할 수 있습니다. 다음 스크린 샷은 Mac 컴퓨터에 설치된 VirtualBox가 가상 컴퓨터 창에서 Windows 8을 실행하는 방법을 보여줍니다. 

![](images/virtualbox/vm-vista-running.png)


### 선수 과목 ###
이 실습 안내서는 다음을 전제로합니다. 
- 인터넷 액세스 가능 (설치 프로그램 및 확장 팩 다운로드, 강사로부터 파일 확인 또는 복사) 
- 호스트 운영체제로 Microsoft Windows 사용https://www.virtualbox.org/manual/ch01.html#hostossupport 
- 오픈 가상화 형식 (.ova)*VM 파일 

#### Oracle VM VirtualBox 설치 

1. [VirtualBox Welcome Page](https://www.virtualbox.org/)로 이동하여 중간에 Download VirtualBox XX 버튼을 클릭하십시오. 

![](images/virtualbox/00.virtualbox.download.png)


2. 다운로드 페이지에서*VirtualBox XXXX 플랫폼 패키지*아래에서 운영 체제 설치 프로그램 다운로드 링크를 선택하십시오. 이 가이드 라인에서는 Windows 호스트를 예제로 사용합니다. 

![](images/virtualbox/01.virtualbox.download1.png)


3. 팝업 창에서 `파일 저장`및 `확인`을 클릭하여 VirtualBox 설치 프로그램을 대상 위치에 저장합니다. 

![](images/virtualbox/02.virtualbox.save.png)


4. 저장된 대상에서 VirtualBox 설치 관리자 실행 파일을 시작합니다. 

![](images/virtualbox/03.virtualbox.installer.png)


5. 설치 프로그램이 시작되면 `다음`을 클릭하십시오. 

![](images/virtualbox/04.virtualbox.installer1.png)


6. **사용자 정의 설치**페이지에서 브라우저를 선택하고 설치를위한 VirtualBox 대상 폴더를 선택한 다음, `다음`을 클릭하십시오. 

![](images/virtualbox/05.virtualbox.installer2.png)


7. 필요한 옵션을 선택하고 `다음`을 클릭하십시오. 

![](images/virtualbox/06.virtualbox.installer3.png)


8. `경고 : 네트워크 인터페이스`페이지에서 `다음`을 클릭하십시오. 

![](images/virtualbox/07.virtualbox.installer4.png)


9. `Install`을 클릭하여 설치 과정을 진행하십시오. 

![](images/virtualbox/08.virtualbox.installer5.png)


10. 설치가 완료 될 때까지 2 분 정도 기다리십시오. 

![](images/virtualbox/09.virtualbox.installer6.png)


11. `설치 후 Oracle VM VirtualBox XXXX 시작`옵션을 선택하고 마침을 클릭하십시오. 

![](images/virtualbox/10.virtualbox.installer7.png)


12. **Oracle VM VirtualBox Manager**창이 시작됩니다. 

![](images/virtualbox/11.virtualbox.start.png)


#### Oracle VM VirtualBox 사용 

13. 상단 메뉴 바에서`File`을 클릭하고`Import Appliance ... `를 선택하십시오. 

![](images/virtualbox/12.virtualbox.file.png)


14. 폴더 아이콘을 클릭하십시오. 

![](images/virtualbox/12.virtualbox.import.png)


15. 브라우저를 선택하고 강사가 제공 한*Open Virtualization Format (.ova)*VM 파일을 선택하십시오. 

![](images/virtualbox/13.virtualbox.import1.png)


16. 어플라이언스 설정에서 기본값을 유지하고 `가져 오기`를 클릭하십시오. 

![](images/virtualbox/14.virtualbox.import2.png)


17. VirtualBox Manager가 .ova 파일을 VM에 로컬로 가져 오기 위해 몇 분 정도 기다립니다. 

![](images/virtualbox/15.virtualbox.import3.png)


18. VM 가져 오기가 완료되면 VirtualBox Manager의 VM 목록에**DevOpsWorkshopV3.04**라는 새 항목이 표시됩니다. 

![](images/virtualbox/16.virtualbox.import4.png)


19. [VirtualBox Download Page](https://www.virtualbox.org/wiki/Downloads)으로 돌아가서**VirtualBox XXXX Oracle VM VirtualBox 확장 팩 옆의`지원되는 모든 플랫폼 `링크를 클릭하십시오. 

![](images/virtualbox/17.virtualbox.extension.png)


20. Oracle VM VirtualBox 확장 팩을 대상 위치에 저장하십시오. 

![](images/virtualbox/18.virtualbox.extension1.png)


21. 확장 팩을 두 번 클릭하거나 실행하십시오. 

![](images/virtualbox/19.virtualbox.extension2.png)


22. 확장 팩 설치 대화 상자가있는 VM VirtualBox Manager가 나타납니다. 팝업 창에서`설치`버튼을 클릭하십시오. 

![](images/virtualbox/20.virtualbox.extension3.png)


23. *VirtualBox License*의 끝으로 스크롤하고 winodw의 하단에있는 &quot;동의 함&quot;버튼을 클릭하십시오. (선택적으로 읽음) 

![](images/virtualbox/21.virtualbox.extension4.png)


24. **Oracle VM VirtualBox Extension Pack**설치가 완료되면 `확인`을 클릭하십시오. 

![](images/virtualbox/22.virtualbox.extension5.png)


25. 이제 VM 실행에 필요한 모든 준비가 완료되었습니다. 새 VM**DevOpsWorkshopV3.04**를 선택하고 `시작`버튼을 클릭하십시오. 

![](images/virtualbox/23.virtualbox.extension6.png)


VM이 시작될 때 VM 컨텐츠를 호스팅하는 새 창이 표시됩니다. 기본 옵션 인**Oracle Linux Server 7.2, Unbreakable Enterprise Kernel 3.8.13-118.9 ->**를 유지하십시오. 

![](images/virtualbox/24.virtualbox.vm-start.png)


27. VM을 시작할 때 Oracle Linux를 몇 분 정도 기다렸다가 마침내 Linux 데스크톱이 표시됩니다. 오늘 Lab 연습에서**Eclipse**및*bracket 아이콘을 사용할 것입니다. 

![](images/virtualbox/25.virtualbox.vm-started.png)


28. Oracle VM VirtualBox의 설치 및 사용이 끝났습니다. 

[Back to JavaAppLab Home](README.md) 

