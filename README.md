# PWM-Solar-Charge-Controller

https://www.instructables.com/DIY-Solar-Charge-Controller-PWM/

With the increasing cost of electricity as well its use, it's high time that we all should switch to more eco-friendly and cost effective source of electricity.
Solar and wind energy is two most commonly harvested source of energy.

To store the solar energy we need a storage device and for that we use a battery. Battery can we lead-acid or Lipo or LiFePO4. They all have there pros and cons but we will not discuss them here. 

For most of us lead-acid is the choice because of the purchase cost, availability and ease of charging.

This PWM solar charge controller is inspired and adopted from Julian Ilett and Adam Welch work.

Please visit Adam Welch github for reference. (https://github.com/AdamWelchUK/PWM85)

# Supplies:
IRF3205PBF - N-channel Mosfet - 55V 98A 8mOhm

ATTINY85 microcontroller

HT7533 - 30V 3.3V 55mV @ 1mA Dropout Regulator (LDO) - 3.3v Linear voltage regulator

for all other passive components BOM is attached

# Charge Controller Specs
Max Solar Panel - 36V

Max current - 5A (15A with heatsink)

Battery Over voltage protection - YES

Battery Over Discharge protection - NO

Charging Over current protection - internal mosfet controlled ( mosfet temp controlled)

Requires a reverse polarity protection diode on the solar panel connections (most solar panel include it -prebuilt)

# Schematic

The schematic is drawn using easyeda software. Its easy and has most of the components with their footprint.

With easyeda it's also extremely easy to export the gerber files and assembly files to jlcpcb for fabrication as easyeda and jlcpcb are very nicely integrated together.

The schematic comprises of 3 parts

1) Attiny85 + its power supply (3.3v)

2) Charge Pump

3) Mosfet Driving circuit

# Ordering PCBs

Now we have got the PCB design and it’s time to order the PCB’s. For that, you just have to go to JLCPCB.com , and click on “QUOTE NOW” button.
JLCPCB are also sponsor of this project. JLCPCB (Shenzhen JLC Electronics Co., Ltd.), is the largest PCB prototype enterprise in China and a high-tech manufacturer specializing in quick PCB prototype and small-batch PCB production. You can order a minimum of 5 PCBs for just $2. To get the PCB manufactured, upload the gerber file you downloaded in the last step. Upload the .zip file or you can also drag and drop the gerber files. After uploading the zip file, you’ll see a success message at the bottom if the file is successfully uploaded. You can review the PCB in the Gerber viewer to make sure everything is good. You can view both top and bottom of the PCB. After making sure the PCB looks good, you can now place the order at a reasonable price. You can order 5 PCBs for just $2 plus shipping. To place the order, click on “SAVE TO CART” button. My PCBs took 5 days to get manufactured and arrived within 20 days using standard registered post delivery option. There are fast delivery options also available. PCBs were well packed and the quality was really good. JLCPCB is now offering SMT assembly service that too at a very reasonable price and after trying it I must say that they are doing excellent work and their craftsmanship is comparable to any other commercial PCB manufacturing and assembly service all over the world. Their backend team is so efficient and through that they will check each and every design and component placement and will inform the customer about required changes in design or about wrong placement and polarity of the components and correct the minor issues at their end itself.

# Working

This is a PWM (pulse width modulation) based charge controller.

PWM based charge controllers are very efficient when solar panel are of 20V open voltage and battery max voltage is 13-14 volts.

PWM means that the microcontroller changes the off-on time (duty cycle) on the mosfet to attain the set voltage on the battery/analog input pin. It is a method to obtain a lower voltage output without a substantial power loss.

When the battery is almost discharged the mosfet is fully open and it's like a direct connection between the solar panel and the battery.

When the battery is fully charged the mosfet is fully closed and there is no current flowing from the panel to battery.

When the battery is partially charged or on the verge of being fully charged or when a electrical load is put on the battery, the microcontroller adjusts the off-on time of the mosfet to make sure that the battery does not overcharge or the battery voltage does not cross the set threshold while charging and works as a top up charge.

For more details on the PWM please visit WikiPedia

# Arduino Code
download code from here - thanks to adam welch for coding and making it bugs-free

https://github.com/AdamWelchUK/PWM85

# Pre requisites

1) ATTINY board manager installed - download board files from here

https://github.com/SpenceKonde/ATTinyCore

2) ISP programmer - you can use arduino as ISP or a USBASP device (amazon.inRobu.in)

https://www.arduino.cc/en/Tutorial/BuiltInExamples/ArduinoISP#use-arduino-as-isp

https://www.amazon.in/Robocraze-USB-AVR-ISP-Programmer/dp/B07928QG37/ref=sr_1_6?crid=20K4D34EBYG9V&dchild=1&keywords=usbasp+programmer&qid=1609824014&sprefix=usbasp%2Caps%2C307&sr=8-6

https://robu.in/product/usbasp-avr-programming-device-for-atmel-proccessors/

You will also need a 10pin to 6pin adapter converter

Windows 10 USBASP install guide

https://www.instructables.com/USBASP-Installation-in-Windows-10/

3) Arduino IDE

