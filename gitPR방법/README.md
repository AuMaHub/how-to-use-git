# GIT Pull requests 방법

## 요청하는 사람
---
1. 협업하는 깃 클론 (현재 터미널 위치에 생성됨)
   
   ``` git clone <REPO_URL> ```
2. 브렌치 확인 
   
   ``` git branch ```
   > mac의 경우 q를 눌러 그만 볼 수 있음
3. 브렌치 생성

    ``` git branch <위 명령어에서 나오지 않는 브렌치명> ```
4. 브렌치 체크아웃
   
   ``` git checkout <생성한 브렌치명> ```
5. 변경내용 추가

    ``` git add . ```
6. 변경내용 커밋
   
   ``` git commit -a -m "<남기고 싶은 메시지>" ```
7. 브렌치 업스트림 푸시
   
   ``` git push --set-upstream origin <브렌치명> ```
8. 


## 승인해주는 사람
---
 git add .
git commit -a -m "testing first commit"
