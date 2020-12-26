---
title: 마크다운(markdown)작성하면서 필요한 HTML 조합
date: 2020-12-26 20:10:00 +0900
categories: [Blog, etc]
tags: [Summary, Markdown, HTML]     # TAG names should always be lowercase
toc: True
---
## markdown + html technique

### 중앙정렬 + 강조
<center><strong>중앙 정렬 + 강조</strong></center>

```html
<center><strong></strong></center>
```
### 펼치기
<details>
<summary>python 코드 펼치기</summary>
<div markdown="1">
```python
python = "py"+"thon"
```
</div>
</details>

```html
<details>
<summary>c++ 코드 펼치기</summary>
<!-- markdown="1"은 jekyll에서 html 코드 내 markdown을 인식하기 위한 태그 -->
<div markdown="1">

</div>
</details>
```

### 다단
<div class="row">
  <div class = "col-md-6">
<center><strong>G1 = (V, E)</strong></center>
<center><strong>V(G1) = {A, B, C}</strong></center>
<center><strong>E(G1) = {(A, B), (B, C)}</strong></center>
  </div>
  <div class = "col-md-6">
<center><strong>G2 = (V, E)</strong></center>
<center><strong>V(G2) = {A, B, C}</strong></center>
<center><strong>E(G2) = {<A, B>, <B, C>}</strong></center>
  </div>
</div>

```html
<div class="row">
  <div class = "col-md-6">
<center><strong>G1 = (V, E)</strong></center>
<center><strong>V(G1) = {A, B, C}</strong></center>
<center><strong>E(G1) = {(A, B), (B, C)}</strong></center>
  </div>
  <div class = "col-md-6">
<center><strong>G2 = (V, E)</strong></center>
<center><strong>V(G2) = {A, B, C}</strong></center>
<center><strong>E(G2) = {<A, B>, <B, C>}</strong></center>
  </div>
</div>
```
