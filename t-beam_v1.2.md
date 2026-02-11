# LILYGO T-Beam v1.2

## Board information [1]

ESP32 LoRA Development Board GNSS NEO-6M

Features:
  * Lora module: SX1262 868MHz
    * ESP32 SoC with built-in WiFi & Bluetooth, 4MB flash
  * GPS module:  GPS-NEO-6M
  * PMU (power management unit): AXP2101, v1.2
  * Power: USB or Li-Ion flat top battery (18650B, 18x65mm)
  * Serial: CH9102
  * Buttons: 3x (power, IO38, reset)
  * Firmware: SoftRF, [Github](https://github.com/Xinyuan-LilyGO/LilyGo-LoRa-Series)

## 1. Getting started

**Prerequsities**:
  * Linux host with PlatformIO in VSCode

Steps, mainly from [3] and [4]:
  * Download the official [Github](https://github.com/Xinyuan-LilyGO/LilyGo-LoRa-Series) repo: ```$ git clone https://github.com/Xinyuan-LilyGO/LilyGo-LoRa-Series```
  * Change to the local repo directory: ```$ cd LilyGo-LoRa-Series/```
  * Start the VSCode: ```$ code .```
    * VSCode will open the **platform.ini** file (project configuration file)
    * Modify following settings:
      * In [platformio] enable "default_envs = T_BEAM_SX1262" and disable **T_BEAM_BPF**
      * Enable the **src_dir = examples/TBeamFactory** example and disable **examples/BPFFactory**
      * In [env:T_BEAM_1262] change **board = esp32dev** to **board = ttgo-t-beam**
      * :exclamation:  In [env] do not modify **framework = arduino** -> refer to issue [#278](https://github.com/Xinyuan-LilyGO/LilyGo-LoRa-Series/issues/278)
     * Build the example (CTL+ALT+B)

## 2. Projects

| Firmware | Framework | What is done | How is it tested | Local repo in $PRV_PRJ, branch | Status |
| --- | --- | --- | --- | --- | --- |
| [LilyGo](https://github.com/Xinyuan-LilyGO/LilyGo-LoRa-Series) | arduino | modify 'platform.ini' | run 'TBeamFactory' example, [#2](https://github.com/ebold/lora/issues/2) | github/LilyGo-LoRa-Series, t-beam-v1.2 | pass ✅ |
| [esp-idf](https://github.com/espressif/esp-idf) | esp-idf | - | run 'hello world' example, [#6](https://github.com/ebold/lora/issues/6) | github/esp-idf, master | pass ✅ |
| [Zephyr](https://github.com/zephyrproject-rtos/zephyr) | platformio | - | run 'blinky' example, [#8](https://github.com/ebold/lora/issues/8) | zephyrproject/zephyr, t-beam-v1.2 | fail :x: |
| [Meshtastic](https://github.com/meshtastic/firmware) | arduino + platformio | modify 'variants/esp32/tbeam/variant.h' | connect via Bluetooth, connect to MeshHessen, [#10](https://github.com/ebold/lora/issues/10) | github/meshtastic/firmware, t-beam-v1.2 | pass ✅ |

## Sources
[1] [Lilygo web site](https://www.lilygo.cc/products/t-beam-softrf?variant=43170155692213)

[2] [Stefan's webblog](https://www.fambach.net/lilygo-t-beam/)

[3] [Liligo LoRa Series](https://github.com/Xinyuan-LilyGO/LilyGo-LoRa-Series)

[3] [TTGO T-Beam in PlatformIO](https://docs.platformio.org/en/latest/boards/espressif32/ttgo-t-beam.html)
