Pull Request
==

병렬적으로 협업하기 위한 가장 기본적인 Git 코드 순서이다.


`git branch create-sample` : 로컬 저장소에 브랜치를 생성. <br>
브랜치는 하나의 기능에 대응하며 브랜치 명도 명시적으로 작성한다. <br>

`git checkout create-sample` : 해당 브랜치로 이동. <br>

`git pull origin master` : master 브랜치와 병합 후 코드 작성<br> **충돌을 해결하기 위함 아주 중요**. <br>


`git push -u origin create-sample` : 원격 저장소에 브랜치를 생성 한 후 작성한 코드 동기화. <br>

> master 브랜치와 병합하기 전, Pull Request 를 팀원에게 보내 안정성을 높일 수 있다. 승인을 받으면 **merge** 진행

