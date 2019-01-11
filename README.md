쿠폰 생성기 웹 어플리케이션 코딩 컨셉 (Todo List)
------------------------------------------

## 목표
- AWS EC2에는 Docker 이외의 다른 것은 설치하지 않고 진행할 것.
- 직접만든 DockerFile, docker compose를 이용하여 도커 컨테이너를 추가할 것.
- Composer와 Lumen 설치는 기존의 dockerfile을 이용할 것.

1. ~~Amazon EC2 SSH ubuntu 원격 연결 (AWS CLI, EC2 SSH)~~
2. ~~PHP Lumen Framework 사용~~
3. 루멘 프로젝트와 Amazon RDS mysql 연결
4. DB 스키마 생성 - 유저 테이블, 쿠폰 테이블 생성 / 유저 중 한명은 admin 관리자. (쿠폰 column : group, created_at, used, user)
5. 로그인 페이지 (기본 사용) admin일 경우 쿠폰 코드 발행 페이지로 이동 / 그 외의 일반 유저는 쿠폰 코드 사용 페이지로 이동
6. 코드 발행 페이지에서 Restful Resource Controller 이용해서 post 로 prefix 값 3자리 입력 
    -> 뒤에 13자리는 랜덤으로 중복되지 않는 난수 쿠폰 생성(10만건)한다.
       생성시에는 랜덤으로 유저가 이미 사용한 것으로 DB에 넣어줄 것 (이때 발행 페이지는 admin만 접근 가능하다.)
7. 권한이 유저들에게 모두 허용된 쿠폰 코드 리스트 페이지 -> 쿠폰코드 100개씩 페이지네이션 처리. 
   (번호 순대로 내림차순, 오름차순 고려할 것, 그룹별 사용자별 또는 사용되었는지 까지 확인할 수 있도록.)
8. 전체 권한으로 접근 가능한 쿠폰 코드 사용 페이지 (사용, 불가능 체크)
9. 그룹별 쿠폰 사용 통계 페이지 (Eloquent ORM 메소드 사용, 자바스크립트 차트 라이브러리 사용하여 원하는 페이지에 시각화)
10. 배포 (git을 통해 업데이트 내역 전송) - vendor, API KEY 같은 private한 (env 파일 등등) 내용들은 FTP FileZilla 이용하여 전송

