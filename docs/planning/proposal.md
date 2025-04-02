# Final project proposal

- [x] I have reviewed the project guidelines.
- [x] I will be working alone on this project.
- [x] No significant portion of this project will be (or has been) used in other course work.

## Embedded System Description

embedded system will function as a simple real-time clock to display and alarm system using the MSP microcontroller. The system will communicate with an I2C-based RTC module to get and display the current time on an LCD screen. Additionally, it will include a button-controlled alarm feature that activates a buzzer when the set alarm time is reached.

Inputs:
Push Button 1: Used to toggle between the current time display and alarm-setting mode.

Push Button 2: Used to increment the alarm time when in alarm-setting mode.

Process:
The MSP will act as the I2C master, communicating with the RTC module (slave) to retrieve time data.

If the user enters alarm-setting mode, they can adjust the alarm time using Push Button 2.

The microcontroller will compare the current time with the set alarm time and trigger an output if they match.

Outputs:
LCD Screen: Displays the current time or alarm-setting interface.

Buzzer: Sounds an alarm when the set time is reached.
## Hardware Setup

The embedded system will require the following hardware components:

MSP Microcontroller – Acts as the master device, handling I2C communication and user inputs.

Real-Time Clock Module – Provides accurate timekeeping and alarm functionality.

16x2 LCD – Displays the current time and alarm settings.

Push Buttons (x2) – Used for toggling display modes and setting the alarm.

Buzzer – Provides an audible alarm when the set time is reached.

Power Supply – Supplies power to the microcontroller and peripherals.

Pull-up Resistors – Ensures stable I2C communication.
![image](https://github.com/user-attachments/assets/139b67b8-39e5-442f-8c5f-89bdebd30c37)

 
## Software overview

The MSP will be structured into functional blocks, including I2C communication, user input handling, display updates, and alarm activation. Below is a description of how the system will operate:
	-System Initialization:
o	Configure GPIO for push buttons and buzzer.
o	Initialize I2C communication with the RTC module and LCD.
o	Retrieve the current time from the RTC.
-Main Loop:
o	Continuously read RTC time and update the LCD display.
o	Check if Push Button 1 is pressed to toggle between time display and alarm-setting mode.
o	If in alarm-setting mode, detect Push Button 2 presses to increment the alarm time.
o	Compare the RTC time with the set alarm time.
o	If they match, activate the buzzer.
![image](https://github.com/user-attachments/assets/69de1d80-b0c8-456b-82a7-dc207cad2c22)

 

## Testing Procedure
-I2C Communication Test:
o	Use a logic analyzer (such as the Analog Discovery 2) to verify that the MSP correctly communicates with the RTC and LCD via I2C.
-Time Display Test:
o	Verify that the LCD correctly updates the current time by comparing it with an external clock.
-Button Functionality Test:
o	Press Button 1 to ensure it toggles between the time display mode and alarm-setting mode.
o	Press Button 2 multiple times and confirm that the alarm time updates correctly on the LCD.
-	Alarm Activation Test:
o	Set the alarm time to a minute in the future and check if the buzzer sounds when the time matches.


## Prescaler

Desired Prescaler level: 

- [ ] 100%
- [ ] 95% 
- [ ] 90% 
- [ ] 85% 
- [x] 80% 
- [ ] 75% 

### Prescalar requirements 

**Outline how you meet the requirements for your desired prescalar level**

**The inputs to the system will be:**
1.Push Button 1 – Allows the user to toggle between normal time display mode and alarm-setting mode.
2.Push Button 2 – Used to increment the alarm time when in alarm-setting mode.

**The outputs of the system will be:**
1.LCD Display – Shows the current time and alarm settings, updating dynamically based on user input.
2.Buzzer – Activates when the alarm time matches the current time, providing an audible alert.

**The project objective is**

The objective of this project is to design and implement an embedded real-time clock system using the MSP microcontroller. The system will display the current time on an LCD screen, allow users to set an alarm using push buttons, and trigger a buzzer when the alarm time is reached. 

**The new hardware or software modules are:**
New Hardware Modules:
1.	Real-Time Clock Module: This module keeps track of the current time and provides accurate timekeeping, even when power is lost, using an onboard battery backup. It communicates with the MSP microcontroller via I2C.
Push Buttons: Two buttons will be used—one for toggling between time display and alarm-setting mode and the other for incrementing the alarm time.
2.	Buzzer: The buzzer will activate when the current time matches the set alarm time, providing an audible alert.
New Software Modules:
1.	Display Update Module: Responsible for retrieving time data from the RTC and updating the LCD display dynamically.
2.	User Input Handling Module: Manages button presses and their effects, such as toggling display modes and adjusting the alarm time.
3.	Alarm Control Module: Continuously compares the current time with the set alarm time and activates the buzzer when they match.


The Master will be responsible for:

The Master will be responsible for handling I2C communication with the RTC module and LCD, processing user inputs from push buttons, and managing the alarm system. It will continuously retrieve and update the current time, compare it with the set alarm time, and activate the buzzer when the alarm condition is met.

The Slave(s) will be responsible for:

The Slave(s), including the RTC module and LCD, will be responsible for providing accurate timekeeping and displaying the current time or alarm settings. The RTC module will store and update the time, while the LCD will present the information received from the MSP microcontroller. 



### Argument for Desired Prescaler

I think this project meets the 80% prescaler level bc it integrates multiple hardware components, including an MSP microcontroller, RTC module, LCD display, push buttons, and a buzzer, with I2C communication. The software is structured into functional modules for I2C communication, user input handling, time display, and alarm control. As a real-time embedded system, it operates independently, interacting with physical inputs and outputs. The combination of real-time processing, modular software design, and the guidelines justifies the 80% prescaler level.

