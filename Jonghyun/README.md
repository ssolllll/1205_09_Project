# eCommerce Project
## 22.12.06
- category_code와 brand의 Nan 값을 제거하지 않은 채로 진행
- 구매내역을 기준으로 데이터 모음
- 브랜드 별 'purchase'이력이 가장 많은 순으로 상위 10개 기업을 pie그래프로 시각
- 가장 많은 매출을 달성한 상위 10개 브랜드를 bar.plot으로 시각화
- 가장 많은 'event_type'('view', 'cart', 'purchase' 모두 합산)을 발생시키는 브랜드 상위 10를 bar.plot으로 시각화


## 22.12.07
 - PV(purcahse/view) 기준으로 상위부터 하위까지 4개의 그룹으로 데이터를 분류
 - 4개의 그룹들 간 user_id 내 v_brand(많이 본 brand), c_brand(cart에 담은 brand), p_brand(purchas를 한 brand) 컬럼 비교
 - 그룹별 평균치를 구하기 위해 각 그룹을 group columns 별로 .query함수를 사용해 묶어 평균치를 구하고 변수에 저장
 - 4개의 변수를 각각 DataFrame화
 - DataFrame화 하여 얻어 낸 4개의 변수를 .concat함수를 통해 한 Frame으로 통합하고 행과 열을 치환(.T)
 - 4개의 그룹에 대한 (v, c, p)_brand 수치를 .barplot을 통해 시각화
