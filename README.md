# 🛒 Tiny 중고거래 플랫폼 - Secure Coding Project

본 프로젝트는 Flask 기반의 중고거래 플랫폼입니다.  
사용자 간 상품 거래, 실시간 채팅, 송금, 신고 기능 등을 포함하고 있으며, 보안 코딩 가이드를 준수하여 개발되었습니다.

---

## 📦 프로젝트 파일
압축 파일을 풀면 프로젝트 전체 디렉토리 구조가 재현됩니다.  
Python 가상환경 설정부터 서버 실행까지 아래 가이드를 따라 주세요.

## 🖥️ 환경 세팅 가이드

### 1. 압축 파일 풀기

```bash
tar -xvf secure.tar.gz
cd secure
```
### 2. 가상환경 생성 및 활성화 (Python 3.8 이상 권장)
```bash
python3 -m venv venv
source venv/bin/activate
```
### 3. 의존성 설치
```bash
pip install -r requirements.txt
```

## 🛠️ DB 초기화

### 1. SQLite DB 초기화 (market.db)
이미 초기화된 market.db 파일이 포함되어 있어 추가 작업 불필요
(단, 필요 시 아래 명령어로 초기화 가능)
```bash
flask db init
flask db migrate -m "Initial migration"
flask db upgrade
```

## 🚀 실행 방법

### 1. Flask 실행
```bash
export FLASK_APP=app.py      
export FLASK_ENV=development 
python app.py
```

### 실행결과
현재 만들어둔 계정
1. id:root, pw:sunrin
2. id:root2, pw:sunrin2
<img width="396" alt="화면 캡처 2025-04-25 230339" src="https://github.com/user-attachments/assets/5f3e0c48-6a3f-4e6e-8b63-a1dd956ed809" />
<img width="395" alt="KakaoTalk_20250421_203007061" src="https://github.com/user-attachments/assets/66943eaa-59d7-4752-b137-3ea97aaed049" />
<img width="397" alt="image" src="https://github.com/user-attachments/assets/dd07569c-8887-41b5-b4fa-6a78a8360789" />
<img width="401" alt="image" src="https://github.com/user-attachments/assets/6926838c-0469-4c5e-807a-71ed8a6ff587" />
<img width="398" alt="image" src="https://github.com/user-attachments/assets/01d53e46-67c4-4b57-8646-38ba29127097" />
<img width="400" alt="image" src="https://github.com/user-attachments/assets/700c4b44-b092-4cc4-8c4f-9fc8fe69e0fd" />
<img width="398" alt="image" src="https://github.com/user-attachments/assets/a41c0e87-2043-4263-bd5e-2298f05e88f6" />





## 기타 
### 🛡️ 관리자 계정 생성 방법
관리자 계정은 기본 DB에 포함되어 있지 않으므로, 수동으로 추가해주셔야 합니다.

아래 과정을 따라 Flask shell에서 직접 생성 가능합니다.
```bash
flask shell
```
```bash
from models import db, User
admin = User(username="admin", email="admin@example.com") //아이디
admin.set_password("adminpass") //비밀번호
admin.is_admin = True
db.session.add(admin)
db.session.commit()
exit()
```
위 명령으로 ID admin / PW adminpass인 관리자 계정이 생성됩니다.
필요 시 is_admin을 False로 설정하면 일반 계정으로도 등록할 수 있습니다.






