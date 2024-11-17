<img width="1093" alt="LogoDarkReady" src="https://github.com/user-attachments/assets/d9c3df89-3937-4ba7-b278-c76bb44f14e9#gh-Dark-mode-only">
<img width="1093" alt="LogoLightReady" src="https://github.com/user-attachments/assets/7c2e239b-3684-436e-a23c-5ebf85db1ab9#gh-Light-mode-only">

# Paraglide - 텍스트 단락 처리기

.TXT 파일을 로드하여 **각 단락별로 순차적으로** 복사하고, Ctrl[Cmd] + V를 감지하면 **다음 단락으로 이동하여 복사**하는 기능을 자동화한 프로그램입니다.


## 핵심 기능

 1. .TXT 파일을 로드, 단락을 나누어 **이전/현재/다음** 단락을 표시.
 
 2. 키보드 입력을 모니터링. 특정 키 조합에 따라 **대응하는 기능**을 수행.
     - **붙여넣기(Ctrl + V, Cmd + V)** : 다음 단락 복사
     - **알트(Alt, Opt) + 좌우 화살표(←→)** : 이전/다음 단락으로 이동
     - **알트(Alt, Opt) + 상하 화살표(↑↓)** : 프로그램 일시정지/재개
 3. 오버레이 창을 통해 현재 **작업중인 단락**을 표시 및 **이전/다음 단락 이동**. 
 4. 로그를 저장해 이전 작업한 파일을 로드할 시 **마지막 위치 복원**


## 개발 의도

[식붕이툴](https://github.com/JOWONRO/SB2Tool)에서 영감을 받아 제작했습니다.

기존 식붕이툴의 가장 큰 단점이었던 **윈도우 전용 프로그램**이라는 점을 해결하고자
코딩은 할 줄 모르지만 GPT 들고 신나게 만들어봤습니다.

**자바스크립트**(NPM, React, Electron)로 작성되어
기존의 윈도우 전용이 아닌, **범용**으로 사용할 수 있다는 점이
가장 큰 장점입니다.

아직 베타 버전도 완성되지 않았지만, 개발 속도를 보아
이번 달 내로 Release가 가능할 것 같습니다.




## 기여

***여러분의 기여가 프로그램의 질을 높입니다!***

능력자분들의 많은 도움이 절실합니다.
단순 훈수도 좋아요, 개선의 여지가 필요한 부분은
주저없이 말씀해주시면 감사하겠습니다!

## 실행

 1. 먼저 Clone해줍니다.
 
   ```bash
   git clone https://github.com/WareAoba/Paraglide
```

 2. 프로그램 루트 디렉토리에 NPM을 설치해주세요.
 
    ```bash
    npm install
    ```

 4. 다음 명령어로 실행합니다.
 
    ```bash
    npm run dev
    ```

컴파일된 프로그램은 추후 업로드하도록 하겠습니다.

## 최근 추가 기능

1. **Sidebar 추가** : 최근 파일 내역을 보고 누르면 해당 파일로 바로 전환합니다.
2. 작업 완료 버튼 추가 : 사실 큰 쓸모는 없는 버튼이긴 합니다.
3. **단축키 활성화** : 드디어 단축키가 작동합니다! 
4. 클립보드 감시 : 프로그램 외부 클립보드 변화 발생시 프로그램이 자동으로 일시정지.

## 추가할 기능

1. **브라우징 기능** : 모든 단락을 스크롤로 볼 수 있게 해주는 기능. (버튼과 새 창으로 구현 예정)
2. **검색 기능** : 텍스트/단락 등을 검색하고 원하는 단락으로 점프할 수 있는 기능
3. 오버레이 창에서 단락 클릭으로 점프하는 기능
4. 다양한 애니메이션 : 제일 난감한 부분. 좀 많이 뜯어고쳐야 할 것 같습니다...
5. **UI 아이콘** 추가 : 일시정지/재개 버튼부터 시작해서, 앞으로 추가하게 될 버튼에까지?
6. **설정** : 프로그램 Settings(폰트 크기와 종류, 오버레이 표시/비표시 기본값, 강조 색상 등등)을 바꿀 수 있는 설정창
7. **유저 가이드** : 베타 릴리즈 할 때 프로그램 상세 설명서를 하나 작성하고 싶네요.
8. **프로그램 내에서 파일 수정 기능** : 그냥 간단하게 파일명이나 단락내용 정도...?


## 수정할 사항

1. 오버레이 레이아웃이 좀 잘못돼있습니다. 모든 단락들이 같은 간격으로 벌어져야 하는데, 이전-현재, 현재-다음만 유난히 넓음. 어떻게 고쳐야 할지 감도 안 잡히는 상황.
2. UI 속성을 CSS로 모두 이관하는 작업중이라 UI가 지금은 개판입니다. 언제 다 고쳐질진 몰?루...
3. 새로 추가한 Sidebar의 디자인이 아주 구립니다. 추후 개선 예정.
4. 실시간 테마 적용에 문제가 발생. 예전엔 됐는데 핸들러가 누락된듯?
5. 파일을 로드하면 자꾸 일시정지 상태에서 시작하는 크나큰 문제가 있음. 왤까요 대체...?
6. 로그가 또 다시 고장 ㅠㅠ
7. 윈도우용으로 컴파일하면 리본 메뉴가 보이는데, 이걸 없애야 합니다.
8. 간헐적으로 파일 로드가 해제되어 버리는데, 진짜 원인 불명......

## 베타 릴리즈?

현재 진행중인 **CSS 테마 적용**이 며칠동안의 험난한 여정이 될 것 같은데, 아마 그 사이에는 당장에 필요한 기능이 모두 완성될 듯 싶습니다.
베타 0.1 ver 출시는 이번달 내를 목표로 하는 중.
사실 코딩 지식이 있었다면 훨씬 빠르게 진행이 됐을 텐데
AI들고 삽질하면 하도 멀쩡한 기능을 고장내는 경우가 많아 그거 고치다가 시간 다 잡아먹어서 문제 ㅋㅋ;;

## 라이센스

해당 프로그램의 대부분의 코드는 **Github Copilot Chat**으로 작성되었습니다.

해당 프로그램과 코드는 **MIT License**를 통해 배포됩니다.

