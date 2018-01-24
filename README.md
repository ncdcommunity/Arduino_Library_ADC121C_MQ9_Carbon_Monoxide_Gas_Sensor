

[![ADC121C_MQ9](ADC121C_I2CGAS_MQ9.png)](https://store.ncd.io/product/mq-9-carbon-monoxide-combustible-gas-sensor-adc121c-12-bit-adc-i2c-mini-module/)

#ADC121C_MQ9
The MQ-9 is capable of sensing carbon monoxide air concentration levels between 10 and 1,000ppm and combustible gas air concentration levels between 100 and 10,000ppm. The ideal sensing condition for the MQ9 is 20°C ±2°C at 65% ±5% humidity.
This Device is available from www.ncd.io 

[SKU: ADC121C_MQ9_I2CS]

(https://store.ncd.io/product/mq-9-carbon-monoxide-combustible-gas-sensor-adc121c-12-bit-adc-i2c-mini-module/)
This Sample code can be used with Arduino.

Hardware needed to interface ADC121C_MQ9 sensor with Arduino

1. <a href="https://store.ncd.io/product/i2c-shield-for-arduino-nano/">Arduino Nano</a>

2. <a href="https://store.ncd.io/product/i2c-shield-for-arduino-micro-with-i2c-expansion-port/">Arduino Micro</a>

3. <a href="https://store.ncd.io/product/i2c-shield-for-arduino-uno/">Arduino uno</a>

4. <a href="https://store.ncd.io/product/dual-i2c-shield-for-arduino-due-with-modular-communications-interface/">Arduino Due</a>

5. <a href="https://store.ncd.io/product/mq-9-carbon-monoxide-combustible-gas-sensor-adc121c-12-bit-adc-i2c-mini-module/">ADC121C_MQ9 Methane,Carbon monoxide and LPG Gas Sensor</a>

6. <a href="https://store.ncd.io/product/i%C2%B2c-cable/">I2C Cable</a>

ADC121C_MQ9:

The MQ-9 is capable of sensing carbon monoxide air concentration levels between 10 and 1,000ppm and combustible gas air concentration levels between 100 and 10,000ppm. The ideal sensing condition for the MQ9 is 20°C ±2°C at 65% ±5% humidity.
Applications:

•Domestic gas leakage detector

•Industrial Combustible gas detector

•Portable gas detector 

How to Use the ADC121C_MQ9 Arduino Library
The ADC121C_MQ9 has a number of settings, which can be configured based on user requirements.

1.Automatic Conversion mode: When these bits are set to zeros, the automatic conversion mode is disabled. This is the case at power-up.When these bits are set to a non-zero value, the ADC will begin operating in automatic conversion mode.

       mq9.setCycleTime(CYCLE_TIME_32);              // Tconvert x 32, 27 ksps
    
2.Alert Hold:This bit tells the Alert will self clear or not.

   0: Alerts will self-clear when the measured voltage moves within the limits by more than the hysteresis register value.
  
   1: Alerts will not self-clear and are only cleared when a one is written to the alert high flag or the alert low flag in the Alert Status register.

      mq9.setAlertHold(ALERT_HOLD_CLEAR);         // Alerts will self-clear

3.Alert Flag Enable:This bit indicates when an alert condition has occurred. When the Alert Bit Enable is set in the Configuration Register, this bit will be high if either alert flag is set in the Alert Status Register.Otherwise, this bit is a zero.

   0: Disables alert status bit [D15] in the Conversion Result register.
  
   1: Enables alert status bit [D15] in the Conversion Result register.

       mq9.setAlertFlag(ALERT_FLAG_DISABLE);     // Disables alert status bit in the Conversion Result register
       
4.Alert Pin Enable:.

   0: Disables the ALERT output pin. The ALERT output will TRI-STATE when the pin is disabled.
  
   1: Enables the ALERT output pin
  
     mq9.setAlertPin(ALERT_PIN_DISABLE);       // Disables the ALERT output pin

5.Polarity: This bit configures the active level polarity of the ALERT output pin.

   0: Sets the ALERT pin to active low.
 
   1: Sets the ALERT pin to active high
 
      mq9.setPolarity(POLARITY_LOW);        // Sets the ALERT pin to active low
    
6.Output measurement:The following commands are used to measure the concentration of different gases.

  1.Carbon monoxide gas measurement:The following command is used to measure the carbon monoxide gas measurement.
       
        mq9.Measure_CarbonMonoxide(-0.45, 2.3);  
     
  2.LPG gas measurement:The following command is used to measure the LPG gas measurement.
    
        mq9.Measure_LPG(-0.46, 2.3);
        
  3.Methane gas measurement:The following command is used to measure the methane gas.
     
        mq9.Measure_Methane(-0.36, 2.3);
