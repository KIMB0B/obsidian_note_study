# 정의

> 사용자 입력의 데이터 바인딩 과정에서 발생하는 오류를 관리하고 추적하는 인터페이스
> 이를 통해 입력 데이터의 유효성 검사 결과를 저장하고, 필요할 때 오류를 쉽게 처리할 수 있도록 도와줌

>[!warning] 주의사항
> Controller의 함수의 매개변수로 들어가는 BindingResult는 [[@ModelAttribute]]이 붙은 매개변수 바로 뒤에 와야한다. 
> ex) public String a