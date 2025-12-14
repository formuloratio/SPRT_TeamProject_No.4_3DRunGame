# 게임명: ThreadRun
<img width="1593" height="892" alt="스크린샷 2025-12-14 183116" src="https://github.com/user-attachments/assets/1319a4db-3fb7-4be0-9560-12387a858d8c" />

## 📑 목차
1. [프로젝트 장르 및 소개](#프로젝트-장르-및-소개)
2. [주요기능](#주요기능)
3. [역할분담](#역할분담)
4. [구현내용](#구현내용)
5. [트러블슈팅](#트러블슈팅)
6. [기술스택](#기술스택)
7. [사용에셋 목록](#사용에셋-목록)

---

## 프로젝트 장르 및 소개

<table>
  <tr>
    <th align="left" width="180"> 항목 </th>
    <th align="left" width="500"> 내용 </th>
  </tr>
  <tr><td> 장르 </td><td> 횡스크롤 3D 러닝 액션 게임 </td></tr>
  <tr><td> 소개 </td><td> 좌우와 점프, 슬라이드 조작을 통해 장애물들을 피해 달리면서 돈을 먹어 점수를 올리는 게임 </td></tr>
  <tr><td> 개발 기간 </td><td> 총 7일 { 2025.11.14 ~ 2025.11.21 } </td></tr>
</table>

* [저장소 원본 링크](https://github.com/shin0112/ThreadKidRun)

---

## 주요기능
### 게임플레이
- 게임 시작 시에 튜토리얼을 통해 조작법을 설명 받으면서 게임이 진행.
- 좌우 이동과 점프, 슬라이드 기능을 통해 장애물을 회피하고 돈을 먹어 점수를 획득.
- 아이템의 종류는 무적과 스피드가 있으며 획득 시 일시적으로 종류에 맞는 버프가 발동.
- 획득한 돈으로 캐릭터 스킨을 구매할 수 있는 상점이 존재하며 스킨 적용이 가능.
- 획득한 돈, 사용된 아이템, 구매한 캐릭터 스킨의 개수에 따른 업적 해금 시스템이 존재.

<img width="1592" height="890" alt="스크린샷 2025-12-14 183312" src="https://github.com/user-attachments/assets/751a992b-b182-4d32-809c-d4c836a9a031" />
<img width="1592" height="893" alt="스크린샷 2025-12-14 183242" src="https://github.com/user-attachments/assets/a0ae66f1-6b13-402c-93f5-46d7034dcf67" />
<img width="1593" height="892" alt="스크린샷 2025-12-14 183258" src="https://github.com/user-attachments/assets/b007130b-de45-4483-bcdc-afd9ac49add2" />
<img width="1594" height="893" alt="스크린샷 2025-12-14 183152" src="https://github.com/user-attachments/assets/f6ffa066-f9ab-4e92-aebd-783cc6f8e231" />
<img width="1595" height="892" alt="스크린샷 2025-12-14 183344" src="https://github.com/user-attachments/assets/6bcde032-f5e4-4dfd-87af-7821df488657" />

### 핵심기술
- Managers
  * GameManager에서 코인, 점수, 데이터, 업적, 씬 등 주요 값 관리.
  * AchievementManager에서 업적 관리.
  * AudioManager에서 사운드(배경음, 효과음) 관리.
  * PowerUpManager에서 버프 관리.
  * UIManager에서 UI 관리.
- Map
  * MapMove에서 맵 이동 관리, 생성 파괴 관리.
  * PlayerCollider에서 장애물 충돌 처리.
  * Coin에서 충돌 시 점수 획득.
- Player
  * CustomizingController에서 커스터마이징 시 저장되어야 하는 정보 전달.
  * PlayerAnimation에서 플레이어 애니메이션 관리.
- PowerUp
  * PowerUpBase에서 파워업 아이템의 기본 클래스.
  * PowerUpItem에서 필드에 배치되는 파워업 아이템 관리.
  * InvincibilityPowerUp에서 무적 파워업 아이템 관리.
  * PowerUpSpawner에서 파워업 아이템 랜덤 스폰.
  * SpeedBoostPowerUp에서 스피드 부스트 파워업 아이템 관리.
- Shop
  * CharacterSlot에서 캐릭터 SkinData(SO) 관리.
  * ShopController에서 상점 회전, 캐릭터 슬롯 관리.
- UI
  * ButtonUI에서 버튼 관리.
  * SettingUI에서 환경 설정 (오디오 조정).
  * Tutorial에서 튜토리얼 UI 관리.
  * ScoreUI에서 점수 창 (최고 점수, 현재 점수) 관리.
  * ShopUI에서 상점 버튼 관리.
  * AchievementUI에서 업적 창 관리.
  * GameOverUI에서 게임오버 창 관리.
- Scriptable Objects
  * AchievementData는 업적 데이터
  * CharacterSkinData는 캐릭터 스킨 데이터
  * PowerUpData는 버프 데이터
  * SoundData는 사운드 데이터
- Etc
  * Define는 상수 관리
  * Extensions는 확장 메서드
  * Logger는 커스텀 로그

---

## 역할분담

<table>
  <tr>
    <th align="left" width="180"> 이름 </th>
    <th align="left" width="500"> 역할 </th>
  </tr>
  <tr><td> 조현일 </td><td> 사운드, 버프 아이템 </td></tr>
  <tr><td> 신주은 </td><td> UI, 상점, 튜토리얼 </td></tr>
  <tr><td> 엄성진 </td><td> 업적 시스템, 코인 및 스코어 처리 </td></tr>
  <tr><td> 이요한 </td><td> 배경 이동, 장애물 충돌 처리 </td></tr>
  <tr><td> 함승효 </td><td> 플레이어 이동 </td></tr>
</table>

---

## 구현내용 [엄성진]


### 스크립트
---


---

## 트러블슈팅

### 1. 코인 획득 업적이 해금되었을 때 다른 업적들도 해금되는 버그
* 문제 :
  * 업적에 따라 타입을 구분하였지만, 타입과 상관없이 코인 업적 해금 시에 다른 업적들도 같이 해금되는 현상이 발생했다.
* 해결 :
  * 타입을 받아오는 시점과 비교 대상의 매칭 오류였고, 코드를 하나하나 순서대로 디버깅해보면서 foreach에서 탐색된 타입과 구분하는 switch의 조건문의 매개변수가 일치하지 않는 것들 확인되어 수정하였다.

### 2. 깃허브로 최종 합병 시에 발생한 충돌 문제
* 문제 :
  * 주어진 과제 내의 기능들을 중심으로 분량에 맞춰서 배분하려다 보니 한정된 기능 설계에서 겹치게 되는 기능들이 존재했고 이러했을 때 나타날 수 있는 합병 문제를 예방하기 위한 스크립트의 기초 설계를 하지 않고 각자 작업을 시작하였다.
* 해결 :
  * 꼬박 하루를 투자하여 팀 내 소통을 통해 순차적으로 병합을 진행하였다.

---

## 기술스택

<table>
  <tr>
    <th align="left" width="180"> 구분 </th>
    <th align="left" width="500"> 기술 </th>
  </tr>
  <tr>
    <td>Language</td>
    <td><img src="https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=csharp&logoColor=white"></td>
  </tr>
  <tr>
    <td>Framework</td>
    <td><img src="https://img.shields.io/badge/unity-FFFFFF?style=for-the-badge&logo=unity&logoColor=black"></td>
  </tr>
  <tr>
    <td>IDE</td>
    <td><img src="https://img.shields.io/badge/Visual%20Studio-5C2D91?style=for-the-badge&logo=visualstudio&logoColor=white"></td>
  </tr>
  <tr>
    <td>Version Control</td>
    <td><img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white"></td>
  </tr>
  <tr>
    <td>Design</td>
    <td><img src="https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white"></td>
  </tr>
  <tr>
    <td>Documentation</td>
    <td><img src="https://img.shields.io/badge/Notion-000000?style=for-the-badge&logo=notion&logoColor=white"></td>
  </tr>
</table>

---

## 사용에셋 목록

<table>
  <tr>
    <th align="left" width="180"> 항목 </th>
    <th align="left" width="500"> 내용 </th>
  </tr>
  <tr><td> 효과음 </td><td> [UI Sfx 8-Bit Pack] (https://assetstore.unity.com/packages/audio/sound-fx/ui-sfx-8-bit-pack-320299?locale=ko-KR&srsltid=AfmBOorkMfzVpU24cLQUs4O-WtSg-pNRcvq6jHJLz2NM_Q7dzAzFz5aL) </td></tr>
  <tr><td> 배경음 </td><td> [RACER MUSIX 20] (https://assetstore.unity.com/packages/audio/music/racer-musix-20-house-dance-techno-atmospheric-retro-racing-game--332174?srsltid=AfmBOoodPMH_2y0LYa_xg4W6BR-l7qNfJA8KWNJIxWUoaf8lT0fGB3JX) </td></tr>
  <tr><td> 맵 구성 </td><td> [KayKit : City Builder Bits] (https://kaylousberg.itch.io/city-builder-bits) </td></tr>
  <tr><td> 캐릭터 </td><td> [KayKit - Character Pack : Adventurers] (https://kaylousberg.itch.io/kaykit-adventurers) </td></tr>
  <tr><td> 애니메이션 </td><td> [KayKit - Character Animations] (https://kaylousberg.itch.io/kaykit-character-animations) </td></tr>
  <tr><td> 그 외 </td><td> AI </td></tr>
</table>
