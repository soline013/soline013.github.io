---
layout: post
title: Github Blog
subtitle: Github Blog를 만들고, Jekyll을 사용하는 방법을 적어두었습니다.
comments: true
categories: ETC
---

# Github Blog

Github Blog를 만들고, Jekyll을 사용하는 방법을 적어두었습니다.

Mac을 기준으로 작성되었습니다.

## Ruby.

맥에는 기본적으로 Ruby가 설치되어 있다.

맥에 기본으로 설치된 Ruby는 버전이 낮고, 업데이트시 문제가 발생할 수 있다.

따라서 rbenv를 사용하여 Ruby의 버전을 관리하는 것이 좋다.

```powershell
#ruby의 버전을 확인한다.
ruby -v

#brew로 rbenv를 설치한다.
brew install rbenv ruby-build

#zsh를 사용하는 경우, zshrc에 rbenv PATH를 추가한다. vol.1.
echo 'export RBENV_ROOT="$HOME/.rbenv"' >> ~/.zshrc
echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.zshrc
source ~/.zshrc

#zsh를 사용하는 경우, zshrc에 rbenv PATH를 추가한다. vol.2.
vim ~/.zshrc

[[ -d ~/.rbenv  ]] && \
  export PATH=${HOME}/.rbenv/bin:${PATH} && \
  eval "$(rbenv init -)"

source ~/.zshrc

#설치 가능한 버전을 확인한다.
rbenv install -l

#원하는 버전을 설치하고, 해시를 재정렬한다.
rbenv install 3.0.2
rbenv rehash

#global, local을 설정한다.
rbenv global 3.0.2
rbenv local 3.0.2

#rbenv로 설치한 ruby 버전을 확인한다.
rbenv versions
```

### Jekyll.

```powershell
#jekyll, bundler gem을 설치한다.
gem install jekyll bundler

#jekyll을 생성한다.
jekyll new ./

#bundle을 설치한다.
bundle install

#jekyll을 로컬 서버에 띄운다.
bundle exev jekyll serve

#`require': cannot load such file -- webrick (LoadError) 해결.
#Ruby 3.0.0부터 webrick이 기본 gem에서 제외되었기 때문에 발생한다.
bundle add webrick
```

`_config.yml` : 전역 환경설정 파일.

`_layouts` : 기본 레이아웃.

`_post` : Post를 저장하는 곳. YYYY-MM-DD-TITLE.md 형식을 지켜야 한다.

`_site` : Generate 된 블로그가 위치하는 곳.

`css` : main.css, syntax.css

`index.html` : 블로그 초기 페이지.

jekyll은 assets 폴더 밑의 파일들을 리소스로 활용한다.

### _config.yml

jekyll에서 많은 설정을 변경할 수 있는 파일.

## Link.

[Downloads](https://rubyinstaller.org/downloads/)