# 그 외 적으로 좋은 리소스들

## 메모리

**Redis : 인메모리 디비이며, RDBS와 다르게 RAM에 파일을 저장한다.**<br>
**RDBS의 부하를 덜어주는 용도로 많이 사용된다. 대부분은 기업들은 RDBS, Redis 를 범용해서 사용한다.**<br><br>

**ElastiCache : Redis 소프트웨어를 management 해주는 AWS 리소스이다.**<br>
**역시 서버 코드와 연결하여 함께 사용한다.**<br><br>

## 로그
**ElasticSearch : 비정형 데이터를 분석하고 검색하는 용도였지만. ELK (LogStash, ElasticSearch, Kibana) 엔진으로 바뀌면서 로그들은 분석해 데이터로 사용한다.**<br>

### Service Architecture
**1. MSA 아키텍처로 바뀌면서 찢어진 서버 파일들이 각각 다른 환경에서 실행되며 로그들이 생성된다.**<br>
**2. Logstash에서 이러한 로그들을 파싱해서 ElasticSearch 에 전송한다.**<br>
**3. ElasticSearch에서 로그 파일을 저장하고 인덱스, 태그와 같은 (검색에 용이한) 옵션들을 추가한다.**<br>
**4. kibana 에서 인덱싱 된 로그들을 간편하게 볼 수 있고, 검색 및 분석을 할 수 있다.**<br><br>

**AWS ElasticSearch 는 이러한 ELK 엔진을 관리해주는 AWS 리소스이다. 다만 Logstash 관리는 제공하지 않기 때문에, 따로 EC2 서버에 직접 접속해 관련 패키지들을 설치 및 설정 해주어야 한다.**<br><br>

## Devops 를 위한 핫한 인프라 구축 tools 
**Docker**<br>
**Kubernetes**<br>
**Terraform**<br>
