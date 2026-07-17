# Smart-guardian-Band
IoT Based Women Safety and Health Monitoring Safety Device.

## Features

SOS Alert
GPS Tracking
Heart Rate Monitoring
SpO2
Temperature
Fall Detection
Emergency Call
Cloud Monitoring
Android App

## Hardware

ESP32
MAX30102
NEO6M GPS
MPU6050
DS18B20
SIM800L
Battery

## Software

Arduino IDE
Firebase
Android Studio
GitHub

## Circuit Diagram
                           ┌───────────┐
                           │   ESP32   │
                           │ Main MCU  │
                           └─────┬─────┘
                                 │
 ┌───────────────────────────────┼───────────────────────────────┐
 │                               │                               │
 ▼                               ▼                               ▼

┌──────────────┐         ┌──────────────┐               ┌──────────────┐
│  MAX30102    │         │   MPU6050    │               │   DS18B20    │
│ Heart Rate   │         │ Fall Detect  │               │ Temperature  │
│ & SpO₂       │         │ Accelerometer│               │ Sensor       │
└──────┬───────┘         └──────┬───────┘               └──────┬───────┘
       │ SDA/SCL               │ SDA/SCL                      │ DATA
       │                       │                              │
       └───────────────┬───────┴───────────────┬──────────────┘
                       │                       │
                       ▼                       ▼

                  ┌──────────────┐
                  │    ESP32     │
                  └──────┬───────┘
                         │
              ┌──────────┼──────────┐
              │          │          │
              ▼          ▼          ▼

      ┌───────────┐ ┌───────────┐ ┌───────────┐
      │ NEO-6M    │ │ SIM800L   │ │ SOS       │
      │ GPS       │ │ GSM       │ │ BUTTON    │
      └─────┬─────┘ └─────┬─────┘ └─────┬─────┘
            │ UART        │ UART        │ GPIO
            │             │             │
            └──────┬──────┴──────┬──────┘
                   │             │
                   ▼             ▼

          ┌──────────────┐ ┌──────────────┐
          │ VIBRATION    │ │   BUZZER     │
          │ MOTOR        │ │   ALERT      │
          └──────┬───────┘ └──────┬───────┘
                 │ GPIO           │ GPIO
                 └──────┬─────────┘
                        │
                        ▼

               ┌─────────────────┐
               │ Cloud/Firebase  │
               │ Mobile App      │
               └────────┬────────┘
                        │
                        ▼

              ┌──────────────────┐
              │ User/Caretaker   │
              │ Emergency Alert  │
              └──────────────────┘

# Block Diagram

                     SMART GUARDIAN BAND
          IoT Based Women Safety & Health Monitoring System

                                │
                                ▼
                    ┌─────────────────────┐
                    │        ESP32        │
                    │ Main Microcontroller│
                    │    Wi-Fi + BLE      │
                    └─────────────────────┘
         ┌──────────────┼───────────────┬───────────────┐
         │              │               │               │
         ▼              ▼               ▼               ▼

 ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐
 │  MAX30102    │ │   MPU6050    │ │   DS18B20    │ │  NEO-6M GPS  │
 │Heart Rate &  │ │Fall Detection│ │Temperature   │ │GPS Tracking  │
 │SpO₂ Sensor   │ │Accelerometer │ │Sensor        │ │              │
 └──────────────┘ └──────────────┘ └──────────────┘ └──────────────┘
         │              │               │               │
         └──────────────┴───────────────┴───────────────┘
                                │
                                ▼
                     ┌─────────────────────┐
                     │   SOS Push Button   │
                     └─────────────────────┘
                                │
                                ▼
                     ┌─────────────────────┐
                     │ Data Processing &   │
                     │ Emergency Decision  │
                     └─────────────────────┘
                                │
      ┌─────────────────────────┼─────────────────────────┐
      ▼                         ▼                         ▼

┌──────────────┐        ┌──────────────┐         ┌──────────────┐
│ SIM800L GSM  │        │ Vibration    │         │   Buzzer     │
│SMS / Call    │        │ Motor Alert  │         │Audio Alert   │
└──────────────┘        └──────────────┘         └──────────────┘
      │                         │                         │
      └───────────────┬─────────┴───────────────┬─────────┘
                      ▼                         ▼
              ┌──────────────────────┐
              │ Cloud / Firebase     │
              │ Data Logging         │
              └──────────────────────┘
                      │
                      ▼
              ┌──────────────────────┐
              │ Android Mobile App   │
              │ Caregiver Dashboard  │
              └──────────────────────┘
                      │
                      ▼
              ┌──────────────────────┐
              │ User / Caretaker     │
              │ Emergency Contacts   │
              └──────────────────────┘


## Working

1. Power ON the Smart Guardian Band.
2. ESP32 initializes all sensors and communication modules.
3. MAX30102 measures Heart Rate and SpO₂.
4. DS18B20 measures Body Temperature.
5. MPU6050 continuously detects motion and fall events.
6. NEO-6M GPS acquires the user's real-time location.
7. ESP32 processes all sensor data.
8. If everything is normal, the system continues monitoring.
9. If a fall, SOS press, or abnormal condition is detected:
      GPS location is fetched.
      Vibration motor and buzzer are activated.
      SIM800L sends an emergency SMS and phone call.
      Data is uploaded to Firebase/Cloud.
      The Android application receives a notification.
      The caregiver or emergency contacts receive the alert.
10. The system continues monitoring until it is turned off. 

## Future Scope

AI Detection
Voice Command
5G
Satellite Tracking

## Authors

Ritam Kayal
