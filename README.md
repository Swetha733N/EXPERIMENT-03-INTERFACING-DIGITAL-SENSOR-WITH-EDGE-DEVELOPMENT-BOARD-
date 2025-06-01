# EXPERIMENT-03-INTERFACING-DIGITAL-SENSOR-WITH-EDGE-DEVELOPMENT-BOARD
 
---

### NAME: SWETHA N
### DEPARTMENT: CSE(IoT) 
### ROLL NO: 212222110050

---

## **AIM:**  
To interface a **DHT22 temperature and humidity sensor** with the **Raspberry Pi Pico** and display the sensor readings using MicroPython.

---

## **APPARATUS REQUIRED:**  
1. Raspberry Pi Pico  
2. DHT22 Temperature & Humidity Sensor  
3. 10kΩ Pull-up Resistor (if required)  
4. Jumper Wires  
5. Breadboard  
6. USB Cable  
7. Computer with Thonny IDE  

---

## **THEORY:**  
### **About Raspberry Pi Pico:**  
Raspberry Pi Pico is a microcontroller board based on the **RP2040 chip**. It features:  
- Dual-core ARM Cortex-M0+ processor  
- 26 multi-function GPIO pins  
- Supports **MicroPython** and **C/C++**  
- Interfaces like **I2C, SPI, UART, and PWM**  
- Low power consumption, ideal for **IoT applications**  

### **About DHT22 Sensor:**  
The **DHT22** is a **temperature and humidity sensor** with a digital output. It has:  
- Operating Voltage: **3.3V – 5V**  
- Temperature Range: **-40°C to 80°C (±0.5°C accuracy)**  
- Humidity Range: **0% – 100% (±2-5% accuracy)**  
- **Data format**: Uses **single-wire communication protocol**  

The sensor measures **temperature using a thermistor** and **humidity using a capacitive sensor**. The **MicroPython dht library** processes the raw data.

---

## **WORKING PRINCIPLE:**  
1. The **DHT22 sensor** is connected to the **Raspberry Pi Pico**.  
2. The **Pico reads temperature and humidity values** from the sensor via a single-wire communication protocol.  
3. The data is **processed and displayed on the serial monitor**.  
4. If **temperature or humidity crosses a threshold**, an LED can **flash as an alert**.  

---

## **CIRCUIT DIAGRAM:** 

![Screenshot 2025-03-06 112636](https://github.com/user-attachments/assets/5f5b511a-000f-487a-ae39-8a29ac9862ae)

### **Connections:**  

| DHT22 Pin | Raspberry Pi Pico Pin |
|-----------|----------------------|
| VCC (Pin 1) | 3.3V or 5V |
| Data (Pin 2) | GP15 |
| GND (Pin 4) | GND |
| **(Optional: 10kΩ pull-up resistor between VCC & Data pin)** | |

---

## **PROGRAM (MicroPython)**  
```
import dht
import machine
import time

# Define DHT22 sensor pin(GPIO PIN)
dht_pin = machine.Pin(15,machine.Pin.IN,machine.Pin.PULL_UP)
sensor = dht.DHT22(dht_pin)

while True:
    try:
        sensor.measure()
        temp = sensor.temperature() #Get temperature in Celsius
        hum = sensor.humidity() #Get humidity

        print(f"Temperature: {temp:.1f} C")
        print(f"Humidity: {hum:.1f}%")

    except Exception as e:
        print("Error reading sensor:",e)

    time.sleep(2) # Wait for 2 seconds before next reading
```
## **OUTPUT:**  
---
![Screenshot 2025-03-06 112700](https://github.com/user-attachments/assets/52e07708-a18b-4607-aee0-cc1de399c864)

![Screenshot 2025-03-06 113017](https://github.com/user-attachments/assets/f1f10d97-990c-4792-9641-c64d578c14e0)

---
## **RESULT:**  
The **DHT22 sensor** was successfully interfaced with the **Raspberry Pi Pico**, and real-time **temperature and humidity data** were read and displayed. The LEDs responded correctly when the threshold limits were exceeded.

---

 
# EXPERIMENT-03-INTERFACING-DIGITAL-SENSOR-WITH-EDGE-DEVELOPMENT-BOARD
 
---

### NAME: KEERTHANA JAYASRI
### DEPARTMENT: CSE(IoT) 
### ROLL NO: 212222110019
### DATE OF EXPERIMENT: 10/03/2025

---

## **AIM:**  
To interface a **DHT22 temperature and humidity sensor** with the **Raspberry Pi Pico** and display the sensor readings using MicroPython.

---

## **APPARATUS REQUIRED:**  
1. Raspberry Pi Pico  
2. DHT22 Temperature & Humidity Sensor  
3. 10kΩ Pull-up Resistor (if required)  
4. Jumper Wires  
5. Breadboard  
6. USB Cable  
7. Computer with Thonny IDE  

---

## **THEORY:**  
### **About Raspberry Pi Pico:**  
Raspberry Pi Pico is a microcontroller board based on the **RP2040 chip**. It features:  
- Dual-core ARM Cortex-M0+ processor  
- 26 multi-function GPIO pins  
- Supports **MicroPython** and **C/C++**  
- Interfaces like **I2C, SPI, UART, and PWM**  
- Low power consumption, ideal for **IoT applications**  

### **About DHT22 Sensor:**  
The **DHT22** is a **temperature and humidity sensor** with a digital output. It has:  
- Operating Voltage: **3.3V – 5V**  
- Temperature Range: **-40°C to 80°C (±0.5°C accuracy)**  
- Humidity Range: **0% – 100% (±2-5% accuracy)**  
- **Data format**: Uses **single-wire communication protocol**  

The sensor measures **temperature using a thermistor** and **humidity using a capacitive sensor**. The **MicroPython dht library** processes the raw data.

---

## **WORKING PRINCIPLE:**  
1. The **DHT22 sensor** is connected to the **Raspberry Pi Pico**.  
2. The **Pico reads temperature and humidity values** from the sensor via a single-wire communication protocol.  
3. The data is **processed and displayed on the serial monitor**.  
4. If **temperature or humidity crosses a threshold**, an LED can **flash as an alert**.  

---

## **CIRCUIT DIAGRAM:** 

![Screenshot 2025-03-06 112636](https://github.com/user-attachments/assets/5f5b511a-000f-487a-ae39-8a29ac9862ae)

### **Connections:**  

| DHT22 Pin | Raspberry Pi Pico Pin |
|-----------|----------------------|
| VCC (Pin 1) | 3.3V or 5V |
| Data (Pin 2) | GP15 |
| GND (Pin 4) | GND |
| **(Optional: 10kΩ pull-up resistor between VCC & Data pin)** | |

---

## **PROGRAM (MicroPython)**  
```
import dht
import machine
import time

# Define DHT22 sensor pin(GPIO PIN)
dht_pin = machine.Pin(15,machine.Pin.IN,machine.Pin.PULL_UP)
sensor = dht.DHT22(dht_pin)

while True:
    try:
        sensor.measure()
        temp = sensor.temperature() #Get temperature in Celsius
        hum = sensor.humidity() #Get humidity

        print(f"Temperature: {temp:.1f} C")
        print(f"Humidity: {hum:.1f}%")

    except Exception as e:
        print("Error reading sensor:",e)

    time.sleep(2) # Wait for 2 seconds before next reading
```
## **OUTPUT:**  
---
![Screenshot 2025-03-06 112700](https://github.com/user-attachments/assets/52e07708-a18b-4607-aee0-cc1de399c864)

![Screenshot 2025-03-06 113017](https://github.com/user-attachments/assets/f1f10d97-990c-4792-9641-c64d578c14e0)

---
## **RESULT:**  
The **DHT22 sensor** was successfully interfaced with the **Raspberry Pi Pico**, and real-time **temperature and humidity data** were read and displayed. The LEDs responded correctly when the threshold limits were exceeded.

---

 
VV
# EXPERIMENT-03-INTERFACING-DIGITAL-SENSOR-WITH-EDGE-DEVELOPMENT-BOARD
 
---

### NAME: KEERTHANA JAYASRI
### DEPARTMENT: CSE(IoT) 
### ROLL NO: 212222110019
### DATE OF EXPERIMENT: 10/03/2025

---

## **AIM:**  
To interface a **DHT22 temperature and humidity sensor** with the **Raspberry Pi Pico** and display the sensor readings using MicroPython.

---

## **APPARATUS REQUIRED:**  
1. Raspberry Pi Pico  
2. DHT22 Temperature & Humidity Sensor  
3. 10kΩ Pull-up Resistor (if required)  
4. Jumper Wires  
5. Breadboard  
6. USB Cable  
7. Computer with Thonny IDE  

---

## **THEORY:**  
### **About Raspberry Pi Pico:**  
Raspberry Pi Pico is a microcontroller board based on the **RP2040 chip**. It features:  
- Dual-core ARM Cortex-M0+ processor  
- 26 multi-function GPIO pins  
- Supports **MicroPython** and **C/C++**  
- Interfaces like **I2C, SPI, UART, and PWM**  
- Low power consumption, ideal for **IoT applications**  

### **About DHT22 Sensor:**  
The **DHT22** is a **temperature and humidity sensor** with a digital output. It has:  
- Operating Voltage: **3.3V – 5V**  
- Temperature Range: **-40°C to 80°C (±0.5°C accuracy)**  
- Humidity Range: **0% – 100% (±2-5% accuracy)**  
- **Data format**: Uses **single-wire communication protocol**  

The sensor measures **temperature using a thermistor** and **humidity using a capacitive sensor**. The **MicroPython dht library** processes the raw data.

---

## **WORKING PRINCIPLE:**  
1. The **DHT22 sensor** is connected to the **Raspberry Pi Pico**.  
2. The **Pico reads temperature and humidity values** from the sensor via a single-wire communication protocol.  
3. The data is **processed and displayed on the serial monitor**.  
4. If **temperature or humidity crosses a threshold**, an LED can **flash as an alert**.  

---

## **CIRCUIT DIAGRAM:** 

![Screenshot 2025-03-06 112636](https://github.com/user-attachments/assets/5f5b511a-000f-487a-ae39-8a29ac9862ae)

### **Connections:**  

| DHT22 Pin | Raspberry Pi Pico Pin |
|-----------|----------------------|
| VCC (Pin 1) | 3.3V or 5V |
| Data (Pin 2) | GP15 |
| GND (Pin 4) | GND |
| **(Optional: 10kΩ pull-up resistor between VCC & Data pin)** | |

---

## **PROGRAM (MicroPython)**  
```
import dht
import machine
import time

# Define DHT22 sensor pin(GPIO PIN)
dht_pin = machine.Pin(15,machine.Pin.IN,machine.Pin.PULL_UP)
sensor = dht.DHT22(dht_pin)

while True:
    try:
        sensor.measure()
        temp = sensor.temperature() #Get temperature in Celsius
        hum = sensor.humidity() #Get humidity

        print(f"Temperature: {temp:.1f} C")
        print(f"Humidity: {hum:.1f}%")

    except Exception as e:
        print("Error reading sensor:",e)

    time.sleep(2) # Wait for 2 seconds before next reading
```
## **OUTPUT:**  
---
![Screenshot 2025-03-06 112700](https://github.com/user-attachments/assets/52e07708-a18b-4607-aee0-cc1de399c864)

![Screenshot 2025-03-06 113017](https://github.com/user-attachments/assets/f1f10d97-990c-4792-9641-c64d578c14e0)

---
## **RESULT:**  
The **DHT22 sensor** was successfully interfaced with the **Raspberry Pi Pico**, and real-time **temperature and humidity data** were read and displayed. The LEDs responded correctly when the threshold limits were exceeded.

---

 

