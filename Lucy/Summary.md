Chap 16. 싱글톤과 모노스테이트 패턴  
 -> 단 하나의 인스턴스만을 가져야 하는 클래스에 적용  
 -> 프로그램이 시작할 때 생성되었다가 끝날 때 소멸  
 -> 해당 클래스는 주로 루트(root)의 역할을 한다.  
 
  1. 싱글톤 패턴(Singleton Pattern)  
	(ex 1) ConsumerContainerFactoryDelegatorConfig.java  
	    참고 : http://zgundam.tistory.com/26  
	(ex 2) Springframework 구현에서의 예제: DefaultListableBeanFactory.java    
		ConfigurableBeanFactory.java의 scope identifier "singleton"의 구현체 중	DefaultListableBeanFactory.java 를 보면,  
		Inner class 로 javaxInjectProviderClass가 private static 으로 선언되어 있다.  
		(*추가) scope가 singleton이면 autowiring될 때 singleton 클래스로 생성된다.   
	(ex 3) Springframework 구현에서의 예제: TrueMethodMatcher.java  
		
	(!Q) NotUsed.scala ??? 

  	    	
  2. 모노스테이트 패턴(Monostate Pattern)  
	-> 2개의 인스턴스가 같은 객체의 서로 다른 이름을 갖고 있는 것  
	  (모든 변수를 정적으로 만들어 객체가 같은 변수를 공유  
	   단, 어떤 메소드도 정적이지 않다!)  
	-> 구조적인 제약을 부여하지 않고도 단일성있는 행위를 강제  

	Monostate => Singleton (O), Singleton => Monostate(X)  

Chap 17. 널 오브젝트 패턴  
 -> null 검사의 필요 제거, 코드 단순화  

 (ex) interface Employee에 대해  
      일반적인 구현 EmployeeImplementation 외에  
      null 처리를 위한 NullEmployee 를 통해 실패한 경우에도 항상 유효한 객체를 반환하도록 함  
 (*추가) org.elasticsearch.cluster.ClusterName: DEFAULT  
 (*추가) BackOfficeUserHolder: BackofficeUser.undefinedUser()  
