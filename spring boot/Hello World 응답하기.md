
## 첫 기능 만들기

#### 컨트롤러

- 모델과 뷰 사이에서 브릿지 역할을 수행
- 앱의 사용자로부터 입력에 대한 응답으로 모델 및 뷰를 업데이트 하는 로직을 포함
- 사용자의 요청은 모두 컨트롤러를 통해 진행되어야 함
- 컨트롤러로 들어온 요청은 모델이 어떻게 처리할지 결정하여 모델로 요청을 전달함

- ex) 쇼핑몰에서 상품을 검색하면 그 키워드를 컨트롤러가 받아 모델과 뷰에 적절하게 입력을 처리하여 전달함

#### @RestController
- Spring Framework 4 버전부터 사용 가능한 어노테이션
- @Controller에 @ResponseBody가 결합된 어노테이션
- 컨트롤러 클래스 하위 메소드에 @ResponseBody 어노테이션을 붙이지 않아도 문자열과 JSON등을 전송할 수 있음
- View를 거치지 않고 HTTP ResponseBody에 직접 Return값을 담아 보내게 됨

어노테이션이란?

프로그램의 소스코드 안에 다른 프로그램을 위한 정보를 미리 약속된 형식으로 포함시킨 것을 어노테이션이라고 한다. 주석처럼 프로그래밍 언어에 영향을 미치지 않으면서도 다른 프로그램에 유용한 정보를 제공하는 기능을 한다.

예를 들어, 소스 코드 중 특정 메서드만 테스트하기를 원하면 "@Test" 어노테이션을 붙여, 테스트 프로그램에 알리는 역할을 하지만 메서드가 포함된 프로그램 자체에 영향을 미치진 않는다.


#### 도식화
![[hello 1.png]]

#### @RequestMapping

- mvc의 핸들러 매핑을 위해서 DefaultAnnotationHandlerMapping을 사용
- DefaultAnnotationHandlerMapping 매핑정보로 @RequestMapping 어노테이션을 활용
- 클래스와 메소드의 RequestMapping을 통해 URL을 매핑하여 경로를 설정하고 해당 메소드에서 처리

     value : url 설정
     method : GET, POST, DELETE, PUT, PATCH 등

- 스프링 4.3버전 부터 메소드를 지정하는 방식보다 간단하게 사용할 수 있는 어노테이션을 사용할 수 있음
-@GetMapping
-@PostMapping
-@DeleteMapping
-@PutMapping
-@PatchMapping