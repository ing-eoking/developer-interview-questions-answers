# 클라우드

<br>

<details>
<summary style="font-size:20px">클라우드 컴퓨팅</summary>
<div markdown="1">

* 인터넷이 연결되어 있으면 언제든 연결 가능한 서버/네트워크
* 클라우드에서 서버, 스토리지, SW 등 필요한 IT 자원을 받아 사용하는 기술 

</div>
</details>

<details>
<summary style="font-size:20px">클라우드 네이티브</summary>
<div markdown="1">

* 클라우드의 이점을 최대로 활용할 수 있도록 애플리케이션을 구축하고 실행하는 방식
* Microservice, 컨테이너, DevOps, CI/CD

</div>
</details>

<details>
<summary style="font-size:20px">클라우드로의 전환이 필수적인 이유</summary>
<div markdown="1">

* 비용 절감: 서버 장비 구매 및 유지 비용이 장기적으로 봤을 때 클라우드 시스템을 이용하는 것보다 비쌈, 사용한 만큼 비용을 지불할 수 있음
* 안정성: 클라우드는 다양한 공간으로 분산하기 때문에, 분선돤 모든 곳에 동시다발적으로 문제가 생기지 않는한 장애가 발생하지 않음
* 확장성: 트래픽이 임계점에 도달하면 빠르게 서버를 확장할 수 있음
* 생산성 향상: 온사이트에서 HW 설치 및 SW 패치 등 많은 시간이 걸리지만 클라우드를 사용하면 이런 작업이 불필요해짐
* 속도 향상: 몇 번의 클릭으로 컴퓨팅 리소스 사용 가능
* 효율적인 인적자원 운영: 직접 방문해야하는 On-premise에 반해 웹에서 100% 제어 및 모니터링이 가능하기 때문에 개발(혹은 설계) 인력과 공존이 가능

</div>
</details>

<details>
<summary style="font-size:20px">스케일 아웃 (Scale-out)과 스케일 업 (Scale-up)</summary>
<div markdown="1">

* `서버 확장`을 위한 기술

#### 스케일 아웃 (Scale-out)
* 서버를 여러 대 추가하여 시스템 확장
* 수평 확장, 지속적 확장 가능
* 분산 처리, 장애 시 전면 장애 가능성이 낮음

#### 스케일 업 (Scale-up)
* 서버에 CPU, RAM 등 HW 장비의 성능을 높임
* 수직 확장, 성능 확장에 한계가 있음
* 서버 1대에 부하가 집중되어 장애 영향이 큼

</div>
</details>

<details>
<summary style="font-size:20px">MSA (Microservice Architecture)</summary>
<div markdown="1">

#### 정의
* 모든 시스템의 구성요소가 한 프로젝트에 통합되어 있는 Monolithic Architecture(모놀리식 아키텍쳐)의 한계점을 극복하고자 등장
* 1개의 시스템을 `독립적으로 배포 가능한` 각각의 서비스로 분할한 것
* 각각의 서비스는 `RESTful API`를 통해 데이터를 주고받으며 1개의 큰 서비스를 구성

#### 장단점
* 확장성이 좋고 일부 서비스에서 장애가 발생해도 전체 서비스에서 장애가 발생하지 않음
* 각 서비스들이 다른 언어와 프레임워크로 구성 가능
* 복잡도 증가, 서비스가 분리되어 있어 테스트, 트랜잭션 처리, 디버깅이 어려움
* REST API로 통신하는 비용 발생

</div>
</details>

<details>
<summary style="font-size:20px">컨테이너</summary>
<div markdown="1">

* APP과 APP을 구동하는 환경을 격리한 공간
* APP마다 OS를 설치하지 않고, 호스트 OS를 공유해 가벼움 
* 애플리케이션 실행의 독립성을 확보하는 OS 수준의 격리 기술
* 애플리케이션을 실제 구동 환경으로부터 추상화

</div>
</details>

<details>
<summary style="font-size:20px">Docker (도커)</summary>
<div markdown="1">

* 컨테이너 기반의 오픈소스 가상화 플랫폼

#### 참고
* 기존에는 OS를 가상화해 Host OS에 Guest OS를 설치해 사용 -> 느리고 무거움
* 이를 극복하기 위해 프로세스를 격리시킨 컨테이너를 통해 가상화하는 도커 사용
* 도커 파일은 버전 관리가 가능
* 도커 이미지: 컨테이너 실행에 필요한 파일과 설정값, `도커 허브`에서 무료로 관리 가능

#### 생성 과정
* 도커 파일 Build -> 도커 이미지 생성 -> 도커 이미지 Run -> 도커 컨테이너 생성

</div>
</details>

<details>
<summary style="font-size:20px">도커의 장단점</summary>
<div markdown="1">

* 쉽고 빠른 실행환경 구축
* HW 비용 절감
* 개발 초기 오버헤드, Linux 친화적

</div>
</details>

<details>
<summary style="font-size:20px">도커(컨테이너)와 가상 머신의 차이</summary>
<div markdown="1">

#### 컨테이너
* `Host OS`에 `도커`를 설치해 그 위에 `애플리케이션` 환경을 설치/운영하는 것
* 애플리케이션에 각각의 OS를 설치하는 것이 아니라 `Host OS를 공유` -> 가벼움
* 컨테이너 이미지만 있다면 어디서든 사용 가능
* 안전성 문제: 호스트 OS를 공유해 장애가 발생하면 다른 컨테이너가 영향을 받을 수 있음

#### 가상 머신
* `하이퍼바이저`를 사용해 Host OS에서 여러 OS를 사용하는 방법
  * Hipervisor: VM과 HW 간의 IO 명령을 처리하는 인터페이스
  * VM의 Guest OS들의 명령을 Host OS가 이해할 수 있게 하나의 명령어로 번역, Host의 HW 자원을 여러 VM에 배분
* Host OS에 VM을 설치하는데 VM은 Guest OS, 애플리케이션, Binary/Library 전체를 포함 -> 무거움
* VM은 `독립된 커널 공간`을 가짐
* 독립된 OS와 자원으로 보안에 좋음

</div>
</details>


<details>
<summary style="font-size:20px">컨테이너를 사용하는 이유</summary>
<div markdown="1">

* 가벼움: 별도의 OS가 없어 크기가 작고 가벼움, 적은 메모리 사용
* 빠른 시작과 종료: 컨테이이너를 실행하는 것은 일반 프로세스를 실행하는 것과 같음
* 이동성이 좋음, 개발/배포 편이성
  * 컨테이너는 애플리케이션에 필요한 모든 종속 항목(라이브러리 등)을 포함
  * 이미지만 있으면 어디든지 실행 가능
* 서비스 무정지 제공
* MSA에 유리

</div>
</details>


<details>
<summary style="font-size:20px">Kubernates (쿠버네티스)</summary>
<div markdown="1">

* 도커를 통해 구동되는 `컨테이너의 배포/확장/관리`를 자동화해주는 오픈소스 플랫폼
* MSA 형태로 설계되어 있음
* GO 언어로 구현되어 있음, 퍼블릭 클라우드에서 사용 가능, 프라이빗 클라우드나 베어메탈(가상화X)에서도 배포 가능

#### 컨테이너 오케스트레이션
* 여러 서버에 컨테이너를 배포/운영하면서 서비스간 연결을 쉽게 해주는 것
* 서버를 자동으로 선택해 애플리케이션을 배포하고 부하가 생기면 자동으로 컨테이너를 늘리고 재가동해주는 것

</div>
</details>

<details>
<summary style="font-size:20px">쿠버네티스가 가장 선호되는 이유</summary>
<div markdown="1">

* 물리/가상 머신의 클러스터에서 컨테이너를 예약하고 실행할 수 있는 플랫폼이 확보됨
* 프로덕션 환경에서 컨테이너 기반 인프라를 구현해 사용할 수 있음

</div>
</details>

<details>
<summary style="font-size:20px">쿠버네티스 아키텍처</summary>
<div markdown="1">

#### 클러스터
* 효율적인 리소스 공유와 균형 배분을 위해 `여러 노드를 묶은 그룹`

#### 클러스터링
* 여러 서버를 묶어 하나의 시스템처럼 동작하게 하며, 클라이언트에게 고가용성 서비스를 제공
* Active-Active 구조: 서버들이 항상 Active 상태
* Active-Standby 구조: Standby 서버는 Active 서버에 장애가 발생하면 바로 Active 상태로 바뀔 수 있음
  * Active -> Standby: Fail Over / Standby -> Active: Fail Back

#### 마스터 - 노드 구조
* 클러스터를 관리하는 마스터와 컨테이너가 배포되는 노드로 구성
* `Master`에 `API 서버`와 `상태 저장소(etcd)`를 두고 각 서버(`Node`)의 에이전트(`kubelet`)와 통신하는 구조
* 모든 명령은 마스터의 `API 서버`를 호출하고 노드는 마스터와 통신하면서 필요한 작업을 수행

##### Master
* 클러스터의 설정 환경 저장 및 클러스터 관리
* Api Server, Controller, Scheduler, etcd로 구성
* Api Server: 관리자의 요청이 kubectl을 통해 클러스터에 요청됨 -> Api Server가 받아 etcd에 상태 저장
* Controller: `Desired State`를 유지하기 위해 변경 사항이 있는지 지속적으로 확인
* Scheduler: 할당되지 않은 Pod을 적절한 노드에 할당해주는 모듈
* etcd: 클러스터의 모슨 상태 정보 저장, Key-Value 저장소

##### Node
* 쿠버네티스에서 최소 단위의 컴퓨팅 하드웨어
* 실제 컨테이너가 생성되는 장소
* 워크로드(Pod) 실행
* Kubelet(큐블릿): Pod의 생명주기 관리, Pod 생성, Pod의 상태를 주기적으로 API Server에 전달
* Kube-proxy: Pod로 연결되는 네트워크 관리

#### Pod
* 배포 가능한 가장 작은 컴퓨팅 단위

</div>
</details>

<details>
<summary style="font-size:20px">쿠버네티스 Auto Scaling</summary>
<div markdown="1">

* CPU, Memory 사용량, 접속자 수와 같은 값을 사용할 수 있음
* 컨테이너의 개수를 조정하는 Horizontal Pod Autoscaler(HPA), 컨테이너의 리소스 할당량을 조정하는 Vertical Pod Autoscaler(VPA), 서버 개수를 조정하는 Cluster Autosclaer(CA) 방식

</div>
</details>

<details>
<summary style="font-size:20px">DevOps</summary>
<div markdown="1">

* 애플리케이션 `개발, 운영` 간의 협업 프로세스를 자동화
* 애플리케이션의 개발, 개선 속도 향상

#### 필요한 이유
* SW가 안정성을 유지하면서 사용자에게 빠르게 제공될 수 있도록 `개발 - 테스트 - 배포 - 운영` 사이클을 자동화된 단일 워크 플로우로 통합

</div>
</details>

<details>
<summary style="font-size:20px">CI/CD</summary>
<div markdown="1">

#### 지속적인 통합(Continous Intergration)
* 개발자가 작업한 코드를 자동으로 테스트하고 테스트에 통과하면 코드를 통합

#### 지속적인 배포(Continuos Deployment)
* 작업한 코드 및 변경 사항들은 테스트를 거쳐 리포지토리에 업로드되고 서비스 배포까지 자동화

</div>
</details>

<details>
<summary style="font-size:20px">고가용성 (High Availability)</summary>
<div markdown="1">

* 서버와 네트워크, 프로그램 등의 정보 시스템이 상당히 `오랜 기간` 동안 지속적으로` 정상 운영이 가능`한 성질

</div>
</details>

<details>
<summary style="font-size:20px">Serverless</summary>
<div markdown="1">

* 서버를 직접 관리할 필요가 없는 아키텍처
* 서버의 자원을 `동적`으로 할당 (자동 스케일링)
  * 사용자가 없다면 자원을 할당하지 않고 대기 -> 요청이 들어오면 자원을 할당해서 요청을 처리 -> 다시 대기 상태로 들어감
  * 경제적이고 가용성이 좋은 모델
* 필요한 기능을 `함수(Fuction)`로 구현

#### BaaS (Backend as a Service)
* 백엔드 개발에 필요한 여러 기능을` API`로 제공하는 서비스
* 즉, 백엔드 기능을 사용자가 직접 구현하는 것이 아니라 `클라우드 공급자가 제공하는 API`로 기능을 개발
* Firebase, Kinvey, Parse

#### FaaS (Function as a Service)
* 함수를 서비스로 제공
* 백엔드를 함수 단위로 쪼개서 사용자가 직접 관리하지 않는 서버
  * 사용자가 작성한 코드(백엔드)를 서버리스 제공자의 서버에 업로드 -> 서버는 업로드한 코드를 함수 단위로 쪼개어 대기상태로 보관 -> 요청이 들어오면 서버가 함수를 실행시켜 처리 -> 작업이 끝나면 다시 대기상태로 돌아감
  * 비용은 함수 호출 횟수에 따라 청구
* 함수들은 특정한 조건 또는 주기, 요청 등으로 트리거 되어서 서버가 알아서 실행되고 종료
* AWS Lambda, Azure Functions, Google Cloud Functions

#### 장점
* 실제 사용량에 대해서만 비용이 청구되어 경제적 (이벤트 기반의 비용)
* 서버에 신경쓸 필요가 없어 비지니스 로직에 집중할 수 있음
* 자동 스케일 업 및 스케일 다운

#### 단점
* 실시간 서비스에는 적합하지 않음 (실행 대기 시간이 오래 걸림)
* 클라우드 서비스 업체에 종속적으로 플랫폼 이전이 쉽지 않음
* 실행 시간 한계 (AWS Lambda의 경우 15분) -> 긴 시간이 필요한 작업에 불리

</div>
</details>