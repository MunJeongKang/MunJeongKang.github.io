---
title: macOS 업그레이드 후 에러
author: Munjeong Kang
date: 2020-03-29 23:00:08 +0800
categories: [Memo, error]
tags: [error]
toc: true
comments: true
---

macOS로 모하비를 사용하고 있었는데 이 때는 모든 명령어가 잘 작동했었다. (지킬이나 깃 등)

그러나 카탈리나로 버전을 업데이트 했더니 홈페이지를 실시간으로 확인하는 명령어가 작동하지 않았다.. 

{% highlight python%}
bundle exec jekyll serve
{% endhighlight %}

bundel을 install 하라는 명령이 나오는데 이 또한 에러가 뜬다. ㅜㅜ

git 명령어 또한 작동하지 않고 다음과 같은 에러가 뜬다. 

{% highlight ruby%}
xcrun: error: invalid active developer path (/Library/Developer/CommandLineTools), missing xcrun at: /Library/Developer/CommandLineTools/usr/bin/xcrun
{% endhighlight %}

에러를 고치기 위해 구글링 해보니 맥 OS 업데이트 후 이와 같은 에러가 많이 발생하는 것 같다. 

이 경우 다음과 같이 XCode를 재설치하면 보통 해결된다고 한다. 

{% highlight ruby%}
xcode-select --install
{% endhighlight %}

XCode 재설치 후 bundle install을 하니 잘 작동한다. 
