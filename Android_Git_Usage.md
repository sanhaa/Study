## Android 스마트폰, 태블릿에서 git 사용하기

---
**목차**
1. linux 터미널(termux) 깔기
2. termux 저장소 접근 권한
3. git 설치 및 config

---

<br>

### 1. 안드로이드용 linux terminal 'termux' 깔기
**설치 방법 세 가지**
1. google play store 이용 (https://play.google.com/store/apps/details?id=com.termux)
    - 제일 간편하지만
    - 2020.09 이후 업데이트가 없음 (deprecated) -> 공식 문서에서는 구글 플레이스토어에서 다운받지 말라고 함
    - latest version: `v0.118.0` 이지만 구글 플레이 스토어에 있는 앱 버전은 `v0.101`
2. F-Droid 이용
    - F-Droid 다운로드: https://www.f-droid.org/
    - F-Droid를 다운로드 받기 
    - F-Droid 실행 후 termux 검색하여 설치
3. APK 바로 다운로드 받기
    - 다운로드: https://f-droid.org/en/packages/com.termux/  
    - Download F-Droid 말고 하단 v0.118.0 버전의 Download APK 클릭
    - ![사진]()

2, 3번 방법 모두 apk 파일을 직접 안드로이드 내에 설치하는 거라 `출처를 알 수 없는 앱 설치` 설정 필요
![사진]()

termux github: https://github.com/termux/termux-app#installation

**termux 실행 및 패키지 업데이트**
```
pkg update && pkg upgrade
```

<br>

### 2. termux 저장소 접근 권한
```
termux-setup-storage
```
명령어 실행 -> 저장소 접근 권한 허용할건지 알림창이 뜨고

```
ls
```
명령어를 실행했을 때 폴더/파일이 보인다면 성공, storage/ 폴더 내의 기본 폴더들에만 접근 가능하다고 함
추가로 뭔가를 설정해줘야 하는 듯..?
귀찮으니까 그 중에 아무 폴더나 사용했음

<br>

### 3. git 설치 및 config

```
pkg install git
```

git add 실행 시 `unsafe directory` 에러나서 아래 명령어 입력
```
git config --global --add safe.directory [directory 경로]
```

21년 8월 이후로 github 계정 password를 통한 인증이 막혀서 access token을 이용해야 한다고
PAT 생성: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token

```
git config --global --user.name "username"
git config --global --user.email "user@email" 
```

하고 git push 에서 password 입력하라고 할 때 생성한 access token 붙여넣기 해주면 된다.

<br>

--- 
### Reference
https://codealone.tistory.com/32
