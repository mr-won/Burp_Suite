회사에서 업무에 필요한 Burp Suite 버프 스위트 프로그램 사용법을 정리하고자 한다.
IGLOO Corp, Won Chi Hyun
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
![image](https://github.com/user-attachments/assets/cdd71cec-0e16-456f-921d-a4ab98e9f669)
open browser proxy 문구 확인
```
Proxy > Intercept 화면에서 Intercept is off를 눌러 Intercept is on으로 변경 시 트래픽 수정이 가능합니다.
```

```
https://www.hira.or.kr/main.do 심평원 주소 입력 -> 443으로 리다이렉팅
리다이렉팅을 막아서 포트 80으로 검색하고 싶을 때 어떻게 해야할까
```

심평원 사이트 버프에서 잡고있기
```
HTTP/1.1 200 OK
Date: Sun, 26 Jan 2025 14:18:37 GMT
Content-Type: text/css
Content-Length: 1893
Connection: close
Last-Modified: Fri, 24 Jan 2025 04:09:59 GMT
ETag: "67931297-765"
Expires: Mon, 27 Jan 2025 14:18:37 GMT
Cache-Control: max-age=86400
Cache-Control: public
Accept-Ranges: bytes
Strict-Transport-Security: max-age=15724800; includeSubDomains

/* Slider */
.slick-slider
{
    position: relative;

    display: block;
    box-sizing: border-box;

    -webkit-user-select: none;
       -moz-user-select: none;
        -ms-user-select: none;
            user-select: none;

    -webkit-touch-callout: none;
    -khtml-user-select: none;
    -ms-touch-action: pan-y;
        touch-action: pan-y;
    -webkit-tap-highlight-color: transparent;
}

.slick-list
{
    position: relative;

    display: block;
    overflow: hidden;

    margin: 0;
    padding: 0;
}
.slick-list:focus
{
    outline: none;
}
.slick-list.dragging
{
    cursor: pointer;
    cursor: hand;
}

.slick-slider .slick-track,
.slick-slider .slick-list
{
    -webkit-transform: translate3d(0, 0, 0);
       -moz-transform: translate3d(0, 0, 0);
        -ms-transform: translate3d(0, 0, 0);
         -o-transform: translate3d(0, 0, 0);
            transform: translate3d(0, 0, 0);
}

.slick-track
{
    position: relative;
    top: 0;
    left: 0;

    display: block;
    margin-left: auto;
    margin-right: auto;
}
.slick-track:before,
.slick-track:after
{
    display: table;

    content: '';
}
.slick-track:after
{
    clear: both;
}
.slick-loading .slick-track
{
    visibility: hidden;
}

.slick-slide
{
    display: none;
    float: left;
    height: 100%;
    min-height: 1px;
}
[dir='rtl'] .slick-slide
{
    float: right;
}
.slick-slide img
{
    display: block;
}
.slick-slide.slick-loading img
{
    display: none;
}
.slick-slide.dragging img
{
    pointer-events: none;
}
.slick-initialized .slick-slide
{
    display: block;
}
.slick-loading .slick-slide
{
    visibility: hidden;
}
.slick-vertical .slick-slide
{
    display: block;

    height: auto;

    border: 1px solid transparent;
}
.slick-arrow.slick-hidden {
    display: none;
}
```
![image](https://github.com/user-attachments/assets/c6cdcfb1-0464-4e47-9722-fa1244672481)

```
raw data repeater에 넣고 configuration -> 심평원 공인 ip 주소 103.206.74.1 넣고 send
```
![image](https://github.com/user-attachments/assets/07919ef2-9794-4a99-bca1-3063baa3bb4e)
```
status 410 유효성 없음.
```
Request, Response intercept 확인

## Burp Suite(버프스위트) Proxy 설정 방법
![image](https://github.com/user-attachments/assets/a5d79684-cfff-443c-8ab5-1c53e31f600e)
이번에는 버프스위트 기능중 Proxy에 대해서 알아보도록 하겠습니다.Proxy는 버프스위트를 사용할때 기본으로 설정해야 하는 도구입니다.
Proxy는 사용자 브라우저와 대상 응용프로그램 사이에서 웹 프록시 서버로 운영되며 그 중간에서 주고받는 패킷을 가로채거나 확인, 수정 등을 할 수 있습니다.   

![image](https://github.com/user-attachments/assets/d31d0887-8ec0-4479-8ae6-c9fb3cb06ad6)
버프스위트에서 Proxy를 사용하려면 Proxy 설정을 해주어야 하는데 설정 방법은Proxy -> Options -> Proxy Listeners 부분을 설정해 주시면 됩니다.    
기본으로 본인이 사용하는 PC를 Proxy 서버로 사용을 하기 위해 127.0.0.1(루프백 IP)의 8080 포트를 사용하도록 설정하였습니다.    

![image](https://github.com/user-attachments/assets/c077e025-8733-438c-8aea-62493d1dbd72)
해당 화면은 제 블로그에 접속했을때의 패킷을 잡은 화면입니다. 이처럼 Proxy가 활성화 되면 Intercept 탭에서 주고받은 패킷을 확인 할 수 있습니다.        
Intercept is on 상태로 설정이 되어 있어야지 기능이 활성화 되니 이점 유의하시기 바랍니다.     
이 상태에서 Forward 버튼을 클릭하면 서버나 브라우저에 메시지를 전송하고 Drop 버튼을 클릭하면 해당 메시지를 담은 패킷을 버립니다.      
(직접 해보면서 웹페이지 접속을 했을때 패킷이 어떻게 잡히고 화면이 어떻게 바뀌는지 보시기를 추천드립니다.)     
버프스위트 프록시 설정 -> 인터넷 브라우저 프록시 설정 -> Intercept is on -> 웹페이지 접속(패킷확인) -> Forward 버튼을 클릭 하면서 확인 -> Intercept is off -> 인터넷 브라우저 프록시 설정 해제      

![image](https://github.com/user-attachments/assets/b4601043-c0c6-44a9-aff7-c3da49d545f0)
Action 버튼은 현재 가로챈 패킷으로 수행할 수 있는 기능을 보여주며, 해당 창에서 마우스 오른쪽 버튼을 클릭하여도 확인할 수 있습니다. 
![image](https://github.com/user-attachments/assets/16d10e2e-e11b-4ffa-a99b-4d1b3e4f2a83)
HTTP history 탭은 Target의 Site map와 마찬가지로 프록시를 통해서 전달된 값들을 기록하고, HTTP 의 모든 요청/응답을 확할 수 있으며 다양한 정보도 함께 출력됩니다.

![image](https://github.com/user-attachments/assets/2d6adfec-df95-470a-b184-660ed912ccaa)
HTTP history에서도 Site map과 마찬가지로 각 항목의 요청과 응답의 내용일 확인 할수 있습니다. 
Request / Response 탭 WebSockets history 탭은 프록시를 통해서 전달되는 WebSocket의 모든 요청과 응답을 기록하고 확인할수 있습니다.
Options 탭에도 여러가지 항목별 기능이 있는데 이 기능들을 살펴 보면
- 1. Proxy Listeners- 웹 브라우저로 들어오는 연결을 수신하는 프록시 서버를 설정할수 있고, 브라우저에서 요청하거나 응답받는 모든 항목을 모니터링하고 가로챌수 있다.
- 2. Intercept Client Requests- 클라이언트가 요청하는 패킷을 가로채는 규칙을 지정할 수 있다.
- 3 Intercept Server Responses- 서버에서 응답하는 패킷을 가로채는 규칙을 지정할 수 있다.
- 4. Intercept WebSockets Messages- 가로채려는 항목에 WebSocket을 추가할 것인가 설정한다.
- 5. Response Modification- 서버에서 전달하는 응답을 정해진 내용에 따라 자동으로 수정해 주는 옵션이다.
- 6. Match and Replace- Proxy를 통한 요청과 응답에 일치하는 항목이 있으면 자동으로 수정한다.
- 7. SSL Pass Through- Proxy를 지나는 서버에서 SSL연결을 사용하는 경우 가로채지 않고 그냥 통과 시키도록 설정 하는 옵션
- 8. Miscellaneous- Proxy 동작의 세부적인 설정을 할수 있는 옵션그럼 Proxy에 대해서는 여기서 마무리 하도록 하겠습니다.

## Burp Suite(버프스위트) 메뉴 Target

## Burp Suite(버프스위트) 메뉴 Proxy

## Burp Suite(버프스위트) 메뉴 Spider

## Burp Suite(버프스위트) 메뉴 Scanner

## Burp Suite(버프스위트) 메뉴 Intruder

## Burp Suite(버프스위트) 메뉴 Repeater

## Burp Suite(버프스위트) 메뉴 Sequencer

## Burp Suite(버프스위트) 메뉴 Decoder

## Burp Suite(버프스위트) 메뉴 Comparer

## Burp Suite(버프스위트) 메뉴 Extender + SQLMAP.py 설치

## Burp Suite(버프스위트) 메뉴 Extender + SQLMAP.exe 설치

## 웹 프록시 도구 사용 시 루프백 주소(127.0.0.1) 사용 및 설정하기

## BURP SUITE(버프스위트) Convert Selection 기능 사용하기

취약점 점검이나 모의해킹을 하다 보면 SQL Injection, XSS 등 테스트를 할 경우 싱글 쿼터가 필터링되어 이를 아스키로 변환 후 테스트를 해야 하는 경우가 있습니다. 자동화 공격 시에는 쉽게 공격이 가능하지만 수동으로 테스트 할시에는 일일이 아스키코드표를 참조하여 변환하는 일이 번거롭고 불편할 것입니다.          
 
여기에서는 버프스위트 (Burp Suite)를 통하여 조금 더 쉽게 변환하는 방법을 알아보도록 하겠습니다.      
![image](https://github.com/user-attachments/assets/6f702ee9-f83f-41bb-9818-7ca1f1620752)         
버프 스위트에서 변환하고자 하는 값을 선택하고 마우스 우클릭을 한 후 "Convert selection -> Construct string"을 선택하여 확인해 보면 JavaScript, MS SQL, Oracle, MYSQL에 대하여 String 값으로 변환이 가능한 것을 확인할 수 있습니다.     

![image](https://github.com/user-attachments/assets/71714717-970a-42c2-9f1c-3f9f8a36597e)             
       
예시)
<script>alert('XSS TEST')</script>      
<script>alert(String.fromCharCode(88,83,83,32,84,69,83,84))</script>  // XSS TEST, 아스키 A 65 B 66 C 67



