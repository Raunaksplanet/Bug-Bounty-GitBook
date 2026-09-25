---
layout:
  width: default
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
  anchors:
    visible: true
---

# Basic Terminologies

#### **1. IoT Device**

A physical device connected to the internet that collects, sends, or receives data.

**Example:** Smartwatch, smart bulb, or Amazon Alexa.

**Use Case:** Tracks health data or controls home lighting remotely.

***

#### **2. User Interface**

How users interact with the IoT device.

*   **Web Interface:** Access via a browser.

    _Example:_ Viewing CCTV camera feed through a website.
*   **Mobile Application:** Access via phone app.

    _Example:_ Controlling smart lights using a mobile app.
*   **Any Other:** Voice or physical buttons.

    _Example:_ Saying “Hey Alexa” or pressing a button on a thermostat.

***

#### **3. Wireless Communication**

Used for IoT devices to talk without cables.

*   **Cellular:** Uses SIM card & mobile networks.

    _Example:_ GPS tracker in vehicles.
*   **Wi-Fi:** Uses internet routers.

    _Example:_ Smart TV or home camera.
*   **Zigbee:** Short-range, low-power network.

    _Example:_ Smart bulbs (Philips Hue).
*   **BLE (Bluetooth Low Energy):** Short-range and low battery use.

    _Example:_ Fitness bands or smart locks.

***

#### **4. Hardware**

The physical components of IoT devices.

*   **Serial Interface (UART, SPI, I2C):** Used for internal data communication between chips.

    _Example:_ Sensors sending temperature data to the main processor.
*   **Debug Interface (JTAG, SWD):** Used by developers to test or fix the device.

    _Example:_ Used to troubleshoot firmware bugs in smart TVs.
*   **ICs (Integrated Circuits):** The “brains” or memory chips.

    _Example:_ Microcontroller in Arduino or Raspberry Pi.
*   **SPI Flash IC:** Stores firmware (device software).

    _Example:_ Flash chip in routers storing the OS.
* **Any Other Storage Chip:** Stores logs or configuration data.

***

#### **5. Firmware**

Software programmed into the hardware that makes the device work.

**Example:** The code inside a smart bulb that controls brightness.

**Use Case:** Enables automatic updates or new features.

***

#### **6. Supply Chain**

The path through which the IoT device and its parts are made, assembled, and delivered.

**Example:** From chip manufacturer → device maker → customer.

**Use Case:** Helps identify potential security risks in manufacturing.

***

#### **7. Side Channel**

Indirect data leaks from the device’s physical behavior (like power use or sound).

**Example:** Hackers using power fluctuations to extract encryption keys.

**Use Case:** Used in advanced security testing to find hidden vulnerabilities.
