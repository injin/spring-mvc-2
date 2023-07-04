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