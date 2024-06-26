# LoT System
A Light of Things (LoT) Transmitter-Reciever System implemented using STM32f0Discovery boards. A simple system communication protocol has been designed for implementation by the transmitter and receiver subsystems.

## Contributers
[Shameera Cassim](https://github.com/ShameeraC), [Tristyn Ferreiro](https://github.com/tristynferreiro), [Sarah Tallack](https://github.com/SarahTallack), [Heather Wimberley](https://github.com/Heather-Wimberley)

## Protocol
The LoT Protocol structure can be seen in the image below. More in-depth explanations can be found in the project report.
<p align="center">
 <img src="https://github.com/tristynferreiro/LoT_System/blob/main/Docs/ProtocolStruct.jpg" width="500">
</p>

## Subsystems Implemented
### Transmitter
The transmitter has two modes: data reading mode and checkpoint mode. When the onboard blue push button is pressed, a data reading is taken from the potentiometer and the reading is transmitted using the laser diode and protocol structure. When the silver push button is pressed, the number of transmissions counter value is transmitted instead. The system hardware can be seen below:
<p align="center">
<img src="https://github.com/tristynferreiro/LoT_System/blob/main/Docs/Transmitter_Circuit.png" width="500">
</p>
  
### Receiver Interfacing Diagram
The receiver has two modes: data reading mode and compare mode. When the onboard blue push button is pressed, the receiver waits for a message. Once light is detected it records the sent data and decodes it. If the data indicates data reading mode, the receiver stores the value. If the data indicates compare mode, the receiver compares teh value to it's transmissions counter; if they are the same the onboard $\color{green}green$ LED flashes, otherwise the $\color{lightblue}blue$ LED flashes and the counter is set to the received value.
<p align="center">
<img src="https://github.com/tristynferreiro/LoT_System/blob/main/Docs/Receiver_Circuit.jpeg" width="500">
</p>
