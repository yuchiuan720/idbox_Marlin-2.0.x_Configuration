# idbox_Marlin-2.0.x_Configuration
<P>
印表機設定:
  常規:
  最大列印高度: 100
  機器限制: ignore
  自定義G-code:
    ;clean nollzer start gcode
    M109 S215                  ;Uncomment to set your own temp
    G21                        ;Set to metric
    G90                        ;Force coordinates to be absolute relative to the origi
    G28                        ;Home all axes
    G1 X1 Y3 Z0.15 F500        ;Move in 1mm from edge and up z 0.2mm
    G92 E 0                     ;Set extruder to zero
    G1 X70 E35 F500            ;Extrude 100mm filiment along Y axis 290mm long to prime and clean the nozzle
    G92 E0                     ;Reset extruder to zero end of cleaning run
  擠出頭1:
      層高度限制:0.3003
列印設置:<br>
  層和輪廓:<br>
    層高:
      層高: 0.2毫米
      首層高度: 0.15mm或%
    垂直外殼:
      輪廓: 2
    水平外殼:
      可靠層數: 頂部: 2  底部: 2
  速度:<br>
    列印移動的速度:
      輪廓: 60 mm/s
  
  
  
    

;end gcode
G91 ;Relative positioning
G90 ;Absolute positionning
G1 Z 100;

idbox_Marlin-2.0.x_Configuration
LCD DISPLAY FAILED INFO<br>
https://www.youtube.com/watch?v=yh-PQ7BpZl8&ab_channel=SteveWagg

marlin pid calibration
use software tools:Pronterface<br>
run command:M303 C8 S220


126c126
< #define BAUDRATE 250000
---
> #define BAUDRATE 115200
134c134
<   #define MOTHERBOARD BOARD_RAMPS_14_EFB
---
>   #define MOTHERBOARD BOARD_RAMPS_13_EEB
139c139
< //#define CUSTOM_MACHINE_NAME "3D Printer"
---
> #define CUSTOM_MACHINE_NAME "idbox"
149c149
< #define EXTRUDERS 1
---
> #define EXTRUDERS 2
152c152
< #define DEFAULT_NOMINAL_FILAMENT_DIA 3.0
---
> #define DEFAULT_NOMINAL_FILAMENT_DIA 1.75
313,314c313,314
< #define TEMP_SENSOR_0 1
< #define TEMP_SENSOR_1 0
---
> #define TEMP_SENSOR_0 5
> #define TEMP_SENSOR_1 5
318c318
< #define TEMP_SENSOR_BED 0
---
> #define TEMP_SENSOR_BED 5
353,357c353,357
< #define HEATER_0_MAXTEMP 275
< #define HEATER_1_MAXTEMP 275
< #define HEATER_2_MAXTEMP 275
< #define HEATER_3_MAXTEMP 275
< #define HEATER_4_MAXTEMP 275
---
> #define HEATER_0_MAXTEMP 260
> #define HEATER_1_MAXTEMP 260
> #define HEATER_2_MAXTEMP 260
> #define HEATER_3_MAXTEMP 260
> #define HEATER_4_MAXTEMP 260
382,385c382,385
<   // Ultimaker
<   #define DEFAULT_Kp 22.2
<   #define DEFAULT_Ki 1.08
<   #define DEFAULT_Kd 114
---
>   // idbox
>   #define DEFAULT_Kp 12.7
>   #define DEFAULT_Ki 0.62
>   #define DEFAULT_Kd 64.49
512c512
< #define USE_ZMIN_PLUG
---
> //#define USE_ZMIN_PLUG
515c515
< //#define USE_ZMAX_PLUG
---
> #define USE_ZMAX_PLUG
521,527c521,527
<   //#define ENDSTOPPULLUP_XMAX
<   //#define ENDSTOPPULLUP_YMAX
<   //#define ENDSTOPPULLUP_ZMAX
<   //#define ENDSTOPPULLUP_XMIN
<   //#define ENDSTOPPULLUP_YMIN
<   //#define ENDSTOPPULLUP_ZMIN
<   //#define ENDSTOPPULLUP_ZMIN_PROBE
---
>   #define ENDSTOPPULLUP_XMAX
>   #define ENDSTOPPULLUP_YMAX
>   #define ENDSTOPPULLUP_ZMAX
>   #define ENDSTOPPULLUP_XMIN
>   #define ENDSTOPPULLUP_YMIN
>   #define ENDSTOPPULLUP_ZMIN
>   #define ENDSTOPPULLUP_ZMIN_PROBE
531,537c531,537
< #define X_MIN_ENDSTOP_INVERTING false // set to true to invert the logic of the endstop.
< #define Y_MIN_ENDSTOP_INVERTING false // set to true to invert the logic of the endstop.
< #define Z_MIN_ENDSTOP_INVERTING false // set to true to invert the logic of the endstop.
< #define X_MAX_ENDSTOP_INVERTING false // set to true to invert the logic of the endstop.
< #define Y_MAX_ENDSTOP_INVERTING false // set to true to invert the logic of the endstop.
< #define Z_MAX_ENDSTOP_INVERTING false // set to true to invert the logic of the endstop.
< #define Z_MIN_PROBE_ENDSTOP_INVERTING false // set to true to invert the logic of the probe.
---
> #define X_MIN_ENDSTOP_INVERTING true // set to true to invert the logic of the endstop.
> #define Y_MIN_ENDSTOP_INVERTING true // set to true to invert the logic of the endstop.
> #define Z_MIN_ENDSTOP_INVERTING true // set to true to invert the logic of the endstop.
> #define X_MAX_ENDSTOP_INVERTING true // set to true to invert the logic of the endstop.
> #define Y_MAX_ENDSTOP_INVERTING true // set to true to invert the logic of the endstop.
> #define Z_MAX_ENDSTOP_INVERTING true // set to true to invert the logic of the endstop.
> #define Z_MIN_PROBE_ENDSTOP_INVERTING true // set to true to invert the logic of the probe.
611c611
< #define DEFAULT_AXIS_STEPS_PER_UNIT   { 80, 80, 4000, 500 }
---
> #define DEFAULT_AXIS_STEPS_PER_UNIT   { 71.1111, 71.1111, 3200, 173.6236 }
618c618
< #define DEFAULT_MAX_FEEDRATE          { 300, 300, 5, 25 }
---
> #define DEFAULT_MAX_FEEDRATE          { 300, 300, 3, 50 }
851c851
< #define INVERT_X_DIR false
---
> #define INVERT_X_DIR true
853c853
< #define INVERT_Z_DIR false
---
> #define INVERT_Z_DIR true
877c877
< #define Z_HOME_DIR -1
---
> #define Z_HOME_DIR 1
882,883c882,883
< #define X_BED_SIZE 200
< #define Y_BED_SIZE 200
---
> #define X_BED_SIZE 150
> #define Y_BED_SIZE 130
891c891
< #define Z_MAX_POS 200
---
> #define Z_MAX_POS 100
</P>
