# LED-BLINK
# 💡 Experiment 01 – Interfacing a Digital Output (LED) with ARM Development Board

### 🎯 **Aim**
To interface a digital output (LED) to an ARM development board and write a blink code.

---

### ⚙️ **Components Required**
- STM32CubeIDE  
- NUCLEO ARM Development Board  

---

### 🧠 **Theory**

**ARM (Advanced RISC Machine)** is a 32-bit processor architecture developed by ARM Holdings. It is widely used in embedded systems and SoC (System-on-Chip) products. Many semiconductor companies like Samsung, Atmel, and Texas Instruments license ARM architecture to design their own SoCs.
### 🧩 **What is an ARM7 Processor?**
The **ARM7 processor** is commonly used in embedded system applications. It provides a balance between the classic ARM architecture and the newer Cortex series, offering an excellent platform for both hardware and software development.
### 🔍 **LPC2148 Microcontroller**
The **LPC2148**, developed by NXP Semiconductors (Philips), is a 16/32-bit ARM7-based microcontroller featuring a wide range of peripherals.
#### **Key Features**
- 16/32-bit ARM7TDMI-S core in LQFP64 package  
- On-chip **Flash memory**: 32 KB – 512 KB  
- On-chip **SRAM**: 8 KB – 40 KB  
- **ISP/IAP** via on-chip bootloader  
- **Embedded ICE-RT** and **Real Monitor** for real-time debugging  
- **USB 2.0** full-speed device controller with 2 KB endpoint RAM  
- **10-bit ADC** (6 or 14 channels, 2.44 μs conversion time)  
- **10-bit DAC** for analog output  
- **Timers:** Two 32-bit timers, watchdog, and PWM unit  
- **RTC** with 32 kHz clock input  
- **UARTs (2x), I²C (2x)** up to 400 kbit/s  
- **5V-tolerant GPIOs**, 21 external interrupt pins  
- **Max CPU Clock:** 60 MHz using on-chip PLL (lock time 100 µs)  
- **Crystal Frequency:** 1 MHz – 25 MHz  
- **Power modes:** Idle and Power-down with peripheral clock scaling  

---

### 🧭 **Procedure**

1. Open **STM32CubeIDE**.
<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/6304ac81-452e-4be3-b3e6-84b2fb41befc" />


2. Click **File → New STM32 Project**.
<img width="1918" height="1198" alt="image" src="https://github.com/user-attachments/assets/97254480-1e3a-4a64-9577-a95b5448f8e3" />
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/150738c4-5aa7-453d-80c0-43277cb1eb2a" />

3. Select the **target microcontroller** or board and click **Next**.
<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/7cd0ebf2-b1ad-4f7f-a3c4-f3884216fe03" />

4. Name the project.

<img width="586" height="654" alt="image" src="https://github.com/user-attachments/assets/8d7032ad-1009-4236-a961-cd858fe94fd1" />

5. The corresponding `.ioc` file will be generated automatically.
<img width="1704" height="1023" alt="image" src="https://github.com/user-attachments/assets/dafdb2c7-2d97-41b1-848a-bf9266f8a608" />

6. Configure the pins as **GPIO (Input/Output)**, **USART**, etc. as needed.
<img width="1702" height="1017" alt="image" src="https://github.com/user-attachments/assets/3af71561-b8d1-42da-bc30-941f17cc9027" />
<img width="1706" height="1016" alt="image" src="https://github.com/user-attachments/assets/604eb147-8725-465b-8923-0dc568785bca" />

7. Save the configuration (`Ctrl + S`) – the base C program will be generated automatically.
<img width="1706" height="1025" alt="image" src="https://github.com/user-attachments/assets/20dcfcd4-2c67-476b-9cfc-afca92389615" />
 
8. Edit the generated main program as required.
<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/575d0309-b8a3-43dd-827b-8bf45e0944bb" />
<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/40b52f6a-e737-4d00-ab79-e5d10c7f312e" />

9. Click **Project → Build All**.
<img width="958" height="242" alt="image" src="https://github.com/user-attachments/assets/b84811c9-e421-40dc-ba65-1ce4ff707588" />

10. Link the **HEX file** using the post-build process.
<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/700c3102-157a-4324-a017-0b68cd4edd4a" />

11. Click **Debug** and connect the **STM Nucleo Board**.
<img width="1914" height="1199" alt="image" src="https://github.com/user-attachments/assets/85697e72-7de7-480d-9965-2bd99cc68ded" />


13. Click **Run** to execute the program.
    
---

### 💻 **Program**


```c
#include "main.h"

void SystemClock_Config(void);
static void MX_GPIO_Init(void);

int main(void)
{
    HAL_Init();
    SystemClock_Config();
    MX_GPIO_Init();

    while (1)
    {
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET);
        HAL_Delay(1000);
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);
        HAL_Delay(1000);
    }
}
```
---
### OUTPUT
CASE 1: LED ON 

![WhatsApp Image 2025-11-07 at 21 04 19_e5fc9080](https://github.com/user-attachments/assets/a3a1e416-5cf3-4cfa-a629-e94a68e92387)

CASE 2: LED OFF

![WhatsApp Image 2025-11-07 at 21 04 19_9a0756c9](https://github.com/user-attachments/assets/4bf3d4ae-d1d3-4c2e-80cc-d1a53d89ade1)

---
### RESULT
Interfacing a digital output with ARM microcontroller is executed and the results are verified.
