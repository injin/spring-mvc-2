# exception 폴더
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
- /templates/error/500.html

## 9. API 예외 처리
### 9.1 시작
- 서블릿이 제공하는 API 오류 처리
- POSTMAN으로 accept 속성 application/json로 설정 후 테스트 => http://localhost:8080/api/members/ex
- WebServerCustomizer.java
- ApiExceptionController.java
- ErrorPageController.java : errorPage500Api
### 9.2 스프링 부트 기본 오류 처리
- BasicErrorController.java
### 9.3 HandlerExceptionResolver 시작
- (요청) http://localhost:8080/api/members/bad
- ApiExceptionController.java
- MyHandlerExceptionResolver.java
- WebConfig.java : extendHandlerExceptionResolvers
### 9.4 HandlerExceptionResolver 활용
- (요청) http://localhost:8080/api/members/user-ex
- UserException.java
- ApiExceptionController.java
- UserHandlerExceptionResolver.java
- WebConfig.java : extendHandlerExceptionResolvers
### 9.5 스프링이 제공하는 ExceptionResolver1
- (요청) http://localhost:8080/api/response-status-ex1
- (요청) http://localhost:8080/api/response-status-ex2
- BadRequestException.java
- ApiExceptionController.java : responseStatusEx1(), responseStatusEx2()
- messages.properties
### 9.5 스프링이 제공하는 ExceptionResolver2
- (요청) http://localhost:8080/api/response-status-ex3?data=qqq
- ApiExceptionController.java : responseStatusEx3()
- DefaultHandlerExceptionResolver.java
### 9.6 @ExceptionHandler
- (요청) http://localhost:8080/api2/members/bad
- (요청) http://localhost:8080/api2/members/ex
- ErrorResult.java
- ApiExceptionV2Controller.java => 주석 해제 후 실행
### 9.7 @ControllerAdvice
- (요청) http://localhost:8080/api2/members/bad
- (요청) http://localhost:8080/api2/members/ex
- ExControllerAdvice.java