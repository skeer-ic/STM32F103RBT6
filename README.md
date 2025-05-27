# STM32F103RBT6
Discover the top 5 real-world projects you can build using the STM32F103RBT6 microcontroller. From motor control to IoT systems, learn how this ARM Cortex-M3 MCU powers advanced embedded applications.
The STM32F103RBT6 is a 32-bit ARM Cortex-M3 microcontroller from STMicroelectronics. With 128KB of Flash, 20KB SRAM, rich peripheral support, and a 64-pin LQFP package, it's perfect for intermediate to advanced embedded systems. Below are five inspiring projects that showcase the power and flexibility of this MCU.

1. Motor Speed Control System with PWM and Encoder
Using the STM32F103RBT6’s advanced timer capabilities, you can build a precise DC motor controller. PWM outputs adjust motor speed, while an incremental rotary encoder provides real-time feedback. This is ideal for robotics and industrial control systems.

Peripherals used: TIM1, TIM2, GPIO, EXTI
Tools: STM32CubeIDE, ST-Link V2
// Example: Basic PWM on TIM2 Channel 1
TIM_OCInitTypeDef TIM_OCInitStructure;
TIM_OCInitStructure.TIM_OCMode = TIM_OCMode_PWM1;
TIM_OCInitStructure.TIM_OutputState = TIM_OutputState_Enable;
TIM_OCInitStructure.TIM_Pulse = 500;
TIM_OCInitStructure.TIM_OCPolarity = TIM_OCPolarity_High;
TIM_OC1Init(TIM2, &TIM_OCInitStructure);
2. IoT Sensor Node with WiFi and MQTT
Connect the STM32F103RBT6 to an ESP8266/ESP01 over UART to create a low-cost IoT device. Collect sensor data using the ADC and transmit readings to the cloud using MQTT. Great for home automation and environmental monitoring projects.

Peripherals used: ADC1, USART1
Cloud platforms: ThingSpeak, HiveMQ, Mosquitto
// Example: Send serial data to ESP8266
char msg[] = "AT CIPSEND=18\r\n";
HAL_UART_Transmit(&huart1, (uint8_t*)msg, strlen(msg), HAL_MAX_DELAY);
3. USB HID Device – Custom Keyboard or Mouse
With its USB Full-Speed peripheral, STM32F103RBT6 can emulate a Human Interface Device. Create a custom macro keyboard, game controller, or mouse. You’ll work with USB descriptors and endpoint management.

Peripherals used: USB FS, GPIO
Tools: STM32 USB Device Library, STM32CubeMX
// Example: HID report descriptor snippet
0x05, 0x01, // Usage Page (Generic Desktop)
0x09, 0x06, // Usage (Keyboard)
0xA1, 0x01, // Collection (Application)
// ... continue descriptor structure
4. Real-Time Data Logger with SD Card and TFT Display
Build a system that reads analog data (like temperature, voltage, or current), logs it to an SD card, and displays it in real-time on a TFT screen. This combines SPI, ADC, and file system handling (FATFS).

Peripherals used: SPI1, ADC1, GPIO
Libraries: FATFS, uGFX or TouchGFX
5. RS485-Based Industrial Communication Node
Design a robust industrial communication device using STM32F103RBT6 with an external MAX485 transceiver. Support Modbus RTU protocol over RS485 for real-world machine integration.

Peripherals used: USART2, GPIO, TIM4
Use case: PLCs, smart meters, sensor networks
Bonus: STM32F103RBT6 vs STM32F103C8T6
Both MCUs share many similarities, including the same core and peripherals. However, STM32F103RBT6 offers:

Double the Flash memory (128KB vs. 64KB)
More GPIOs due to 64-pin package
Greater flexibility for multitasking and bootloader integration
Conclusion
The STM32F103RBT6 microcontroller is an excellent choice for both educational and commercial embedded development. Its performance, I/O capabilities, and ST’s development ecosystem make it perfect for diverse project types. Whether you're logging data, controlling motors, or building a USB peripheral, this chip delivers.

Download the official STM32F103RBT6 datasheet to learn more and start building!

Frequently Asked Questions (FAQ)
What is the difference between STM32F103RBT6 and STM32F103C8T6?
The STM32F103RBT6 offers 128KB of Flash and a 64-pin package, while the STM32F103C8T6 has 64KB Flash and a 48-pin package. RBT6 provides more GPIOs and code space for complex applications.

Can I use STM32F103RBT6 with STM32CubeIDE and ST-Link?
Yes. STM32F103RBT6 is fully compatible with STM32CubeIDE and can be programmed using ST-Link V2. The MCU is supported in STM32CubeMX for graphical configuration.

What development boards use the STM32F103RBT6?
Several Blue Pill-style or custom STM32 boards include the STM32F103RBT6. You can also find it on some STM32F1 Nucleo boards and industrial controller modules.
