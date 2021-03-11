---
title: matplotlib 한글 깨짐 & mac, windows에 따른 환경설
date: 2021-03-11 20:11:00 +0900
categories: [Develop&Tech, Python]
tags: [code_tip]     # TAG names should always be lowercase
toc: True
---

```python 
from matplotlib import font_manager, rc
import platform


# 운용체제 환경에 따라 글꼴 선택.
osSelect = platform.system()
if osSelect == 'Windows':
    font_name = font_manager.FontProperties(fname="c:/Windows/Fonts/malgun.ttf").get_name()
    rc('font', family=font_name)
elif osSelect == 'Darwin':
    rc('font', family='AppleGothic')
plt.rcParams['axes.unicode_minus'] = False
```
