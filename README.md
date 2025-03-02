# Speed Control of a DC Motor Using ePWM on the TMS320F28379D Microcontroller

## Description
This project implements **Open-Loop Speed Control** of a **DC motor** using **PWM (Pulse Width Modulation) Signals** generated by the **TMS320F28379D microcontroller**. The motor speed is controlled by varying the **PWM duty cycle**, which is adjusted based on the **ADC (Analog-to-Digital Converter) input** from a **potentiometer**.  

## Features
- **PWM-based speed control**

## Getting Started

### **1. Hardware Requirements**
- **TMS320F28379D LaunchPad**
- **Motor Driver Circuit (e.g., L293D, DRV8871)**
- **Power Supply for the Motor**

### **2. Software Requirements**
- **Code Composer Studio (CCS)**
- **C2000Ware (For TMS320F28379D support)**

# GPIO Connections and Potentiometer Setup

## GPIO Connection Table

| SL. No | GPIO Pin   | Launchpad Pin | Name of the Component  |
|------|------------|--------------|------------|
| 1    | ADCINA0    | Pin 30       | Potentiometer |
| 2    | GPIO0      | EPWM1A (Pin 40) | Oscilloscope |
| 3    | GPIO0      | Connected to Relay | Motor |

## Connecting the Potentiometer

Follow these steps to correctly connect the potentiometer to the **TMS320F28379D**:

1. Connect the **Negative Pin** of the potentiometer to **GND PIN** on the TMS320.
2. Connect the **Signal Pin** of the potentiometer to **ADCINA0** on the TMS320.
3. Connect the **Positive Pin** of the potentiometer to **5V PIN** on the TMS320.

## About the Potentiometer  

The **potentiometer** is used to adjust the **PWM duty cycle** through the **TMS320F28379D's Analog-to-Digital Converter (ADC)**, thereby directly controlling the **motor speed**. As the potentiometer's position changes, the ADC reads the corresponding voltage, which is then used to modify the PWM signal and regulate the motor speed dynamically.  

### How It Works  
- Rotating the **potentiometer** increases or decreases the ADC value.  
- A **higher ADC value** results in a **lower duty cycle**, causing the motor to **slow down or stop**.  
- A **lower ADC value** increases the duty cycle, allowing the motor to **run at full speed**.  
- The motor speed is continuously adjusted based on the potentiometer’s position.  

### Potentiometer Overview  
A **potentiometer** is a **three-terminal electrical component** that can change its **resistance** either by rotating or through linear motion. It is commonly used in circuits for **voltage division** or as a **variable resistor**.  

Below is the circuit diagram illustrating how the **potentiometer is connected to the TMS320F28379D** for motor speed control:  

<p align="center">
  <img src="https://github.com/vandemataram15aug1947/Speed_Control_of_a_DC_Motor_Using_ePWM_on_the_TMS320F28379D_Microcontroller/blob/2b16567f4e88e164c2485ad860fb8435e7360a20/Photos/F28379D%20LaunchPad%20with%20Potentiometer.png" width="500">
</p>  

<p align="center"><b>Figure 1:</b> F28379D LaunchPad with Potentiometer</p>  

This setup ensures smooth and precise **DC motor speed control**, making it a fundamental part of this project. 🚀  

### Configuration Modes
The potentiometer can be used in two primary configurations:
1. **Voltage Control Mode:** The potentiometer acts as a voltage divider, providing an adjustable voltage output.
2. **Resistance Control Mode:** The potentiometer alters its resistance dynamically, depending on the rotation or movement.

This setup is useful for applications such as analog signal control, sensor calibration, and user input interfaces.

---

## Hardware Used  

### **10K Ohm 3-Pin 15mm Shaft Potentiometer**  

The **10K Ohm 3-Pin 15mm Shaft Potentiometer** is a versatile component widely used in electronic circuits for adjusting parameters such as **voltage, current, and resistance**. It operates as a **variable resistor** or a **voltage divider**, depending on the circuit configuration.  

### **How It Works**  
- When the **potentiometer knob is rotated**, the resistance changes between its minimum and maximum values.  
- At **halfway rotation**, the resistance is approximately **half** of its total value.  
- This behavior is **ideal for controlling electrical parameters** such as **light intensity** or **motor speed**.  
- However, for **audio applications**, **logarithmic potentiometers** are preferred over linear ones, as they align with the human ear’s nonlinear response to sound.  
- A **logarithmic potentiometer** increases its resistance **exponentially**, ensuring a smooth volume transition that **matches human perception**.  

### **Features**  
- **Resistance:** 10kΩ  
- **Tolerance:** ±20%  
- **Temperature Coefficient:** ±100ppm/℃  
- **Operating Temperature Range:** -40°C to 80°C  
- **Mounting Type:** Through-Hole  
- **Dimensions:**  
  - **Length:** 20mm  
  - **Width:** 17mm (Body Diameter)  
  - **Height:** 24mm  
- **Weight:** 6g  

This **10K Ohm potentiometer** is a crucial component in **PWM-based motor speed control**, providing smooth and precise **user input for speed regulation**. It is widely used in applications such as **dimmer controls, fan speed adjustments, and signal calibration circuits**.  

---

### **2. 5-36V Switch Drive High-Power MOSFET Trigger Module**  
This **MOSFET driver module** is designed for **high-power switching applications**. It enables efficient **PWM control of motors, light bulbs, LEDs, solenoid valves, and more**.

<p align="center">
  <img src="https://github.com/vandemataram15aug1947/Speed_Control_of_a_DC_Motor_Using_ePWM_on_the_TMS320F28379D_Microcontroller/blob/05cd3fc4fea9986c3477eadd6b7c7f1b312ca83d/Photos/Connection%20Diagram%20of%20Motor%20Drive.jpg" width="300">
</p>  

<p align="center"><b>Figure 2:</b> Connection Diagram of Motor Drive</p> 

#### **Working Principle**  
- The module features a **dual-MOS parallel active output**, reducing internal resistance and increasing current capacity.  
- It supports **PWM input**, allowing for **motor speed control** and **lamp brightness adjustments**.  
- At room temperature, it can handle **15A continuous current** and up to **400W power**, making it ideal for high-power applications.  

#### **Specifications**  
- **Input Voltage:** 5V - 36V  
- **Trigger Source:** Digital High/Low (3.3V - 20V)  
- **Maximum Continuous Current:** 15A  
- **Maximum Power Output:** 400W  
- **Supported PWM Frequency:** 0 - 20 kHz  
- **Applications:** Motor speed control, lamp brightness control, solenoid valves, and high-power switching.  

---

### **3. 5V 1-Channel Relay Module (Without Light Coupling)**  
The **relay module** acts as an **electrical switch**, enabling **low-power microcontroller signals** to control **high-power loads**.  

<p align="center">
  <img src="https://github.com/vandemataram15aug1947/Speed_Control_of_a_DC_Motor_Using_ePWM_on_the_TMS320F28379D_Microcontroller/blob/0e9c00de53b215e1765fe919d105fd0743c52c6a/Photos/Relay.png" width="300">
</p>  

<p align="center"><b>Figure 3:</b>  Realy Module</p> 

#### **Working Principle**  
- When triggered, the relay **closes or opens** its circuit, allowing for control of **AC or DC loads**.  
- It features a **fault-tolerant design**, ensuring stability even if the control line is disconnected.  
- The **status indicators** provide a clear visual representation of relay activity.  

#### **Specifications**  
- **Operating Voltage:** 5V DC  
- **Trigger Current:** 5mA  
- **Max Load:**  
  - **AC:** 250V/10A  
  - **DC:** 30V/10A  
- **Relay Control Interface:** MCU I/O  
- **LED Indicators:**  
  - Power Indicator (Green)  
  - Relay Status Indicator (Red)  

---

### **4. DIP 3-Color LED Module**  
This **RGB LED module** allows for **color mixing** using **Pulse Width Modulation (PWM)**.  

<p align="center">
  <img src="https://github.com/vandemataram15aug1947/Speed_Control_of_a_DC_Motor_Using_ePWM_on_the_TMS320F28379D_Microcontroller/blob/05cd3fc4fea9986c3477eadd6b7c7f1b312ca83d/Photos/LED.jpg" width="300">
</p>  

<p align="center"><b>Figure 4:</b>  LED Module</p> 

#### **Working Principle**  
- The module includes a **5mm RGB LED** and **three 150Ω resistors** to prevent burnout.  
- By adjusting the **PWM signals** for each color, a wide range of colors can be generated.  
- It is connected to the **TMS320F28379D GPIO pins** for easy integration.  

#### **Specifications**  
- **Operating Voltage:** 5V  
- **Drive Mode:** Common Cathode  
- **Resistor Protection:** Built-in 150Ω resistors for each color channel  
- **Applications:** Visual indicators, status lighting, color mixing projects  

---

### **5. 5V Active Alarm Buzzer Module**  
This **active buzzer module** generates an audible alarm or tone when activated.  

<p align="center">
  <img src="https://github.com/vandemataram15aug1947/Speed_Control_of_a_DC_Motor_Using_ePWM_on_the_TMS320F28379D_Microcontroller/blob/9b9796890e468fe01caf99e192418d73d101803b/Photos/Buzzer.png" width="200">
</p>  

<p align="center"><b>Figure 5:</b>  Buzzer Module</p> 

#### **Working Principle**  
- Unlike a **passive buzzer**, an **active buzzer** emits sound **as soon as it receives power**.  
- It is commonly used for **alarms, notifications, and user input feedback**.  

#### **Specifications**  
- **Operating Voltage:** 3.3V - 5V  
- **Frequency:** 2500 Hz  
- **PCB Dimensions:** 29mm × 14mm × 12mm  
- **Wire Length:** 20cm  
- **Weight:** 7g  
- **Applications:** Alarm systems, timers, notification devices  

---

## **Implementation Steps**  

### **1. Hardware Setup**  
- **Connect all components** to their appropriate **GPIO pins** and **power supply lines** on the **TMS320F28379D**.  
- The **potentiometer output** is connected to the **ADC** to provide real-time speed control input.  
- The **MOSFET trigger module** is connected to the **PWM output** of the microcontroller.  
- The **relay module**, **LED module**, and **buzzer** are connected to dedicated GPIO pins for additional control functions.  
- A **current-limiting resistor** is placed in series with the LED to **prevent excessive current draw**.  

### **2. Software Implementation**  
- The **firmware is written in C/C++** using **Code Composer Studio (CCS)**.  
- The **PWM duty cycle** is dynamically adjusted based on the **ADC reading from the potentiometer**.  
- **GPIOs are configured** for controlling the **relay, LED, and buzzer**.  
- The **PWM signal is generated using the ePWM module** of the **TMS320F28379D**.  
- The **buzzer and LED module** provide **status indication** during operation.  

# **Code Implementation**

Below is the main loop implementation for Speed Control of a DC Motor:

```c
/*
 * Speed Control of a DC Motor Using ePWM on the TMS320F28379D Microcontroller
 *
 * Created on: Dec 5, 2023
 * Author: Vande
 */

#include "F2837xD_device.h"
#include "F28x_Project.h"
#include "driverlib.h"
#include "device.h"

/* ----------------------- Macro Definitions ----------------------- */
#define EX_ADC_RESOLUTION 12  /* ADC Resolution (12-bit) */

/* ----------------------- Function Prototypes ----------------------- */
void gpio_init(void);
void PinMux_init(void);
void initEPWM1(void);

void toggleLED(void);
void toggleBuzzer(void);
void toggleRelay(void);

void setLED(bool set);
void setBuzzer(bool set);
void setRelay(bool set);

void delayCount(void);
void ConfigADC(void);
void initADC_SOC(void);

/* ----------------------- Global Variables ----------------------- */
uint16_t Adc_Result_1, prev_Adc_Result_1, Adc_Result_2;
uint16_t delayCounter_ms, delayCounter_s;
int count;

/* ----------------------- Main Function ----------------------- */
void main(void) {
    /* Initialize Device and Peripherals */
    Device_init();
    Device_initGPIO();
    PinMux_init();
    
    Interrupt_initModule();
    Interrupt_initVectorTable();
    
    IER = 0x0000;
    IFR = 0x0000;
    
    SysCtl_disablePeripheral(SYSCTL_PERIPH_CLK_TBCLKSYNC);
    SysCtl_enablePeripheral(SYSCTL_PERIPH_CLK_TBCLKSYNC);
    
    ConfigADC();
    initADC_SOC();
    
    /* Initialize Variables */
    Adc_Result_1 = 0;
    prev_Adc_Result_1 = 0;
    delayCounter_ms = 0;
    delayCounter_s = 0;
    count = 0;
    
    EINT;
    ERTM;
    
    while (1) {
        /* ADC Conversion and Result Processing */
        // Force ADC Conversion
        // Wait for completion
        // Store ADC result
        
        /* Motor Control Logic */
        // Implement PWM control based on ADC result
        
        /* Peripheral Control Logic */
        // LED, Buzzer, and Relay Control
        
        /* Timing and Delay Handling */
        delayCount();
    }
}

/* ----------------------- Function Definitions ----------------------- */

void PinMux_init(void) {
    /* GPIO Pin Initialization for PWM, LED, Buzzer, and Relay */
}

void toggleLED(void) {
    /* Toggle LED State */
}

void toggleBuzzer(void) {
    /* Toggle Buzzer State */
}

void toggleRelay(void) {
    /* Toggle Relay State */
}

void setLED(bool set) {
    /* Set LED State */
}

void setBuzzer(bool set) {
    /* Set Buzzer State */
}

void setRelay(bool set) {
    /* Set Relay State */
}

void delayCount(void) {
    /* Delay Function Implementation */
}

void initEPWM1(void) {
    /* PWM Initialization and Configuration */
    EPwm1Regs.TBPRD = 1250;       /* Set timer period 801 TBCLKs */
    EPwm1Regs.TBPHS.bit.TBPHS = 0x0000;        /* Phase is 0 */
    EPwm1Regs.TBCTR = 0x0000;

    /* Set Compare Values */
    EPwm1Regs.CMPA.bit.CMPA = Adc_Result_1;    /* Set compare A value */

    /* Setup Counter Mode */
    EPwm1Regs.TBCTL.bit.CTRMODE = TB_COUNT_UPDOWN; /* Count up and down */
    EPwm1Regs.TBCTL.bit.PHSEN = TB_DISABLE;        /* Disable phase loading */
    EPwm1Regs.TBCTL.bit.HSPCLKDIV = TB_DIV1;       /* Clock ratio to SYSCLKOUT */
    EPwm1Regs.TBCTL.bit.CLKDIV = TB_DIV1;

    /* Configure Action Qualifier */
    EPwm1Regs.AQCTLA.bit.CAU = AQ_SET;     /* Set PWM1A on event A, up count */
    EPwm1Regs.AQCTLA.bit.CAD = AQ_CLEAR;   /* Clear PWM1A on event A, down count */
}

void ConfigADC(void) {
    /* ADC Configuration Structure */
}

void initADC_SOC(void) {
    /* ADC Start-of-Conversion Setup */
}

```

---

# Results

The implementation of DC motor control using the **TMS320F28379D** microcontroller was successfully demonstrated. The motor speed was regulated through a **PWM duty cycle**, which was controlled based on the input from an **ADC-connected potentiometer**.

### Observations:
1. **Motor Speed Control**
   - When the **ADC value is at its maximum**, the motor **stops** completely.
   - When the **ADC value is at its minimum**, the motor **runs at full speed**.
   - By adjusting the potentiometer, the **PWM duty cycle** changes, allowing fine-tuned control over the motor speed.

<p align="center">
  <img src="https://github.com/vandemataram15aug1947/Speed_Control_of_a_DC_Motor_Using_ePWM_on_the_TMS320F28379D_Microcontroller/blob/05cd3fc4fea9986c3477eadd6b7c7f1b312ca83d/Photos/Motor%20is%20Rotating%20at%20normal%20Speed%20Only%20Relay%20Module%20and%20LED%20On.jpg" width="500">
</p>  

<p align="center"><b>Figure 6:</b>  Motor is Rotating at Normal Speed, Only the **Relay Module LED is ON**</p> 

#### **Working Principle**  
2. **LED and Buzzer Indication**
   - During **normal operation**, only the **relay module LED** remains **on**.
   - If the motor speed exceeds a predefined limit, **both the LED and buzzer turn on** as a warning indicator.

<p align="center">
  <img src="https://github.com/vandemataram15aug1947/Speed_Control_of_a_DC_Motor_Using_ePWM_on_the_TMS320F28379D_Microcontroller/blob/05cd3fc4fea9986c3477eadd6b7c7f1b312ca83d/Photos/Motor%20is%20Rotating%20at%20Full%20Speed%20LED%20and%20Buzzer%20On.jpg" width="500">
</p>  

<p align="center"><b>Figure 7:</b>  Motor is Rotating at Full Speed, Both the **LED and buzzer are ON**</p> 

---

# Conclusion and Future Considerations

The **PWM-based DC motor control system** implemented in this project provides a solid foundation for further development in motor control applications. The project effectively demonstrates how **PWM duty cycle modulation** can be used to control a **DC motor’s speed**, utilizing an **ADC input from a potentiometer**.

### Key Takeaways:
- The motor **speed** can be adjusted using a potentiometer, providing a simple yet effective way to regulate motion.
- The system **incorporates safety mechanisms** such as an LED and buzzer to indicate when the motor exceeds a certain speed.
- The **TMS320F28379D microcontroller** proves to be an efficient platform for real-time motor control applications.

### Future Enhancements:
1. **Optimizing PWM Parameters**: Fine-tuning the duty cycle adjustments to improve the system's response and efficiency.
2. **Implementing Closed-Loop Control**: Adding a feedback mechanism using **encoders or Hall-effect sensors** to maintain a precise speed.
3. **Integration with Additional Sensors**: Incorporating **temperature and current sensors** for real-time monitoring and protection.
4. **Advanced Control Techniques**: Exploring **PID (Proportional-Integral-Derivative) control** for more precise speed regulation.

In conclusion, this project successfully demonstrates the feasibility of **PWM-based DC motor control** and serves as a stepping stone for **more advanced motor control applications**. Future improvements can focus on **refining control strategies, increasing system adaptability, and integrating additional safety features** to enhance performance and reliability.

📌 **Author**: [Vande]  
📌 **License**: GPL  
📌 **Contributions**: Open to suggestions and improvements! Feel free to submit PRs or open issues. 🚀


