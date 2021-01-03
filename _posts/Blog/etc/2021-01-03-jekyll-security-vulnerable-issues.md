---
title: jekyll blog nokogiri 보안 이슈
date: 2021-01-03 11:00:00 +0900
categories: [Blog, etc]
tags: [gitblog, jekyll, security]     # TAG names should always be lowercase
toc: True
---

루비 위에서 동작하는 jekyll 블로그의 루비라이브러리 중 nokogiri 1.10.10의 보안 이슈가 발견되어 github의 jekyll blog build를 실패했습니다.

![image](https://user-images.githubusercontent.com/19174106/103470402-49f2cb80-4db5-11eb-81a1-20521ab2764f.png)
위와 같이 종속성에 잠재적 보안 취약성을 발견했다고 github Actions에서 빌드를 실패 시켰습니다.

see dependabot alert을 클릭하면 해결방법이 나옵니다.

Gemfile의 nokogiri를 1.11.0.rc4버전으로 설치하도록 명시해주면 됩니다.

```
gem "nokogiri", ">= 1.11.0.rc4"
```

gemfile에는 위와 같이 입력하고 terminal에서 `bundle update`를 실행시켜주면, Gemfile.lock에서 버전이 바뀐걸 확인하실수 있습니다.

그럼에도 Gemfile.lock이 바뀌지 않거나 오류가 계속 발생한다면, 강제로 해당 라이브러리를 버전업해야 합니다.

[nokogiri 다운로드 페이지에 가면](https://rubygems.org/gems/nokogiri) install 커멘드가 나와 있습니다.

```
gem install nokogiri -v 1.11.0.rc4 --pre
```
위와 같이 설치하고, 다시 빌드해보면 대부분 Gemfile.lock에 nokogiri가 `nokogiri (1.11.0.rc4-x86_64-darwin)`이렇게 변경 될 것 입니다.

이제 정상적으로 빌드를 수행해서 신규 컨텐츠를 올리실 수 있습니다.

