* 처음에 요청이 들어오면 AuthenticationFilter(UsernamePassAuthenticationFilter)를 거친다.

* 요청에 따른 UsernamePasswordAuthenticationToken을 생성한다. (Authentication 인터페이스의 구현체다.)

* UsernamePasswordAuthenticationToken(통상 Token이라고 하겠다.)을 AuthenticationManager에게 이 Token은 올바른 유저인지 물어본다.

* AuthenticationManager는 1개 이상의 AuthenticationProvider(통상 A-Provider)를 갖고 있는데, A-Provider는 Token 객체를 적절히 판단하여 인증처리를 할려고 한다.

* A-Provider가 우리가 직접 구현한 서비스(UserDetailsService 구현 클래스)에 해당 유저에게 인증요청을 보내 사용자 정보를 가져온다.

* UserDetailsService 구현 클래스는 사용자 정보를 가져와 UserDetails를 반환한다.

* Provider는 UserDetailsService에서 반환된 UserDetails와 클라이언트가 제공한 인증정보(Token)를 대조해서 이용자가 정당한 사용권한을 가지고 있는지 확인한다.
그리고 SecurityContext에 저장한다.
