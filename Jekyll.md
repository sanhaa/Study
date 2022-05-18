# Github Pages와 Jekyll
```
github pages로 포트폴리오랑 블로그 관리하려고 하는데, jekyll은 뭐고 ruby는 뭔지, github pages랑 무슨 상관인지 도통 모르겠어서 정리하는 중
```

<br>

## What is github pages
```
정적 웹사이트 호스팅
```


## 1. What is Jekyll
```
plain text -> static sites 전환
```
jekyll = `정적 사이트 생성기`

**특징**
1. Simple
    - DB, 댓글 기능 없이 콘텐츠 위주
2. Static
    - Markdonw, Liquid, HTML&CSS -> 정적 사이트 전환
3. Blog-aware
    - permalink(고유 주소), 카테고리, 페이지, 포스트, 사용자 레이아웃 등의 블로그 기능 포함

_DB 같은거 필요 없이, 빠르고 간단하게, 무료 정적 사이트를 만들고 싶을 때 사용_

---

<br>

## Jekyll Environment Setting
1. Ruby 설치 (Windows 10)
    - ruby installer 다운로드: https://www.ruby-lang.org/en/downloads/
    - ruby+devkit 버전 선택 후 다운로드 (여러 gem과 C 확장모듈 포함) _jekyll 사용하려면 `gcc`나 `make`가 필요하므로 devkit 포함된 버전 추천_
    - github pages ruby version(2.7.3)과 동일하게 설치하는 것이 안전
    - ruby, gem 설치(버전) 확인
        ```
        ruby -v
        gem -v
        ```


2. jekyll 설치    
    ```
    gem install jekyll bundler
    ```
    - 참고: ruby versiondl 3.0.0 이상이면 dependency를 위해 `webrick` 필요
    ```
    bundle add webrick
    ```

## Jekyll 실행
1. jekyll 프로젝트 생성 (./myblog)
    ```bash
    jekyll new myblog
    cd myblog
    ```
    - 혹은, 이미 있는 지킬 테마 (깃헙 레포) clone 해오기
    ```bash
    git clone [git repo url]
    cd repo
    bundle update # 이미 프로젝트에 포함된 패키지들 버전 업데이트 의존성 해결
    ```
2. local server에서 사이트 빌드하기
    ```bash
    bundle exec jekyll serve
    ```
    - http://localhost:4000 접속



## 정리
- github pages: `웹호스팅` (**배포**)
- github pages는 jekyll로 작동
- `jekyll`: `markdown or html/css -> site 전환`, 블로그 만들기 편하다 (**개발**)
- `jekyll`은 RubyGem (ruby로 개발된 라이브러리)
- `gem`은 ruby에서 지원하는 패키지 시스템 (node의 `npm`과 같은 역할)

---

### Refernce
- jekyll 공식 사이트: https://jekyllrb-ko.github.io/
- ruby installation in w10: https://junstar92.tistory.com/5
- https://shryu8902.github.io/jekyll/jekyll-on-windows/