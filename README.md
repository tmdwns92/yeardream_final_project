# Year-Dream School : Final_Project


<p>
<img src="images/Cover.png">
</p>



<div align=center><h2>📚 프로젝트 기술 스택</h2></div>

<div align=center>

#### [Programming Skill] 

  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/opencv-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white">
  <img src="https://img.shields.io/badge/numpy-013243?style=for-the-badge&logo=numpy&logoColor=white">
  <img src="https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <br>

#### [IDE & Environment]
<img src="https://img.shields.io/badge/visual studio code-007ACC?style=for-the-badge&logo=visualstudiocode&logoColor=white">
<img src="https://img.shields.io/badge/anaconda-44A833?style=for-the-badge&logo=anaconda&logoColor=white">

#### [Deep Learning]
<img src="https://img.shields.io/badge/Pytorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white">

#### [Team Collaboration Tool]

<img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white">
<img src="https://img.shields.io/badge/Slack-4A154B?style=for-the-badge&logo=slack&logoColor=white">
<img src="https://img.shields.io/badge/notion-000000?style=for-the-badge&logo=notion&logoColor=white">
<img src="https://img.shields.io/badge/discord-5865F2?style=for-the-badge&logo=discord&logoColor=white">
<img src="https://img.shields.io/badge/google drive-4285F4?style=for-the-badge&logo=googledrive&logoColor=white">

</div>

<br>

<!-- <!DOCTYPE html PUBLIC> -->

<!-- <div align=center><h2> 프로젝트 역할 </h2></div>

<div align=center> -->

<br>

<head>
<meta charset="EUC-KR">
<!-- <title>테이블</title> -->
</head>
<body>
    <table border="1">
	<th>역할</th>
	<th style="text-align:center">팀원</th>
	<tr><!-- 첫번째 줄 시작 -->
	    <td>팀원</td>
        <td>
         - 학습에 필요한 데이터셋 구축 <br>
         - YOLOv8 모델 구성 및 실험 <br>
        </td>
	</tr><!-- 첫번째 줄 끝 -->
    </table>
</body>



<br>

---

<br>

# 1. 프로젝트 개요

일본의 배수기장 시설 내부에 이상징후를 포착 및 진전 여부를 탐지하는 모델 개발

<br>

# 2. 프로젝트의 배경 및 기획 의도
 
배수기장 시설 내부의 콘크리트 구조물이 시간의 흐름에 따라 노후화되면서 수분 침투에 의한 철근 부식, 균열 등 안전성 관련된 이상징후들이 발생하고 있습니다. 이러한 구조물의 이상징후 관리를 위해서 터널 내로 들어가 육안 검사나 초음파 장비를 사용한 전역적 탐색을 하게 되는데 구조물 특성상 접근성이 어렵고 인력, 시간, 비용 면에서 많은 부담을 야기합니다. 이 문제를 해결하기 위해, 저희는 로보틱스 촬영 기반 컴퓨터 비전 안전 진단 솔루션(이하 '스마트 솔루션')을 제안하고 이 솔루션을 통해 구조물의 상태를 효과적으로 촬영하고 수집된 영상을 통해서 손쉽게 이상 징후를 감지함으로써, 안전 점검의 효율성을 높이고 경제적인 이점을 제공할 것으로 예상되어 프로젝트를 기획하게 되었습니다.

<!-- - 팀 프로젝트시 참여 인원 및 본인의 역할 
    - YOLO 모델 구성 및 실험진행 -->

</br>

# 3. 문제 접근 방법

(1) 로보틱스 장비로 사람이 탐색하기 어려운 구조물에 대한 데이터 확보 <br>
(2) 1차 : 촬영한 영상에 대하여 위험이 있는 이상징후 포착 및 기록 <br>
(3) 일정시간 이후 : 같은 구역의 2차적으로 촬영된 영상에 대하여 이상징후의 진전 여부 탐지 <br>

<p>
<img src="images/workflow.jpg">
</p>

> 1.로보틱스(드론) 이전 촬영 영상과 일정 시간이 지난 뒤의 촬영 영상(비교군)을 input으로 설정합니다. <br>
> 2.각 영상을 frame단위로 slicing하여 segmentation model의 입력값으로 넣습니다. <br>
> 3.탐지된 이상징후(철근노출,bleeding)현상의 frame을 matching합니다 (ImageRetrieval) <br>
> 4.매칭된 이상징후의 면적 비교를 통해 이상징후의 진전 여부를 판단합니다. <br>

</br>


# 4. 문제 접근 방식 정의 - Instance Segmentation

해당 문제를 풀기위해서 Computer Vision에서 어떤 Task를 적용할지 고민을 했었고 노후화로 인해 발생하는 이상 징후들을 이전 시점에서 촬영한 영상과 현재 시점에서 촬영한 영상을 비교해서 각 객채별로 기존보다 진전 여부가 있는지 비교하기 위해서 면적 비교가 필요했습니다. 이를 위해 픽셀 단위로 구별하고 개별적으로 분류할 수 있는 Instance Segmentation이 가장 적합한 접근법이라고 판단했습니다.



# 5. 데이터 출처


<div>
    <img src="images/sample_video.png" width="400" height="400">
    <img src="images/AI HUB.png" width="400" height="400">
</div>

> (왼) 실제 배수기장 내부 촬영 영상,  (우) AI HUB에서 제공된 데이터 셋<br>
> - 백태누수 (white bleeding) : 콘크리트 표면에 발생하는 백색의 얼룩 <br>
> - 백태누수 (red bleeding) : 콘크리트 내부에 있는 철근이 녹슬어 표면에 녹슨물이 흘러나오는 현상

<br>

기업에서 제공받은 실제 배수기장 내부를 촬영한 동영상에서 철근 노출, 백태 누수(white bleeding, red bleeding)를 모델이 잘 탐지할 수 있도록 만들기 위해 AI 허브에서 구축되어있는 "건물 균열 탐지 이미지" 데이터 셋중 백태누수와 철근노출 데이터 다운 받아 실제 배수기장 환경과 유사한 이미지만을 판별했고 기존의 구축된 데이터 라벨링이 Object Detection으로 되어있어서 Instance Segmentation Task에 맞게 Roboflow 툴을 이용해 라벨링을 진행하였습니다.


<br>

# 6. 모델 선정

<p>
<img src="images/Mask R-CNN vs YOLOv8.png">
</p>

이 프로젝트에서 Instance Segmentation Task를 할 수 있는 모델을 실험해보기 위해 MMDetection, Detectron2, YOLOv8 이렇게 세 가지 프레임워크를 선정하였습니다. MMDetection, Detectron2는 현재 Task에 특화된 Mask R-CNN 모델과 다양한 Backbone들을 변경해가며 실험할 수 있는 환경이 잘 구축되어있고 YOLOv8은 실시간 객체 탐지에 초점을 맞추고 있지만 기존 버전보다 경량화 및 성능 향상을 강조하고 다른 Task에 실험결과들도 나쁘지 않아 잘 적용이 되는지 테스트해보기 위해 선택하게 되었습니다. <br> 

실제 실험 결과를 진행한 결과 MASK R-CNN 계열에서는 특정 클래스(red bleeding)에 대해서는 잘 예측을 하지 못하는 문제가 발생했었는데 YOLOv8은 전반적으로 균등하게 잘 예측하는 결과를 보여줬기 때문에 사용할 모델은 YOLOv8로 선정하게 되었습니다.
<br>
<br>

# 7. 프로젝트 결과

<p>
<img src="images/report_sample.jpg">
</p>

동일한 조건으로 촬영한 기존 영상과 일정 시간이 지난 영상을 인풋으로 넣게 되면 영상을 슬라이싱 후 학습된 YOLOv8 모델을 통해서 이상징후들을 감지하게 되고 동일한 객체끼리 이미지 매칭을 진행하고 기존보다 어느정도 진행되었는지 면적 변화량을 제시해줄 수 있습니다.

<br>

# 8. 프로젝트 회고

### 잘 한점
- AI허브 데이터 셋을 배수기장 실제 환경에 맞춰 분류하면 성능이 오를거라 판단했고 실제로 분류 작업을 진행해보고 테스트해본 결과 기존에 비해 10 ~ 20% 정도의 성능이 올랐습니다.

### 한계점
- 데이터 수의 부족으로 데이터 증강을 진행하였음에도 특정 클래스(red bleeding)에 대해서는 일정 기준 이상 모델 성능 개선이 이루어지지 않아 성능이 다소 아쉬웠던 결과를 보여줬습니다.
- MMDetection, Detectron2 프레임워크로 다양한 테스트를 진행할때 일부 모델들은 파라미터 사이즈가 커서 가지고 있는 리소스 환경에서는 학습을 진행할 수 없었고 한번 학습할때마다 오랜 시간이 걸려 충분히 테스트를 해보지 못한점이 아쉬웠습니다.
