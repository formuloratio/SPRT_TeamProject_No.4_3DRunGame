# 게임명: ThreadRun
<img width="1593" height="892" alt="스크린샷 2025-12-14 183116" src="https://github.com/user-attachments/assets/1319a4db-3fb7-4be0-9560-12387a858d8c" />

## 📑 목차
- [프로젝트 장르 및 소개](#👨‍🏫-프로젝트-장르-및-소개)
- [주요기능](#🔧-주요기능)
- [역할분담](#역할분담)
- [구현내용(스크립트)](#🖥️-구현내용(스크립트))
- [트러블슈팅](#트러블슈팅)
- [기술스택](#기술스택)
- [사용에셋 목록](#사용에셋-목록)

---

## 👨‍🏫 프로젝트 장르 및 소개

<table>
  <tr>
    <th align="left" width="180"> 항목 </th>
    <th align="left" width="500"> 내용 </th>
  </tr>
  <tr><td> 장르 </td><td> 횡스크롤 3D 러닝 액션 </td></tr>
  <tr><td> 소개 </td><td> 좌우와 점프, 슬라이드 조작을 통해 장애물들을 피해 달리면서 돈을 먹어 점수를 올리는 게임 </td></tr>
  <tr><td> 개발 기간 </td><td> 총 7일 { 2025.11.14 ~ 2025.11.21 } </td></tr>
</table>

* [저장소 원본 링크](https://github.com/shin0112/ThreadKidRun)

---

## 🔧 주요기능
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

## 🖥️ 구현내용(스크립트)

* [엄성진]
<img width="1164" height="610" alt="UML_N4_" src="https://github.com/user-attachments/assets/9b843b8f-79c5-41f0-8357-3a0def7b850a" />


### 스크립트

---

* #### 업적 및 스코어 관리

  <details>
    <summary> GameManager.cs </summary>

    ```csharp
    using GameName.Managers;
    using System;
    using UnityEngine;
    using UnityEngine.SceneManagement;
    
    public class GameManager : MonoBehaviour
    {
        [Header("코인 저장 값 초기화")]
        public bool isReset; //디버깅용
    
        public static GameManager Instance { get; private set; }
    
        // Managers
        public UIManager UI { get; set; }
        public PowerUpManager PowerUp { get; set; }
        // todo: 추가
    
        // 플레이어
        [SerializeField] private GameObject _player;
        public GameObject Player { get { return _player; } set { _player = value; } }
    
        // 현재 획득한 총 코인 개수
        private int totalCoinCount = 0;
        public int TotalCoinCount
        {
            get { return totalCoinCount; }
            private set
            {
                if (value < 0)
                {
                    Logger.Log("코인 개수 부족");
                    return;
                }
    
                totalCoinCount = value;
                Logger.Log($"현재 코인 개수: {totalCoinCount}");
    
                UIManager.Instance.CoinUI.UpdateCoinText(totalCoinCount);
            }
        }
    
        // 업적
        private int currentScore = 0; //현재 스코어
        private int getItemCount = 0; //획득한 아이템 수
        private int buyCharacterCount = 0; //구매한 캐릭터 수
    
        [SerializeField]
        private AchievementManager achievementManager;
    
        //// 이벤트 통신
        public event Action<int> OnScoreChanged; // 점수가 변경될 때 외부에 알림
        //public event Action<string> OnAchievementUnlocked; // 업적이 잠금 해제될 때 외부에 알림
    
        // 스킨 정보
        [Header("스킨 정보")]
        [SerializeField] private int _curSkinIndex;
        public int CurSkinIndex
        {
            get { return _curSkinIndex; }
            set
            {
                if (_curSkinIndex == value)
                {
                    Logger.Log("동일한 스킨 선택");
                    return;
                }
    
                _curSkinIndex = value;
                OnSkinIndexChanged?.Invoke(_curSkinIndex);
            }
        }
        public event Action<int> OnSkinIndexChanged;
    
        private void Awake()
        {
            if (Instance == null)
            {
                Instance = this;
                DontDestroyOnLoad(gameObject); // 씬 전환에도 유지
            }
            else
            {
                Destroy(gameObject);
            }
    
            LoadData();
            Init();
        }
    
        private void Start()
        {
            InitPlayer();
        }
    
        private void Init()
        {
            UI = GetComponentInChildren<UIManager>();
            PowerUp = GetComponentInChildren<PowerUpManager>();
        }
    
        private void InitPlayer()
        {
            Player = FindObjectOfType<PlayerCollider>().gameObject;
            PowerUp.Init(Player);
        }
    
        public void AddScore(int amount)
        {
            if (amount <= 0) return;
            currentScore += amount;
            OnScoreChanged?.Invoke(currentScore);
            EarnCoin(amount);
            UnityEngine.Debug.Log($"코인 획득! 현재 스코어: {currentScore}");
        }
    
        public void ScoreReset()
        {
            currentScore = 0;
            OnScoreChanged?.Invoke(currentScore);
        }
    
        #region 코인 관리
        // 코인을 획득할 때 호출되는 메서드
        public void EarnCoin(int amount)
        {
            if (amount < 0) return;
            totalCoinCount += amount;
            UnityEngine.Debug.Log($"코인 획득! 현재 총 코인: {totalCoinCount}");
            UIManager.Instance.CoinUI.UpdateCoinText(totalCoinCount); //코인 UI에 반영
    
            // 코인 개수가 변경될 때마다 업적 해금 조건을 검사
            if (achievementManager != null)
            {
                achievementManager.CheckAchievements(totalCoinCount, AchievementType.CoinAcquisition);
            } // <- 업적 해금 방법. 다른 업적(아이템 사용, 아이템 구매하는) 함수에 위의 코드를 가져다 쓰면 됨
        }
    
        public bool CheckSpendCoinAndGetSkin(int amount)
        {
            Logger.Log($"코인 {amount}개 사용");
    
            if (totalCoinCount > amount)
            {
                TotalCoinCount -= amount;
                return true;
            }
            else
            {
                Logger.Log("코인 부족");
                return false;
            }
        }
    
        public void ResetCoin()
        {
            TotalCoinCount = 0;
        }
        #endregion
    
        #region 업적
        public void EarnItem(int amount)
        {
            if (amount < 0) return;
            getItemCount += amount;
            UnityEngine.Debug.Log($"아이템 사용! 현재 사용한 아이템 수: {getItemCount}");
            if (achievementManager != null)
            {
                achievementManager.CheckAchievements(getItemCount, AchievementType.UseItem);
            }
        }
    
        public void EarnCharacter(int amount)
        {
            if (amount < 0) return;
            buyCharacterCount += amount;
            UnityEngine.Debug.Log($"캐릭터 구매! 구매된 캐릭터 수: {buyCharacterCount}");
            if (achievementManager != null)
            {
                achievementManager.CheckAchievements(buyCharacterCount, AchievementType.BuySomething);
            }
        }
        #endregion
    
        #region 데이터 관리
        private void LoadData()
        {
            if (isReset)
            {
                totalCoinCount = 0;
                return;
            }
            totalCoinCount = PlayerPrefs.GetInt("CurrentCoin", 0);
            getItemCount = PlayerPrefs.GetInt("CurrentUseItem", 0);
            buyCharacterCount = PlayerPrefs.GetInt("CurrentBuyCharacter", 0);
            _finishedTutorial = PlayerPrefs.GetInt(_finishiedTutorialKey, 0) == 0 ? false : true;
            EarnCoin(0);
            EarnItem(0);
            EarnCharacter(0);
        }
    
        public void SaveData()
        {
            PlayerPrefs.SetInt("CurrentCoin", totalCoinCount);
            PlayerPrefs.SetInt("CurrentUseItem", getItemCount);
            PlayerPrefs.SetInt("CurrentBuyCharacter", buyCharacterCount);
            PlayerPrefs.Save();
        }
    
        private void OnApplicationQuit()
        {
            SaveData();
        }
        #endregion
    
        #region 씬 관리
        public void GameReload()
        {
            SceneManager.sceneLoaded += OnSceneLoaded;
            SceneManager.LoadScene(SceneType.GameScene.ToString());
        }
    
        private void OnSceneLoaded(Scene scene, LoadSceneMode mode)
        {
            SceneManager.sceneLoaded -= OnSceneLoaded;
    
            // ui 로딩
            UIManager ui = UIManager.Instance;
            ui.Camera = Camera.main;
            ui.SetSceneLoadMode();
            ui.TutorialUI.Init();
    
            InitPlayer();
        }
        #endregion
    
        #region 튜토리얼
        private bool _finishedTutorial = false;
        public bool FinishedTutorial => _finishedTutorial;
        private string _finishiedTutorialKey = "FinishTutorial";
    
        public void EndTutorial()
        {
            Logger.Log("튜토리얼 완료");
            _finishedTutorial = true;
            PlayerPrefs.SetInt(_finishiedTutorialKey, (_finishedTutorial ? 1 : 0));
            PlayerPrefs.Save();
        }
    
        public void ResetTutorial()
        {
            _finishedTutorial = false;
        }
        #endregion
    }
    ```

  </details>

* #### 업적 해금

  <details>
    <summary> AchievementManager.cs </summary>

    ```csharp
    using UnityEngine;
    using System.Collections.Generic;
    using System;
    
    public class AchievementManager : MonoBehaviour
    {
        // 업적이 해금되었을 때 UI에 알리기 위한 이벤트
        public static event Action<AchievementData> OnAchievementUnlocked;
    
        [Tooltip("관리할 모든 AchievementData ScriptableObject 목록")]
        public List<AchievementData> allAchievements;
    
        // GameManager에서 호출되어 현재 습득한/사용된 개수를 확인
        public void CheckAchievements(int currentCount, AchievementType type)
        {
            foreach (var achievement in allAchievements)
            {
                // 이미 해금된 업적은 다시 검사할 필요가 없음
                if (achievement.IsUnlocked)
                {
                    continue;
                }
    
                if (achievement.type == type)
                {
                    if (currentCount >= achievement.requiredCount)
                    {   // 해금 요구량을 충족하면 업적을 해금
                        achievement.Unlock();
    
                        // UI 업데이트를 위해 이벤트 발생
                        OnAchievementUnlocked?.Invoke(achievement);
                    }
                }
            }
        }
    }
    ```
  
  </details>

* #### 업적 데이터 (SO)

  <details>
    <summary> AchievementData.cs </summary>

    ```csharp
    using UnityEngine;
    
    public enum AchievementType //업적 종류
    {
        CoinAcquisition, // 코인 획득
        BuySomething, // 물건 구매
        UseItem // 아이템 사용
    }
    
    [CreateAssetMenu(fileName = "NewAachievement", menuName = "Game System/Achievement Data")]
    public class AchievementData : ScriptableObject
    {
        [Header("필수 정보")]
        [SerializeField]
        public string id;   // 고유 ID
        public string achievementName;  // 업적 이름
        public string description;  // 업적 설명
    
        [Tooltip("업적 해금에 필요한 값")]
        public int requiredCount; // 목표값
    
        [Header("로직 정보")]
        public AchievementType type;    // 업적 타입
        public bool isUnlocked; // 달성 여부
    
        [Header("보상 정보")]
        public int scoreReward; // 보상 점수
    
        // 업적 해금 상태를 외부에서 읽기 전용으로 접근
        public bool IsUnlocked => isUnlocked;
    
        /// <summary>
        /// 업적을 해금하고 상태를 변경합니다.
        /// </summary>
        public void Unlock()
        {
            if (!isUnlocked)
            {
                isUnlocked = true;
                Debug.Log($"업적 해금: {achievementName}");
                // 업적 해금 시 필요한 추가적인 로직을 여기에 추가
            }
        }
    }
    ```
  
  </details>

* #### 코인 획득 점수

  <details>
    <summary> Coin.cs </summary>

    ```csharp
    using UnityEngine;
    using GameName.Managers;
    
    public class Coin : MonoBehaviour
    {
        [Tooltip("이 코인을 획득했을 때 증가할 점수")]
        public int coinValue = 1;
    
        private void OnCollisionEnter(Collision collision)
        {
            // 플레이어 태그와 충돌했는지 확인 (플레이어에게 "Player" 태그가 있어야 합니다.)
            if (collision.gameObject.CompareTag("Player"))
            {
                // 코인획득시 효과음 재생
                // ============================================
                if (AudioManager.Instance != null)
                {
                    AudioManager.Instance.PlaySFX("SFX_CoinGet");
                }
                // ============================================
                if (GameManager.Instance != null)
                {
                    GameManager.Instance.AddScore(coinValue);
                }
                Destroy(gameObject);
            }
        }
    }
    ```
  
  </details>

* #### 업적 UI

  <details>
    <summary> AchievementUI.cs </summary>

    ```csharp
    using UnityEngine;
    using UnityEngine.UI;
    using TMPro;
    
    public class AchievementUI : MonoBehaviour
    {
        [Header("UI References")]
        [Tooltip("이 UI가 나타내는 AchievementData (인스펙터에서 연결)")]
        public AchievementData linkedAchievement;
    
        [Tooltip("색상을 변경할 UI 이미지 컴포넌트")]
        public Image imageToChange;
    
        [Header("Color Settings")]
        public Color lockedColor = Color.gray; // 잠금 상태일 때의 색상
        public Color unlockedColor = Color.yellow; // 해금 상태일 때의 색상
    
        [Header("업적 이름")]
        public TextMeshProUGUI titleText;
    
        [Header("업적 설명")]
        public TextMeshProUGUI descriptionText;
    
        private void Start()
        {
            titleText.text = linkedAchievement.achievementName;
            descriptionText.text = linkedAchievement.description;
        }
    
        private void OnEnable()
        {
            // AchievementManager의 이벤트에 구독합니다.
            AchievementManager.OnAchievementUnlocked += HandleAchievementUnlocked;
    
            // 초기 상태 설정
            if (imageToChange != null && linkedAchievement != null)
            {
                imageToChange.color = linkedAchievement.IsUnlocked ? unlockedColor : lockedColor;
            }
        }
    
        private void OnDisable()
        {
            // 이벤트 구독을 해지합니다.
            AchievementManager.OnAchievementUnlocked -= HandleAchievementUnlocked;
        }
    
        // 업적 해금 이벤트가 발생했을 때 호출됩니다.
        private void HandleAchievementUnlocked(AchievementData unlockedData)
        {
            // 이벤트로 전달된 업적 데이터가 현재 이 UI가 연결된 업적 데이터와 일치하는지 확인합니다.
            if (unlockedData == linkedAchievement)
            {
                UpdateUI();
            }
        }
    
        private void UpdateUI()
        {
            if (imageToChange != null)
            {
                // 이미지 색상을 해금 상태 색상으로 변경
                imageToChange.color = unlockedColor;
    
                // 해금 시 애니메이션, 소리 재생 등의 추가 로직을 여기에 삽입
                Debug.Log($"UI 업데이트: {linkedAchievement.achievementName} 해금됨.");
            }
        }
    }
    ```
  
  </details>
  

---

## ⏲️ 트러블슈팅

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

## 🧩 기술스택

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

## 🚀 사용에셋 목록

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
