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

