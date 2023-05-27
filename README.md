# sin-cos-encoder-implement-on-STM32
In this repo, I will give a snippet of code about the implementation of position/angle measurement of using sin/cos encoder based on STM32F303 MCU.
This includes mainly 3 parts:
1. Hardware resource deployment
   Hardware circuit used for Analog sin&cos signal measurement, 4 times frequency processing of encoder sin/cos output signal for generating pulses used in encoder interface module of TIMx in STM32F303 MCU and MCU peripheral used in firmware;
2. Firmware resource deployment
   ADC configuration for ChA_Sin and ChB_Cos measurent simultaneously, Encoder interface configuration of TIMx, ADC triggering with precisely timing synchronized with system timer and necessary interrupt ISR for position/angle interpolation;
3. Algorithm proposed
   Total position/angle consists of coarse part of fine part of position/angle. Coarse part can be obtained via counter in Encoder interface module of TIMx while fine part can be calculated via a) Arctan/Arccot method including table indexing, directly calculating and approximating(McLaughlin's series); b) Tracking loop Method.

Due to some reasons, the entire code of handling will not be discovered but only the snippet of core code will be attached.
