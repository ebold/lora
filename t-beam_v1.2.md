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
      * Enable the **T3_S3_V1_2_SX1262** environment (disable **T_BEAM_BPF**)
      * Enable the **examples/T3S3Factory** example (disable **examples/BPFFactory**)
      * Add **framework = espidf** under the **[env:T3_S3_V1_2_SX1262]** config item (PlatformIO will download the espressif32@6.7.0 if it's specified under [env])
     * Build the example => compilation fails indicating to SD.h dependency :x:

## Sources
[1] [Lilygo web site](https://www.lilygo.cc/products/t-beam-softrf?variant=43170155692213)

[2] [Stefan's webblog](https://www.fambach.net/lilygo-t-beam/)

[3] [Liligo LoRa Series](https://github.com/Xinyuan-LilyGO/LilyGo-LoRa-Series)

[3] [TTGO T-Beam in PlatformIO](https://docs.platformio.org/en/latest/boards/espressif32/ttgo-t-beam.html)
