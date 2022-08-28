# pod install 하기

까다로운 우리 맥북은 intel, m1, m2 에서마다 패키지 설치할 때 입력하는 명령어를 달리 해줘야한다. <br><br>
그 이유는 바로 m1,m2 가 arm 기반이기 때문이다.<br><br>

따라서 pod install 할 때, `arch -x86_64 pod install` 명령어를 통해 설치해줘야 한다.<br><br>
