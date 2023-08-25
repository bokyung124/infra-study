# 1. EC2 (Elastic Compute Cloud)

- 늘어나는 임대 컴퓨터

- Instance
    - 가상 컴퓨터 환경
    - 원하는 만큼 구축 가능
- Instance Type
    - CPU, 메모리, 스토리지, 네트워킹 용량 등 선택 가능
- Key Pair
    - 공개키-개인키 보안 방식
    - SSH 접속, 데이터 암호화하여 교환할 때 사용
- Instance Store Volume
    - 임시 데이터를 저장하는 스토리지 볼륨
    - 인스턴스 중단 및 종료 시 삭제됨


<br>

# 2. EBS (Elastic Block Store)

- 인스턴스에 추가적으로 달아 사용되는 블록 수준의 스토리지 서비스
- 인스턴스에 연결된 **스토리지 용량** 관리
- EC2와의 차이점
    - EC2는 인스턴스의 CPU, 메모리, 디스크 용량 등의 **컴퓨팅 리소스** 관리

<br>

# 3. S3 (Simple Storage Service)

- 늘어나는 데이터 저장소

- 여러 형식의 데이터가 S3로 이동하여 어디서든 사용할 수 있게 저장된 후 다양한 형태로 검색 및 활용됨

<img width="790" alt="스크린샷 2023-08-24 오후 5 25 44" src="https://github.com/bokyung124/infra-study/assets/53086873/e74e49ff-d962-4d62-8867-3adbb0b42ffc">

- 보안 이슈 존재 -> IM 서비스로 커버

<br>

## Use Case

- Data Lake
    - Image
    - Video
    - CSV
    - JSON

- Static Website Hosting
    - HTML
    - CSS
    - JavaScript

- BackUp & Archive
    - Server Log File
    - App Log File
    - DB BackUp file
    - 버전 관리도 가능


<br>

# 4. ELB (Elastic Load Balancer)

- 트래픽 자동 분산기

- 둘 이상의 가용 영역 내에서 들어오는 앱 트래픽을 인스턴스들에게 자동으로 분산

- 가용성, 내결함성
- 전체적 요청 흐름에 방해 없음
- 컴퓨터 리소스의 상태 모니터링 가능

<br>

## 4 types of ELB

<img width="630" alt="스크린샷 2023-08-24 오후 5 35 08" src="https://github.com/bokyung124/infra-study/assets/53086873/2379eb85-43fe-48dc-b3e7-6d8b64a0bcaa">

<br>

# 5. Auto Scaling

- EC2 인스턴스 모음

<img width="551" alt="스크린샷 2023-08-24 오후 5 36 19" src="https://github.com/bokyung124/infra-study/assets/53086873/a0635578-968f-4448-aad2-43e70295cf8d">

- 내결함성
    - 비정상 인스턴스 감지

- 가용성
    - 최적의 용량으로 감지

- 비용 관리 가능

## ELB & Auto Scaling

<img width="538" alt="스크린샷 2023-08-24 오후 5 37 15" src="https://github.com/bokyung124/infra-study/assets/53086873/9e5dd315-1d39-4121-8a3d-c2f51c84920b">

- ELB: 인스턴스 분배
- Auto Scaling: 인스턴스 수 조절 -> 트래픽 변화에 대처

<br>

# 6. ECS (Elastic Contatiner Service)

- 컨테이너 오케스트레이션

- ECS Layers

<img width="559" alt="스크린샷 2023-08-24 오후 5 39 16" src="https://github.com/bokyung124/infra-study/assets/53086873/11d82f18-7457-411a-8d5b-04eec017028f">

<br>

# 7. EKS (Elastic Kubernetes Service)

- 쿠버네티스 관리형 서비스

- workflow
<img width="731" alt="스크린샷 2023-08-24 오후 5 39 55" src="https://github.com/bokyung124/infra-study/assets/53086873/748ab647-297c-4e83-a8e4-70f11ec88dae">

<br>

# 8. Lambda

- 서버리스 컴퓨팅 플랫폼

- 서버 설정 없이 곧바로 코드 실행
- 이벤트 트리거 방식
- 최대 실행 시간 15분
    - 한 번 쏘면 15분
    - 건 당으로 요금 부과
- Amazon LINUX2 기반 실행
- 컨테이너를 지원하진 않음
- 엔지니어링 
    - 데이터 전처리 (로그데이터 처리 등)에 배치성으로 사용
- HW를 거치지 않고 뿌리기 때문에 아마존 입장에서도 저렴함
- 당근마켓에서 사진 crop 기능에 Lambda 사용

<br>

# 9. Fargate

- 서버리스 기반 컴퓨팅 플랫폼
- 컨테이너 환경에서 사용 가능
- 전체적으로 봤을 땐 Fargate가 더 빠름
- reponse time만 보면 Lambda가 더 빠름

<img width="688" alt="스크린샷 2023-08-24 오후 6 03 30" src="https://github.com/bokyung124/infra-study/assets/53086873/c923e4fd-ee73-4a48-b0ed-79b29274b6ba">