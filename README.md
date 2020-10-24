# Lotte-Is-Horse
롭스의 소비자-점주 연결 서비스

1. 재고확인(온라인/오프라인)
2. 실시간 주문  *1시간 내 배달
3. 회원관리
4. 오프라인 매장 연결   *지도 API 이용

#### Model 종류
# 모델 목록
### User(유저)
##### isSeller : Boolean
true면 판매자(지점장) -> Store에 연결
##### store : Store
지점 저장

---
### Store(지점)
##### name : Char
지점 이름(지점 리스트에 있는 이름)

---
### Product(제품)
##### name : Char
제품 이름
##### brand : Char
브랜드 이름
##### price : Integer
제품 가격
##### image : Image
상품 사진
메인 이미지(750x750): 1개
소개 이미지: 10개

---

### Sell(판매하다)
##### store : Store
지점 연결
##### product : Product
제품 연결
##### count : Integer
제품 개수

---

#### API 관리 방법
방법1: 관리자 아이디로 로그인하여 /api/ 주소로 들어가기
방법2: REST 통신 보내기 (Rest Client 확장프로그램 추천)

#### 설치한 pip
```bash
pip install django
pip install Pillow
pip install djangorestframework
pip install django-filter
```

#### requirement 생성 및 설치
생성 `pip freeze > requirements.txt`
설치 `pip install -r requirements.txt`

#### 데이터베이스 초기화
```bash
find . -path "*/migrations/*.py" -not -name "__init__.py" -delete
find . -path "*/migrations/*.pyc"  -delete
```
`db.sqlite3` 삭제

#### 데이터베이스 생성
```bash
python manage.py makemigrations
python manage.py migrate
```

#### 명령어 모음
가상환경 실행: `. myvenv/Scripts/activate`

static 파일 모으기: `python manage.py collectstatic`

app 만들기: `python manage.py startapp (앱이름)`

관리자 만들기: `python manage.py createsuperuser`

관리자 편하게 만들기: `python manage.py createsuperuser --email admin@example.com --username admin`

서버 포트 변경: `python manage.py runserver 8080`

#### 만든 계정 종류(아이디/비번)
superuser: admin/admin, 