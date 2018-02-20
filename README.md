# Peanut3D
==========================

![SparkFun MP3 Player Shield](https://github.com/makezonefablab/Peanut3D/blob/master/img/feature1.jpg)  

[*프린터 적용 예시 - 메이크존 사이트 바로가기*](http://makezone.co.kr/blog/2015/12/07/peanuti3/)

소개
--------------
피넛i3에 사용되었던 콘트롤러 보드입니다.
한국에서 개발되어 직접 제작하였고요, 안정된 성능을 보여주며 쉽게 프린터에 적용 가능하도록 되어 있습니다.
잘알려진 marlin 소스를 사용하였고, megatronix라는 보드를 참고하여 제작되었습니다.

[*메가트로닉스 Wiki 바로가기*](http://reprap.org/wiki/Megatronics_2.0)


설정
--------------
![ScreenShot](https://github.com/makezonefablab/Peanut3D/blob/master/img/wiring.jpg)


 **사용툴 - Arduino IDE 1.6.5
 
 **보드형식 - Arduino Mega
 
 사용툴은 아두이노 1.6.5버전을 사용하였습니다.
 
 신 버전은 소스호환에 에러가 있어 현재는 사용하지 않고요, 반드시 위의 버전을 다운받아 사용하는게 좋습니다.
 
 src폴더에 있는 파일을 다운로드하여 바로 컴파일하여 에러가 없는지 확인 합니다. 컴파일 시 보드형식은 mega보드를 선택하여야 합니다. 피넛보드는 Atmega2560을 기반으로 제작되고 부트로더 또한 메가용 부트로더가 올라가 있습니다.
 
 
수정
--------------
**Configuration.h 만 수정하면 현재 자신의 프린터에 맞는 설정을 할 수 있습니다.

> 1. 주요 위치
```
~ $ cd /home/mediaflow
~ $ wget https://github.com/makezonefablab/TinyFarmer-HUB/tree/master/src/TinyfarmerHubWeb.zip
~ $ wget https://github.com/makezonefablab/TinyFarmer-HUB/tree/master/src/TinyfarmerHub.zip
~ $ tar xvf TinyfarmerHub.zip
~ $ tar xvf TinyfarmerHubWeb.zip
```

제작영상
--------------
[![ScreenShot](https://raw.githubusercontent.com/makezonefablab/HungryBot/master/img/vimeo.png)](https://vimeo.com/102814242)


