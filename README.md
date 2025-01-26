# Self-Checkout-Smart-Shopping-Cart
## Overview
The **IoT-Based Self Checkout Smart Shopping Cart** is an embedded system designed to automate in-store shopping, eliminating long checkout queues through real-time product tracking and billing. The system leverages **RFID technology, Wi-Fi connectivity, and an Arduino Mega 2560 microcontroller** to streamline the shopping experience by dynamically managing the cart's contents and generating automated bills.

## Features
- **RFID-Based Product Detection**: Uses the **RC-522 RFID module** to identify and track purchased items.
- **Wireless Communication**: Utilizes **ESP8266 Wi-Fi module** for real-time data synchronization with a remote server.
- **Automated Billing System**: Generates a unique **Order ID** and retrieves product details from a **MySQL database**.
- **User Interface**: Displays cart contents and total bill on a **16x2 LCD screen**.
- **Product Addition/Removal**: Users can dynamically add or remove products, with instant updates to the bill.
- **Power Optimization**: Integrated **buck converter and voltage regulators** ensure efficient power management.

## System Architecture
1. **RFID Module (RC-522)**: Reads product tags and sends UID to the microcontroller.
2. **Arduino Mega 2560**: Acts as the central processing unit, handling RFID inputs and interfacing with peripherals.
3. **ESP8266 Wi-Fi Module**: Establishes communication with a web server for fetching product details.
4. **16x2 LCD Display**: Provides real-time feedback on scanned items and total bill.
5. **MySQL + PHP Backend**: Stores product data, handles order processing, and generates bills.
6. **Push Buttons & Buzzer**: User controls for removing items and alerting successful scans.

## Hardware Components
- **Arduino Mega 2560**
- **RFID Module (RC-522) with RFID Tags**
- **ESP8266 Wi-Fi Module**
- **16x2 LCD Display**
- **Potentiometer (10k ohm)**
- **Push Buttons & Buzzer**
- **Power Supply (Li-Po Battery + Buck Converter)**
- **Jumper Wires & Breadboard**

## Software Requirements
- **Arduino IDE** (C/C++ for hardware programming)
- **MySQL & phpMyAdmin** (Database Management)
- **PHP** (Server-side scripting)
- **HTML/CSS & JavaScript** (Web Interface for bill generation)

## Installation & Setup
### 1. Hardware Setup
- Connect the **RFID Module (RC-522)** to the Arduino Mega.
- Interface the **ESP8266 Wi-Fi Module** for wireless communication.
- Connect the **LCD Display** to display real-time product details.
- Ensure proper power regulation with the **buck converter**.

### 2. Software Setup
1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/smart-shopping-cart.git
   cd smart-shopping-cart
   ```
2. **Upload the Arduino Code**:
   - Open `shopping_cart.ino` in Arduino IDE.
   - Install necessary libraries (`MFRC522`, `SPI`, etc.).
   - Configure Wi-Fi credentials in the code.
   - Upload the sketch to the **Arduino Mega**.
3. **Set Up the Database**:
   - Import the `database.sql` file into **phpMyAdmin**.
   - Update `config.php` with correct database credentials.
4. **Run the PHP Server**:
   ```bash
   php -S localhost:8000
   ```
   - Ensure the server is reachable by the ESP8266 module.

## Usage Instructions
1. **Start the system**: Press the **reset button** to initialize the cart.
2. **Scan products**: Place items near the **RFID reader** to add them to the cart.
3. **Remove products**: Press the **remove button** and scan an item to delete it.
4. **Generate Bill**: Press the **generate bill button**, retrieve the **Order ID**, and proceed to checkout.
5. **View Bill Online**: Enter the **Order ID** on the web portal to view a **detailed invoice**.

## Future Improvements
- **AI-powered Shopping Suggestions**
- **Mobile App Integration for Contactless Checkout**
- **Voice Assistance for Shopping Guidance**
- **Multi-cart Synchronization for Shared Lists**
