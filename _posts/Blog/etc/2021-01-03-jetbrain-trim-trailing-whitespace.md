---
title: webstorm(jetbrain) 후행 공백 제거
date: 2021-01-03 20:00:00 +0900
categories: [Blog, etc]
tags: [gitblog, jekyll, security]     # TAG names should always be lowercase
toc: True
---

### 문제 발생

md 파일 작성하고 줄바꿈을 위해 행마지막에 공백2개를 추가해야 합니다.  
현재 블로그를 webstorm에서 작성하는데 jetbrain류 IDE에서는 후행 공백을 제거하는 설정이 있습니다.
IDE 설정에서 후행 공배 제거하지 않도록 해야 합니다.

### 문제 해결

#### 1. 간단 설정
`Preferences` - `General` - `On Save`에서 `Remove trailing spaces on`을 체크 해줘야 합니다.
혹은 드롭다운에서 `None`으로 변경해 줄 수 있습니다.   

![image](https://user-images.githubusercontent.com/19174106/103477326-248baf00-4e01-11eb-8126-c0dbaa6a9890.png)

#### 2. `.editorconfig` 설정 수정
   
![image](https://user-images.githubusercontent.com/19174106/103477380-c14e4c80-4e01-11eb-8f0c-21ed811cce37.png)

파일 목록에 `.editorconfig` 설정에 들어갑니다.
![image](https://user-images.githubusercontent.com/19174106/103477395-eba00a00-4e01-11eb-962a-d4fceecb212e.png)

`trim_trailing_whitespace`를 `false`로 변경하고 에디터를 종료 후 재실행합니다.

 2번 해결 출처 : https://github.com/nicoulaj/idea-markdown/issues/138
