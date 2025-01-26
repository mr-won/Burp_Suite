회사에서 업무에 필요한 Burp Suite 버프 스위트 프로그램 사용법을 정리하고자 한다.
```
Burp Suite: Burp Suite는 브라우저와 서버 간의 HTTP/S 트래픽을 가로채고 수정하기 위한 웹 프록시 기능을 포함하는 강력한 웹 애플리케이션 보안 테스트 도구입니다. 
이를 통해 사용자는 트래픽의 다양한 측면을 분석, 수정 및 테스트할 수 있으므로 보안 전문가 및 개발자에게 널리 사용됩니다.
```
[Burp Suite Download](https://portswigger.net/burp/releases/professional-community-2023-3-5?requestededition=community&requestedplatform=)
![image](https://github.com/user-attachments/assets/581ad742-0e30-4534-a23f-a297db3aa7e2)
```
그냥 Next 누릅니다. 
```
![image](https://github.com/user-attachments/assets/e74fe9c1-cd07-4344-9234-4db92b79a874)
```
그냥 바로 Start 버튼 누릅니다.
```
![image](https://github.com/user-attachments/assets/72cced10-71e8-4b3a-b823-89c38a905303)
```
첫 화면입니다.

Proxy > Proxy settings 선택합니다.
```
![image](https://github.com/user-attachments/assets/4c8d6ccd-02f0-487c-82b5-a6f47f16cad6)
```
Tools > Proxy > Proxy listeners > interface에서 IP:PORT 세팅을 확인합니다. (기본값: 127.0.0.1:8080)
```
![image](https://github.com/user-attachments/assets/c5960d93-027a-4533-999b-05b9634efbda)
```
Windows에서 '프록시 설정 변경' 선택합니다.
수동 프록시 설정 메뉴에서 주소와 포트를 burp 설정과 동일하게 설정합니다.
```
[Burp Suite CA Certificate](http://burp/)
![image](https://github.com/user-attachments/assets/1ae0d87d-c725-4948-9b74-9ac76dd90d3a)
```
프록시 기본 설정 후 인터넷 브라우저에서 http://burp/ 입력합니다.

접속된 페이지에서 CA Certificate 선택 후 인증서 다운로드합니다.
```
![image](https://github.com/user-attachments/assets/9b9e5926-be1a-43bf-bc5a-aa5d8fb4ad89)
```
인증서 실행 후 인증서 설치를 선택합니다.
로컬 컴퓨터 선택 후 다음을 선택합니다.
```
![image](https://github.com/user-attachments/assets/b3e26d5e-71f7-4c05-b9ec-40c603f20edf)
![image](https://github.com/user-attachments/assets/81d5a7cb-e71a-4cf1-93fe-4ea93d5cdf4a)
```
찾아보기 선택 후 '신뢰할 수 있는 루트 인증 기관' 선택 후 다음을 선택합니다.
마침 선택 후 인증서 설치를 완료합니다.
```
![image](https://github.com/user-attachments/assets/3087697f-2b31-4901-b8ef-ff14f22ca96c)
```
Tools > Proxy > Request interception rules 메뉴에서 intercept requests based on the following rules 선택합니다.

Tools > Proxy > Response interception rules 메뉴에서 intercept requests based on the following rules 선택합니다.

해당 옵션을 선택해야 Request, Response 모두 Intercept가 가능합니다.
```

```
Proxy > Intercept 화면에서 Intercept is off를 눌러 Intercept is on으로 변경 시 트래픽 수정이 가능합니다.
```

Request, Response intercept 확인
