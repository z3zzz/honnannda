## 목차
* [프로젝트 개요](#프로젝트-개요)
* [문제 인식](#문제-인식)
* [해결 방안](#해결-방안)
* [사용 기술](#사용-기술)
* [실행 방법](#실행-방법)
* [대표 코드](#대표-코드)
* [시사점](#시사점)


## 프로젝트 개요
## SNS기반 사용자 콘텐츠 활용 맛집 정보/위치 공유 플랫폼
- TLS, DNS 적용, WSGI-Apache2 기반 구글 검색이 가능한 완성형 웹 서비스 배포

<br />

![image](https://user-images.githubusercontent.com/91174156/198237698-ac2b3fb5-471d-4257-a20a-b191c8ecb429.png)

<br />

- 자신의 게시물에 한해 Private/Public 토글 가능
- 페이지네이션
- 코멘트, 좋아요, 별점 기능

## 프로젝트 개요
1. 사용자는 맛집에 대한 정보, 위치, 이동 방법을 기록하고, 본인의 의사에 따라 기록을 포스팅하여 다른 사용자와 공유하고 댓글을 달 수 있음 
2. 맛집 주인은 포스팅을 통해 인사이트를 얻고, 커뮤니티 형성을 통해 매출 향상을 이룰 수 있음
3. 비즈니스 모델: 맛집 주인의 커뮤니티 형성 시 수수료 지급, 사용자는 일정 이상의 팔로워 달성 시 광고 수익

## 개발 방식
1. 기획 및 GCP VM, Linux(Ubuntu), MariaDB, Python, WSGI, Apache2 인프라 기반 백엔드 서버 구축 및 배포
2. TLS (OpenSSL)를 통한 보안 적용 / DNS, SEO 적용을 통한 서치엔진 대응 및 사용자 유입  
3. Jinja2 Template 기반 데이터 처리 및 페이지 렌더링 

## 사용 기술
* Flask 2.2
* Jinja Template 2.4
* MariaDB
* WSGI, Apache2, Linux
	
## 실행 방법
1. `git clone git@github.com:z3zzz/hongdae5star.git` 
2. 패키지 설치 및 실행

```terminal
pipenv install;
pipenv run python app.py;
```

## 차별점
1. 네이버에는 없는 자신의 게시물(맛집 후기) 공개/비공개 토글 기능 구현
2. Apache2 서버에 OpenSSL을 적용하는 오픈소스 프로그램인 Certbot의 오류 발견 및 수정 개선
3. 단기간 내 부트캠프에 참여한 100여명 수강생 및 홍대 인근 자영업자 유입, 우수 프로젝트 선정  

## 시사점
1. 간단한 웹사이트라도 실제 Production은 Dev 때와 완전히 다른 차원의 문제 해결 능력과 끈기가 필요하며, 오픈소스 프로그램, 게시물을 100% 신뢰해서는 안 됨 
2. Apache2의 conf 파일 작성에만 3일 이상이 소요, WSGI와 Apache2의 연결, Python의 가상환경 설정, TLS 적용 도중 사소한 설정 오류로 VM을 10번 넘게 초기화 및 반복
   -> 소프트웨어 프로그램의 모든 버그는 결국 원인을 찾을 수 있으며, 논리적으로 접근하면 시간은 걸릴지라도 해결이 결국 가능함  
