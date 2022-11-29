# cheat-sheet

### 1. 로컬 저장소 초기화
```
git init <directory>
```
### 2. 원격 저장소 복제
```
git clone <url>
```
### 3. 스테이징 영역에 파일 추가
```
git add <file>

git add .
```
### 4. 변경 사항 커밋
```
git commit -m "<message>"
```
추적된 파일 및 커밋 에 대한 모든 변경 사항을 추가하려는 경우
```
git commit -a -m "<message>"
```
or
```
git commit -am "<message>"
```
### 5. 스테이징 영역에서 파일 제거
```
git reset <file>
```
### 6. 파일 이동 또는 이름 바꾸기
```
git mv <current path> <new path>
```
### 7. 리포지토리에서 파일 제거
```
git rm <file>
플래그 를 사용하여 스테이징 영역 에서 제거할 수도 있습니다.--cached
git rm --cached <file>
```
## 기본 Git 개념
```
기본 지점 이름:main
기본 원격 이름:origin
현재 분기 참조:HEAD
의 부모 HEAD: HEAD^또는HEAD~1
조부모 HEAD: HEAD^^또는HEAD~2
```
### 13. 분기 표시
```
git branch
유용한 플래그 :

-a: 모든 지점 표시 (로컬 및 원격)
-r: 원격 지점 표시
-v: 마지막 커밋이 있는 분기 표시
```
### 14. 브랜치 만들기
```
git branch <branch>
분기 를 만들고 checkout명령 을 사용하여 전환할 수 있습니다.
git checkout -b <branch>
```
### 15. 지점으로 전환
```
git checkout <branch>
```
### 16. 브랜치 삭제
```
git branch -d <branch>
플래그 를 사용하여 분기 를 강제로 삭제할 수도 있습니다 .-D
git branch -D <branch>
```
### 17. 브랜치 병합
```
git merge <branch to merge into HEAD>
유용한 플래그 :

--no-ff: 병합이 빨리 감기 로 해결되더라도 병합 커밋 을 생성합니다.
--squash: 지정된 브랜치 의 모든 커밋 을 단일 커밋 으로 스쿼시합니다.
빨리 감기 병합
빨리 감기 병합

빨리 감기가 아닌 병합
빨리 감기 병합 없음

--squash 플래그 를 사용하지 않는 것이 좋습니다. 모든 커밋 을 단일 커밋 으로 스쿼시 하여 커밋 히스토리가 지저분해 지기 때문 입니다.
```
### 18. 브랜치 리베이스
```
리 베이스는 일련의 커밋 을 새로운 기본 커밋 으로 이동하거나 결합하는 프로세스입니다.

리베이스
git rebase <branch to rebase from>
```
### 19. 이전 커밋 체크아웃
```
git checkout <commit id>
```
### 20. 커밋 되돌리기
```
git revert <commit id>
```
### 21. 커밋 재설정
```
git reset <commit id>
플래그를 추가하여 --hard모든 변경 사항을 삭제할 수도 있지만 주의해서 사용하십시오.
git reset --hard <commit id>
```
### 22. 저장소 상태 확인
```
git status
```
### 23. 커밋 히스토리 표시
```
git log
```
### 24. 준비되지 않은 파일에 대한 변경 사항 표시
```
git diff
--staged플래그를 사용하여 준비된 파일 에 대한 변경 사항을 표시 할 수도 있습니다 .
git diff --staged
```
### 25. 두 커밋 간의 변경 사항 표시
```
git diff <commit id 01> <commit id 02>
```
### 26. 보관 변경 사항
```
숨김 을 사용하면 변경 사항을 커밋 하지 않고 임시로 저장할 수 있습니다 .
git stash
stash 에 메시지를 추가할 수도 있습니다 .
git stash save "<message>"
```
### 27. 보관함 목록
```
git stash list
```
### 28. 숨김 적용
```
숨김 을 적용 해도 숨김 목록 에서 제거 되지 않습니다 .
git stash apply <stash id>
를 지정하지 않으면 <stash id>최신 숨김 이 적용됩니다(유사한 모든 숨김 명령에 유효) .

형식을 사용하여 숨김stash@{<index>} 을 적용 할 수도 있습니다 (모든 유사한 숨김 명령 에 유효 함).
git stash apply stash@{0}
```
### 29. 보관함 제거
```
git stash drop <stash id>
```
### 30. 모든 보관함 제거
```
git stash clear
```
### 31. 보관함 적용 및 제거
```
git stash pop <stash id>
```
### 32. 숨김에 변경 사항 표시
```
git stash show <stash id>
```
### 33. 원격 저장소 추가
```
git remote add <remote name> <url>
```
### 34. 원격 저장소 표시
```
git remote
원격 저장소 의 URL-v 을 표시하는 플래그를 추가 합니다 .
git remote -v
```
### 35. 원격 저장소 제거
```
git remote remove <remote name>
```
### 36. 원격 저장소 이름 바꾸기
```
git remote rename <old name> <new name>
```
### 37. 원격 저장소에서 변경 사항 가져오기
```
git fetch <remote name>
```
### 38. 특정 지점에서 변경 사항 가져오기
```
git fetch <remote name> <branch>
```
### 39. 원격 저장소에서 변경 사항 가져오기
```
git pull <remote name> <branch>
```
### 40. 변경 사항을 원격 저장소로 푸시
```
git push <remote name>
```
### 41. 특정 브랜치에 변경 사항 푸시
```
git push <remote name> <branch>
```
