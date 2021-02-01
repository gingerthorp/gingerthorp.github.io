---
title: MSSQL Expess 에디션 제한과 RDS 엔진 옵션별 비용 정리
date: 2021-01-01 12:00:00 +0900
categories: [Develop&Tech, AWS]
tags: [Research]     # TAG names should always be lowercase
toc: True
---

## 사건 발단

연구를 위해 회사 PC에 저장된 MSSQL 데이터를 AWS RDS에 마이그레이션하기 위해 RDS 엔진 옵션 중 Express Edition을 선택하여 작업하였습니다.
(비용절감하기 위해 제일 싼 옵션을 고르고 별 생각없이 진행했습니다.)

1개 DB에 약 25GB 정도되는 파일을 불러와 분석해야 했기 때문에 스토리지는 넉넉히 40GB로 설정하여 진행했습니다.

MSSQL 데이터 정렬로 인한 [한글 깨짐 현상을 해결하고](https://youeye.tistory.com/153), 데이터 내보내기를 통해 순조롭게 진행하길래 잠시 자리를 비우고 돌아오니 에러가 났습니다.

![스크린샷 2021-01-01 오후 1 29 44](https://user-images.githubusercontent.com/19174106/103433516-8697b900-4c35-11eb-9a03-3d5ddf156539.png)

처음엔 DB에 할당된 메모리가 적어서 발생하는 원인으로 생각하고 [DB 메모리를 늘리기 위해 찾아봤습니다.](https://tshooter.tistory.com/6)
해당 DB의 메모리를 늘리는 쿼리를 실행했을 경우 다음과 같은 에러메시지가 나왔습니다.

```
Msg 1827, Level 16, State 2.
CREATE DATABASE or ALTER DATABASE failed because the resulting cumulative database size would exceed your licensed limit of 10240 MB per database.
```
라이센스에 부여된 10240MB를 초과했기 떄문에 실패했다고 나옵니다.

제대로 알아보니 [MSSQL Expess Edition은 DB당 최대 10GB까지 할당](https://m.blog.naver.com/PostView.nhn?blogId=dosz&logNo=221168345166&proxyReferer=https:%2F%2Fwww.google.com%2F) 가능하기 때문에 다른 에디션을 선택해야 한다고 합니다.

## 해결

AWS MSSQL 라이센스는 너무 비싸기 때문에 다른 DB엔진을 선택하려고 합니다.

DB 선택 조건
1. MSSQL에서 마이그레이션이 가능하다.
2. 비용이 저렴하다.

마이그레이션은 대부분 가능하고, AWS RDS 비용을 비교 정리해봤습니다.

![image](https://user-images.githubusercontent.com/19174106/103441413-2fbfcd00-4c91-11eb-8afb-c1be42ae66b8.png)

MSSQL 제외하고, 대부분 비슷한 수준이기 때문에 엔진별 특징도 고려해볼 필요가 생겼습니다.
