# 채팅 서비스 운영
- 친구와 채팅을 제공하는 서비스 입니다.
## repo
- [채팅 클라이언트 서비스](https://github.com/sangholim/talk-client-server-2023)
- [회원 서비스](https://github.com/sangholim/member-service-2023)
- [채팅 메세지 자원 서비스](https://github.com/sangholim/message-service-2023)
- [계정 인증 서비스](https://github.com/sangholim/spring-authorization-server-2023)
## 기능
- 통합 인증 시스템 적용
  - 계정 인증 서비스를 통해 승인 권한을 부여하고, 서비스를 보호하는 인증 시스템을 제공합니다 
  - 승인 대상은 계정이고, OIDC, OAUTH2 프로토콜을 지원합니다
  - redis 를 통하여 인증 정보를 관리합니다
  - 회원의 계정 정보를 제공합니다
- 회원 서비스
  - 프로필, 친구, 채팅방, 채팅 참가자 정보를 제공합니다
  - REST API 를 통해서 정보를 접근할수 있습니다
  - 정보를 접근시 인증 서비스의 승인 권한이 필요합니다
  - RDBMS 데이터 베이스를 처리하는 서버 입니다
- 메세지 서비스
  - 채팅방 메세지 정보를 제공합니다
  - Reactive Stream library `rsocket` 을 통하여, \
    클라이언트로 메세지 보내는 경우: `request-channel` \
    클라이언트로 부터 메세지 받는 경우 `request-stream` 데이터 모델링으로 구현하였습니다
  - 클라이언트루 부터 메세지를 보내는 경우에서 메세지를 수신후, mongodb 에 저장된 경우 \
    chage-stream 통하여 받은 이벤트를 발생 시킨후, 클라이언트로 메세지를 발송합니다
- 채팅 클라이언트 서비스
  - 로그인, 프로필, 친구, 채팅 서비스의 UI 기능을 구현한 front-end 서비스를 제공합니다
## 구성도
![image](https://github.com/sangholim/deploy-2023/assets/55565835/f036ec07-bdbb-45c3-91a4-b94d4cef0dfd)
