# VR Drone

## 📌 프로젝트 목표
+ 드론을 실제로 비행하기 위해서는 각종 규제를 준수해야 하고 장치 승인이 필요하여 사용할 수 있는 공간이 극히 제한적이다. 또한 조작이 미숙할 경우 안전사고가 발생할 수 있고 시험이 있을 정도로 조작 난이도가 매우 높은 편에 속한다. 본 프로젝트에서는 **가상 현실 기술을 접목하여 드론을 자유롭게 조작할 수 있는 가상환경을 구축**하는 것이 목표이다. 만약, 현실과 거의 흡사하도록 물리적 효과를 포함한다면, 드론 사업에도 긍정적 영향을 미칠 수 있고, 부수적으로 가상환경 내에서 드론 사업과 관련한 다양한 시뮬레이션을 할 수 있어 확장성도 높을 것으로 기대한다.
  
## ⏲ 프로젝트 기간
- 2019.03~2019.06
- 도전학기제 I : 팀 프로젝트

## ⚙ 개발 환경
+ 개발 툴 : `Unity 2018.3.0f2`
+ VR Headset : `Oculus Rift S`
+ 텍스처 수정 : `Adobe Photoshop`
+ 오디오 편집 : `GoldWave`
+ 모델링 수정 : `3ds Max`
+ 참고 프로그램 : `DJI Flight Simulator`

## 📋 개발 과정
- 본격적으로 개발을 시작하기 전에 인터넷 검색을 통해 이론을 학습하고 실제 **드론 조종사**를 대면하여 드론이 비행하는 원리, 컨트롤러 사용법을 자세히 조사했다.
- 콘텐츠를 기획하는 단계에서 실제 환경에서의 극한 상황을 재현하고자, 건물과 가로등이 도로에 복잡하게 얽혀있어 드론을 조작하기 어려운 환경인 **도시**를 선택했다.
- 대부분의 드론 물리효과는 기존 Unity에 있는 Rigidbody 클래스 함수들을 사용하여 구현했다. 드론 오브젝트가 중력 효과를 받을 수 있도록 하고, 드론의 움직임 중 기본이 되는 **호버링**(Hovering)은 드론의 위 방향으로 velocity 값을 중력과 일치한 수준으로 가하여 일정한 높이에 떠 있도록 했다. 적용한 velocity 값을 낮추거나 높임으로써 드론의 상승과 하강을 구현할 수 있고, 회전을 하면 기울어진 방향으로 힘을 가하게 되어서 드론이 앞으로 나아갈 수 있었다. velocity의 특성상 충돌이나 저항으로부터 힘을 잃기 전까지 그대로 유지가 되어 **관성**도 구현할 수 있었다. 추가적으로, 방향 벡터에 따른 **로터리(Rotary) 회전**과, 큰 충돌 시 엔진 정지가 이루어지도록 했다.
- 전용 SDK(Oculus Integration)를 이용하여 오큘러스 리프트를 동작할 수 있게 하고 컨트롤러 키를 실제 드론 **컨트롤러**처럼 매핑(Mapping)했다.
- **비행음, 풍절음, 마찰음, 충돌음**을 추가했고, 각 효과음은 AudioSource Component를 이용하여 드론의 속도에 따라 음량이 조절되도록 구현했다.
- 사용자 근처에 속도, 고도, 드론 카메라를 표시하는 **World Canvas**가 있어서 실시간으로 정보를 전달받을 수 있다.
- Scene을 구분하여 **1인칭 시점**과 **3인칭 시점**을 오갈 수 있도록 했다.

## ✔ 프로젝트 평가
+ 현재 개발된 부분까지 보면 그럴 듯해 보이지만 아직 시간상 구현되지 않은 부분이 남아있다. 드론의 물리 구현은 되었으나, 바람이나, 온도, 배터리, 날씨 등과 같은 외적인 요소가 아직 개발되지 않았다. 시뮬레이터가 현실 세계와 최대한 흡사해야 한다는 것을 고려하면 아직 미완성 수준이라고 할 수 있다. 또한, 드론의 종류가 너무 한정적이다. 드론은 로터리의 개수가 다양하게 있으므로 물리 작용도 각각 작용되어야 할 것으로 보인다. 이 외에도 환경을 조정할 수 있는 옵션 기능과 다양한 맵으로 변경할 수 있는 기능이 추가되어야 할 것이다.
+ 드론 모델이 움직이도록 하는 것은 간단했지만 실제 같은 움직임을 재현하기 위해서는 많은 고민이 필요했다. 드론에 관련된 지식과 물리적인 지식이 부족했기 때문에 더욱 쉽지 않은 작업이었고, 이러한 부분은 지인에게 상담하거나 주기적인 회의를 통해 해당 부분에 대해서 많은 고민을 했다. 의견이 모이면서 점차 기능들이 추가되었고, 도중 발생하는 오류들을 수정하면서 Unity 프로그램에 대한 지식을 축적할 수 있었다.
+ 본 프로젝트의 구성원은 본인을 포함한 세 명이었다. 생각 외로 물리 구현이 상대적으로 많은 시간이 필요했다 보니, 역할의 구분이 많이 희미해졌다. 프로젝트 수행 기간을 좀 더 길게 잡았으면 좋았겠다는 생각이 들었고, 바쁜 학기 일정 중에도 팀원들이 잘 모여주었기 때문에 결과를 낼 수 있었다고 생각한다.

  <div align="center">
      <table border="0">
	      <tr>
	        <td align="center"><img width="100%" height="100%" src="https://user-images.githubusercontent.com/60832219/209480779-e6546705-8f5e-44f8-b9da-0ada42964fc3.gif"/></td>
	        <td align="center"><img width="100%" height="100%" src="https://user-images.githubusercontent.com/60832219/209480782-5ce14d1d-c2b0-4cbc-aa3a-908bb72ba32a.gif"/></td>
        </tr>
	      <tr>
          <td align="center">작동</td>
          <td align="center">호버링</td>
        </tr>
        <tr>
	        <td align="center"><img width="100%" height="100%" src="https://user-images.githubusercontent.com/60832219/209480394-5b6c3124-4233-44a7-a213-5b26c40c4a04.gif"/></td>
	        <td align="center"><img width="100%" height="100%" src="https://user-images.githubusercontent.com/60832219/209480396-5351630d-0fef-4741-a767-104ec54c9354.gif"/></td>
        </tr>
        <tr>
          <td align="center">이동I</td>
          <td align="center">이동II</td>
        </tr>
        <tr>
	        <td align="center"><img width="100%" height="100%" src="https://user-images.githubusercontent.com/60832219/209480420-7aec8d52-b0ab-4f3d-a93a-71777f80f668.gif"/></td>
	        <td align="center"><img width="100%" height="100%" src="https://user-images.githubusercontent.com/60832219/209480604-836dfe8c-cb67-43a3-b8cc-8a88b0bdc31a.gif"/></td>
        </tr>
        <tr>
          <td align="center">회전</td>
          <td align="center">상승/하강</td>
        </tr>
        <tr>
	        <td align="center"><img width="100%" height="100%" src="https://user-images.githubusercontent.com/60832219/209480533-2d995c93-35d8-4232-98d0-5fd9f6ae25a1.gif"/></td>
	        <td align="center"><img width="100%" height="100%" src="https://user-images.githubusercontent.com/60832219/209480702-561ade48-bd69-49e7-8d31-9f8fa9b1d0a0.gif"/></td>
        </tr>
        <tr>
          <td align="center">충돌</td>
          <td align="center">비행</td>
        </tr>
      </table>
  </div>
