# ADFrig
ADF4350 based 3.5-2500MHz wideband transceiver

This project aims to make a hobbyist grade transceiver that has receive bandwidth from 3.5MHz to 2500MHz.
The receive and transmit coverage is not continous due to the construction (146MHz IF).
Currently planed bands where transmit is possible with proper suppression of harmonics are:
80m (3.500 - 3.800MHz)
60m (5.3515 – 5.3665MHz)
40m (7.000 - 7.200MHz)
30m (10.100 - 10.150MHz)
17m (18.068 - 18.168MHz)
6m  (50.000 - 52.000MHz)
4m  (70.000 - 70.200MHz)
70cm (432.000 - 438.000MHz)
23cm (1240.000 - 1300.000MHz)
13cm (2300.000 - 2450.000MHz)

Hardware details:

1st LO based on ADF4350 137.5 - 4400MHz VCO+PLL synthesizer from Analog Devices.
http://www.analog.com/media/en/technical-documentation/data-sheets/ADF4350.pdf

1st Mixer is ELCM-25MH (also known as MAMX-007238-CM25MH). It is specified for 5-2500MHz, but we are using it a bit outside of spec to get 80m reception. 
https://cdn.macom.com/datasheets/MAMX-007238-CM25MH.pdf
biakom.com/pdf/ELCM-25MH_MACOM.pdf

2nd LO based on 125MHz crystal oscillator. (might get changed to 15x.xxxMHz to avoid 146MHz QRM and to gain 2m reception). 

1st IF is 146MHz using Mobira RC25 RX RF filter, RX Mixer and FM IF strip. 
2nd IF is 21.4MHz with a 25kHz crystal filter. 2nd Mixer if BF981.
3rd Mixer is MC3357.

455kHz IF is tapped after 455kHz ceramic filter in the MC3357 and fed to the SSB/CW/AM demodulators. 

The UI is done with Arduino Nano and 3.5" TFT screen.
