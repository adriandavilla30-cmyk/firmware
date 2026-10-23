# ES3C40P (LCDWIKI / Hosyond 4.0-inch ESP32-S3)

**Experimental, untested device port. Do not flash until the firmware builds and hardware settings are reviewed.**

This board profile was adapted from Bruce's ES3C28P profile while leaving Bruce's existing features and devices unchanged.

Hardware reference: https://www.lcdwiki.com/4.0inch_ESP32-S3_Display

- ESP32-S3 N16R8: 16MB flash, 8MB OPI PSRAM.
- Display: ST7796S, 320 x 480, SPI pins CS=10, DC=46, CLK=12, MOSI=11, MISO=13; shared reset, backlight=45.
- Touch: FT6336U, I2C SDA=16, SCL=15, INT=17, RESET=18, address 0x38 (verify on board).
- SD card: SDIO CLK=38, CMD=40, DAT0=39; remaining DAT1=41 DAT2=48 DAT3=47.
- ES8311 audio codec, FM8002E amplifier enable GPIO1, I2S clocks GPIO4/5/7, codec GPIO6/8. Verify audio orientation and codec behavior before use.
- Battery sensing ADC=9; RGB LED=42; BOOT=0; expansion GPIO2, GPIO3, GPIO14, GPIO21.
- Port inherits most ES3C28P HAL code and peripherals; experimental display orientation, color inversion, touchscreen orientation, sound and GPIO configuration all require actual-device testing.
- CC1101, NRF24L01, IR and other radio features depend on additional hardware and correct pin assignments; their UI presence does not imply onboard capability.

For the ES3C40P branch, `platformio.ini` defaults to `ES3C40P`. The original Bruce main branch and ES3C28P profile are untouched. Keep a verified full-flash backup of factory firmware before uploading.
