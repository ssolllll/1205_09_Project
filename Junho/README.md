22-12-06
category_code와 brand의 Nan 값 모두 etc로 대체
user_id별 구매 데이터 내림차순으로 정렬
각 event_type별 총 행동 데이터 추출 및 plot.bar 그래피프 생성
평균 구매 전환율, 평균 카트 전환율, 평균 카트 구매 전환율 계산
독립변수 Event_type (view, cart, purchase) 별 가장 많은 브랜드 top 10 그래프 항목들 생성
- Event_type vs Brand
- Event_type vs Product_id
- Event_type vs Category_Code_1
- Event_type vs User_ID
- Event_type vs User_Session

고려해야할 수정 사항 들
 - Event_type vs Product_id 그래프들이 현재 view count 기준 내림차순 정렬이 되지 않고 product_id 데이터의 이름으로 정렬되고 있어 view count 기준으로 내림차순 정렬 하는 법 찾아야함
 - Event_type vs User_ID 그래프들이 현재 view count 기준 내림차순 정렬이 되지 않고 User_ID 데이터의 이름으로 정렬되고 있어 view count 기준으로 내림차순 정렬 하는 법 찾아야함
 - Event_type vs User_Session 그래프들에서 user_session 데어터의 이름이 너무 길어서 그래프 x축을 보기가 너무 힘들다 데이터 이름을 간소화 하는 방법 찾아야함
