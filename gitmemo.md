# github

Git, Github 사용법을 기록하는 페이지입니다. / 제로초 사이트의 깃 강좌 필기입니다. [https://www.zerocho.com/category/Git](https://www.zerocho.com/category/Git) 

## Git 저장소 생성(init), 최초로 commit 하기

---

### git init

git example 라는 폴더를 만들고 안에다가 git.html, git.css라는 예제 파일을 만든다.

- gitexample(folder)
    - git.html
    - git.css

그리고 터미널에 이 gitexample 폴더 위치로 간 후 **git init** 명령어를 입력하면 

```jsx
/Users/inhyeokjo/Desktop/gitexample/.git/ 안의 빈 깃 저장소를 다시 초기화했습니다
```

가 뜨면서 .git이라는 숨겨진 폴더가 생성되었다.(ls -a를 터미널에 치면 확인이 가능하다!)
이제 이 프로젝트에 Git을 사용할 수 있다.

---

### git status

![github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__9.22.34.png](github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__9.22.34.png)

**git status** 를 쳐보자. 현재 파일들의 상태를 볼 수 있다.(사진은 git.html만 만들고 git status를 입력한 모습)

branch는  master.(추후에 배우자!)

아직 커밋commit이 없다고 나온다. 여기서 **commit란**

> 파일을 추가 하거나 변경 내용을 저장소에 저장하는 작업

위에 추적하지 않는 파일 (왜 한글이지?) 

Untracked files : git.html  뜰 텐데 저 파일은 commit이 되지 않는다. commit 대상에 포함시키려면 

**git add [파일 이름]**을 해야 한다.

---

### git add

**git add git.html**을 하게 되면 git.html이 commit할 대기를 하게 된다. 

파일이 많다면 git add . 으로 Untracked 파일들을 모두 저장 할 수 있다.

---

### git commit

**commit : 파일을 추가하거나 변경 내용을 저장소에 저장하는 작업**

이제 모든 파일이 commit 대기중이다. commit를 해보자

git commit -m [설명]하면 된다. 

여기서 주의할 점은 로그인을 안 한 경우 에러가 뜬다. 그때는

```jsx
git config --global user.emal "내 이메일"
git config --global user.name "내 이름"
```

을 적으면 된다.

이제 커밋을 해보면 잘된다.

이 첫 번째 commit 을 기준으로 자유롭게 코드를 수정하거나 추가, 삭제할 수 있다. 문제가 생기면 이 commit로 돌아오면 된다.

add와 commit를 동시에 하는 방법도 있는데 

**git commit -am [설명]** 으로 -a를 추가해주면 add도 동시에 된다.

---

### git log

![github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__9.40.31.png](github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__9.40.31.png)

commit 내역을 볼 수 있는 git log 입니다.

commit을 하면 여기에 내용이 쌓이게 되고 쌓인 commit 간에 되돌릴 수 있고 서로 합칠 수 있다.

빠져나오려면 q를 클릭하면 된다.

**git log -p**

를 하게 되면 변경사항도 같이 볼 수 있다.

---

## Github 사용하기, remote, clone, push, pull

깃허브 저장소를 생성하기 위해 New repository를 생성해보자

![github%20f05d1922bd4e44e0b7bab7c33a7223f2/Untitled.png](github%20f05d1922bd4e44e0b7bab7c33a7223f2/Untitled.png)

바로 생성을 해보면

![github%20f05d1922bd4e44e0b7bab7c33a7223f2/Untitled%201.png](github%20f05d1922bd4e44e0b7bab7c33a7223f2/Untitled%201.png)

이렇게 생성이 되는데
오른쪽 Watch는 저장소에 변화가 있을 때 알림이 오게 설정하는 거고, 
star는 페이스북의 좋아요 기능
Fork는 남의 저장소를 복사하여 내 저장소에 붙여넣기 하는 기능이다.
중간에는 Code/ Issues / Pull requesrt(PR)/ actions / Projects / Wiki / Security / insights/ settings가 있다.
Code는 현재 저장된 코드를 보여주는 거고 Issues는 남들이 자기 저장소를 쓰는데 문제가 생길 경우 문제를 제기하는 공간이다. 그리고PR은 남들이 직접 수정해서 올려주는 곳이다.
PR을 통해 남의 코드에 기여할 수도 있고 기여받을 수도 있다.

---

### git remote

git remote가 원격 저장소를 관리할 수 있는 명령어다. 

```jsx
git remote add origin https://github.com/[이름]/gitExample 
```

로 origin 이라는 이름의 원격 저장소 주소를 등록한다. 

만약 이 origin 이라는 원격 저장소를 지우고 싶다면 

```jsx
git remote remove origin 
```

을 하면 된다.

---

### git push

원격 저장소에 commit을 저장해보자. **git push origin master** 을 해보면 origin은 원격 저장소 이름이고, master은 현재 사용하는 컴퓨터의 브랜치 이름이다. 

![github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__9.55.33.png](github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__9.55.33.png)

---

### git pull

git pull은 다른 사람이 PR을 통해서 코드를 업데이트 했거나, github을 통해서 commit했을때 그 내용을 클라이언트로 내려받는 명령어이다. 
**git pull origin master**

하게 되면 origin의 내용이 master 로 복사된다.

---

### git clone

git clone 은 git pull과 비슷하지만 클라이언트 상에 아무것도 없을 때 서버의 프로젝트를 내려받는 명령어이다.

```jsx
git clone [저장소 주소]
```

를 하면 된다. 저장소의 내용을 다운받고 자동으로 init도 됩니다.

---

## Git commit 수정하기, diff, checkout, revert, reset

이번에는 두 번째 commit을 push해보자. 실수로 잘못된 commit을 만든 경우를 가정하고 진행해본다.

Git에는 크게 2가지 상태가 있다

**Untracked** 와 **Tracked** 파일이다.

Untracked는 Git 버전관리에 포함되지 않은 파일이고 Tracked는 포함된 파일인데 이 Tracked는 세 가지 상태로 나뉜다.

git.html을 수정하고 git status를 보면

![github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__10.03.08.png](github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__10.03.08.png)

수정된 파일도 직접 add를 해줘야 다음 commit때 반영된다.

commit는 Git에서 하나의 **단위**로 취급되며 따라서 최대한 잘게 commit을 해주는게 좋다. 

---

### git diff

수정된 파일에서 어떤 부분이 달라졌는지 확인하고 싶다면 **git diff** 명령어가 있다.

![github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__10.05.33.png](github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__10.05.33.png)

바뀐 부분이 -와 +로 보여지게 된다. 

![github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__10.07.44.png](github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__10.07.44.png)

위 그림은 Untracked와 Tracked의 3단계를 보여준다. 3단계로 Unmodified, Modified, Staged가 있는데 

- Unmodified : commit을 한 후 변경점이 없는 상태
- Modified : 초기 생성 후 add된 파일(Tracked)이 수정됐을때
- Staged : 처음 생성 파일을 add 한 경우(Untracked > Staged) 혹은 add된 파일이 수정된 경우(Modified > Staged)

Staged 상태의 파일을 commit 하면 다시 Unmodified 상태가 된다.

---

### git checkout

Modified 상태의 파일을 add 하지 않고 다시 Unmodified로 되돌려보내고 싶을 때, 수정을 잘못해서 파일을 원상태로 되돌리고 싶을때 **git checkout git.html** 하면 원래대로 되돌아온다.

```jsx
git checkout [파일 이름] //후에 checkout의 다른 경우가 있다.
```

---

### git reset

만약 add까지 해서 Modified가 아니라 Staged 상태라면 원래대로 되돌릴때 git reset을 사용한다.

**git reset git.html**하면 Staged 상태에서 Modified 상태로 돌아간다. 그 상태에서 **git checkout git.html을** 하면 Modified > Unmodified로  간다.

![github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__10.17.02.png](github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__10.17.02.png)

commit을 한 후에 되돌릴 때도 git reset이 사용된다. 옵션은 세 가지가 있는데

- —soft
- —mixed
- —hard

이다. (하이픈 2개, notion 상에서 합쳐져 보인다)

soft는 commit 후의 Unmodified 에서 commit 직전의 Staged 상태로 만들고,

mixed는 Unmodified에서 commit 전의 Modified 상태로 만들고

hard는 Unmodified 에서 commit 전의 Unmodified 로 만듭니다. 

—mixed 가 기본 옵션이다.

![github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__10.23.25.png](github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__10.23.25.png)

위의 사진을 보면 두번째 커밋을 한 후에 **git reset HEAD~1** 을 했는데 HEAD가 현재 commit의 위치를 나타내고 ~1은 commit 1개 전으로 되돌아가라는 뜻이다.

**HEAD : 현재 작업하는 로컬 브런치.**

아무런 옵션을 넣어주지 않았기 때문에 git status을 해보면 Modified 상태로 돌아간 것을 확인 할 수 있다.

---

### git revert

revert는 reset과 비슷하지만 이전 commit 내용을 새 commit으로 만들어서 저장한다.

![github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__10.29.46.png](github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-22__10.29.46.png)

commit을 한 후에 git revert HEAD를 하면 화면이 바뀌면서 vi로 적을수 있는 창이 나온다

revert에 대한 commit 메세지를 바꿀 수 있는데(캡처를 못함..)저장하고 log를 보면 Revert는 이전 커밋을 덮어씌웠기 때문에 새로운 commit이 추가된다.

revert를 하는 이유는 commit을 이미 push해서 서버에 저장해버린 경우 사용하는데 서버에는 이미 잘못된 commit이 저장되었기 때문에 클라이언트에서 reset을 해봤자 서버에서는 되돌릴 수 없다. 그래서 commit을 덮어쓰는 revert 방법을 쓴다.

---

## git 브랜치(Branch) 관리

1) 혼자 작업할  때 : 홈페이지를 만들다가 실시간 알림 기능 등을 추가하고 싶을때 한 번에 만들 수 있을거라는 확신이 없어서 무수히 많은 commit을 해야 완성 할 수 있을것 같을 때, 그리고 실패 시에는 commit을 이전으로 되돌리고 싶은데 master 브랜치의 log가 지저분해지는 것은 원하지 않을 때

2) 협업 할 때: A와 B 두명이서 협업하는데 하나의 파일을 둘이 동시에 작업을 하고 있을 경우 여러 명이 같은 파일을 작업해서 commit을 한 후 동시에 Github에 push를 하면 충돌이 발생할 수 있다. 

위와같은 상황에서 branch 기능을 사용한다. 기본으로 생성되는 master 브랜치 말고 다른 브랜치를 만들어서 사용하는데 위의 예시가 다른 브랜치를 사용하는 이유고, 또 하나의 이유는 실제 환경에선 master 브랜치에 배포 준비가 된 commit들만 남기는 경우가 많기 때문이다.

---

### git branch

명령어를 통해 새로운 branch를 만들어보자

```jsx
git branch [브랜치명]
```

![github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-23__3.28.45.png](github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-23__3.28.45.png)

feature 라는 새 브랜치를 만들었다.

*표시가 있는게 현재 HEAD가 있는 branch

---

### git checkout

새로만든 feature 브랜치에서 작업하려면 feature 브랜치로 HEAD를 옮겨야 한다. 

```jsx
git checkout [브랜치명]
```

파일에 사용했을 때는 Modified에서 Unmodified로 상태를 변경하는 명령어지만, 브랜치에 사용하는 경우 브랜치간 전환을 한다.

이후 Feature commit 라는 메시지로 commit 하면( git.html 파일을 수정 후 )

![github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-23__2.47.04.png](github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-23__2.47.04.png)

현재 

master와 feature는 "Second commit" 까지는 공유하지만 그 다음부터는 별개의 프로젝트이다.

---

## Merge와 Rebase

### git merger

feature에서 작업하던 내용을 master와 합치게 하려면 merge를 사용해야 한다

```jsx
git merge [브랜치명]
```

여기서 주의할 점은 브랜치 명은 합칠 branch여야 하며 바탕이 되는 branch가 아니다. 

여기서 합칠 branch는 feature이며 merge 전에 항상 git branch로 현재 HEAD가 바탕이 되는 master에 있나 확인해야 한다.

![github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-23__3.11.32.png](github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-23__3.11.32.png)

master branch로 변경 후 merge를 했다.

> merge 결과에 fast-forward 라고 표시되어 있는데 이것은 master 브랜치를 앞으로 쭉 당겼다는 뜻이다. feature 브랜치가 master 브랜치보다 한 commit 앞에 있었기 때문에 master 브랜치가 feature 를 merge 한 순간 한 commit 앞으로 당겨지는 것이다.

### conflict

branch 끼리 충돌이 나는 경우가 있는데 그 경우를 알아보자.

**git reset HEAD~1** 으로 master branch를 뒤로 돌려보자 (—mixed > Unmodified 에서 commit 전 modified 로 이동)

이전 commit로 이동 후 branch를 featrue로 이동 시켜 modified 상태에서(master branch) 다른 브랜치로 이동해 commit를 하려 했으나 ..... 

![github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-23__11.25.33.png](github%20f05d1922bd4e44e0b7bab7c33a7223f2/_2020-12-23__11.25.33.png)

git에서 막아주네요 .. 버전이 달라서 그런것 같으니 빠른 포기,

---

### git rebase

두 branch를 합치는 다른 방법.  말 그대로 rebase , base를 재설정 한다는 의미이다. 

제로초 사이트에는 conflict 관련해서 정리했기 때문에 다른 사이트를 참고했는데.. 너무 좋은 글이 많아서 따로 정리하려고 한다.

<rebase는 다른 페이지에 정리하기>