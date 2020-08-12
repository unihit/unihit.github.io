---
layout: post
title: How to make github Blog
date: 2020-08-12
excerpt: "Jekyll 테마를 이용해서 github 블로그를 만드는 방법"
tags: [sample post, blog, github.io, theme]
comments: true
---

## github 블로그를 시작하기 전에..

---

여기서는 jekyll의 테마를 이용해서 github 블로그를 제작하는 방법을 서술한다.

먼저 아래의 링크에서 자신이 마음에 드는 블로그의 테마를 선택한다.

선택할 때 유의해야 할 점은 해당 테마를 고르고 License를 봤을 때 웬만해서는 License가 MIT License인 것을 고르는 것이 좋다는 것이다. (여러모로 귀찮은 일에 걸릴 일이 없는 License라고 생각하자)

[Jekyll Themes](http://jekyllthemes.org/)

마음에 드는 jekyll 테마를 골랐고 License가 MIT인 테마를 골랐다면, 다운로드 버튼을 눌러 해당 테마를 다운로드 받자.

그리고 github에 들어가 로그인 한 뒤에 repository를 만들자.

repo name을 지을 때 닉네임.github.io로 만들어야 한다.

Description을 자유롭게 작성하고 public에 체크, initialize this repository with a README 항목도 체크해서 Create repository 버튼을 누르자.

repo가 생성되었다면, 이제 닉네임.github.io이 URL이 되어 브라우저 상단에 입력하면 자신의 블로그에 접속할 수 있게 된다. (아직은 repo만 만들었기 때문에 텅 비어있을 것이다.) 

## github블로그를 git clone해와 local repo를 만들어 유지보수하기

---

우선 자신의 C드라이브나 D드라이브의 여유공간이 남는 곳에 local repo를 만들 것이다.

폴더명을 마음대로 짓고 cmd를 이용해서 `cd`명령어로 해당 폴더로 이동하자.

github의 자신이 만든 블로그의 repo로 이동하면 code라고 초록색 버튼이 보일 것이다.

초록색 버튼을 누르고 Clone with HTTPS 항목의 클립보드 아이콘을 누르거나 URL을 복사해둔다.

cmd로 해당 폴더로 이동한 명령줄에서 `git clone` 명령을 입력해 해당 폴더로 clone해온다.

```
git clone https://github.com/닉네임/닉네임.github.io.git
```

지금은 만든 항목이 없어서 README.md밖에 없을 것이다.

## Ruby 설치하기

---

이제 윈도우즈에 Ruby를 설치해보자.

[Ruby Installer](https://rubyinstaller.org/downloads/)

해당 링크로 들어가서 Ruby를 다운로드 받는다.

자신의 환경에 맞는 것으로 다운로드 받는데, With DEVKIT이라고 적혀있는 항목에서 다운로드 받도록 하자.

다운로드가 완료되고 

![최근에 추가된 앱](https://user-images.githubusercontent.com/40714505/89969635-e2b36e00-dc91-11ea-8905-00234909701f.png)

windows 버튼을 누르고 최근에 추가된 앱 항목을 살펴보면 Start Command Prompt with Ruby 항목이 보일텐데 이를 클릭해 실행한다.

실행하면 다음과 같은 화면이 보일 것이다.

![ruby install](https://user-images.githubusercontent.com/40714505/89969649-ed6e0300-dc91-11ea-9950-01e27d21ae12.PNG)

해당 항목이 보이면 1을 누르고 Enter를 눌러서 설치를 완료하도록 하자.

설치가 완료되면 네모칸이 뜨면서 항목이 보일텐데 무시하고 그냥 끄고 재시작한다.

재시작하면 Ruby 프롬프트가 보일 것이다. (>)

여기서 `cd`명령어를 이용해서 자신이 설치한 폴더로 이동한다.

## Jekyll 테마 적용하기

---

다운로드 받아놨던 테마의 압축을 풀고, 폴더 안의 내용물을 전부 자신이 clone했던 폴더의 경로로 이동시킨다. (README.md가 있는 폴더)

### Ruby를 이용해 jekyll 서버를 만들어 로컬 호스트에서 블로그 미리보기

실행시켜 놓았던 Start Command Prompt with Ruby로 이동해서 아래의 명령어를 입력한다.

```ruby
gem install jekyll
gem install bundler
```

두 개의 프로그램 설치가 완료되면, 아래의 명령어를 입력한다.

```ruby
jekyll server
```

서버를 구동했을 때 아래와 같은 텍스트가 출력되면 서버가 돌아가고 있는 것이다.

```
Server address: http://127.0.0.1:4000/
Server running... press ctrl-c to stop.
```

서버는 자신의 로컬호스트의 4000번 포트로 접속할 수 있다.

[localhost](http://localhost:4000/)

위와 같은 방법으로 jekyll server에 자신의 블로그를 올려서 github에 clone하기 전에 변경사항을 미리 확인할 수 있다.

이제 _config.yml 파일을 수정해서 블로그의 대문을 수정하거나, _posts폴더에 md파일을 만들어 블로그에 포스팅을 해주고 jekyll server로 github에 commit하기 전에 확인할 수 있다!

## 팁

---

테마 설정을 하다 꼬였을 때 가끔씩 Gem::LoadError가 뜨는데 이는

```
bundle clean --force
```

해당 명령어를 사용해 bundle을 clean해주면 잘 작동하게 된다.

repo에 푸시하고 블로그에 적용되는데 시간이 좀 걸릴 수 있으니 기다려보자.