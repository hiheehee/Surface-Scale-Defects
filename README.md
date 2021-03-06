# Surface Scal Defects
Data Analysis Project
-----------------------------
# Overview
* Organization : POSCO AI BIG DATA ACADEMY  
* Project Title : 압연 공정 scale 불량 유발 영향인자 분석 및 해결 방안 도출  
* Project Description : 압연 공정의 scale 발생 원인 파악 및 결과 해석을 통한 개선 기회 도출  
* Author : 황규희  
* Date : 2021.03.11  
-----------------------------
# 🏭 Dataset  
* SCALE불량.csv : 후판공정 scale 데이터  
-----------------------------
# 🏭 철의 5대 원소
* C (Carbon) 탄소
  - 강도를 높이는 역할
  - 탄소 증가 : 경도 증가, 항복점 증가, 인장강도 증가
  - 탄소 감소 : 연신율 증가, 연성 증가
* Si (Silicon) 규소
  - 산소를 빼는 탈산제 역할
  - 규소 증가 : 인성 저하
* Mn (Manganese) 망간
  - 점성을 부여하는 역할
  - 내산성을 저해하는 역할
* P (Phosphorus) 인
  - 일반적으로 강에 해로운 원소
  - 인 증가 : 내후성 향상, 피삭성 개선, 충격저항 저하
* S (Sulfur/Thion) 황
  - 철과 결합하여 FeS를 형성
  - 취약하고 용융점이 낮아 열간 및 냉간 가공시 균열을 발생 시킴
### 용어 설명
- 경도 : 딱딱한 정도
- 항복점 : 탄성 한도를 넘어서 최초로 원형을 회복하지 못할 때의 응력이 나타내는 값
- 인장강도 : 재료가 절단되도록 끌어당겼을 때 견뎌내는 최대 하중을 재료의 단면적으로 나눈 값
- 연신률 : 쇠붙이 따위가 끊어지지 않고 늘어나는 비율
- 연성 : 물질이 탄성 한계를 넘는 힘을 받아도 파괴되지 않고 늘어나는 성질
- 인성 : 잡아당기는 힘에 견디는 성질
- 소성가공성 : 재료의 소성을 이용하여 가공하는 것
- 내산성 : 산(酸)에 잘 견디는 성질.
------------------------------
# 🏭 공정의 종류
* 제선 공정
  - 고로에 철광성을 넣고 코크스를 태워 철광석 중 산소를 제거하고 용해시켜 선철로 만드는 공정을 의미한다.
* 제강 공정
  - 고로에서 생산된 쇳물인 용선은 탄소의 함유량이 많고 인, 황과 같은 불순물이 포함되어 으스러지기 쉬운 상태다.
  - 탄소 함유량을 줄이고 인, 황등 불순물을 제거하는 공정을 의미한다.
* 연속주조 공정
  - 전로에서 생산된 용강을 일정한 형태의 주형에 부어서 강괴를 만든 후 분괴압연을 거쳐 슬래브를 제조하던 종래의 조괴법을 발전시킨 기술을 의미한다.
  - 중간소재
    + 슬래브(Slab) : 두꺼운 널판지 모양
    + 블룸(Bloom) : 단면이 직사각형인 굵은 막대 모양
    + 빌릿(Billet) : 단면이 정사각형인 가늘고 긴 막대 모양
* 압연 공정
  - 금속  소성 가공 방법 중 하나인 roll을 이용해 두께를 줄이고 일정하게 만드는 공정을 의미한다.
  - 이때 roll을 압연기 즉 rolling mill이라고 지칭한다.
  - 제강 공정에서 생성된 용강은 연성과 전성이 있기 때문에 형태를 바꿀 수 있다.
  - 열간 압연 : 금속의 재결정 온도 이상에서 작업이 수행되는 경우
  - 냉간 압연 : 금속의 재결정 온도 이하에서 작업이 수행되는 경우
    - 슬래브(Slab) -> 열연제품 : 슬래브를 1100도씨 이상 가열하여 회전하는 롤사이를 통과시킨 제품 ex) 건축자재, 파이프등 산업체에서 사용됨 
    - 슬래브(Slab) -> 냉연제품 : 열연제품을 실온에서 더 얇게 가공한 제품 ex) 일반가전제품, 드럼, 자동차 프레임
    - **슬래브(Slab) -> 후판제품 : 강판두께가 6mm 이상의 두꺼운 철판 ex) 원유 수송하는 강관, 빌딩, 선박**
    - 냉연제품 -> 도금제품 : 냉염제품 표면에 아연을 입힌 제품 ex) 고급가전제품, 사무기기, 자동차 외장
    - 열연제품 -> 전기강판 : 열연제품에 전기적 성질을 부여하여 만든 제품 ex) 변압기, 모터
    - 빌릿(Billet) -> 선재제품 : 1000도씨 이상의 원형을 롤을 통과시킨 제품 ex) 자동차 타이어 코드, 교량용 와이어, 피아노 현, 해저 케이블
    - 스테인리스 제품 : 철에 니켈과 크롬을 첨가하여 별도의 생산설비로 생산하는 제품 ex) 주방용품, 의료기기, 건축물의 외벽 및 지붕재 
------------------------------
# 🏭 후판 제조 공정
![후판공정](https://user-images.githubusercontent.com/49300728/125164940-c2f13680-e1cf-11eb-9532-7028402f14a6.jpg)
1. HSB(Hydraulic Scale Breaker) : 후판 공장에서 가열중 발생되는 1차 Scale 제거장치
2. 압연
3. 가속냉각 (TMCP)
4. 열간교정
5. 절단
6. 열처리
7. 초음파 검사
------------------------------
# 🏭 참고 문헌
http://product.posco.com/homepage/product/kor/jsp/process/s91p2000220p.jsp
https://fi-fi.facebook.com/HELLOPOSCO/videos/612927005439425/
