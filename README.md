# Lab 5_1: STM Blinking Lights
### Author: Tymur Krasnianskyi
### Description: 
Implemented a cycle of blinking lights that change the direction when button pressed.

### Parts used:
- 1x STM32F411E-DISCO

### Video demo:
https://drive.google.com/file/d/1j1A75bA85hfjz0vrY7jjjVYdlj17zdlx/

### IOC Setup:
- Pins PD12-PD15 are setup for the internal LEDs:
    - PD12 -- Green
    - PD13 -- Orange
    - PD14 -- Red
    - PD15 -- Blue

- Pin PA0 -- internal button

### Bouncing resolution:
- Busy loop
```
if(HAL_GPIO_ReadPin(GPIOA, GPIO_PIN_0) == GPIO_PIN_SET){
    direction *= -1;
    HAL_Delay(50);
    while(HAL_GPIO_ReadPin(GPIOA, GPIO_PIN_0) == GPIO_PIN_SET){ }
    HAL_Delay(50);
}
```
