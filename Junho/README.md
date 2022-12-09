# eCommerce Project


## 22.12.06

- category_code와 brand의 Nan 값 모두 etc로 대체
- user_id별 구매 데이터 내림차순으로 정렬
- 각 event_type별 총 행동 데이터 추출 및 plot.bar 그래프 생성
- 평균 구매 전환율, 평균 카트 전환율, 평균 카트 구매 전환율 계산

- 독립변수 Event_type (view, cart, purchase) 별 가장 많은 브랜드 top 10 그래프 항목들 생성
  - Event_type vs Brand 
  - Event_type vs Product_id
  - Event_type vs Category_Code_1
  - Event_type vs User_ID
  - Event_type vs User_Session

- 고려해야할 수정 및 추가 사항
  - Event_type vs Product_id 그래프들이 현재 view count 기준 내림차순 정렬이 되지 않고 product_id 데이터의 이름으로 정렬되고 있어 view count 기준으로 내림차순 정렬 하는 법 찾아야함
  - Event_type vs User_ID 그래프들이 현재 view count 기준 내림차순 정렬이 되지 않고 User_ID 데이터의 이름으로 정렬되고 있어 view count 기준으로 내림차순 정렬 하는 법 찾아야함
  - Event_type vs User_Session 그래프들에서 user_session 데어터의 이름이 너무 길어서 그래프 x축을 보기가 너무 힘들다 데이터 이름을 간소화 하는 방법 찾아야함



## 22.12.07


-전일 고려해야할 수정 및 추가 사항 작업 로그
 - 아래 PV수치 기준으로 가공된 데이터 기준 bar graph 작업 완료 (송한솔) 

-결측치 처리 완료된 데이터로 22.12.06 과정 재수행

-User_ID 별 아래의 컬럼들 정렬 제안
  - view, cart, count_purchase, total_amount_purchase, user_session_unique, number_behavior, view_count_brand, cart_count_brand, purchase_count_brand, weekday_max, time_max, view_price_avg, cart_price_avg, purchase_price_avg, product_id_unique, purchase_price_max, purchase_price_min, count_category_code, category_code_max, category_code_min, CV(cart/view), PC(count_purchase/cart), PV(count_purchase/view), VS(view/session), CS(cart/session), PS(count_purchase/session)

-view가 0인 이상치 제거

-PV와 PC가 100이상인 user를 발견하여 product_id_unique와 count_purchase 대조를 통해 두가지 추측
  - count_purchase는 제품의 종류가 아닌 제품의 수 기준
  - 카트에 담지않고 바로 구매를 하는 경우
 
-PV 수치를 기준으로 25% 구간을 네개의 그룹으로 나누어 각 그룹별 행동분석 시작. 최상위(Group 1), 차상위(Group 2), 차하위(Group 3), 최하위(Group 4).
 
-시각화를 통해 insight 도출 
  - scatterplot view와 총 구입액 상관도
    - 상위 그룹일수록 상품을 보는 횟수와 총 구매금액의 상관관계가 더욱 크다. 최상위와 차상위 그룹은 많이 볼수록 총 구매금액이 높아지는 반면 차하위와 최하위 그룹은 많이 보아도 많은 금액을 지불하지 않는다. PV기준 타겟마케팅 방안을 고려할때 상위그룹으로 갈수록 최대한 많은 제품들을 열람하게 유도하는 전략이 고효율 전략일 것으로 짐작해볼 수 있다. 그룹1과 그룹2에 대한 마케팅 방안으로 해당 전략을 제시한다.
 
 
-고려해야할 수정 및 추가 사항
 - 각 그룹별 특성 정리 (총구매액, 컬럼들 중 유의미한 평균값 등)
 - 히트맵 관찰을 통해 관계도 높은 변수들을 기준으로 시각화 등 분석
 - 회의에서 나온 user_session 및 category_id 기준의 행동패턴 분석


## 22.12.08


 -전일 고려해야할 수정 및 추가 사항 작업 로그
  - 각 그룹별 특성 정리 -> 완료
  - 히트맵 관찰을 통해 관계도 높은 변수들을 기준으로 시각화 등 분석 -> 완료
  - 회의에서 나온 user_session 및 category_id 기준의 행동패턴 분석 (category_id) 완료 user_session 미완료
 
 -price 히스토그램
 -purchase_price_avg 박스플롯 표현
 -purchase 기준 최빈도 brand 워드 클라우드 작성
 
-분석결과
  - 네개의 그룹은 행동횟수와 판매횟수간 역의 상관 관계를 보이고 있다. 상위 그룹일수록 적게보고 많이 사는 반면 하위 그룹일수록 많이 보고 적게산다.
  - 브랜드는 애플, 삼성, LG, 하웨이, 루센테, 샤오미 등이 가장 많은 판매빈도를 보였다.
  - 판매액 기준 상위 10%의 샘플 그룹의 제풉 구익 가격 구간은 2500달러 선까지 분포되어 있다. 가장 많이 판매되는 구간은 0~500달러 수준이고 그 외 1000달러 내외 구간과 1500달러 내외 구간이 두드러지게 판매되는 것을 확인할 수 있다. 이는 전자제품 카테고리가 해당 표본에서 가장 많이 팔리고 있고 해당 카테고리의 가격 구간이 이외같이 분포되어 있음을 확인할 수 있다.
  - 그룹 간 평균 구매 제품가격 분포 차이를 구했음. 각 그룹별로 500달러에서 1000달러 사이의 제품을 구매하는 것을 확인할 수 있고 최상위와 차상위 그룹의 구매제품의 평균 가격이 더욱 넓은 범위에 분포하고 있는 것을 확인할 수 있음.
  - 상위 그룹일수록 상품을 보는 횟수와 총 구매금액의 상관관계가 더욱 크다. 최상위 그룹은 많이 볼수록 총 구매금액이 높아지는 반면 최하위 그룹은 많이 보아도 많은 금액을 지불하지 않는다. PV기준 타겟마케팅 방안을 고려할때 상위그룹으로 갈수록 최대한 많은 제품들을 열람하게 유도하는 전략이 고효율 전략일 것으로 짐작해볼 수 있다. 그룹1과 그룹2에 대한 마케팅 방안으로 위의 전략을 제시한다.
