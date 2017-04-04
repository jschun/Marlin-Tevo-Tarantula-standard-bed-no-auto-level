# Marlin-Tevo-Tarantula-standard-bed-no-auto-level
Marlin Tevo Tarantula standard bed no auto level

I found that all the firmware on the community Facebook page did not work with my standard bed, no auto level Tevo Tarantula (TT). Therefore I took the Marlin firmware and educated myself with the Interwebs and YouTube and build my own firmware.

This is the result.

Please understand that you need to do some adjustments yourself in order to make it just perfect for your TT. But by default it should work just fine (if your Y-stepper motor is on the left when you look from the front of your TT) on the MKS MakerBase 1.3/1.4 motherboard.

Good luck!

Some extra adjustments are:

Auto PID configuration for your extruder
From a terminal connected to your MKS Makerbase 1.3/1.4 motherboard give the following command: "M303 E0 C10 S230" to run autotune on the hotend at 230 degreesC for 10 cycles. In the terminal window you will see the finished PID values after the tenth cycle. Put those numbers in you configuration.h file.

mine are:
 #define  DEFAULT_Kp 16.24
 #define  DEFAULT_Ki 1.35
 #define  DEFAULT_Kd 48.69

Auto PID configuration for your hotbed
Do the same as above, but with this command: "M303 E-1 C10 S90" and use the values given after the tenth cycle aswell.

Mine are:
 #define  DEFAULT_bedKp 231.48
 #define  DEFAULT_bedKi  45.29
 #define  DEFAULT_bedKd 295.80



