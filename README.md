# stm32helloworld
This repository documents the details of the UART project on STM32F103C8T6 MCU together with the STM32CubeIDE, an open-source C/C++ development platform for STM32 microcontrollers and microprocessors.

We are required to program an STM32 MCU using open-source STM32CubeIDE in C language to print the "Hello World" message and the value of the 4-bit DIP switch on the terminal once the switch value is changed. A C code is included in this repository for reference.

stm32helloworld contains the project that uses pins GPIOB-PIN12, GPIOB-PIN13, GPIOB-PIN14 and GPIOB-PIN15 to read DIP switch input and GPIOA-PIN9 and GPIOA-PIN10 as UART interface. Also, this project uses GPIOD-PIN0 and GPIOD-PIN1 for teh RCC controller.



## Group Members (Driven Raven)
1. Ashraf Aminin bin Arman Alim
2. Izzat bin Idris



## Project Prerequisites
1. STM32CubeIDE software
2. STM32 MCU
3. Putty



## Hardware Requirements
1. STM32F103C8T6 Board Blue Pill
2. ST-Link V2 Programming Unit
3. CH340 USB to TTL Converter UART Module 
4. DIP switch - 1 
5. 1k ohm resistors - 4
6. 10k ohm resistors - 4



## Project Procedures
1. Start a new STM32 project on STM32CubeIDE and input part number according to the MCU being used.

![Semantic description of image](/image/pic1.jpg)


<br/>
<br/>


2. Input valid project name and click finish.

![Semantic description of image](/image/pic2.png)


<br/>
<br/>


3. Assign GPIOB-PIN12, GPIOB-PIN13, GPIOB-PIN14 and GPIOB-PIN15 as the GPIO input by clicking the pin in the pinout view. 

![Semantic description of image](/image/pic3.png)


<br/>
<br/>


4. Right-click the Connectivity > USART1 and set the mode as ‘Asynchronous’.

![Semantic description of image](/image/pic9.png)


<br/>
<br/>


5. Right-click the System Core > RCC and then click ‘Crystal/Ceramic Resonator’ in from the High Speed Clock feature. This will enable the RCC external clock source.

![Semantic description of image](/image/pic10.png)


<br/>
<br/>


6. Right-click the Clock Configuration found at the top and set HCLK to 72 MHz.

![Semantic description of image](/image/pic11.png)


<br/>
<br/>


7. Only a section of the generated code is modified. In this project, the executing loop is added with built-in functions to print "Hello World" and the value of the 4-bit DIP switch on the terminal once the switch value is changed.

![Semantic description of image](/image/pic4.png)

<br/>
<br/>


8. Under project properties(Right click project, select properties), select to convert builds to binary and hex files under MCU Post build outputs. Apply the changes.

![Semantic description of image](/image/pic6.png)


<br/>
<br/>


9. Start building the debug for the current project.

![Semantic description of image](/image/pic5.png)


<br/>
<br/>


10. Connect the STM32 with all the components as shown below.

![Semantic description of image](/image/schematic.png)


<br/>
<br/>


11. STM32 ST-LINK Utility is utilized to program the SM32F103C8T6 MCU through an ST-LINK V2. The generated binary/hex files are opened through this application.

![Semantic description of image](/image/pic7.png)


<br/>
<br/>


12. Connect the STM32 MCU through the USB port with the ST-LINK V2. Then, connect with the MCU in the utility and start to program it.

Note: Move the BOOT jumper to the right to enable the microcontroller to go into programming mode.

![Semantic description of image](/image/pic8.png)


<br/>
<br/>


13. Use the CH340 USB to TTL Converter to connect the STM32 MCU through the USB port.

Note: Move the BOOT jumper to the left to enable the microcontroller to go into normal mode.


<br/>
<br/>


14. Open the device manager to check the COM port for the CH340 USB to TTL Converter. In our case, it is COM4.

![Semantic description of image](/image/pic12.png)

<br/>
<br/>


15. Open the Putty software and set the correct speed and COM port and then press Open to establish a connection. The message send from the STM32 MCU will be displayed throught the terminal.


<br/>
<br/>


# Reflections

This STM32 project creation facilitates us in understanding the UART interface, especially on how to implement it on the STM32. The UART interface transmits data asynchronously and does not use a clock signal to synchronize the transmitter and receiver devices. As a result, the UART interface does not require the clock pin and only 2 pins are required for the transmitter and receiver. This project requires us to use the external UART module in which we are using CH340 USB to TTL Converter since the STM32 board does not have an onboard converter.




# References
1. STM32 Blue Pill UART Communication Tutorial with CubeIDE and HAL Libraries: https://microcontrollerslab.com/stm32-blue-pill-uart-tutorial-polling-method/*

