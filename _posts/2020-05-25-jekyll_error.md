---
layout: post
title: Jekyll FilePermissionError
subtitle : 
tags: [jekyll]
author: sunsoo Kim
comments : False
---


```
gem install bundler jekyll

bundle exec jekyll serve
```


-> 

FilePermissionError

![error](https://user-images.githubusercontent.com/45762604/82772073-02987a00-9e79-11ea-9208-6b475af83248.png)

이유는 시스템 ruby를 이용하고 있기 때문에 권한이 없어 gem 설치가 안된 것입니다.


->

해결 방법
```
brew install rbenv ruby-build

rbenv install 2.6.5 

rbenv global 2.6.5

rbenv versions

```

 rbenv PATH를 추가하기 위해 본인의 쉘 설정 파일 (..zshrc, .bashrc)에 추가

```
vi ~/.bashrc
```

```
export PATH={$Home}/.rbenv/bin:$PATH && \
eval "$(rbenv init -)"
```

터미널 재시작 또는 다음 명령어 입력 합니다.
```
source ~/.bashrc
```

다시 gem install을 실행 합니다. 

```
gem install bundler
```
정상적으로 실행이 되면 깃블로그를 시작!!

```
bundle exec jekyll serve
```



->

![성공](https://user-images.githubusercontent.com/45762604/82772006-cfee8180-9e78-11ea-8b05-71b537d036b0.png)



