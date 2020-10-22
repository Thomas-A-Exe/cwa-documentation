# Architecture Corona Warn Buzzer Application

This document outlines the current state of the architecture and basic principle of the CWB application (CWBA) and might change later.

## Overview
The Corona Warn Buzzer application is the is responsible for the overall CWB functionality.
Thus, the main purpose of the CWBA is to take care of user input, as well as to combine the respectice CWB features to an overall system.

### 

### Operating concept 

Considering the process from scooping document, the different states are shown in figure 1:

The behavior and prupose of the respectice states is shown in table below:

 
State | Purpose | Behavior | Lade-LED | Status-LED | Alarm-LED
---------- | ---------- | ---------- | ---------- | ---------- | ---------- 
Off | Devices is switched off | No tracing functionality | Off | Off | Off |
Charging<br/> (Device-off) | Device is switched off but battery is currently charged | No tracing functionality | **Orange**: during recharging <br/> **Green** when recharging finished | Off | Off
Charging<br/> (Device-on) | Device is switched on and battery is currently charged | Tracing activ | **Orange**: during recharging <br/> **Green** when recharging finished | Off | Off
Tracing & Risk evaluation | Only tracing functionality | Tracing activ | Off | **Green**: pulsing when battery load > 20% and accustic & haptic feedback enabled<br/> **Blue** blinking when battery load > 20% and accustic & haptic feedback enabled<br/> **Red** blinking when battery load < 20% and accustic & haptic feedback enabled<br/> **Red/Blue** blinking alternativly when battery level below 20% | Off 
Alerting | Risc encounter detected and Alerting user | Tracing actic <br/> CWB beeps every 10 seconds for 1 minute (repeats very 15 Minutes) short ACK-button press snoozes the alerting for current risc encounter <br/> | As described in Tracing & Risc evaluation | 
