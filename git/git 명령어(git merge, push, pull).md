<h3>리모트저장소에 push 되어있는 branch를 dev 브랜치로 merge 하는 방법</h3>
자신의 로컬에 있는 브랜치를 리모트 저장소에 있는 해당 브랜치에 push 한다.

```
git add .
git commit -m "Add data"
git push origin <branch명>
```

merge를 담당하는 사람이 자신의 로컬에 있는 dev 브랜치에 리모트 저장소에 있는 두 브랜치를 모두 merge 한다.
```
git remote update
```
(로컬에서 원격 브랜치에 접근하기 위한 명령어 - fetch와 동일)

위 명령어는 원격의 브랜치를 찾지 못해서 발생하는 fatal: Cannot update paths and switch to branch 'feature/rename' at the same time. 라는 오류 메세지를 해결해준다.

로컬의 dev 브랜치로 이동한다.
```
git checkout dev
또는
git switch dev
```

리모트 저장소에 push 되어있는 새로운 브랜치를 merge 한다.
```
git merge branch명
```

모든 브랜치들을 로컬의 dev 브랜치로 merge 했다면, 이 dev 브랜치를 리모트 저장소로 push 한다.
```
git push origin dev
```

merge된 리모트 저장소 dev 브랜치를 다른 팀원이 로컬로 받아와 코드를 동일하게 한다.
```
git pull origin dev
```

