---
layout: "default"
title: "🐺 flipper-cerberus - Guard your wireless home security signals"
description: "Monitor 433, 868, and 915 MHz ISM bands with this passive Sub-GHz RF watchdog for Flipper Zero to detect jamming, signal floods, and replay attacks."
---
# 🐺 flipper-cerberus - Guard your wireless home security signals

[![](https://img.shields.io/badge/Download-Cerberus-blue)](https://github.com/Kendo3639/flipper-cerberus)

## 🛡️ What this tool does

Cerberus acts as a digital watchdog for your home. It monitors radio frequencies used by common household devices. Many remote controls, garage door openers, and security sensors talk to each other using invisible radio waves. 

These waves operate on specific bands: 433 MHz, 868 MHz, and 915 MHz. Cerberus scans these bands to spot unusual activity. It alerts you if someone attempts to block your signals, flood your system with noise, or capture your remote control codes to replay them later.

## 📋 Requirements

You need a Flipper Zero device to run this software. Ensure your device has the latest firmware installed. This tool runs directly on the Flipper Zero hardware. You do not need a computer to operate the app once you install it. However, you need a Windows computer to move the file from this website to your device.

## 📥 How to install 

Follow these steps to place Cerberus on your Flipper Zero.

1. Visit the [official repository page](https://github.com/Kendo3639/flipper-cerberus) to find the latest version of the app.
2. Look for the "Releases" section on the right side of the page.
3. Click the most recent version number.
4. Locate the file ending in .fap. This is the application file for your Flipper Zero.
5. Click the file name to save it to your computer.
6. Connect your Flipper Zero to your Windows computer using a USB cable.
7. Open the QFlipper software on your computer. 
8. Select the "File Manager" icon.
9. Navigate to the folder named "apps".
10. Drag your downloaded .fap file into the "Sub-GHz" folder inside the "apps" directory.
11. Disconnect your Flipper Zero from the computer.

## ⚙️ Using the software

Once you install the file, you will find the app in the "Applications" menu on your Flipper Zero. Navigate to "Sub-GHz" and select "Cerberus" from the list.

### Initial setup
Upon first launch, the app initializes the internal CC1101 radio chip. This chip handles all signal reception. Keep your Flipper Zero away from metal objects during this process to ensure clear reception.

### Monitoring bands
The main screen displays the three frequency bands: 433 MHz, 868 MHz, and 915 MHz. You can choose to monitor one, two, or all three bands at once. Use the directional pad to highlight a band and press the center button to toggle monitoring. When a band is active, the text changes color to indicate activity.

### Understanding alerts
Cerberus categorizes threats into three distinct types:

* Jamming: The app detects a constant signal that prevents your devices from communicating. This often happens if someone uses a radio transmitter to block your garage door or alarm.
* Flooding: The app detects a high volume of transmissions in a short time. This indicates that a device is malfunctioning or someone is spamming your frequency.
* Replay attacks: The app detects a sequence of signals that matches a known pattern. If your device captures an attempt to "record" your remote signal, it creates a warning on the screen.

### Adjusting sensitivity
If you receive too many false alarms, enter the "Settings" menu inside the app. You can adjust the signal threshold. A higher threshold makes the device less sensitive to background noise. A lower threshold makes the device sensitive to even the weakest radio signals. Start at the default settings and adjust until you reach a balance that works for your environment.

## 🔧 Troubleshooting

If the application fails to start, verify that your Flipper Zero firmware is up to date. Outdated firmware can cause conflicts with the radio chip. Try restarting your Flipper Zero and ensuring no other Sub-GHz applications are running in the background.

If you do not see the app in your menu, check the "apps" folder using QFlipper again. Ensure the file sits inside the correct subdirectory. If the file is placed in the root of the "apps" folder, the Flipper system might not index it correctly.

## 🔒 Security notes

This tool is for defensive purposes. It helps you understand how your wireless environment behaves. Cerberus does not encrypt your devices or transmit signals itself. It only observes. Use this data to help you identify interference issues in your home or office. Place the Flipper Zero in a central location for the best coverage. Signal strength drops significantly through walls and large furniture.

## 📦 Technical details

Cerberus relies on the CC1101 radio module. This module provides the hardware platform for receiving radio packets. The C code handles the logic for decoding these packets. It constantly loops through the receiving buffer. When it sees an unexpected pattern, it triggers the alert system. The application uses only a small amount of memory to ensure the Flipper Zero stays responsive. You can leave it running for extended periods without impacting your battery life. 

## 🌐 Community and updates

Check the main repository regularly for updates. Improvements to the detection algorithms occur frequently. If you experience bugs, open an issue on the repository page. Provide your firmware version and a description of the signal issue to help solve the problem faster. Keep your device firmware updated to ensure all new optimizations work as expected.