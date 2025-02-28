# Speed_Control_of_a_DC_Motor_Using_ePWM_on_the_TMS320F28379D_Microcontroller

## Description
This project implements **Open-loop speed control** of a **DC motor** using **PWM signals** generated by the **TMS320F28379D** microcontroller.

## Features
- **PWM-based speed control**

## Getting Started

### **1. Hardware Requirements**
- **TMS320F28379D LaunchPad**
- **Motor Driver Circuit (e.g., L293D, DRV8871)**
- **Power Supply for the Motor**

### **2. Software Requirements**
- **Code Composer Studio (CCS)**
- **C2000Ware (for TMS320F28379D support)**

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

A **potentiometer** is a three-terminal electrical and electronic component that can change its resistance by rotating or statically moving. It is commonly used for voltage division or as a variable resistor.

### Configuration Modes
The potentiometer can be used in two primary configurations:
1. **Voltage Control Mode:** The potentiometer acts as a voltage divider, providing an adjustable voltage output.
2. **Resistance Control Mode:** The potentiometer alters its resistance dynamically, depending on the rotation or movement.

This setup is useful for applications such as analog signal control, sensor calibration, and user input interfaces.

# Hardware Used

## 10K Ohm 3-Pin 15mm Shaft Potentiometer
The **10K Ohm 3-Pin 15mm Shaft Potentiometer** is a versatile component used for adjusting various parameters like voltage and current in an electronic circuit. When turned or slid halfway, its resistance is halfway between its minimum and maximum settings, making it ideal for applications such as dimmer controls, fan speed adjustments, and more.

For audio applications, logarithmic potentiometers are preferred over linear ones since they better match the human ear's nonlinear response to sound. A log potentiometer increases resistance exponentially, ensuring that volume changes appear more uniform to human perception. In contrast, a linear potentiometer used for volume control would result in large variations in loudness at lower levels and minor changes at higher levels.

### Features:
- **Resistance:** 10kΩ
- **Tolerance:** ±20%
- **Temperature Co-efficient:** ±100ppm/℃
- **Operating Temperature Range:** -40 to 80°C
- **Mounting Type:** Through Hole
- **Dimensions:**
  - **Length:** 20mm
  - **Width:** 17mm (Body Diameter)
  - **Height:** 24mm
- **Weight:** 6g

## 5-36V Switch Drive High-Power MOSFET Trigger Module
The **5-36V Switch Drive High-Power MOSFET Trigger Module** is a powerful control board designed to manage high-power devices such as motors, light bulbs, LED lights, DC motors, micro-pumps, solenoid valves, and more. It supports PWM-based control for motor speed adjustment and light dimming.

This module uses imported dual MOSFETs in a parallel active output configuration, reducing internal resistance and allowing for higher current and power handling. It can operate efficiently at **15A and 400W** under normal conditions, making it suitable for most power control applications.

### Features:
- **Input Voltage:** 5V - 36V
- **Current Handling:** Up to 15A
- **Power Handling:** Up to 400W
- **Low Internal Resistance:** Ensures efficient power control
- **PWM Compatibility:** Supports PWM input for motor speed and light intensity control
- **Application:** Suitable for power equipment, motor control, light dimming, and other high-power switching applications

This module provides an effective way to control high-power devices efficiently and is widely used in various automation and electronic control systems.

# Additional Components

## 5V 1 Channel Without Light Coupling Relay
This **5V 1 Channel Relay Module** is used to control high-voltage AC and DC loads. It allows easy interfacing with microcontrollers, PLCs, and other digital control systems.

### Features:
- **Operating Voltage:** 5V DC
- **Trigger Current:** 5mA
- **Max Load:** AC 250V/10A, DC 30V/10A
- **Control Interface:** Configurable for high-level or low-level triggering
- **Indicators:** Power LED (Green), Relay Status LED (Red)
- **Protection:** Fault-tolerant design ensures relay stability even if the control line is disconnected
- **Mounting:** Includes fixed bolt holes for secure installation

## DIP 3-Colour LED Module
This module consists of a **5mm RGB LED** and three **150Ω limiting resistors** to prevent burnout. The LED colour can be controlled via PWM signals applied to its pins.

### Features:
- **LED Type:** Common cathode RGB LED
- **Operating Voltage:** 5V
- **Resistors:** Built-in 150Ω limiting resistors for each colour
- **Interface:** Compatible with microcontroller GPIO pins
- **Usage:** Used for multi-colour lighting effects and status indicators

## 5V Active Alarm Buzzer Module
A **5V Active Alarm Buzzer Module** is used for generating alarm sounds, notifications, and alerts in various applications.

### Features:
- **Operating Voltage:** 3.3V - 5V
- **Frequency:** 2500Hz
- **PCB Dimensions:** 29mm x 14mm x 12mm
- **Wire Length:** 20cm
- **Weight:** 7g
- **Application:** Suitable for alarm devices, timers, and user feedback systems

# Implementation Steps

## Hardware Setup
1. Connect all components to the appropriate **GPIO pins** or **communication interfaces** on the **TMS320F28379D** microcontroller.
2. Ensure that power supply connections, data lines, and ground connections are properly made according to the respective datasheets.
3. Connect an **LED** to a GPIO pin with a **current-limiting resistor** to prevent damage.

## Software Implementation
1. Write the firmware in **C/C++** using **Code Composer Studio (CCS)** or any other compatible **IDE** for the TMS320F28379D.
2. Configure **GPIOs, PWM, ADC, and timers** for appropriate interfacing with sensors and actuators.
3. Implement logic to control the relay, MOSFET module, LED module, and buzzer using digital signals.
4. Develop **PWM-based** control for motor speed and LED colour mixing.
5. Test and debug the firmware using the CCS debugger and real-time variable monitoring.

This structured approach ensures a reliable and efficient implementation of the hardware and software components in your project.

# Results

The implementation of DC motor control using the **TMS320F28379D** microcontroller was successfully demonstrated. The motor speed was regulated through a **PWM duty cycle**, which was controlled based on the input from an **ADC-connected potentiometer**.

### Observations:
1. **Motor Speed Control**
   - When the **ADC value is at its maximum**, the motor **stops** completely.
   - When the **ADC value is at its minimum**, the motor **runs at full speed**.
   - By adjusting the potentiometer, the **PWM duty cycle** changes, allowing fine-tuned control over the motor speed.

2. **LED and Buzzer Indication**
   - During **normal operation**, only the **relay module LED** remains **on**.
   - If the motor speed exceeds a predefined limit, **both the LED and buzzer turn on** as a warning indicator.

### Figures:
- **Figure 1:** When the motor is running at a **normal speed**, only the **relay module LED is ON**.
- **Figure 2:** When the motor is running at **full speed**, both the **LED and buzzer are ON**.

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

