# MySQL,postman 실습 정리

### 목적. Database
Actually Server와 DB가 어떻게 연동되고, 포스트맨 같은 Client에서 요청을 보내면 서버가 어떻게 Data를 처리하고 respond하는지 전체 flow을 experience하는 것이 우리의 Goal입니다.
### 1. 새 DB 생성 (DB명은 본인 이름으로 설정)
Mysql workbench를 실행하여 query에 CREATE DATABASE hanjin; 를 통해 이름으로 새 DB를 생성한다.
 

### 2. USER Table 생성 후 ID/PW 저장,
이후 CREATE TABLE USER (id VARCHAR(50) PRIMARY KEY,pw VARCHAR(100) NOT NULL); 를 입력하여 USER Table을 생성한다.
그 다음 
INSERT INTO USER (id, password) VALUES ('test', 'testpassword');
SELECT * FROM USER; 로 ID/PW를 저장할 수 있다.
### 3.POSTMAN 사용하여 POST 요청시 app.post() ID,PW가 저장되도록 설정
Visual studio code에 app.post, app.get 등의 코드를 작성 후, POSTMAN에서 POST를 통해 ID/PW의 정보를 localhost:3000/db에 보낸다.
### 4. localhost:3000/db로 접속 후, user 데이터 확인
GET으로 localhost:3000/db로 접속 하여 GET을 통해 전체 user 데이터를 확인한다.

| 과정 단계  | 스크린샷                                                       
| ---------- | --------------------------------------                        
| DB 생성    | ![Image](https://github.com/user-attachments/assets/30328606-2dd9-40b6-b0df-68b69b73de0b)               
| Table 생성 | ![Image](https://github.com/user-attachments/assets/6022a8a7-357f-47de-894f-34ac6e5ea257)       
| POST 요청  | ![Image](https://github.com/user-attachments/assets/88479e43-8d66-48bd-82e1-276748c46cf2) 
| GET 요청   | ![get_request]![Image](https://github.com/user-attachments/assets/07e30752-a257-4a30-9941-d8f2cf1a1320)   


### 전체 요약
MySQL에서 HanJin 데이터베이스와 USER 테이블 생성.
Express 서버(app.js)를 설정하여 MySQL과 연결, POST 및 GET 요청 처리.
Postman으로 POST /users 요청을 보내 ID와 비밀번호 저장.
GET /db로 사용자 데이터를 조회하여 결과 확인.