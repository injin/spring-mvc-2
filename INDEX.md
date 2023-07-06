# spring-mvc-2
[인프런] 스프링 MVC 2편 - 백엔드 웹 개발 활용 기술

---
# message 폴더
## 3. 메시지, 국제화
- application.properties
- messages.properties
- messages_en.properties
- MessageSourceTest.java


---
# validation 폴더
## 4. 검증1 - Validation
- ValidationItemControllerV1.java
- ValidationItemControllerV2.java
- ItemValidator.java
- templates/validation/v1/*.html
- templates/validation/v2/*.html
### 4.15 Validator의 분리
- ItemValidator.java

## 5. 검증2 - Bean Validation
- 테스트 시 Item.java에서 Bean Validation 애노테이션 원복
- ValidationItemControllerV3.java
- templates/validation/v3/*.html
### 5.11 Form 전송 객체 분리
- ValidationItemControllerV4.java
- ItemSaveForm.java
- templates/validation/v4/*.html
### 5.13 Bean Validation - HTTP 메시지 컨버터
- ValidationItemApiController.java


---
# login 폴더
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
### 7.5 서블릿 인터셉터 - 요청 로그
- LogInterceptor.java
- WebConfig.java : addInterceptors
### 7.6 서블릿 인터셉터 - 인증 체크
- LoginCheckInterceptor.java
- WebConfig.java : 
### 7.7 ArgumentResolver 활용
- HomeController.java : homeLoginV3ArgumentResolver
- Login.java
- LoginMemberArgumentResolver.java
- WebCoinfig.java : addArgumentResolvers

---
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


---
# typeconverter 폴더
## 10. 스프링 타입 컨버터
### 10.2 스프링 타입 컨버터 소개
- (요청) http://localhost:8080/hello-v2?data=5
- HelloController.java : helloV1(), helloV2()
### 10.3 타입 컨버터 - Converter
- (요청) http://localhost:8080/ip-port?ipPort=127.0.0.1:8080
- HelloController.java
- StringToIntegerConverter.java
- IntegerToStringConverter.java
- ConverterTest.java
- IpPort.java
- StringToIpPortConverter.java
- IpPortToStringConverter.java
### 10.4 컨버전 서비스 - ConversionService
- ConversionServiceTest.java
### 10.5 스프링에 Converter 적용하기
- WebConfig.java
### 10.6 뷰 템플릿에 컨버터 적용하기
- (요청) http://localhost:8080/converter-view
- (요청) http://localhost:8080/converter/edit
- ConverterController.java
- converter-view.html
### 10.7 포매터 - Formattter
- MyNumberFormatter.java
- MyNumberFormatterTest.java
### 10.8 포매터를 지원하는 컨버전 서비스
- FormattingConvertionServiceTest.java
### 10.9 포매터 적용하기
- (요청) http://localhost:8080/converter-view => 쉼표 확인
- (요청) http://localhost:8080/hello-v2?data=1,000
- WebConfig.java
### 10.10 스프링이 제공하는 기본 포매터
- (요청) http://localhost:8080/formatter/edit
- FormatterController.java

---
# upload 폴더
## 11. 파일 업로드
### 11.3 서블릿과 파일 업로드1
- (요청) http://localhost:8080/servlet/v1/upload
- ServletUploadControllerV1.java
### 11.4 서블릿과 파일 업로드2
- application.properties
- ServletUploadControllerV2.java
### 11.5 스프링과 파일 업로드
- SpringUploadController.java
### 11.6 예제로 구현하는 파일 업로드, 다운로드
- (실행) http://localhost:8080/items/new
- ItemRepository.java
- UploadFile.java
- Item.java
- FileStore.java
- ItemForm.java
- ItemController.java
- item-form.html
- item-view.html
