## 8. 예외 처리와 오류 페이지
### 8.1 서블릿 예외 처리 - 시작
- ServletExController.java
###8.2 서블릿 예외 처리 - 오류 화면 제공
- ExceptionApplication.java
- ErrorPageController.java
### 8.3 서블릿 예외 처리 - 필터
- LogFilter.java
- WebConfig.java : logFilter
### 8.4 서블릿 예외 처리 - 인터셉터
- LogInterceptor.java
- WebConfig.java : addInterceptors
### 8.5 스프링 부트 - 오류 페이지1
- /templates/error/4xx.html
- /templates/error/404.html
- /templates/error/500.html
### 8.5 스프링 부트 - 오류 페이지2
