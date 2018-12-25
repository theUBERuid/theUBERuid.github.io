---
layout: post
title: "Git 블로그 시작하기"
description:
headline:
modified: 2018-12-12
category: git
tags: [git, github, jekyll]
imagefeature:
mathjax:
chart:
comments: true
featured: true
---

# {git 블로그 :zap:시작하기}

#### :mag_right: 목차

1. [GitHub pages 장점](#GitHub-pages-장점)
1. [git 설치](#git-설치)
1. [git 명령어](#git-명령어)
1. [GitHub에서 간단하게 사이트 만들기](#GitHub에서-간단하게-사이트-만들기)
1. [jekyll을 사용하여 블로그 만들기](#jekyll을-사용하여-블로그-만들기)
1. [GitHub를 이용한 블로그](#GitHub를-이용한-블로그)
1. [참고 사이트](#참고-사이트)

## :thumbsup: GitHub pages 장점

|  | 구축형 (Wordpress) | 가입형 (Tistory) | GitHub Pages |
|:--:|:--:|:--:|:--:|
| 비용 | 유료(서버) | 무료 | 무료 |
| 서버 구축 | 필요함 | 필요없음 | 필요없음 |
| 네트워크 설정 | 필요함 | 필요없음 | 필요없음 |
| Markdown | 가능 | 불가능(제한적) | 가능 |
| HTML 편집 | 가능 | 불가능(제한적) | 가능 |

> Markdown이란?<br><br>
> 마크다운은 HTML 보다 더 빨리 입력할 수 있고, 배우는데 드는 시간도 적으며 일반적인 글자 서식을 적용하는데 사용할 수 있다. 기울이기, 인용문 넣기, 여러 수준의 제목 추가(h1, h2, h3...), 숫자/글 머리 기호 목록 작성, 취소선 긋기 같은 서식들. URL 링크, 이메일 링크, 이미지, 주석과 주석 링크, 간단한 표를 넣는데도 사용 가능하다.<br><br>
> 마크다운은 지원하는 환경이라면 어디서든 쓸 수 있으며 복사해서 옮겨도 서식이 깨지지 않는다.

## :cd: git 설치

>[Git](https://git-scm.com/)

## :computer: git 명령어

#### 최초 설정(필수)

	$ git config --global user.name 'user name'
	$ git config --global user.email 'user.email@example.com'

#### 기본 명령어

|  | command |
|-|-|
| 전체 설정 확인 |  `git config --global -l` |
| 저장소 url 변경 |  `git remote set-url <name> <url>` <br> `git remote set-url origin https://github.com/theUBERuid/theUBERuid.github.io.git` |
| 상태 확인 |  `git status` |
| 파일을 추적 대상에 등록 |  `git add <file name>` <br> `git add index.html`|
| 파일을 추적 대상에 등록(전체) |  `git add .` |
| 커밋 |  `git commit -m '<commit message>'` <br> `git commit -m 'first commit'`|
| 서버에 업로드 |  `git push <repogitory> <branch>` <br> `git push origin master` |
| 서버에서 다운로드 |  `git clone <repository> <directory>` <br> `git clone https://github.com/theUBERuid/theUBERuid.github.io.git theUBERuid`|
| 변경 이력 보기 |  `git log` |


>[누구나 쉽게 이해할 수 있는 Git](https://backlog.com/git-tutorial/kr/)



## :book: jekyll을 사용하여 블로그 만들기

#### jekyll?

- 위에서 거론된 Markdown 포맷을 지원하기 위해서 GitHub에서는 [Jekyll(:kr:)](https://jekyllrb-ko.github.io/)라는 정적 사이트 생성기(Static Site Generator)를 사용한다.
- Markdown 문법으로 작성된 파일을(*.md) 정적 사이트 생성기가 알아서 HTML로 바꾸어 준다.

> **정적**이라는 단어는 그 동안에 웹 어플리케이션이 발전해 온 데 있어서 **정반대**의 위치에 있는 단어다.<br>
> **정적인 페이지**란 말그대로 이미 **완성된 HTML**이다. 클라이언트의 요청을 받는 서버의 역할은 단순히 이렇게 완성되어 있는 HTML을 보내주는 역할을 할 뿐이다. 이러한 모델은 **우편부**를 통해서 비유하기에 아주 적절하다.<br>
> 그렇다면 웹이 **동적**으로 발전해왔다는 건 어떤 걸 의미할까?<br>
> 여기서 **동적**이란 화려한 **시각적 효과**나 **움직임**을 지칭하는 단어가 **아니다**. 좀 더 정확히 말하자면 **HTML 페이지**를 클라이언트의 요청에 따라서 **실시간으로 생성해서 보내준다**는 의미를 가지고 있다. 즉 **서버는 완성된 HTML을 가지고 있지 않다**. 거의 완성되어있거나, 심지어는 아무것도 없이도 **요청에 따라 실시간으로 완성된 문서**를 다시 보내준다.

> [정적 웹사이트 생성기의 역습 - 동적 스크립트를 넘어 다시 정적 컨텐츠로](https://blog.nacyot.com/articles/2014-01-15-static-site-generator/)



#### 구조

가장 기본적인 Jekyll 사이트 구조

```sh
├── _config.yml
├── _data
|   └── members.yml
├── _drafts
|   ├── begin-with-the-crazy-ideas.md
|   └── on-simplicity-in-technology.md
├── _includes
|   ├── footer.html
|   └── header.html
├── _layouts
|   ├── default.html
|   └── post.html
├── _posts
|   ├── 2007-10-29-why-every-programmer-should-play-nethack.md
|   └── 2009-04-26-barcamp-boston-4-roundup.md
├── _sass
|   ├── _base.scss
|   └── _layout.scss
├── _site
├── .jekyll-metadata
└── index.html
```

#### 포스팅하기

##### 1. 파일 생성

- 파일 이름 `_posts/YYYY-MM-DD-name-of-post.md`
- 기본 문법 MARKDOWN(*.md)

##### 2. 머리말 설정

- 머리말 설정

```markdown
---
layout: post
title: "Welcome to Jekyll!"
date: 2018-12-25 16:16:01 -0600
categories: jekyll update
---
```

##### 3. 본문 작성

- 마크다운을 이용해서 본문 작성

```markdown
# 제목

## 부제목

- 내용 A
- 내용 B
- 내용 C

[링크제목](https://링크주소.com/)
```

> [jekyll themes download](http://jekyllthemes.org/)

## :earth_americas: GitHub를 이용한 블로그

> [theUBERuid.github.io](https://theUBERuid.github.io)

> [kakao 기술 블로그](http://tech.kakao.com/)

> [우아한형제들 기술 블로그](http://woowabros.github.io/)

## :link: 참고 사이트

> [누구나 쉽게 이해할 수 있는 Git](https://backlog.com/git-tutorial/kr/)

> [윈도우에서 지킬 설치 및 블로그 생성하기](https://shryu8902.github.io/jekyll/jekyll-on-windows/)

> [정적 웹사이트 생성기의 역습 - 동적 스크립트를 넘어 다시 정적 컨텐츠로](https://blog.nacyot.com/articles/2014-01-15-static-site-generator/)