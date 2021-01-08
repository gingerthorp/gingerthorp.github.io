---
title: cafe24서버에서 젠트레이더 구동 
date: 2021-01-03 20:00:00 +0900
categories: [Blog, etc]
tags: [cafa24, genport]     # TAG names should always be lowercase
toc: True
---
# Cafe24 서버 생성 및 젠트레이더 구동방법

## 목차
1. [cafe24 호스팅 가입하기](#sector1)  
   
2. [윈도우용 가상서버 호스팅 신청하기](#sector2)  
   2.1. [서버 방식 선택](#sector2-1)  
   2.2. [윈도우 가성서버 일반형 신청하기](#sector2-2)  
   2.3. [서버 관리용 개별 아이디 등록하기](#sector2-3)  
   2.4. [세부정보 입력](#sector2-4)  
   2.5. [서비스 기간 선택 및 청구가격 확인](#sector2-5)  
   2.6. [Cafe24 서버 결제하기](#sector2-6)  
   
3. [원격 데스트톱 설정 방법](#sector3)  
   3.1. [Cafe24 호스팅센터의 나의 서비스 관리 접속하기](#sector3-1)  
   3.2. [서버 IP 알아내기](#sector3-2)  
   3.3. [원격 데스크톱 설정하기](#sector3-3)  
   
4. [기본 설정 및 공인인증서, OpenAPI, 젠트레이더 설치](#sector4)  
   4.1. [인터넷 익스플로러 보안 강화 해제](#sector4-1)  
   4.2. [필요한 페이지 url 다운로드 및 크롬 브라우저 설치](#sector4-2)  
   4.3. [키움증권 홈페이지에서 공인인증서 가져오기](#sector4-3)  
   4.4. [키움증권 Open API 설치하기](#sector4-4)  
   4.5. [젠트레이더 설치하기](#sector4-5)  
   
5. [젠트레이더 구동하기](#sector5)  
   5.1. [젠트레이더 실행 및 버전 처리](#sector5-1)  
   5.2. [젠트레이더 실행확인 및 오토스타터 설정](#sector5-2)  
   

6. [기타 추가 설치 및 설정](#sector6)
  6.1. 서버 재부팅 시 즉시 로그인 설정하기
  6.2. 원격 데스크톱 공격 방어1
  6.3. 원격 데스크톱 공격 방어2
  6.4. 시간 싱크 맞추기

7. [자주 묻는 질문](#sector7)
  7.1. cafe24 기간 연장하기
  7.2. cafe24 서버 여러개 이용하기
  7.3. 서버 접속 암호 변경하기

---

<a name="sector1"></a>
## 1. cafe24 호스팅센터 가입하기

<img src="https://user-images.githubusercontent.com/19174106/103838105-90a33700-50cf-11eb-800f-37d9cef2664f.png" width="100%">

- cafe24 호스팅센트 URL : [https://hosting.cafe24.com/](https://hosting.cafe24.com/)  
- cafe24 호스팅센터에 접속하여 회원가입합니다.
   
---

<a name="sector2"></a>
## 2. 윈도우용 가상서버 호스팅 신청하기
<a name="sector2-1"></a>
### 2.1. 서버 방식 선택

<img src="https://user-images.githubusercontent.com/19174106/103838553-b54bde80-50d0-11eb-9b1c-f9b23a1647fd.png" width="100%">

- 페이지 상단 탭에서 `가상서버호스팅` 클릭합니다.

---
<a name="sector2-2"></a>
### 2.2. 윈도우 가상서버 일반형 신청하기

<img src="https://user-images.githubusercontent.com/19174106/103838778-41f69c80-50d1-11eb-9866-bb730b67d536.png" width="100%">

1. 왼쪽 탭에서 가상서버호스팅의 `윈도우용` 클릭합니다.  
2. 일반형 서비스 `신청하기` 클릭합니다.

---
<a name="sector2-3"></a>
### 2.3. 서버 관리용 개별 아이디 등록하기

<img src="https://user-images.githubusercontent.com/19174106/103840140-4a040b80-50d4-11eb-8f95-505969ab06e9.png" width="100%">

1. 처음 회원가입 하셨다면, 신규 아이디를 등록합니다.
2. 개별 서버를 관리하기 위한 각각의 아이디를 생성해야 합니다.

---
<a name="sector2-4"></a>
### 2.4. 세부정보 입력

<img src="https://user-images.githubusercontent.com/19174106/103867046-0deb9d80-510a-11eb-9dda-11e82b263707.png" width="100%">

- `임시 administrator 비밀번호`는 원격 접속할 때 필요하오니 꼭 기억해주시기 바랍니다.
- 나머지 세부정보를 모두 입력한 뒤 다음을 클릭합니다.

---
<a name="sector2-5"></a>
### 2.5. 서비스 기간 선택 및 청구가격 확인

<img src="https://user-images.githubusercontent.com/19174106/103840494-01008700-50d5-11eb-9707-a2b4f3438eee.png" width="100%">

<center>
<div markdown="1">

| 기간 | 할인율 | 사용료 | 설치비 | 합계 |  
|:---:|:---:|:---:|:---:|:---:|  
| 1개월 | - | 16,500원 | 22,000원 | 38,500원 |
| 3개월 | - | 49,500원 | 22,000원 | 71,500원 |
| 6개월 | 5% | 94,050원 | 22,000원 | 116,050원 |
| 1년 | 10% | 178,200원 | 22,000원 | 200,200원 |
| 2년 | 12% | 348,480원 | 22,000원 | 370,480원 |
| 3년 | 15% | 504,900원 | 22,000원 | 526,900원 |

윈도우 가상서버 기간별 비용 정리

</div>
</center>

- 사용하실 기간의 비용을 확인하신 뒤 기간을 선택해 줍니다.

---
<a name="sector2-6"></a>
### 2.6. Cafe24 서버 결제하기

<img src="https://user-images.githubusercontent.com/19174106/103841099-3194f080-50d6-11eb-908e-c43b569b6bcb.png" width="80%">

- DB옵션은 선택하지 않고, 결제 수단을 선택하여 `결제`를 진행해 주시기 바랍니다.
- 결제를 완료하셨다면, 자동으로 `서비스 사용현황`페이지로 넘어가게 됩니다.


---
<a name="sector3"></a>
## 3. 원격 데스트톱 설정 방법
<a name="sector3-1"></a>
### 3.1.Cafe24 호스팅센터의 나의 서비스 관리 접속하기

<img src="https://user-images.githubusercontent.com/19174106/103854403-b17d8380-50f3-11eb-92de-ebd98c16f7ce.png" width="100%">

- `서비스 사용현황`으로 가기 위해 메인 화면에서 `나의 서비스 관리`-`서비스 사용현황`을 클릭합니다.

<img src="https://user-images.githubusercontent.com/19174106/103962173-a8df8880-5199-11eb-8688-c7453b4ae4d2.png" width="100%">

- 결제 이후 자동으로 OS가 설치되는데 약 15~30분 정도 소요됩니다.
- 설치가 완료되면, 가입 시 입력했던 핸드폰번호로 설치가 완료되었다는 문자가 수신됩니다.

---
<a name="sector3-2"></a>
### 3.2. 서버 IP 알아내기

<img src="https://user-images.githubusercontent.com/19174106/103858723-34a2d780-50fc-11eb-9de3-4f945d23a564.png" width="100%">

- OS 설치가 모두 완료되었다면, `서버 접속 정보`에 IP주소가 나타납니다.  
  (해당 아이피를 통해 원격 접속을 하게 됩니다.)
   
---
<a name="sector3-3"></a>
### 3.3. 원격 데스크톱 설정하기

<img src="https://user-images.githubusercontent.com/19174106/103859712-decf2f00-50fd-11eb-970e-aa17216a0460.png" width="70%">

- 원격으로 접속하는 소프트웨어를 원격 데스크톱 클라이언트라고 합니다. 클라이언트 소프트웨어는 여러 가지가 있습니다. 
- 윈도우 10이라면 `원격 데스크톱 연결` 앱으로 접속할 수 있습니다.
- 좌측 하단의 `윈도우 버튼`이나 키보드 상의`윈도우 키`를 누르고 '원격 데스크톱 연결'으로 검색하면 해당 앱이 나타나고, 클릭해줍니다.

<img src="https://user-images.githubusercontent.com/19174106/103860009-62891b80-50fe-11eb-8ee1-05b222ae930d.png" width="70%">

- `원격 데스크톱 연결`앱이 실행되었다면, 좌측 하단 `옵션 표시(O)`를 클릭합니다.


<img src="https://user-images.githubusercontent.com/19174106/103860484-096db780-50ff-11eb-9912-6f46d5cb738a.png" width="70%">

1. `컴퓨터(C)`에는 Cafe24에서 알아낸 IP를 입력합니다.  
   `사용자 이름`에는 `administrator` 입력합니다.
2. `자격 증명 저장 허용(R)`를 체크합니다.
3. 접속의 편의성을 위해 입력한 정보를 파일로 저장하겠습니다. `다른 이름으로 저장(V)`를 클릭합니다.


<img src="https://user-images.githubusercontent.com/19174106/103864249-9ca9eb80-5105-11eb-94c1-2ba896173365.png" width="70%">

- 적절한 위치에 저장합니다.


<img src="https://user-images.githubusercontent.com/19174106/103864259-a03d7280-5105-11eb-9b95-07aff47abfb5.png" width="70%">

- 저장된 `원격 데스크톱 앱`을 실행합니다.


<img src="https://user-images.githubusercontent.com/19174106/103860887-cfe97c00-50ff-11eb-96de-23990b6cb877.png" width="70%">

<img src="https://user-images.githubusercontent.com/19174106/103867714-29a37380-510b-11eb-8b9f-82ac64bbbcb2.png" width="60%">

- 관리 아이디를 등록 할 때 작성 했던 `임시 administrator 비밀번호`를 입력 후 `확인버튼`을 클릭합니다.


<img src="https://user-images.githubusercontent.com/19174106/103862399-628b1a80-5102-11eb-99a2-7a8ee94cd1c7.png" width="70%">

- 재확인 팝업이 뜰 경우 `이 컴퓨터로의 연결을 다시 묻지 않음(D)` 옵션을 체크 해 주시고 `예(Y)`버튼을 클릭합니다.

---

<a name="sector4"></a>
## 4. 기본 설정 및 공인인증서, OpenAPI, 젠트레이더 설치

<a name="sector4-1"></a>
### 4.1. 인터넷 익스플로러 보안 강화 해제

**이 작업은 IE 실행 시 원활하게 사이트에 접속하기 위해 필요한 작업입니다.**

<img src="https://user-images.githubusercontent.com/19174106/103961847-bb0cf700-5198-11eb-8b40-10c7945cf19c.png" width="80%">

- 좌측 하단 `윈도우` 메뉴를 들어가서, `서버 관리자`를 실행합니다.

<img src="https://user-images.githubusercontent.com/19174106/103962773-1213cb80-519b-11eb-8cfe-a0635aa0c078.png" width="80%">

1. 좌측 탭에서 `로컬 서버`를 클릭합니다.  
2. `IE 보안 강화 구성`의 `사용`을 클릭합니다.

<img src="https://user-images.githubusercontent.com/19174106/103962612-b77a6f80-519a-11eb-9dfc-5befb332bba8.png" width="80%">

- 관리자와 사용자 모두 `사용 안 함`옵션을 선택 후 확인합니다.

---
<a name="sector4-2"></a>
### 4.2. 필요한 페이지 url 다운로드 및 크롬 브라우저 설치

<img src="https://user-images.githubusercontent.com/19174106/103965778-d5979e00-51a1-11eb-8b3b-e08e7beca39a.png" width="80%">

- 하단의 인터넷 익스폴로러를 여시고, 아래의 주소를 입력해 줍니다.

[https://drive.google.com/drive/folders/1R8A6f_Fb_TcEBycp65nB1dLx42L6e0-E?usp=sharing](https://drive.google.com/drive/folders/1R8A6f_Fb_TcEBycp65nB1dLx42L6e0-E?usp=sharing)

- 위 링크는 cafe24 서버에서 젠트레이더를 운용하기 위해 접속해야할 웹페이지의 바로가기를 정리해둔 파일 입니다.

링크 목록  
> [1.Chrome 웹브라우저](https://www.google.com/intl/ko/chrome/) : Chrome(크롬) 브라우저를 다운 받는 링크입니다. 키움증권 공인인증서 복사할 때 필요합니다.  
> [2.키움증권](https://www3.kiwoom.com/) : 키움증권 홈페이지 바로가기입니다. 공인인증서와 Open API를 다운받게 됩니다.  
> [3.젠포트 - 젠트레이더](https://genport.newsystock.com/GenTrader/) - 젠트레이더 : 젠포트 전략을 실제로 운용할 수 있는 젠트레이더를 다운받게 됩니다.  
> [오류 대처 방법](https://wikidocs.net/8688) : wiki독스에 정리된 오류 대처 방법를 확인 하실 수 있습니다.  
> [젠포트 - wiki메뉴얼](https://wikidocs.net/108731) - wiki 메뉴얼 : 지금 보고 계신 wiki독스 페이지로 이동합니다.

<img src="https://user-images.githubusercontent.com/19174106/103965983-43dc6080-51a2-11eb-8061-1f22f56ae819.png" width="80%">

- 위와 같은 화면에서 cafe24 자료를 다운로드 합니다.

<img src="https://user-images.githubusercontent.com/19174106/103966154-a5043400-51a2-11eb-9d34-1580b3fbd90b.png" width="80%">

- 다운로드 받은 파일을 우클릭하여 압축을 풀어줍니다.

<img src="https://user-images.githubusercontent.com/19174106/103966246-d67cff80-51a2-11eb-972a-259e980174d0.png" width="80%">

- 압축 푼 파일 중 `Chrome 웹브라우저`를 클릭 해 Chrome(크롬) 브라우저를 설치합니다.

---
<a name="sector4-3"></a>
### 4.3. 키움증권 홈페이지에서 공인인증서 가져오기

**AWS 서버에서는 yessign(예스싸인)의 `인증서 가져오기`를 실행했지만,  
Cafe24서버에서는 보안상 이유로 예스싸인 이용이 불가능하여 키움증권 홈페이지에서 인증서를 가져와야 합니다.**

<img src="https://user-images.githubusercontent.com/19174106/103966712-c31e6400-51a3-11eb-95d4-d829b57a957d.png" width="80%">

- 설치 된 크롬 브라우저를 통해 `키움증권`에 접속하여 `필수 보안 프로그램을 모두 설치`하시기 바랍니다.

<img src="https://user-images.githubusercontent.com/19174106/103967998-79834880-51a6-11eb-9b4a-5433e928e6d1.png" width="80%">

- 키움증권 홈페이지로 돌아와서 `인증서복사`를 클릭 합니다.

<img src="https://user-images.githubusercontent.com/19174106/103968230-ce26c380-51a6-11eb-89fe-cec489f9eff6.png" width="80%">

1. `스마트폰 -> PC 인증서 복사`를 클릭 합니다.
2. `스마트폰 -> PC 인증서 복사하기`를 클릭하여 인증서 복사를 진행합니다.

---
<a name="sector4-4"></a>
### 4.4. 키움증권 Open API 설치하기

<img src="https://user-images.githubusercontent.com/19174106/103976097-32528300-51b9-11eb-8493-8d7414459f8e.png" width="80%">

- 인증서 복사가 완료되었다면, 키움증권 메인 페이지로 돌아옵니다.
- 키움증권 홈페이지 하단에 `트레이딩채널` - `Open API`를 클릭합니다.

<img src="https://user-images.githubusercontent.com/19174106/103976680-c113cf80-51ba-11eb-9787-3dd2ec67846d.png" width="80%">

- `키움 Open API+ 모듈 다운로드`를 클릭하여 다운 받고 설치해줍니다.

---
<a name="sector4-5"></a>
### 4.5. 젠트레이더 설치하기

<img src="https://user-images.githubusercontent.com/19174106/103977743-37b1cc80-51bd-11eb-9fca-a40490459b50.png" width="80%">

- 젠포트 - 젠트레이더 페이지에 접속해서 `키움증권 전용 프로그램 다운로드`를 클릭하여 다운로드 후 설치해 줍니다.

---

<a name="sector5"></a>
## 5. 젠트레이더 구동하기

<a name="sector5-1"></a>
### 5.1. 젠트레이더 실행 및 버전 처리
<img src="https://user-images.githubusercontent.com/19174106/103977962-b9095f00-51bd-11eb-9ff4-346da2debe83.png" width="80%">

- 바탕화면에 설치된 `젠트레이더`를 실행시켜줍니다.

<img src="https://user-images.githubusercontent.com/19174106/103979304-df7cc980-51c0-11eb-8ca8-46831834f4d5.png" width="50%">

- 이전의 Open API가 잘 설치되었다면, 해당 화면이 나타납니다.
- 키움증권 `아이디`와 `패스워드`, `공인인증서 암호`까지 입력하고 실행합니다.
- OpenAPI 업데이트를 기다려줍니다. `설치 후 첫 업데이트`이라면 `10~15분` 정도 걸립니다.

<img src="https://user-images.githubusercontent.com/19174106/103980582-7ba7d000-51c3-11eb-967b-df39c54e1698.png" width="80%">

1. 버전처리 화면에선 절대로 `확인`버튼을 먼저 클릭하지 마시고, `젠트레이더를 먼저 종료`해주시길 바랍니다.
2. 젠트레이더가 종료된 후 `확인`버튼을 눌러주시면 됩니다.  
   (버전처리가 끝나면 젠트레이더를 다시 실행시켜주시기 바랍니다.)
- 만약 `확인`버튼을 먼저 누르셨다면, Open API를 종료 후 다시 젠트레이더를 실행시켜주시기 바랍니다.

---
<a name="sector5-2"></a>
### 5.2. 젠트레이더 실행확인 및 오토스타터 설정

<img src="https://user-images.githubusercontent.com/19174106/103982147-49e43880-51c6-11eb-820c-b12c4f44a250.png" width="80%">

- 젠트레이더가 정상적으로 실행되었다면, 오토스타터를 실행시켜줍니다.
- `로그인 설정`버튼을 클릭하여 `뉴지스탁 아이디`와 `암호`를 저장해줍니다.

**여기까지 Cafe24 서버에서 기본적인 젠트레이더 설치를 모두 완료 하셨습니다.**
