# Smart HVAC & Fire-Safety Controller

An ESP32-based building automation prototype that regulates room temperature with hysteresis control and switches to a fire-alarm state when smoke or gas is detected. Simulated in Wokwi.

## Features
- Temperature and humidity monitoring (DHT22)
- Automatic cooling control with hysteresis (ON above [28]°C, OFF below [25]°C) to prevent relay chattering
- Smoke/gas detection with a priority fire-alarm state: buzzer on, HVAC shut off, alert raised
- State-based logic: Normal, Cooling, Alarm
- Live status on a 16x2 I2C LCD
- Remote data logging to ThingSpeak [or MQTT]

## Hardware (simulated)
ESP32, DHT22, gas/smoke sensor, relay module (cooling unit), buzzer, 16x2 I2C LCD

## How It Works
1. Sensors are read continuously with non-blocking `millis()` timing.
2. The controller evaluates readings and sets the system state.
3. The relay, buzzer, and LCD are driven by that state.
4. Fire detection overrides all other states.

## Tech Stack
ESP32 · Arduino C++ · Wokwi · ThingSpeak [/ MQTT]

## Future Improvements
- PID-based fan speed control using PWM
- Multi-zone monitoring
- Integration with BACnet/Modbus for building management systems

## Simulation
[Wokwi project link]
