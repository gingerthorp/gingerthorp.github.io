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
   

6. [추가 설치 및 설정 사항 안내](#sector6)  
  6.1. [시간 싱크 맞추기](#sector6-1)  
  6.2. [원격 데스크톱 보안1 : username 변경](#sector6-2)  
  6.3. [원격 데스크톱 보안2 : 인바운드 규칙 설정 하기](#sector6-3)  

[comment]: <> (  6.4. 원격 데스크톱 보안3 : ip 블락.)

[comment]: <> (  6.5. 서버 재부팅 시 즉시 로그인 설정하기)


7. [자주 묻는 질문](#sector7)  
  7.1. [cafe24 서버 강제종료 및 재시작](#sector7-1)  


[comment]: <> (  7.1. cafe24 기간 연장하기)

[comment]: <> (  7.2. cafe24 서버 여러개 이용하기)

[comment]: <> (  7.3. 서버 접속 암호 변경하기)


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

---

<a name="sector6"></a>
## 6. 추가 설치 및 설정 사항 안내

<a name="sector6-1"></a>
### 6.1. 시간 싱크 맞추기

![image](https://user-images.githubusercontent.com/19174106/104149966-92e0fa80-541b-11eb-940b-5a1833fdd43f.png)

한국 표준 과학 연구원 표준 시각 맞추기 : [https://www.kriss.re.kr/standard/view.do?pg=standard_set_01](https://www.kriss.re.kr/standard/view.do?pg=standard_set_01)

간혹 서버의 시간이 틀려질 경우가 있습니다. 서버 시간이 틀어질 경우 괴리가 발생할 확률이 높아지기 때문에 서버 시간을 체크하여 동기화 해줄 필요가 있습니다.  

1. 한국표준과학연구원에서 제공하는 UTCk3.1 프로그램을 다운받습니다.

![image](https://user-images.githubusercontent.com/19174106/104150247-9fb21e00-541c-11eb-8a88-0ef0c5f4a43a.png)

다운 받으신 프로그램을 설치하면, 위와 같이 실행됩니다.   
`동기`버튼을 클릭하시면 서버과 표준시간이 `동기화` 됩니다. (0.1초 이내라면 정상적으로 동기화가 된 것 입니다.)

---

<a name="sector6-2"></a>
### 6.2. 원격 데스크톱 보안1 : username 변경

`윈도우 원격 데스크톱` 사용은 `보안에 매우 취약한 기능`입니다.  
이유는 원격 데스크톱 사용하는 IP를 쉽게 알아낼 수 있고, 접속에 제한이 없어 `무차별 대입 공격`이 가능하기 때문입니다.  
실제로 해커는 모든 아이피들을 스캔하여 그 중 윈도우 원격 데스크톱 기능을 사용하는 IP를 추출하여 집중적으로 패스워드 대입공격을 하고 있습니다.  
해킹 당한 컴퓨터들은 좀비PC로 활용되어 또 다른 PC에게 공격을 가하게 될 수 있습니다.   
관련기사 : [RDP 공격이란 무엇인가, RDP 노출을 완화하는 7가지 요령](https://www.itworld.co.kr/news/110782)  

![image](https://user-images.githubusercontent.com/19174106/104152344-9d52c280-5422-11eb-8d17-025812319e54.png)

글을 작성하는 시점에도 보안 조취를 취하지 않은 PC에서 30분 동안 100번의 무차별 대입 공격이 있었습니다.  
공격 가능한 PC라고 인식되면, 더 많은 대입 공격이 발생하게 되어 컴퓨터 환경을 느리게 만들 수도 있습니다.  

따라서 보안 설정을 사용하여 공격의 노출을 최소화 시켜주셔야 합니다.  

첫번째로 `username를 변경`해 줄 필요가 있습니다.  
해커가 무차별 공격을 실행 할 때 `username을 정해진 몇가지로 고정`하고 암호만 바꿔가며 공격합니다.  
공격시 사용되는 `username`은 주로 `administrator, admin, pc, sys`를 사용합니다.    

cafe24의 가상서버의 `username`은 `administrator`이라서 때문에 변경해야 합니다.  

![image](https://user-images.githubusercontent.com/19174106/104155178-ef4b1680-5429-11eb-9f26-4c2381252722.png)

1. `윈도우키`+`R`를 눌러 실행 창을 엽니다.
2. `netplwiz`를 입력, 확인 합니다.

![image](https://user-images.githubusercontent.com/19174106/104155342-5668cb00-542a-11eb-81c1-cbe2629d40b5.png)

- 사용자 이름을 클릭 한 뒤 `속성`을 클릭합니다.

![image](https://user-images.githubusercontent.com/19174106/104155494-b5c6db00-542a-11eb-9293-fe8e61a48d9c.png)

- 속성 메뉴에서 `사용자 이름`,`전체 이름`을 변경하고자 하는 계정 이름으로 변경 후 적용 및 확인을 클릭합니다.

- 최종적으로 적용하기 위해 재부팅해주시면 됩니다.  
  (재부팅이 정상적으로 진행되지 않을 경우 [7.1. cafe24 서버 강제종료 및 재시작](#sector7-1)을 참조바랍니다.)
  
---

<a name="sector6-3"></a>
### 6.3. 원격 데스크톱 보안2 : 인바운드 규칙 설정하기

인바운드 규칙이란 자신의 컴퓨터로 네트워크 데이터가 들어올 수 있도록 하는 규칙을 말합니다.  
쉽게 말해 지정한 IP만 원격 데스크톱 연결 시도를 할 수 있게하는 보안 설정입니다.  
**주의사항 : 해당 설정을 진행하게 되면, 유동 IP인 핸드폰에선 리모트데스크탑 앱을 통해 접속할 수 없습니다.**

먼저 cafe24 호스팅센터의 `나의 서비스 관리 접속하기`에 접속합니다.

![image](https://user-images.githubusercontent.com/19174106/104159477-b82d3300-5432-11eb-86dc-b50137865835.png)

1. 우측 탭의 `서비스관리` - `방화벽관리`를 클릭합니다.
2. 방화벽관리의 `ON`를 클릭하여 방화벽 정책을 설정합니다.

![image](https://user-images.githubusercontent.com/19174106/104159058-fd049a00-5431-11eb-9d15-0825a2b20432.png)

- 해당 화면에서 `다음`버튼을 클릭 합니다.

![image](https://user-images.githubusercontent.com/19174106/104159122-19083b80-5432-11eb-8a8b-409503d4ed15.png)

- 위와 같이 모든 `적용적책`에 대해서 `개별접속(특정IP)` 옵션을 선택하시고 `확인` 버튼을 클릭해줍니다.

![image](https://user-images.githubusercontent.com/19174106/104160027-bb74ee80-5433-11eb-8ed5-9821f4160b24.png)

- 방화벽 정책이 설정되고 다음 화면에서 `3389 포트`를 선택하시고 `허용IP추가`버튼을 클릭합니다.

![image](https://user-images.githubusercontent.com/19174106/104160201-14dd1d80-5434-11eb-8671-7bebc8c8ada4.png)

- Cafe24 서버에 접속할 본인의 PC IP를 입력합니다.  
- IP 확인하기 : [https://search.naver.com/search.naver?query=IP확인](https://search.naver.com/search.naver?query=IP%ED%99%95%EC%9D%B8)

![image](https://user-images.githubusercontent.com/19174106/104160552-acdb0700-5434-11eb-9c33-d1f1a111a590.png)

- 모든 설정이 완료되면 `접근허용 IP`에 나타납니다. 이로써 접근허용 IP만 원격 접속이 가능합니다.
- IP는 여러개 등록 가능하기 때문에 자주 사용하는 PC의 IP를 등록 해두시면 좋습니다.


---

<a name="sector7"></a>
## 7. 자주 묻는 질문

<a name="sector7-1"></a>
### 7.1. cafe24 서버 강제종료 및 재시작

cafe24 서버가 고장난 경우나 종료된 경우 서버를 재시작 시켜줄 필요가 있습니다.  
cafe23서버 관리 페이지에서 서버를 `종료`, `강제종료`, `재시작` 시켜줄 수 있습니다.

![image](https://user-images.githubusercontent.com/19174106/104161645-8cac4780-5436-11eb-9342-bfc07eb8d3ae.png)

- `서비스 사용현황`에서 서버상태의 `서버원격 관리`버튼을 클릭해줍니다.

![image](https://user-images.githubusercontent.com/19174106/104161770-be251300-5436-11eb-91e4-aac325458c7d.png)

- 위와 같은 화면에서 필요하신 옵션을 선택하여 `실행`버튼을 클릭해주시면 됩니다.
