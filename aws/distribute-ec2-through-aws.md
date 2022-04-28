# AWS 통해 백엔드 파일 배포하기

## 단어 설명

**VPN : 가상 사설망으로 실제 존재하는 네트워크가 아닌,말 그대로 가상의 네트워크이다. 상황에 맞게 네트워크를 분리하고 싶을 때, 실제로는 회선망을 새로 구축해야 하지만 VPN은 그럴 필요가 없다.**<br><br>
**VPC : 가상 사설 클라우드로 VPN과 비슷한 개념이다. 물리적으로는 개발 세팅이 끝났지만, 어느 작업은 네트워크 안에서 진행하고 중요한 작업처리나 데이터의 보안이 이슈되는 작업은 네트워크 밖에서 진행하고 싶을 때. 즉 네트워크를 분리할 때 사용한다.**<br><br>
**Subnet : 더 많은 네트워크를 분리할 때 사용하며, VPN을 여러 서브넷 네트워크로 분리시켜 독립적으로 사용한다. 서브넷 안에 EC2, RDS 과 같은 리소스를 배치시킬 수 있다.**<br><br>
**Routing Table : VPC 서브넷 네트워크들의 구성 정보를 담고 있는 표로, 몇 번 ip 로 들어왔을 때 어디로 가라는 네트워크 경로를 알려준다.**<br><br>
**보안그룹 = 방화벽 : 포트를 제어한다. 요청이 들어오고 나가는 인바운드, 아웃바운드 (포트)를 정한다.**<br><br>
**인바운드 : 내 리소스로 들어오는 포트. 어떤 리소스에 접근 할 때 하는 규칙**<br><br>
**아웃바운드 : 호출되면 나가는 포트. 오픈 api 를 호출할 때 그 api 의 아웃바운드를 알아야한다.**<br><br>
**탄력적 IP : 리소스에 IP 를 지정하는 것이다.**<br><br>
<br><br>

## EC2 서비스란 ?
AWS에서 제공하는 대표적인 서버 리소스로 하나의 서버 컴퓨터 시스템이다. 서버 컴퓨터를 사서 idc 센터에 올리고 네트워크를 연결하는 과정을 대체해준다.<br>
실습예제 flask framework 파이썬 서버 코드는 보통 5000번 포트로 실행되기 떄문에 인바운드 보안 그룹에서 tcp 5000번포트 0.0.0.0/0 을 열어줘야 접속할 수 있다.<br><br>
**몇번 포트를 사용할 것이고, ip 접근을 어디까지 허용할 것인지 잘 설계해서 보안그룹을 설정해야한다.** 


<br><br>
## ELB 서비스란 ?
기존 LB(Load Balancing) 기능을 소프트웨어 적으로 만든 AWS 리소스이다. <br>하나의 EC2 서버를 가지고는 대용량 트래픽을 감당하지 못한다. 
ELB 트래픽이 증가하면 EC2 서버를 여러대 사용하며 실시간으로 처리해준다. <br>
도메인을 EC2 IP 주소와 연결하는 것이 아닌, ELB End Point 에 연결한 후, ELB 에 EC2를 등록해서 사용한다. <br>
대부분 ELB 유형 중 Application Load Balancer 를 사용한다. <br>



<br><br>
## Auto Scaling 란 ?
Auto Scaling 을 통해 Auto Scaling Group 을 만들고, 그 그룹들 안에서 자동으로 ELB 서비스를 이용해 옵션을 걸어 EC2 리소스를 추가시켜줄 수 있다. <br>
하지만 추가된 EC2에 접속해 파이썬을 실행시켜줘야 하는 단점이 있다.

<br><br>
## ElasticBeanStaalk 란 ?
줄임말고 EB라고 하며, ELB + AUTOScaling + EC2 한 번에 관리할 수 있는 서비스 리소스이다.<br>
실무에서는 EB 로 통합하여 관리한다.


<br><br>
## 리소스 사용법 
**모든 리소스 사용법과 옵션을 기억하고 있을 수는 없다. 어느 상황에 필요한지 아는게 중요하다. 필요할 때마다 검색해 사용하자.**<br>
**보안 그룹을 잘 설정하고, IAM 에 리소스들을 등록하고, 키 값들을 Github 시크릿 및 AWS 시크릿에 잘 보관하는게 중요하다.**<br><br>
cors : APi 요청의 도메인이 달라도 요청을 허용하겠다는 라이브러리