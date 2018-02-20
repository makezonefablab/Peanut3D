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


본 보드는 Peanuti3 제품에 사용되었던 보드입니다.
![Peanuti3](https://github.com/makezonefablab/Peanut3D/blob/master/img/IMG_4490.jpg)  




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

본 헤더파일에서 아래의 항목들만 수정하면 자신의 프린터보드에 적용가능합니다. 아래의 항목을 확인하여 수정바랍니다.

> 1. 보드 선택 - Megatronics v2.0 선택
```
#ifndef MOTHERBOARD
#define MOTHERBOARD 701
#endif

```

> 2. 익스투루더 힛터 및 베드 온도 최대값 설정 
```
#define HEATER_0_MAXTEMP 220 // 현재 220도를 넘으면 자동 리셋 걸리게 설정
...
#define BED_MAXTEMP 90       // 베드 온도는 90도

```

> 3. 베드에 공급되는 전원 최대로 설정 - 베드는 12V전원과 직결되는데 PWM값을 Full로 설정하여 최대값까지 쓸 수 있도록 설정
```
#define MAX_BED_POWER 255 // limits duty cycle to bed; 255=full current
```

> 4. 익스투루더 X,Y,Z 움직임 영역 설정 - 베드의 크기에 맞게 설정
```
// Travel limits after homing
#define X_MAX_POS 120
#define X_MIN_POS 0
#define Y_MAX_POS 150
#define Y_MIN_POS 0
#define Z_MAX_POS 120
#define Z_MIN_POS 0
```

> 5. 각 축 스텝모터 회전대비 이송값 설정 (아주 중요함)
```
#define DEFAULT_AXIS_STEPS_PER_UNIT   {79.78, 79.73, 160*16, 9.28346*16} // X, Y, Z,  extruding 값 순으로 설정

```

이송값 계산은 1mm 이송되는데 필요한 스텝모터에 주어지는 스텝값입니다. 현재 설정은 x,y 축은 79.78스텝을 주면 1mm,  z축은 160x16스텝, 그리고, 필라멘트 1mm 뽑아내는데 9.28346 x 16 스텝을 주어야 합니다.  이는 모두 peanuti3 기준이므로 자신의 프린터에 맞게 계산하여 정확한 값을 설정하여야 합니다.



제작영상
--------------
[![ScreenShot](https://raw.githubusercontent.com/makezonefablab/HungryBot/master/img/vimeo.png)](https://vimeo.com/102814242)


