# Multi-Core RC4 Code-Breaking

This repository contains the design and implementation of an **RC4 decryption and brute-force cracking circuit**, created as part of the **CPEN 311: Digital Systems Design** course at the **University of British Columbia**.

---

## Overview

This project explores the RC4 stream cipher through hardware implementation. We first design a functional RC4 decryption core and then extend the system to perform a brute-force attack to recover a secret key. The project emphasizes hands-on experience with:

- Modular hardware design
- Multiple FSMs (Finite State Machines)
- On-chip memory structures
- Signal synchronization and glitch-free design principles

---

## Project Structure

The project is divided into three main tasks:

### Task 1: Memory Creation and Initialization

- Create a single-port RAM block using the **Megafunction Wizard**
- Fill memory with values from 0 to 255
- View and verify contents using the **In-System Memory Content Editor**

### Task 2: Single Decryption Core

- Implement the **RC4 Key Scheduling Algorithm (KSA)** and **Pseudo-Random Generation Algorithm (PRGA)**
- Use a **24-bit secret key** set via FPGA switches
- Decrypt a 32-byte encrypted message stored in ROM and store the result in RAM
- Validate the decrypted message using the **In-System Memory Content Editor**

### Task 3: Brute-Force RC4 Cracking

- Modify the design to cycle through all possible 24-bit keys
- Use HEX displays to show the current key being tested
- Use onboard LEDs to indicate:
  - Failed decryption attempts
  - Successful key match

---

## Usage

### Task 1: Creating and Testing Memory

1. Use the Megafunction Wizard to generate 256×8-bit single-port RAM  
2. Fill it with sequential data (0–255)
3. Observe and verify contents using the In-System Memory Content Editor

### Task 2: RC4 Decryption Core

1. Implement KSA and PRGA logic
2. Use board switches to input the 24-bit key
3. Store encrypted message in ROM
4. Decrypt and verify result in RAM using the In-System Editor

### Task 3: Brute-Force Key Cracker

1. Modify the FSM to iterate over all key possibilities
2. Monitor progress via HEX displays
3. Use LEDs to indicate when the correct key has been found

---

## Running the Design

1. Open the project in **Quartus**
2. Compile and generate the bitstream
3. Program the **DE1-SoC FPGA board**
4. Set your desired key using the onboard switches
5. Use the **In-System Memory Content Editor** to verify memory and decryption outputs

---

## Acknowledgments

This lab was originally written by **Prof. Steve Wilton** and adapted for **CPEN 311** at UBC. Special thanks to the TAs for their support and guidance throughout the project.
