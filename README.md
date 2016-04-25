# STM32F1-FreeRTOS-Template

### OverView
1. Use the offical STM32F10x_StdPeriph_Driver V3.5
2. Use the FreeRTOSV8.2.3
3. Use CMake V3.5

### How to Install
1. make a directory in the project directory
```
  1. mkdir Build
  2. cd Build
```
2. cmake the project directory CMakeList.txt
```
  cmake ..
```
3. Build the Source
```
  make
```

### If you wang to clean the all Build file , you can
```
  make clean-all
```

### If you install the st-link V1/V2/V2.1, you can
```
  make flash
```
