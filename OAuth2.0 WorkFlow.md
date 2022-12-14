# Oauth2.0이란?
Third-Party 프로그램에서 리소스 소유자를 대신하여 리소스 서버에서 제공하는 자원에 대한 접근 권한을 위임하는 방식

이 말을 간단하게 설명하자면 구글, 카카오, 네이버 등등의 인증시스템이라고 보면 된다.

## Access Token
  리소스 서버에서 리소스 소유자의 보호된 자원을 획득할 때 사용되는 만료 기간이 있는 토큰

## Refresh Token
  Access Token 만료 시 이를 갱시하기 위한 용도롤 사용하는 Token입니다. Refresh Token은 일반적으로 Accss Token보다 만료 기간이 김


1. 권한 부여 승인 방식
  가장 많이 사용되는 방식이 되며 기본이 되는 방식

  ![image](https://user-images.githubusercontent.com/65396939/207488049-04abb17d-d2a8-4d81-b9d4-e587b6ba7917.png)


2. Implicit Grand(암묵적 승인 방식)
  자격증명을 안전하게 저장하기 힘든 클라이언트에게 최적화된 방식(-> JS등의 스크립트 언어 기반 브라우저)
  
  ![image](https://user-images.githubusercontent.com/65396939/207487542-57afd12e-f89e-4cdb-87b9-f8a1b76ff969.png)
  
  그림에서 볼 수 있듯이 권한 부여 승인 과정에서 차이를 보이고 있다. Implicit Grand 같은 경우 권한 부여 승인 요청 시 response_type을
  token으로 설정하여 요청. 이후 클라이언트는 권한 서버에서 제공하는 브라우저를 띄워 출력하게 되며 로그인이 완료되면 권한 서버는 인증 
  코드가 아닌 Access Token을 redirect_url로 바로 전달
  
  
3. Resource Owner Password Credentials Grant
