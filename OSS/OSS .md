# OSS
## 복붙하면 KILL U .. 지구 끝까지 쫓아감


Status: In progress
Created: 2023년 11월 27일 오후 8:30
복습: No
유형: 강의

oss 기말고사 

# 6-1 원격 저장소 복제 Clone

## 지역에서 깃허브 원격 저장소 복제 clone

clone (클론) : 원격 저장소를 지역 저장소에 복제

공개된 저장소는 소유와 관계없이 누구나 가능

깃허브 원격저장소 생성

저장소 이름 : git-clone

https 주소 복사

pc 깃에서 원격저장소 복제

- $ git clone [복사된-주소] - 원격저장소와 동일한 이름으로 복제
- $ git clone [복사된-주소] [새로운-폴더명] - 하부 폴더 [새로운-폴더명] 이름으로 복제
- $ git clone [복사된-주소] - 현재 폴더에 바로 복제

원격 저장소 별칭 이름 점검

- $ git remote - 원격저장소 이름 목록만
- 기본 이름 origin 점검
- 위에서 clone 을 했기 때문에 별칭 origin이 위의 주소가 설정

- $ git remote -v : 원격저장소 주소와 이름 목록

원격 저장소 별칭 관리

- $ git remote add origin URL - 원격저장소 별칭 저장
- $ git remote show origin - 자세한 정보
- $ git remote rename origin org - 이름 수정
- $ git remote rm org - 삭제
- $ git remote show origin(atom) - 원격저장소의 모든 브랜치 보기 가능

유명 오픈 소스 소프트웨어

- 편집기 vscode
- 편집기 atom
- VCS 깃
- 구글 인공지능라이브러리

---

# 6-2 지역과 원격 저장소 연동 push pull

## 개인 접근 토근 ( personal access token) 생성

## 깃허브 원격 저장소 수정 후 pull

push , pull 깃허브에선 올리기 내리기

git commit --amend --no-edit --date="OCT 02 11:00:00 2023 +0000”

깃허브 원격 저장소에서 수정 후 커밋

- 원격 저장소의 수정을 지역 저장소에 반영 —> 지역 저장소에서 pull
- 참조 오류 발생 가능
- 인증 오류 발생 가능

인증 오류 해결 방법

PAT (Personal access token)로 연결

지역 저장소에서 Push

- 쓰기 권한이 있어야 push 가능 - 자신의 저장소나 다른 사람의 저장소라면 협업자로 등록
- Push - 로컬 저장소에서 남겨놓은 코드 변경 이력들이 원격 저장소로 전송
- $ git push <저장소 별칭명> <브랜치명> : $ git push origin topic

명령 Push 에서 인자 생략하기

- 옵션 -u 사용
- 최초에 한 번만 저장소명과 브랜치명을 입력하고 그 이후에는 모든 인자 생략
- $ git push 성공 이후 간단히 가능

원격 저장소 수정 사항 fetch로 지역 저장소로 가져와 병합하기

- fetch 원격 저장소에서 로컬 저장소로 소스를 가져와 병합을 미수행하는 명령
- $ git fetch <remote> , $ git fetch origin main , $ git merge origin/main

지역 저장소 수정 사항 push로 원격저장소 보내기

- $ git push origin main
- $ git push

---

# 6-3 지역과 원격 저장소 브랜치 연동

## clone과 push , pull , fetch

git clone - 원격 저장소를 지역 저장소에 복제

git pull - 원격 저장소 > 지역 저장소

git push - 지역 저장소 > 원격 저장소

git fetch - 원격 저장소 지역 저장소로 가져와 병합 미수행

---

# 7-1 오픈소스 소프트웨어

## 오픈소스 소프트웨어

oss : open source software 오픈소스

- 누구나 특별한 제한 없이 코드를 보고 사용할 수 있는 오픈 소스 라이선스를 만족하는 sw
- 소스코드를 공개 , 공개 소스의 복제도 가능

open source initative ( osi ) 

opensource.org

공개 소스 정의의 관리 및 촉진을 담당하는 비영리 조합

자유 소프트웨어 (free software)

- 리처드 스톨먼 자유 소프트웨어 재단 설립
- GNU 프로젝트와 관련된 소프트웨어에서 자유를 중시
- 카피레프트 : 제작자에게 저작권은 인정하면서 누구나 sw를 복제해 사용 할 수 있는 권리를 주어야 한다는 개념을 갖는 sw의미
- 공개된 무료 유닉스 운영체제
- oss가 자유 소프트웨어에서 나온 오픈소스 소프트웨어

오픈소스 방식의 의미

오픈소스 지원 관리 서버

- 소스코드를 통해 여러 개발자가 협업하고 공유하며 이를 지원하는 방안을 마련
- 오픈소스 커뮤니티 내의 사고 및 협업 양식

협업 방식

- 서로 간에 소스코드를 사용 , 변경 및 공유할 수 있도록 커뮤니티 프로덕션과 동료 평가에 의존
- 개발자들은 혁신적인 솔루션을 만들기 위해 인사이트 , ටㅏ이디어  및 코드 공유
- 모든 사용자가 수정 ,개선 및 재분배 할 수 있도록 보장
- 대규모 협업의 기본 원칙으로 운용

장점

- 누구든 보다 쉽게 연구하여 새로운 프로그래밍 기술을 개발
- 커스터마이징과 혁신 지원

단점

- 공개의 의무
- 품질보증 및 유지보수 보안 등의 어려움

오픈소스 개발 모델

LAMP : 대부분의 웹을 지원하는 서비스 스택 모델

- Linux : 오픈소스 운영체제이자 세계 최대 규모의 오픈소스 프로젝트
- apache : 초기 웹에서 핵심 역할을 한 오픈소스 크로스 플랫폼 웹 서버
- MySql : 대부분 db 기반 웹 애플리케이션에서 사용하는 오픈소스 관계형 데이터베이스 관리 시스템
- PHP : 소프트웨어 개발에 사용되는 범용 스크립팅 언어

빅데이터 , 인공지능 분야

- Python
- Scikit-learn
- Tensorflow
- Pytorch

다양한 오픈소스 개발 모델

- Android 모바일 os
- mozila firefox 웹 브라우저
- open office , libreoffice
- 버전 제어 시스템인 git

---

## 오픈소스 소프트웨어 저작권

오픈소스 소프트웨어 라이선스 종류

- GNU General Public
- MIT License
- Apache
- BSD
- MySQL
- SUSE
- Ubuntu

소스코드 반환 의무

GPL,AGPL,LGPL,MPL,EPL 등

- 링크되거나 코드가 포함된 SW의 소스코드를 공개
- 특허 , 영업비밀 , 핵심 기술 등이 외부로 유출될 가능성이 있으니 주의
- 저작권 고지의무

GPL ( GNU - General Public License )

자유소프트웨어재단에서 만든 라이선스

- 자유소프트웨어재단 설립자인 리처드 스톨만
- 카피레프트
- 목적이나 형태 제한 없이 사용 가능ㅇ
- 수정하고 배포하는 모든 경우에 무조건 GPL로 공개 [ gpl 라이센스 명시 ]

AGPL ( GNU - Affero GPL )

GPL을 기반으로 만든 라이선스

- 네트워크로 상호작용 하는 소프트웨어의 소스코드도 공개해야 한다는 조항을 추가한 라이선스
- 서버에서 프로그램을 실행해서 다른 사용자들과 통신 중 [ 사용자들이 다운로드 할 수 있도록 해야하는 조항을 포함 ]

LGPL ( GNU - Lesser GPL )

보다 완화된 GPL 라이선스

- 실무에서 사용되기 어려운 점을 보완하기 위해서 만들어진 라이선스
- Lesser GPL로 명칭 변경

Apache License

- 소스코드 공개에 대한 의무사항은 라이센스에 포함되어 있지 않음

MIT License

- MIT에서 학생들을 지원하기 위해서 만든 라이센스
- 라이센스와 저작권 관련 명시 의무
- 가장 느슨한 조건을 가지고 있어서 많은 사람들이 사용하기 용이함

| 카테고리 | 소스코드 공개 의무 | 사례 |
| --- | --- | --- |
| Strong copy | 2차 저작물 소스코드 공개 의무 ㅇ | GPL |
| Weak copyleft | 특정 조건에서 2차 저작물 소스코드 공개 의무 없음 | LGPL |
| Non copyleft | 2차 저작물 소스코드 공개 의무 없음 | Apache. , BSD , MIT |

---

# 7-2 임시저장 stash

## 깃 4영역과 임시 저장 개요

### 깃 4영역 : 깃 3영역 + stash 영역

Git stash : 놓다 , 남겨두다 , 감추다 , 안전한 곳에 숨겨두다

커밋할 필요 없이 파일의 변경 사항을 숨기거나 비밀리에 저장할 수 있는 강력한 도구

- 작업 디렉토리와 스테이징 영역의 원래의 내용을 stash 스택에 저장
- 작업 디렉토리와 스테이징 영역의 값을 깃 저장소의 마지막 커밋 내용으로 복사

따로 안전한 곳에 저장했다가 다시 가져올 수 있는 기능

Stash 저장 구조

깃에서 임시저장소(스택 구조)에 저장

- Stack of git stashes
- 가장 최근의 내용이 가장 위에 저장되는 구조

Git stash 필요성

브랜치 이동 또는 이전 커밋으로 이동하려면 커밋할게 없고 , 작업트리 clean 해야함

But 수정한 내용이 있거나 커밋할 게 있는 상황에서 다른 브랜치 이동 혹은 이전 커밋으로 이동하려면 현재 작업 공간의 수정 내용과 인덱스의 내용을 보관할 필요가 있음, —> 나중에 다시 사용하기 위해

stash 저장되는 내용

작업 디렉토리 내용과 스테이징 영역 내용이 stash 저장 , 작업 디렉토리 내용과 스테이징 영역 내용이 최신 커밋 자료로 남음

## 임시 저장 명령 stash

작업 폴더와 스테이징 영역을 stash에 저장하고 작업 폴더를 정리

- git stash
- git stash -m ‘메시지’
- git stash save
- git stash save ‘메시지’

옵션

- —keep -index , -k 스테이징 영역은 제외하고 작업 디렉토리더만 저장 ( 작업 디렉토리는 스테이징 영역의 내용으로 )
- —include -untracked , -u     Untracked 파일도 포함해 저장

최근 임시저장 내용을 가져와 반영 , stash 목록은 그대로

기본으로 작업 디렉토리 내용만 다시 복사해 활용

- git stash apply

스테이지 영역도 함께 복사하기 위해서는 옵션 사용

- git stash apply —index

주요 옵션

옵션 -k | —keep -index

- 스테이징 영역은 저장하지 않고 그대로 놔둠
- 그러므로 checkout 할 수는 없음

옵션 -u | —include -untracked 

- Untracked파일도 포함해 저장

옵션 -p | —patch

- 변경된 모든 사항들 저장 x 대화형 프롬프트를 통해 자신이 stash에 저장할 것과 저장 ㄴㄴ 것 지정 가능

stash 목록 보기

- git stash list

stash @{0} >>> 가장 최신 것이 0번

stash @{1}

stash @{2}

…

특정 stash 확인

커밋 자료와 최신 stash 항목 간의 차이로 표시

- git stash show
- git stash show -p : (-p:  파일 내용의 차이까지 보이기)

커밋 자료와 해당 stash 항목 간의 차이로 표시

- git stash show stash@{n}
- git stash show stash@{n} -p : 내용의 차이까지 보이기

임시 저장된 stash 반영

최근 또는 지정된 임시저장소 내용을 가져와 반영하고 삭제

- git stash pop
- git stash pop stash @{n}

최근 또는 지정된 임시저장소 내용을 가져와 반영, 작업 디렉토리만 반영 , stash 목록은 그대로

- git stash apply
- git stash apply stash @{n}

최근 또는 지정된 임시저장소 내용을 가져와 반영, 작업 디렉토리와 스테이징 영역도 반영 , stash 목록은 그대로

- git stash apply —index
- git stash apply —index stash @{n}

특정 stash 삭제와 모든 stash 삭제

최근 임시저장 내용을 삭제

- git stash drop

저장된 임시저장 내용을 삭제

- git stash drop stash @{n}

모든 stash 목록을 모두 제거

- git stash clear

Untracked 파일 삭제

- git clean
- git clean -i
- git clean -f —> 무조건 삭제

---

# 8-1 다양한 브랜치 병합

## 브랜치 병합 개요

브랜치 병합

병합(merge)

- 두 개의 브랜치를 하나로 모으는 과정
- fast-forward(빨리 감기) 병합
- 3-awy 병합

빨리감기 fast-forward 병합의 이해

- fast-forward 병합 조건
- 현재 브랜치 master 가 병합할 대상 커밋의 직접적인 뿌리가 되는 경우
- 간단히 두 브랜치가 일렬 상태
- bugfix 브랜치 이력이 master 브랜치 이력을 모두 포함하는 경우
- 브랜치 master에서 병합
- git merge bugfix

fast-forward 병합 수행

master 브랜치는 단순히 이동

기준 브랜치 master

3-way 상태 : 두 분기가 갈라진 상태

두 브랜치의 조상이 같은 경우

- master 브랜치 내의 변경 내용과 bugfix 브랜치 내의 변경 내용을 하나로 통합할 필요

3-way 병합

- 새로운 커밋을 사용하여 두 기록을 합침

3-way 병합 수행

새로운 커밋 E 생성

- 두 브랜치의 변경을 가져온 ‘merge commit’병합 커밋 E를 생성
- 병합 완료 후, 통합 브랜치인 ‘master’ 브랜치로 통합된 이력이 생성

$ git merge bugfix [ -m이 없으면 메시지 입력할 기본 편집기 실행 ]

$ git merge bugfix -m ‘merge msg’

기본이 fast-forward 상태에서 non fast-forward 병합

마스터에서 dev1을 fast forward로 병합

- git merge dev1
- 일렬병합

마스터에서 dev1을 non fast forward로 병합(3-way 병합)

- 옵션 —no-ff
- git merge dev1 —no-ff

## 병합의 다양한 옵션

‘non fast forward’ 병합 옵션을 지정

non fast forward 병합

- git merge —no-ff {병합할 브랜치 명}

병합 실행 시에 ‘fast-forward 병합’이 가능한 경우라도 3-way병합을 수행

- 병합된 브랜치가 그대로 남기 때문에
- → 그 브랜치로 실행한 작업 확인 및 브랜치 관리 면에서 더 유용

병합의 다양한 옵션 종류

$ git merge {병합할 브랜치 명}

- 보통의 병합, 융통성 있는 병합
- 현 브랜치와 병합할 브랜치가 일렬 상태
- fast - forward 병합
- → 새로운 병합 커밋 없이 병합할 브랜치 커밋으로 이동
- 현 브랜치와 병합할 브랜치가 갈라져 있는 상태
- 3-way 병합
- → 새로운 병합 커밋을 생성해 두 브랜치를 합침

$ git merge —no-ff {병합할 브랜치 명}

- 무조건 3-way 병합되는 옵션

$ git merge —ff-only {병합할 브랜치 명}

- 상태가 fast forward인 일렬 상태에서만 병합 진행

$ git merge—squash {병합할 브랜치 명}

- 현재 브랜치에 병합 대상과의 합치는 커밋을 하나 생성해 병합
- → 병합되는 브랜치는 사용하지 않고 그대로 남음

옵션 —squash

강압적인 병합

- git merge —squash hotfix
- 커밋 이력과 병합되는 브랜치 이력도 남기지 않음
- 새로운 커밋에 상대 브랜치의 내용을 모두 합해 새로운 커밋으로 병합

---

# 8-3 병합 충돌과 해결

## 병합 충돌

병합 충돌(conflict) 이해

3-way 상태에서 두 브랜치의 동일 조상인 커밋1을 기준

- 병합할 두 브랜치 마지막 커밋을 비교

충돌의 기준

- 파일 충돌 없음
- 수정 되지 않거나 한쪽 브랜치에서만 수정되면

- 파일 충돌 발생
- 두 브랜치 모두에서 변경 사항이 달리 발생한 파일

충돌 해결

충돌이 발생하면 해당 파일의 충돌을 먼저 해결

- 충돌 해결
- 직접 파일 내용을 수정 후 저장
- 계속해서 add,commit 진행
- 필요하면 합병된 이전 브랜치 삭제

충돌 발생 코드 표시

충돌한 파일 내부 표시 - 3개의 표시로 구분

- <<<<<<<< HEAD
- →  현재 브랜치 HEAD의 수정 내용
- ===========
- → 병합되는 브랜치 feat/list 의 수정 내용 (밑에꺼)
- >>>>>>>>feat / list

수정 후 3개의 표시는 모두 삭제

## 충돌 해결

병합 취소 후 다시 병합

병합 취소

- git merge —abort

다시 병합

- git merge feat / list

직접 수정 후 저장

- 충돌 표시 모두 제거

추가,커밋 다시

- git commit -am ‘Resolve conflict, main’

---

# 9-1 브랜치 리베이스 rebase

## 병합 rebase

3-way 상태에서 base의 이해

‘master’ 브랜치 커밋 B에서 분기되는 ‘bugfix’ 브랜치

- 커밋 B
- 현재 master와 bugfix의 공통 조상
- → 이를 base라 칭함

선형적 통합 rebase 이해

브랜치 bugfix에서 base를 바꾸는 재배치 하기 이전

- git rebase master

**재배치 rebase 병합 수행**

- base를 수정
- B에서 마스터의 최신 커밋인 D로 수정
- → D 이후에 bugfix를 배치
- 이후 다시 fast forward 병합 수행 : 이 병합을 직접 다시 해야함
- ‘master’ 브랜치의 HEAD가 ‘bugfix’브랜치 마지막 커밋으로 이동
- → 로그 이력이 분기 없이 하나의 줄기로 이어짐

rebase를 이용한 브랜치 병합 과정

fast-forward 병합 방식

- master 브랜치 뒤로 bugfix 브랜치의 이력이 이동
- 이력이 하나의 줄기로 이어짐
- 충돌 발생이 가능

마스터 브랜치의 위치를 변경하기 위해서는

- master 브랜치에서 bugfix 브랜치를 fast forward 병합 필요

Rebase에서의 충돌

충돌 발생 가능

→ 각각의 커밋에서 발생한 충돌 내용을 수정 후 , 추가 , 계속 수행 필요

충돌 발생 후 해결 절차

1. 파일수정
2. 파일 추가 → git add <수정 파일>
3. rebase 계속 수행,마지막 메시지 수정 

→ git rebase —continue

## 3-way, fast-forward와 rebase 비교

3-way merge와 rebase 비교

merge

- 여러 분기가 생긴 변경 내용의 **이력이 모두 그대로 남아 있기 때문에 이력이 복잡해짐**

rebase

- 히스토리가 선형으로 단순해지고 **좀 더 깨끗한 이력을 남김**
- 원래의 커밋 이력이 변경됨
- → 정확한 이력을 남겨야 할 필요가 있을 경우에는 사용하면 안됨

fast-forward merge와 rebase 비교

fast-forward merge

- 조상에 위치한 브랜치에서 선행 브랜치의 마지막 이동하는 병합

rebase

- 두 갈래의 브랜치에서
- → 기존의 베이스를 수정
- → 병합할 브랜치 마지막 커밋

3-way 병합

- git checkout master
- git merge experiment

git rebase <newparent> <branch>

일반적 rebase 방법

- topic에서 main을 rebase 한 후 , 다시 main으로 이동 fast-forward 병합 수행
- git checkout topic
- git rebase main
- git checkout main
- git merge topic

다른 rebase 방법 : 어느 브랜치든 main topic 순서로 재배치 방법

- git rebase main topic
- git checkout main
- git merge topic

---

# 9-2 커밋 이력 수정

## 최신 커밋 수정

최근 커밋 메세지 수정

기본 편집기 설정 방법

- git config —global core.editor ‘code—wait’

설정된 편집기로 최근 커밋 메시지 수정

- git commit —amend
- → 새로운 커밋 ID로 수정됨

최근 커밋 메시지를 직접 입력해 수정

- git commit —amend -m “an uppdate commit message”
- → 새로운 커밋 ID로 수정됨

최근 커밋 내용 수정

HEAD의 내용 수정

- 새로운 파일을 추가하거나 파일을 수정한 후
- 새로운 커밋으로 생성하지 않고
- 최신 커밋에 반영
- → 새로운 커밋 ID로 수정됨

커밋 옵션 —amend 사용

- 기본 편집기로 메시지 편집
- git commit —amend

- 명령어 상에 직접 메세지 입력
- git commit —amend -m ‘new message’

- 메시지 수정 없이 다시 커밋 수정
- git commit —amend —no-edit

## rebase -i로 여러 커밋 수정

rebase —interactive 를 사용

작업 공간이 깨끗한 이후, 이전 여러 개의 커밋을 수정

→ 이전 커밋을 다시 작성한 경우 새 ID가 부여

rebase의 —interactive를 사용하여 커밋 시퀀스를 새로운 기본 커밋에 결합

→ git rebase -i HEAD~3

→ git rebase —interactive HEAD~3

→ HEAD~3 : 수정할 커밋의 직전 커밋

→ 실제 HEAD~2 부터 수정 가능

rebase 의 —interactive 주요 명령어

git rebase —interactive HEAD~3

- 기본 편집기로 열리며, HEAD~3이면 HEAD~2,HEAD~1, HEAD  3개의 행 편집ㄱㄴ
- 로그 결과와 다르게 오래된 커밋부터 표시

주요 reabase -i 대화형 명령어

- p (ick) : 해당 커밋을 수정하지 않고 그대로 사용
- r (eword) : 개별 커밋 메시지를 다시 작성
- s (quash) : 계속된 이후 커밋을 이전 커밋에 결합
- d (rop) : 커밋 자체를 삭제

명령 squash 방법

이후 것( 더 최신의 커밋)을 이전 커밋(더 오래된 커밋)에 뭉치는 방법

- 상위에 위치한 커밋에 pick이 있으면서
- 래로 연속적으로 squash 명령
- 다음으로 커밋 E가 커밋 BB에 뭉쳐져 커밋 E가 제거

새로운 커밋 메시지를 입력하는 단계가 있음

- 기본 편집기로 편집
- BB와 E를 합친 커밋 메시지를 지정

최신 4개를 부분 메시지 수정

- [ ]  git rebase —interactive HEAD~4

명령 drop

- [ ]  마지막 커밋 제거
- git rebase —interactive HEAD~2

---

# 9-3 비주얼스튜디오코드에서 깃 활용

## vscode에서 깃 활용 기초

수정 작업 취소

- [ ]  git restore
- [ ]  git restore —staged

작업 영역과 스테이지 영역 파일 수정 취소

- [ ]  명령어 git restore
- [ ]  옵션 —staged : index 파일 unstage ( index를 최근 커밋으로 수정[복사] )

---

# 10-1 버전 되돌리기 reset

## 버전 되돌리기 reset과 옵션

기능 reset 이해

커밋 이력에서 이전 특정 커밋으로 완전히 되돌아가는 방법

- 이동되는 해당 커밋 이후의 이력은 모두 사라지므로 주의
- → 새로운 커밋 생성 x
- 깃 저장소는 이전 커밋 내용으로 수정
- → 다만 reset 이전에 있던 작업 폴더와 스테이지 영역 내용을 어떻게 유지할지가 관건

reset의 옵션

—hard , —mixed , —soft

- 깃 저장에소는 반드시 복사
- git reset —hard HEAD~ / commit ID → 이동되는 커밋의 내용으로 작업 폴더와 스테이지 영역 , 깃 저장소를 모두 복사
- git reset HEAD ~ / commit ID → 아래와 동일
- git —miexed HEAD~ / commit ID → 이동되는 커밋의 내용으로 스테이지 영역과 깃 저장소 두 부분에 복사, 작업 폴더는 이전 내용 그대로 남음
- git reset —soft HEAD~ / commit ID → 이동되는 커밋의 내용으로 깃 저장소에만 복사, 스테이지 영역과 작업 폴더는 이전 내용 그대로 남음

—hard

git reset —hard HEAD~ 

- 지정된 HEAD~ 의 내용으로 작업 폴더와 스테이지 깃 영역, 깃 저장소가 모두 복사 , 수정
- → reset 전에 있던 작업 폴더와 스테이지 영역에 작업 내용이 모두 사라지므로 주의 필요

git reset —hard HEAD~2

- 지정된 HEAD~2 의 내용으로 작업 폴더와 스테이지 영역 , 깃 저장소가 모두 복사 수정
- → reset 전에 있던 작업 폴더와 스테이지 영역에 작업 내용이 모두 사라지므로 주의가 필요

—mixed

git reset —mixed HEAD~

- 지정된 HEAD~ 의 내용으로 스테이지 영역과 깃 저장소가 모두 복사,수정
- → 커밋 메시지 로그 이력과 함께 당시 스테이지 영역, 깃 저장소 내용이 모두 사라짐
- → 단, 작업 폴더의 내용은 이전 그대로 남음

—mixed는 기본 옵션으로 [ git reset ] 과 동일

→ 옵션 —mixed는 옵션이 없는 것과 같음

—soft

git reset —soft HEAD~

- 지정된 HEAD~ 의 내용으로 깃 저장소만 복사 , 수정
- 커밋 메시지의 로그 이력은 사라짐
- → 작업 폴더와 스테이지 영역의 내용이 모두 이전 그대로 남음

## reset 정리, checkout과 reset 비교

reset의 3가지 방식

git reset —옵션 commit ID

- —hard
- → 인자인 커밋 깃 저장소의 내용을 작업 폴더와 스테이지 영역, 그리고 깃 저장소에 모두 복사 수정 (3)
- —mixed
- → 기본 옵션으로 스테이지 영역과 깃 저장소 두 곳에 복사 수정 (2)
- —soft
- → 깃 저장소에만 복사 , 수정 하므로 **작업 폴더와 스테이지 영역은 이전 내용이 그대로 남음** (1)

커밋 되돌리기

git reset <옵션> <돌아가고 싶은 커밋>

- hard , mixed , soft 세가지
- —soft
- → 바로 다시 커밋할 수 있는 상태로 남아있음
- → **다시 마지막 이전 head로 돌아가려면 commit 만 필요**

- —mixed
- → 이력은 되돌려지고 , 인덱스도 되돌가는 커밋의 내용으로 초기화
- → 다시 마지막 이전 head로 돌아가려면 add ,commit이 필요

- —hard
- → 돌아가려는 이력 이후의 모둔 내용을 삭제
- → 다시 마지막 이전 head로 돌아가려면 파일수정,add,commit 필요

reset 후 다시 바로 이전 상태로 되돌아가기

‘ORIG_HEAD’ 이용하면 매우 간단

→ 바로 이전 커밋 참조

→ git reset —hard ORIG_HEAD

reset과 checkout 비교

git reset 9033

→ 브랜치의 마지막 커밋을 수정하는 명령

git checkout 9903

→ HEAD 포인터를 브랜치 마지막 커밋 이전으로 이동하는 명령

summary

HEAD~2 작업 디렉토리 | 스테이지 영역 | 깃 저장소 에 복사

→ 작업 디렉토리,스테이지 영역, 깃 저장소 : git reset —hard HEAD~2

→ 스테이지영역, 깃 저장소 : git reset —mixed HEAD~1

→ 깃 저장소 : git reset —soft HEAD~2

이전에 수정한 reset을 바로 취소하는 명령

git reset —hard ORIG_HEAD

---

# 10-2 [실습] 버전 되돌리기 reset

버전 되돌리기 reset 전에 수행

버전 되돌리기를 하면 현재 상태가 모두 제거되므로 

 현재의 작업 디렉토리와 스테이징 영역을 임시 저장에 저장

→ git stash

저장 확인

→ git stash list

현재 상태 확인

→ git status

작업 디렉토리와 스테이징 영역 수정

3회 커밋과 이후의 다음 상태로 복원

- 작업 폴더와 스테이징 영역을 임시 저장에 저장해 놓았음
- 임시 저장을 다시 불러오면 됨
- → 스테이징 영역까지 복원하려면 옵션 —index 사용

- git stash apply —index

---

# 10-3 커밋 취소 revert

## 커밋 취소 revert

커밋 취소 revert

undo와 비슷한 기능

- 지정한 특정 커밋을 취소해 바로 이전 상태로 되돌리는 방법
- reset과 다르게 커밋할 것이 없고, 작업 영역이 깨끗해야 수행 가능
- → Nothing to commit , working tree clean
- → 커밋해온 모든 변경 사항들을 rollback
- → 이전의 커밋 히스토리는 그대로 유지, 되돌리는 새로운 커밋이 그 이후에 추가

revert 충돌과 해결

인자가 HEAD~ 와 같이 HEAD 이전을  취소하면 충돌이 발행할 수 있음

- 충돌이 발생하지 않으려면
- 바로 이전 취소를 여러번 계속 → 마치 워드 프로세서에서 취소 [ctrl + z]를 여러 번 하는 것과 비슷

충돌해결 방법

1. 파일수정
2. git add file
3. git revert —continue

옵션 —no -edit

추가되는 커밋 메세지가 자동으로 ‘Revert’ “이전 커밋 메시지”로 지정

| git revert HEAD~ | commit ID | 이동되는 커밋의 내용으로 작업 폴더와 스테이지 영역, 깃 저장소를 모두 복사하고 커밋 메시지를 수정하도록 편집기가 실행됨 |
| --- | --- |
| git revert HEAD~ | commit ID —no -edit  | 옵션 —no -edit 으로 편집기 실행 없이 커밋 메시지가 자동으로 ‘Revert’ 이전 커밋 메시지로 지정되어 있어 새로운 커밋 생성 |

오류가 발생해 revert가 취소

커밋할 것이 있고 작업 영역이 깨끗하지 않으면 오류

→ Nothing to commit, working tree clean

해결방법

커밋을 하고 다시 revert 하는 방법

- → 현재 커밋 내용으로 작업 폴더와 , 스테이지 영역 , 깃 저장소를 모두 복사 , 수정
- → 수정한 내용 사라짐

git reset —hard HEAD~

- 이전 커밋 내용으로 작업 폴더와 스테이지 영역, 깃 저장소를 모두 복사 ,수정
- → 수정한 내용이 사라지고 , 현재 커밋 로그도 삭제

revert로 HEAD 바로 이전 상태로 돌아가기

취소 인자를 HEAD로 사용 

- git revert HEAD : 기본 편집기에서 커밋 메시지 편집 화면 실행
- git revert HEAD —no -edit : 편집 화면 실행없이 자동 커밋 메시지로 커밋 revert “이전 메시지”

## reset vs revert 비교

reset vs revert

- [ ]  되돌리기와 취소
- [ ]  revert : 지정된 이전 커밋을 취소하는 커밋이 생성
- [ ]  reset : 지정된 이전 커밋으로 이동

되돌리기, 재설정 reset 

- 특정 커밋으로 **되돌아가고 그 이후의 로그 이력은 모두 제거**

커밋 취소 revert

- 특정 커밋을 **취소하는 새로운 커밋 생성, 이전 모든 이력은 그대로 남음**

| 항목 | reset | revert |
| --- | --- | --- |
| 기능 | 이전 커밋 상태로 이동 | 이전 커밋을 취소해 그 전 상태로 이동 |
| 새로운 커밋 | 없음 | 있음 |
| 이전 커밋 이력 | 삭제 | 유지 |
| 커밋할 것 없고 작업트리 클린 | 상관 x | 깨끗해야함 |
| 충돌 발생 | 없음 | 발생할 수 있음 |
| 충돌 해결 | - | add 후 commit 혹은 —continue |
| 옵션 | —hard , —mixed , —soft | —continue , —abort , —no -edit , -n | —no -commit |

summary

취소 revert 전체 조건

nothing to commit , working tree clean > 커밋할 것 없고 작업트리 클린

HEAD를 취소해 HEAD~ 상태로 가는 커밋 생성

git revert HEAD

git revert HEAD —no -edit
