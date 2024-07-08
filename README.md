# LightSensor

This is my project for the Computer System Design exam.

The objective is to measure the ambient light intensity using a GY-302 BH1750 light sensor. Two development boards were used: the STM32F3DISCOVERY, which acts as the master and sends commands to the STM32F407G-DISC1 board.

The BH1750 sensor is connected to the STM32F407G-DISC1 board. In this configuration, the sensor acts as the slave, while the board functions as the master. Communication between the master and slave is carried out via the I²C protocol. The board sends commands to the sensor and receives the light intensity value detected by the sensor.

The STM32F407G-DISC1 board is connected to the STM32F3DISCOVERY board via the UART protocol and receives two commands: "Start" and "Stop", which respectively allow the start and stop of data reading from the sensor. To decide which command to send, the button on the STM32F3DISCOVERY board is used. Each time the button is pressed, it alternates between the Start and Stop commands.

When in "Start" mode, the STM32F407G-DISC1 board processes the sensor's results and sends them via the UART protocol to the STM32F3DISCOVERY board.

Using the LEDs on the STM32F3DISCOVERY board, the results of the sensor readings will be displayed.
