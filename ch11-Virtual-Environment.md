# 11. Virtual Environment

`virtualenv`에 대해 들어본 적 있으신가요? 여러분이 만약 입문자라면 들어보지 못했을 수도 있고, 경험자라면 사용하는 도구 중에서 매우 중요한 도구일 것입니다. 

그래서 `virtualenv`은 무엇일까요? `virtualenv`은 분리된 가상의 파이썬 환경을 만들어주는 툴입니다.  애플리케이션 하나에서는 버전 2가, 나머지에는 version 3이 필요한 애플리케이션을 가지고 있다고 생각 해보세요. 어떻게 이 애플리케이션을 사용과 개발 모두 할 수 있을까요?

만약 이 모든 것들을 `/usr/lib/python2.7/site-packages`\(여러분의 플랫폼의 기본 저장소가 어딘가\)에 설치했다고 생각해보세요.  
그러면 여러분이 업그레이드 해서는 안되는 패키지를 원치않게 업그레이드 할 가능성이 정말 높습니다. 또 다르게 사용하고 있는 라이브러에 변화가 없길 원하도록 이미 애플리케이션을 개발해 놓은 동시에, 업그레이드가 필요한 라이브러리를 사용하는 다른 애플리케이션을 개발해야한다고 생각해보세요.   
그렇다면 어떻게 해야할까요? 이 시점이 `virtualenv`을 사용해야할 때입니다. 파이썬 애플리케이션을 분리된 환경에서 생성해주고,  
각 라이브러리들을 전역적인 환경이 아니라 분리된 환경에 설치할 수 있도록 도와줍니다.

설치하기 위해서는 터미널에서 간단하게 아래와 같이 치면 됩니다:

```
  $ pip install virtualenv
```

그리고 `virtualenv`의 명령어 몇 개를 적어보겠습니다. 가장 중요한 것은 바로,

```
  $ virtualenv myproject
  $ source bin/activate
```

첫번째 명령은 `myproject`폴더 안에 분리된 가상환경을 생성하는 것이고, 두번째 명령어는 분리된 가상환경을 실행시킵니다. 첫번째 명령을 실행하는 동안 가상환경을 작동시킬 지 결정해야 합니다.

여러분 시스템 안의 `site-packages` 에 있는 패키지들을 사용하고 싶다거나, 여기 있는 패키지들을 virtualenv의 `site-packages`에 설치하고 싶지는 않나요?  
기본적으로는 `virtualenv` 안에서 패키지들을 설치할 때, 여러분 시스템의 `site-packages`에 설치되어 있다면, 이 패키지를 동기적으로 링크시킵니다. 만약 여러분이 완전히 분리된 `virtualenv`를 만들고 싶다면 아래와 같이 하시면 됩니다. 

이를 위해서는 `virtualenv`를 만들때, 아래와 같이 `no-site-packages` 로 바꾸어서 실행시키면 됩니다.

```
  $ virtualenv --no-site-packages mycoolproject
```

자 이제 여러분은 그 어떤 라이브러리도 전역 라이브러리나 라이브러리나 다른 환경에 영향을 끼치지 않고 설치할 수 있습니다.   
가상환경을 종료하고 싶다면, 아래와 같은 방법으로 종료할 수 있습니다.

```
  $ deactivate
```

##### 추가 팁

여러분은 bash나 zsh를 위한 라이브러리 `smartcd`을 사용해서 폴더를 변경함과 동시에 여러분의 다른 bash\(혹은 zsh\) 가상환경을 만들 수 있습니다.  
폴더를 변경할 때 `virtualenv`을 activate와 deactivate 해주기 때문에 편합니다. 필자는 이것을 많이 사용하고 좋아합니다. [github](https://github.com/cxreg/smartcd)에서 더 많은 정보를 얻을 수 있습니다.

`virtualenv`에 대한 간단한 소개글이었고 이 외에도 정말 많이 있습니다. 더 알아보고 싶다면 이 [링크](http://docs.python-guide.org/en/latest/dev/virtualenvs.html)를 추천드립니다. `virtualenv`에 대해 헷갈리는 부분들을 많이 해결 해 줄 것입니다.
