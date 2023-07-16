
Недавно QMK обновилась и при компиляции прошивки может выскакивать ошибка. Так что лучше все обновить.

Заходим в QMK MSYS и обновляемся

```
cd qmk_software

git pull --recurse-submodules
```

После этого QMK обновится до версии Firmware 0.21.6

И теперь если мы будем компилировать наш старый код у нас будет выдаваться ошибка

```
☒ bastardkb/charybdis/3x6/v2/promicro: RGB_DI_PIN in config.h is no longer a valid option and should be replaced with WS2812_DI_PIN or APA102_DI_PIN
Making bastardkb/charybdis/3x6/v2/promicro with keymap default

☒ bastardkb/charybdis/3x6/v2/promicro: RGB_DI_PIN in config.h is no longer a valid option and should be replaced with WS2812_DI_PIN or APA102_DI_PIN
Generating: .build/obj_bastardkb_charybdis_3x6_v2_promicro_default/src/info_deps.d                  [OK]
☒ bastardkb/charybdis/3x6/v2/promicro: RGB_DI_PIN in config.h is no longer a valid option and should be replaced with WS2812_DI_PIN or APA102_DI_PIN
avr-gcc.exe (GCC) 8.5.0
Copyright (C) 2018 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
```

Эта ошибка выдается из-за того, что в QMK сейчас поменялись переменные. Раньше использовалась RGB_DI_PIN, сейчас WS2812_DI_PIN.

Поэтому надо поменять все в нашем конфиге
