## 6. 로그인 처리1 - 쿠키, 세션
### 6.6 로그인 처리하기 - 쿠키 사용
- HomeController.java : homeLoginV1
- LoginController.java loginV1, logoutV1
- loginHome.html
### 6.9 로그인 처리하기 - 세션 직접 만들기
- SessionManager.java
- SessionManagerTest.java
- LoginController.java : loginV2, logoutV2
- HomeController.java : homeLoginV2
### 6.10 로그인 처리하기 - 서블릿 HTTP 세션1
- LoginController.java : loginV3, logoutV3
- HomeController.java : homeLoginV3
### 6.10 로그인 처리하기 - 서블릿 HTTP 세션2
- HomeController.java : homeLoginV3Spring
### 6.13 세션 정보와 타임아웃 설정
- SessionInfoController.java

## 7. 로그인 처리2 - 필터, 인터셉터
### 7.2 서블릿 필터 - 요청 로그
- WebConfig.java : logFilter
- LogFilter.java
### 7.3 서블릿 필터 - 인증 체크
- WebConfig.java : loginCheckFilter
- LoginCheckFilter.java
- LoinController : loginV4
### 7.5 서블릿 인터셉터 - 요청로그
- LogInterceptor.java
- WebConfig.java : 

