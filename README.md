# yeardream_final_project


<p>
<img src="images/Cover.png">
</p>


# 1. 프로젝트 개요


- 프로젝트 한 줄 설명
    - 일본의 배수기장 시설 내부에 이상징후를 포착 및 진전 여부를 탐지하는 모델 개발

- 프로젝트의 배경 또는 기획 의도
    - 배수기장 시설이 시간의 흐름에 따라 노후화가 진행되면서 붕괴의 위험이 발생되기 시작했고 그에따라 안전진단 검사를 진행하게 되는데 
    이때 구조물 특성상 접근성이 좋지 않고 육안 검사를 하거나 초음파 장비를 이용해 구조물을 전역적으로 탐색하다 보니 인력이 부족하고 많은 시간이 발생하는 상황이 발생하기 때문에 이를 로보틱스 촬영 기반 컴퓨터 비전 솔루션 (이하 '스마트 솔루션')을 제시하고 이를 통해 손쉽게 포탁한다면 경제적인 효과를 거둘 수 있을것으로 예상되기 때문에 해당 프로젝트를 기획함

- 개인 프로젝트 or 팀 프로젝트
    - 팀프로젝트

- 팀 프로젝트시 참여 인원 및 본인의 역할 
    - YOLO 모델 구성 및 실험진행

- 진행 기간 및 소속
    - 프로젝트 기간 : 23.11.06 ~ 23.12.14

<br></br>

# 2. 기술 스택 및 데이터셋 설명

- 활용한 기술 스택
    - python, openCV

- 데이터 출처, 용량, 특징 등
    - 기업에서 드론으로 촬영한 배수기장 내부 촬영 영상, AI허브 데이터



### [Programming Language] <br>
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"> 
<img src="https://img.shields.io/badge/opencv-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white">
<img src="https://img.shields.io/badge/numpy-013243?style=for-the-badge&logo=numpy&logoColor=white">
<img src="https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
<br>

### [IDE & Environment]
<img src="https://img.shields.io/badge/visual studio code-007ACC?style=for-the-badge&logo=visualstudiocode&logoColor=white">
<img src="https://img.shields.io/badge/anaconda-44A833?style=for-the-badge&logo=anaconda&logoColor=white">

### [Deep Learning]
<img src="https://img.shields.io/badge/Pytorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white">

### [협업 툴]

<img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white">
<img src="https://img.shields.io/badge/Slack-4A154B?style=for-the-badge&logo=slack&logoColor=white">
<img src="https://img.shields.io/badge/notion-000000?style=for-the-badge&logo=notion&logoColor=white">
<img src="https://img.shields.io/badge/discord-5865F2?style=for-the-badge&logo=discord&logoColor=white">
<img src="https://img.shields.io/badge/google drive-4285F4?style=for-the-badge&logo=googledrive&logoColor=white">


<br></br>
# 3. 프로젝트 진행 단계

<p>
<img src="images/workflow.jpg">
</p>

- 4~5단계로 구분하여 설명
    - 1.이전 촬영 영상과 일정 시간이 지난 뒤의 촬영 영상(비교군)을 input으로 설정합니다.
    - 2.각 영상을 frame단위로 slicing하여 segmentation model의 입력값으로 넣습니다.
    - 3.탐지된 이상징후(철근노출,bleeding)현상의 frame을 matching합니다 (ImageRetrieval)
    - 4.매칭된 이상징후의 면적 비교를 통해 이상징후의 진전 여부를 판단합니다.


<br></br>
# 4. 프로젝트 세부 과정

- 각 단계별 세부 진행 과정 설명

# 5. 프로젝트 결과

<p>
<img src="images/report_sample.jpg">
</p>

- 모델의 성능

<p>
<img src="images/yolo_benchmark.jpeg">
</p>


- 배포 링크



<br></br>

# 6. 프로젝트 회고

- 잘 한점

- 한계점 및 개선 방안
    - 데이터의 

### 직무별 포트 폴리오 포인트 (Data Scientist)
- 문제인식
- 문제를 풀기 위한 기술 적용
- 기술의 구현 수준
- 성능









# 포트폴리오란?
- 프로젝트에 대한 상세한 설명
- 업무 관련 경험을 보여주고, 설명하는 것
    - 프로젝트의 배경 및 목적 등 아래 



# 기업이 필요로 하는 부분이 내 포폴에서 잘 보여야 함 
- 문제 정의를 명확하게 함
- 비즈니스 및 사용자에 대한 이해 부족
- 어떤 문제를 해결하려고 했는가
    - 왜 이런 프로젝트를 기획하고 실행했는가?
    - 이 프로젝트는 어떤 문제를 해결할 수 있는가
- 이 문제는 왜 중요한가? 어떤 가치가 있는가
    - 해결하면 시간 및 비용을 아낄 수 있다.







