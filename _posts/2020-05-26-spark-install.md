---
layout: post
title: Spark 설치(mac)
subtitle : 
tags: [spark]
author: sunsoo Kim
comments : False
---


## Apache Sparck 설치

mac 유저라면 homebrew 사용하여 설치 가능

우선 scala 설치

```
-> brew search scala

==> Formulae
scala ✔         scala@2.11      scala@2.12      scalaenv        scalapack       scalariform     scalastyle
==> Casks
homebrew/cask/scala-ide

-> brew install scala
```

그리고 spark 설치


```
-> brew search spark

==> Formulae
apache-spark                          spark                                 sparkey
==> Casks
homebrew/cask/spark

-> brew install apache-spark
```

설치 확인

```
-> brew list | grep spark

apache-spark
```

버젼 확인

```
-> brew info apache-spark

apache-spark: stable 2.4.5, HEAD
Engine for large-scale data processing
https://spark.apache.org/
/usr/local/Cellar/apache-spark/2.4.5 (1,059 files, 250.9MB) *
  Built from source on 2020-05-27 at 10:15:09
From: https://github.com/Homebrew/homebrew-core/blob/master/Formula/apache-spark.rb
==> Requirements
Required: java = 1.8 ✔
==> Options
--HEAD
        Install HEAD version
==> Analytics
install: 4,507 (30 days), 15,472 (90 days), 62,046 (365 days)
install-on-request: 4,451 (30 days), 15,201 (90 days), 60,617 (365 days)
build-error: 0 (30 days)

```

환경 변수에 추가(.bashrc / .zshrc)

```
-> vi ~/.bashrc

export SPARK_HOME=/usr/local/Cellar/apache-spark/2.4.5/libexec
export PATH=$PATH:$SPARK_HOME
```


spark-shell 실행

```
-> spark-shell
```

오류 발생 
Service 'sparkDriver' could not bind on a random free port.

```
WARN Utils: Service 'sparkDriver' could not bind on a random free port. You may check whether configuring an appropriate binding address.
```

해결방법

```
sudo hostname -s 127.0.0.1
```

다시 실행해 보면 

웰컴투 스파크~!!

```
Welcome to
    ____              __
   / __/__  ___ _____/ /__
  _\ \/ _ \/ _ `/ __/  '_/
 /___/ .__/\_,_/_/ /_/\_\   version 2.4.5
    /_/
         
Using Scala version 2.11.12 (OpenJDK 64-Bit Server VM, Java 14.0.1)
Type in expressions to have them evaluated.
Type :help for more information.
```






