# navigation 버전 맞추기

헬스장 아이파크 앱 ios 파트 개발을 하는데, Drawer navigator, screen 이 필요한 경우가 생겼다.<br><br>
기존에는 Stack 밖에 없었기 때문에, 문제가 발생하지 않았었지만 이번에 Drawer 라이브러리를 설치하고 실행하니 문제가 발생했다.<br><br>

도저히 잘못된 부분을 찾지 못 했다. screen path가 틀린 것도 없고, 철자도 맞고, 구조도 다 맞는데 왜 안돼 !!<br><br>
도대체 뭐가 문제일까 2시간 삽질 후에 알아냈다.<br><br>

***바로 라이브러리 간의 버전이 맞지 않는다는 것 ,,***

이전에 추가해둔 stack, navigate 라이브러리들을 모두 업데이트하니 정상적으로 돌아갔다.<br><br>
***결론은 중간에 추가되는 라이브러리는 다른 라이브러리 간의 버전을 잘 확인해야 한다. 아니면 정말 큰일나 .. 삽질할 거야*** 
