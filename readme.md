# JPA 학습 리포지터리

---


# 실전예제
## 요구사항 분석
* 회원은 상품을 주문할 수 있다.
* 주문 시 여러 종류의 상품을 선택할 수 있다.
### 회원 기능
* 회원 등록
* 회원 조회
### 상품 기능
* 상품 등록
* 상품 수정
* 상품 조회
### 주문 기능
* 상품 주문
* 주문 내역 조회
* 주문 취소

## 도메인 모델 분석
![도메인 모델 분석](./image/도메인%20모델.png)
* 회원과 주문의 관계<br/>
회원은 여러 번 주문할 수 있으므로 회원과 주문은 일대 다 관계
* 주문과 상품의 관계<br/>
주문할 대 여러 상품을 함께 선택할 수 있고, 하나의 상품이 여러번 주문 될 수 있으니 다대다 관계이다.
주문 상품에는 해당 상품을 구매한 금액과 수량 정보가 포함되어 있다.

## 테이블 설계
![테이블 설계](./image/테이블%20설계.png)

## 엔티티 설계와 매핑
![엔티티 설계](./image/엔티티%20설계.png)

## version log
### v 0.1
엔티티 기본 매핑
#### 문제점
* 테이블 설계에 맞춘 설계 방법
  * 외래키만 가지고 있기 때문에 연관된 엔티티를 찾을 때 외래키로 데이터 베이스를 다시 조회해야 한다.
  * 
