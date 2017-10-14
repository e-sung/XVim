- [\[日本語版\]](README_jp.md)
- [\[English\]](README.md)



# !!!Xcode9은 (아직) 지원되지 않습니다!!!

# XVim

  XVim은 Xcode를 위한 Vim 플러그인입니다. 이 플러그인은 Xcode의 어떤 기능도 포기하지 않으면서 Vim의 탁월한 사용자 경험을 제공하는 것을 목표로 합니다.

#### 안내사항

  - Xcode 8 사용자들은. [INSTALL_Xcode8.md](INSTALL_Xcode8.md)를 먼저 참고하십시오.
  - Xcode 7 사용자들은, 809527b 이전의 커밋을 사용해 주십시오.
  - XVim은 BountySource를 사용하기 시작했습니다.
  - [Google Group for XVim developers](https://groups.google.com/d/forum/xvim-developers) 가 만들어졌습니다.



## 지원되는 Xcode 버전들

- Xcode7 : 809527b 이전의 커밋을 사용하십시오
- Xcode8 : 최신의 마스터 브랜치의 커밋을 사용하십시오. 

## INSTALL

Xcode8 사용자들은  [INSTALL_Xcode8.md](INSTALL_Xcode8.md) 의 안내사항을 먼저 따라주십시오.

소스코드를 다운로드 받거나, 이 저장소를 클론하십시오. 그 다음,

1. `xcode-select` 가 당신의 Xcode를 가리키도록 하십시오.

  ```bash
  $ xcode-select -p
  /Applications/Xcode.app/Contents/Developer
  ```

  이 명령어가 Xcode가 설치된 경로를 보여주지 않는다면, `xcode-select -s` 명령으로 그 경로를 설정해 주십시오.

2. make로 빌드합니다.

  ```bash
  $ make
  ```

  이 때, 아래와 같은 경고가 보일 수 있습니다.

  ```
  XVim hasn't confirmed the compatibility with your Xcode, Version X.X
  Do you want to compile XVim with support Xcode Version X.X at your own risk? 

  Xvim은 아직 당신의 Xcode버전인 Version X.X와의 호환성을 확인하지 않았습니다. 
  위험을 감수하고 Xcode Version X.X를 지원하도록 XVim을 컴파일 하시겠습니까?
  ```
   현재의 Xcode 버전에서 (작동하지 않을 위험을 감수하고)XVim을 사용하고자 할 경우, y를 누르십시오.  

3. 본인의 필요에 따라 `.xvimrc` 파일을 만드십시오.

4. Xcode를 실행하십시오. XVim을 로드 할 지의 여부를 묻는 팝업이 뜰것입니다. 'Yes'를 클릭하십시오. 이 때 실수로 'No'를 눌렀을 경우, Xcode를 종료한 뒤, 터미널에서 다음의 명령을 실행하십시오.

    ```
    defaults delete  com.apple.dt.Xcode DVTPlugInManagerNonApplePlugIns-Xcode-X.X     
    // (X.X 는 당신의 Xcode 버전입니다.)
    ```

    그리고 Xcode를 다시 실행하십시오.



## 브랜치와 릴리즈
 XVim에는 몇 개의 브랜치와 릴리즈가 있습니다. 보통은 '릴리즈' 중 하나만 다운로드 하면 됩니다.
 다음은 각각의 브랜치들과 릴리즈들에 대한 설명입니다.

 - 릴리즈(태그들) : 릴리즈들은 마스터 브랜치의 태그들입니다. 이 태그들의 코드들과 문서들은 잘 정리되어 있습니다. 대부분의 XVim 사용자들은 이 릴리즈들 중 하나를 사용하면 됩니다.
 - master : 가장 안정적인 브랜치입니다. 치명적인 버그의 수정 및 'develop' 브랜치에서 개발된 안정적인 기능들은 'master' 브랜치로 머지됩니다. 만약 어떤 릴리즈에서 치명적인 버그를 발견하셨다면, 가장 최신의 'master' 브랜치를 사용하십시오.
 - develop : 새로운 기능들과 치명적이지 않은 버그들의 수정은 이 브랜치에 머지됩니다. 실험적인 기능들을 원하신다면, 이 브랜치를 사용하십시오. 

 다른 모든 브랜치들은 임시적인 브랜치들입니다. 이 브랜치들은 새로운 기능을 개발하거나 버그를 수정하기 위해 만들어졌으며, 최종적으로는 'develop'브랜치로 머지됩니다.
 모든 pull request는 반드시 'develop' 브랜치로 요청되어야 합니다.

## 제거
  ```bash
  $ make uninstall
  ```

### 수동 제거
다음 폴더를 삭제하시면 됩니다:
    $HOME/Library/Application\ Support/Developer/Shared/Xcode/Plug-ins/XVim.xcplugin

## 기능 리스트
  [FeatureList.md](Documents/Users/FeatureList.md)를 참고하십시오.

## 버그 리포트
  안타깝게도, XVim은 종종 Xcode를 크래시 나게 합니다. 모든 버그를 없애기 위해 노력하고 있지만, 이는 대단히 어려운 일입니다. 여러분께서 다음의 정보가 포함된 버그 리포트를 제공해 주시면 저희에게 큰 힘이 됩니다.

   * 크래시 정보 ( Xcode는 크래시가 발생했을 때 쓰레드 스택의 트레이스를 보여줍니다. 그것을 복사해 주십시오.)
   * 크래시가 발생했을 때 당신이 했던 작업(일련의 키보드 입력, 혹은 마우스 클릭 등)
   * 당신이 수정하던 텍스트
   * Xcode 버전
   * XVim 버전 (당신이 빌드한 Xvim의 버전)

  위에 명시된 정보들만으로 문제를 푸는 것이 어려울 때는, 아래의 영상에 나온 방법대로 debug log를 얻어 보내주십시오.

  [How to get XVim debug log](http://www.youtube.com/watch?v=50Bhu8setlc&feature=youtu.be)

  버그에 대한 test case를 만들어주신다면 대단히 감사하겠습니다. Documents/Developsers/PullRequest.md의 "Write Test" 섹션에 어떻게 테스트 케이스를 작성하는지 나와 있습니다. 여기에 명시된 7개의 항목들을 당신이 작성한 issue에 적어주십시오. 어떤 소스코드를 올릴 필요는 없습니다.

## Bountysource
  XVim은 Bountysource를 지원합니다. 당신의 issue를 좀 더 빨리 해결하고 싶으시다면, 당신의 issue에 상금을 거십시오. 기여자는 그 이슈를 좀 더 먼저 해결하고자 할 것입니다(반드시 그런 것은 아닙니다.)
  상금을 걸고자 하신다면, 아래의 링크를 따라간 뒤 그곳에서 'Issue'탭을 클릭하십시오. 당신의 issue를 선택한 뒤 그에 대한 상금을 거십시오.

  https://www.bountysource.com/teams/xvim

## 기여자 가이드라인
  [CONTRIBUTING.md](.github/CONTRIBUTING.md)를 참고하십시오.

## 기부
  이 플러그인이 유용하다고 생각하신다면, 기부를 부탁드립니다. 
  기부를 할 수 있는 두 가지 방법이 있습니다. 일본의 대지진 및 쓰나미 피해에 대한 구호를 위해 기부하거나, [BountySource](https://www.bountysource.com/teams/xvim)를 통해 이 프로젝트를 지원하는 방법이 있습니다. 물론 둘 다 하셔도 됩니다 :) .


### 일본 대지진 및 쓰나미에 대한 구호
  저는 이 프로젝트를 통해 돈을 벌고자 하지 않기 때문에, 이 프로젝트로 들어오는 기부를 2011년 동북 대지진 및 쓰나미의 피해를 입어 고통 받는 사람들에게 돌리고 있습니다.
  아래 Paypal을 통해 직접 기부해 주십시오. 그렇게 하면 수수료가 절약되어 더 많은 돈이 필요한 곳에 쓰이게 됩니다.

  https://www.paypal-donations.com/pp-charity/web.us/campaign.jsp?cid=-12

  위 paypal 링크를 통해 기부를 해도, 저희에게 어떤 메시지가 발송되지는 않기 때문에 [Message Board]( https://github.com/JugglerShu/XVim/wiki/Donation-messages-to-XVim )에 당신의 기부메시지를 적어주시면 저(희)는 매우 감사하겠습니다. 또한 이는 저(희)에 큰 동기부여가 됩니다!

### BountySource
  이 프로젝트를 돕고 향상시키고자 하신다면, [BountySource](https://www.bountysource.com/teams/xvim)를 통해 지원하는 것을 고려해 주십시오. 
  당신은 팀을(즉 프로젝트 전체를)지원할 수도 있고, 특정 issue에 대해 상금을 걸 수도 있습니다. (만약 당신이 발견한 버그나 추가되어야 할 기능이 issue에 등록되지 않았다면, 직접 만들 수도 있습니다)

## 기여자들
  깃헙 저장소의 contributors page를 참고하시기 바랍니다.
  https://github.com/XVimProject/XVim2/contributors

## License
  MIT License
