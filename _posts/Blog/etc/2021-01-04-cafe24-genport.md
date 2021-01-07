---
title: cafe24서버에서 젠트레이더 구동 
date: 2021-01-03 20:00:00 +0900
categories: [Blog, etc]
tags: [cafa24, genport]     # TAG names should always be lowercase
toc: True
---
# Cafe24 서버 생성 및 젠트레이더 구동방법

## 목차
1. [cafe24 호스팅 가입](#sector1)
2. [윈도우용 가상서버 호스팅 신청하기](#sector2)
3. [원격 데스트톱 설정 방법](#sector3)
4. [기본 설정 및 공인인증서 설치를 위한 과정](#sector4)
5. [오픈 api 설치](#sector4)
6. [젠트레이더 설치 및 구동](#sector4)
7. [기타 추가 설치 및 설정](#sector4)
8. [자주 묻는 질문](#sector4)

---

<a name="sector1"></a>
## 1. cafe24 호스팅센터 가입

<img src="https://user-images.githubusercontent.com/19174106/103838105-90a33700-50cf-11eb-800f-37d9cef2664f.png" width="100%">

- cafe24 호스팅센트 URL : [https://hosting.cafe24.com/](https://hosting.cafe24.com/)  
- cafe24 호스팅센터에 접속하여 회원가입합니다.
   
---

<a name="sector2"></a>
## 2. 윈도우용 가상서버 호스팅 신청하기

### 2.1. 서버 방식 선택

<img src="https://user-images.githubusercontent.com/19174106/103838553-b54bde80-50d0-11eb-9b1c-f9b23a1647fd.png" width="100%">

- 페이지 상단 탭에서 `가상서버호스팅` 클릭합니다.

---

### 2.2. 윈도우 가상서버 일반형 신청하기

<img src="https://user-images.githubusercontent.com/19174106/103838778-41f69c80-50d1-11eb-9866-bb730b67d536.png" width="100%">

1. 왼쪽 탭에서 가상서버호스팅의 `윈도우용` 클릭합니다.  
2. 일반형 서비스 `신청하기` 클릭합니다.

---

### 2.3. 서버 관리용 개별 아이디 등록

<img src="https://user-images.githubusercontent.com/19174106/103840140-4a040b80-50d4-11eb-8f95-505969ab06e9.png" width="100%">

1. 처음 회원가입 하셨다면, 신규 아이디를 등록합니다.
2. 개별 서버를 관리하기 위한 각각의 아이디를 생성해야 합니다.

---

### 2.4. 세부정보 입력

<img src="https://user-images.githubusercontent.com/19174106/103867046-0deb9d80-510a-11eb-9dda-11e82b263707.png" width="100%">

- `임시 administrator 비밀번호`는 원격 접속할 때 필요하오니 꼭 기억해주시기 바랍니다.
- 나머지 세부정보를 모두 입력한 뒤 다음을 클릭합니다.

---

### 2.5. 서비스 기간 선택 및 청구가격

<img src="https://user-images.githubusercontent.com/19174106/103840494-01008700-50d5-11eb-9707-a2b4f3438eee.png" width="100%">

<center>
<div markdown="1">

| 기간 | 할인율 | 사용료 | 설치비 | 합계 |  
|:---:|:---:|:---:|:---:|:---:|  
| 1개월 | - | 16,500원 | 22,000원 | 38,500원 |
| 3개월 | - | 49,500원 | 22,000원 | 71,500원 |
| 6개월 | 5% | 94,050원 | 22,000원 | 116,050원 |
| 1년 | 10% | 178,200원 | 22,000원 | 200,200원 |
| 2개월 | 12% | 348,480원 | 22,000원 | 370,480원 |
| 3개월 | 15% | 504,900원 | 22,000원 | 526,900원 |

윈도우 가상서버 기간별 비용 정리

</div>
</center>

- 사용할 기간을 선택해 줍니다.

---
### 2.6. 결제하기

<img src="https://user-images.githubusercontent.com/19174106/103841099-3194f080-50d6-11eb-908e-c43b569b6bcb.png" width="80%">

- DB옵션은 선택하지 않고, 결제 수단을 선택하여 `결제`합니다.


---
<a name="sector3"></a>
## 3. 원격 데스트톱 설정 방법

### 3.1.cafe24 호스팅센터의 나의 서비스 관리 

<img src="https://user-images.githubusercontent.com/19174106/103854403-b17d8380-50f3-11eb-92de-ebd98c16f7ce.png" width="100%">

- 메인 화면에서 `나의 서비스 관리`-`서비스 사용현황`을 클릭합니다.

---

### 3.2. 서버 IP 알아내기

<img src="https://user-images.githubusercontent.com/19174106/103858723-34a2d780-50fc-11eb-9de3-4f945d23a564.png" width="100%">

- 윈도우 원격 접속하기 위한 IP 주소를 알아냅니다.   
  (해당 아이피를 통해 원격 접속을 하게 됩니다.)
   
---
   
### 3.3. 원격 데스크톱 설정

<img src="https://user-images.githubusercontent.com/19174106/103859712-decf2f00-50fd-11eb-970e-aa17216a0460.png" width="70%">

- 원격으로 접속하는 소프트웨어를 원격 데스크톱 클라이언트라고 합니다. 클라이언트 소프트웨어는 여러 가지가 있습니다. 
- 윈도우 10이라면 `원격 데스크톱 연결` 앱으로 접속할 수 있습니다.
- `윈도우 키`를 누르고 '원격 데스크톱 연결'으로 검색하면 해당 앱이 나타나고, 클릭해줍니다.

---

<img src="https://user-images.githubusercontent.com/19174106/103860009-62891b80-50fe-11eb-8ee1-05b222ae930d.png" width="70%">

- `원격 데스크톱 연결`앱이 실행되었다면, 좌측 하단 `옵션 표시(O)`를 클릭합니다.

---

<img src="https://user-images.githubusercontent.com/19174106/103860484-096db780-50ff-11eb-9912-6f46d5cb738a.png" width="70%">

1. `컴퓨터(C)`에는 Cafe24에서 알아낸 IP를 입력합니다.  
   `사용자 이름`에는 `administrator` 입력합니다.
2. `자격 증명 저장 허용(R)`를 체크합니다.
3. 접속의 편의성을 위해 입력한 정보를 파일로 저장하겠습니다. `다른 이름으로 저장(V)`를 클릭합니다.

---

<img src="https://user-images.githubusercontent.com/19174106/103864249-9ca9eb80-5105-11eb-94c1-2ba896173365.png" width="70%">

- 적절한 위치에 저장합니다.

---

<img src="https://user-images.githubusercontent.com/19174106/103864259-a03d7280-5105-11eb-9b95-07aff47abfb5.png" width="70%">

- 저장된 `원격 데스크톱 앱`을 실행합니다.

---

<img src="https://user-images.githubusercontent.com/19174106/103860887-cfe97c00-50ff-11eb-96de-23990b6cb877.png" width="70%">

<img src="https://user-images.githubusercontent.com/19174106/103867714-29a37380-510b-11eb-8b9f-82ac64bbbcb2.png" width="60%">

- 관리 아이디를 등록 할 때 작성 했던 `임시 administrator 비밀번호`를 입력 후 `확인버튼`을 클릭합니다.

---

<img src="https://user-images.githubusercontent.com/19174106/103862399-628b1a80-5102-11eb-99a2-7a8ee94cd1c7.png" width="70%">

- 재확인 팝업이 뜰 경우 `이 컴퓨터로의 연결을 다시 묻지 않음(D)` 옵션을 체크 해 주시고 `예(Y)`버튼을 클릭합니다.

---

<a name="sector4"></a>
## 4. 기본 설정 및 공인인증서 설치를 위한 과정
