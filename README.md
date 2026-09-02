# Automatic Street Light Control System Using Combinational Logic

## Project Overview

This project presents the design and simulation of an Automatic Street Light Control System using combinational logic in Logisim Evolution.

The system controls street-light brightness based on:
- Enable status
- Day/Night condition
- Mobility or motion detection

## Objectives

- Design an automatic street-light control system.
- Implement the system using combinational logic.
- Simulate the circuit using Logisim Evolution.
- Reduce unnecessary energy consumption.
- Provide full lighting only when mobility is detected at night.

## Inputs

| Input | Description |
|---|---|
| E | Master Enable Switch |
| L | Night Light Sensor |
| M | Mobility / Motion Sensor |

### Input Logic

- `E = 1` → System enabled
- `E = 0` → System disabled
- `L = 0` → Day mode
- `L = 1` → Night mode
- `M = 0` → No mobility detected
- `M = 1` → Vehicle or pedestrian detected

## Outputs

| Output | Description |
|---|---|
| F | Full Power Luminaire |
| D | Dim Standby Luminaire |

- `F = 1` → 100% brightness
- `D = 1` → 30% brightness

## System Operation

### 1. Day Mode

When:

`E = 1, L = 0`

The street lights remain OFF.

### 2. Night Mode – No Mobility

When:

`E = 1, L = 1, M = 0`

The system activates dim standby lighting at approximately 30% intensity.

### 3. Night Mode – Mobility Detected

When:

`E = 1, L = 1, M = 1`

The system activates full brightness at 100%.

### 4. System Disabled

When:

`E = 0`

Both outputs remain OFF regardless of the sensor inputs.

## Truth Table

| E | L | M | F | D | Operating State |
|---|---|---|---|---|---|
| 0 | X | X | 0 | 0 | System Disabled |
| 1 | 0 | 0 | 0 | 0 | Day – Lights OFF |
| 1 | 0 | 1 | 0 | 0 | Day – Motion Ignored |
| 1 | 1 | 0 | 0 | 1 | Night – Dim Standby |
| 1 | 1 | 1 | 1 | 0 | Night – Full Brightness |

## Circuit Diagram

The circuit is designed and simulated using Logisim Evolution.

## Simulation Results

### Day Mode

`E = 1, L = 0, M = 0`

Output:

`F = 0, D = 0`

Lights remain OFF.

### Night Mode – No Mobility

`E = 1, L = 1, M = 0`

Output:

`F = 0, D = 1`

Dim standby lighting is activated.

### Night Mode – Mobility Detected

`E = 1, L = 1, M = 1`

Output:

`F = 1, D = 0`

Full brightness is activated.

![Night Motion](Images/night_motion.png)

## Software Used

- Logisim Evolution

## Project Files

- `Automatic_Street_Light.circ` – Logisim circuit
- `Images/` – Circuit and simulation screenshots
- `README.md` – Project documentation
- `Presentation/` – Project presentation

## Energy Efficiency

The system keeps the lights OFF during the day, uses dim standby lighting during periods of no mobility at night, and activates full brightness only when motion is detected.

## Conclusion

The Automatic Street Light Control System was successfully designed and simulated using combinational logic in Logisim Evolution.

The system provides three main lighting conditions:

**Day → OFF**

**Night + No Mobility → DIM**

**Night + Mobility → FULL BRIGHTNESS**

This provides automatic operation and helps reduce unnecessary energy consumption.
