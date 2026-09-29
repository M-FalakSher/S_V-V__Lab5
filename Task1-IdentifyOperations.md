# Museum Conservation Chamber System - Task 1: Identify Operations

## 1. Identify Operations

### Operations Table - OP-ID | Operation | Purpose

| OP-ID | Operation | Purpose |
|-------|-----------|---------|
| OP-01 | Sensor Self-Test | Validate all essential sensors are functional |
| OP-02 | Environmental-Device Self-Check | Verify control devices are operational |
| OP-03 | Artifact Registration | Record artifact ID and metadata |
| OP-04 | Load Environmental Profile | Retrieve artifact's environmental limits |
| OP-05 | Start Monitoring | Begin continuous sensor data collection |
| OP-06 | Validate Door Closure | Confirm chamber door is closed |
| OP-07 | Activate Conservation | Initiate environmental control and artifact protection |
| OP-08 | Compare Temperature | Check if temperature is within permitted range |
| OP-09 | Compare Humidity | Check if humidity is within permitted range |
| OP-10 | Correct Temperature | Issue command to adjust heating/cooling |
| OP-11 | Correct Humidity | Issue command to adjust humidifier/dehumidifier |
| OP-12 | Verify Correction | Re-read sensors to confirm restoration |
| OP-13 | Activate Protection Mode | Switch to artifact protection priority |
| OP-14 | Reduce Light Exposure | Decrease light intensity for protection |
| OP-15 | Enable Additional Controls | Activate extra environmental systems |
| OP-16 | Generate Alert | Create operator notification |
| OP-17 | Detect Vibration | Identify significant vibration |
| OP-18 | Suspend on Vibration | Stop risky activities |
| OP-19 | Verify Stabilization | Confirm vibration below threshold |
| OP-20 | Suspend on Door Open | Stop environmental operations |
| OP-21 | Re-Entry Safety Check | Verify conditions after door closes |
| OP-22 | Transfer to Emergency Power | Switch to backup power |
| OP-23 | Record Safe Shutdown | Log incident and enter safe state |
| OP-24 | Authorize Artifact Removal | Confirm chamber is safe for removal |

---

## 2. Complete Operation Schema

### Full Operation Details - ID | Operation | Pre-condition | Input | Post-condition

| ID | Operation | Pre-condition | Input | Post-condition |
|----|-----------|-----------------------|-------|-----------------|
| OP-01 | Sensor Self-Test | Chamber powered on | Self-test command | All sensors verified OR failure detected |
| OP-02 | Environmental-Device Self-Check | Chamber powered on | Device verification command | All devices operational OR failure detected |
| OP-03 | Artifact Registration | Artifact physically present in chamber | Artifact ID, metadata | Artifact data stored in system database |
| OP-04 | Load Environmental Profile | Artifact registered in system | Artifact ID | Temperature/humidity limits loaded and stored |
| OP-05 | Start Monitoring | Self-checks complete, artifact profile loaded | Monitoring activation signal | Continuous sensor polling begins |
| OP-06 | Validate Door Closure | Conservation startup initiated | Door sensor reading | Door confirmed closed OR conservation blocked |
| OP-07 | Activate Conservation | Door closed, profile loaded, validation passed | Activation command | System enters CONSERVATION_ACTIVE mode |
| OP-08 | Compare Temperature | System in conservation mode | Current temp reading, target temp range | Temperature status: In-Range OR Out-of-Range |
| OP-09 | Compare Humidity | System in conservation mode | Current humidity reading, target humidity range | Humidity status: In-Range OR Out-of-Range |
| OP-10 | Correct Temperature | Temperature reading out of range | Control signal (heat/cool) | Command sent to heating/cooling device |
| OP-11 | Correct Humidity | Humidity reading out of range | Control signal (humidify/dehumidify) | Command sent to humidity control device |
| OP-12 | Verify Correction | Correction command issued | New sensor readings | Condition restored to range OR still out of range |
| OP-13 | Activate Protection Mode | Recovery period exceeded, condition not restored | Protection mode signal | System enters PROTECTION_MODE |
| OP-14 | Reduce Light Exposure | Protection mode activated | Light dimming command | Light level reduced to safe threshold |
| OP-15 | Enable Additional Controls | Protection mode activated | Additional control activation signal | Extra environmental controls engaged |
| OP-16 | Generate Alert | Protection mode OR critical failure detected | Alert parameters | Alert message transmitted to operator console |
| OP-17 | Detect Vibration | Artifact in chamber, monitoring active | Vibration sensor reading exceeds threshold | Vibration event detected and flagged |
| OP-18 | Suspend on Vibration | Vibration event detected | Suspension command | Risky operations immediately halted |
| OP-19 | Verify Stabilization | Vibration level decreasing | Vibration readings over time interval | Stabilization confirmed OR vibration persistent |
| OP-20 | Suspend on Door Open | Conservation active, door sensor triggered | Door open signal | All environmental operations suspended immediately |
| OP-21 | Re-Entry Safety Check | Door closed again, conservation suspended | Safety verification command | Safe to resume OR hazards detected |
| OP-22 | Transfer to Emergency Power | Power loss detected during conservation | Emergency power activation signal | Emergency power engaged OR power unavailable |
| OP-23 | Record Safe Shutdown | Emergency power unavailable or depleted | Shutdown and incident logging command | Incident recorded, system in safe shutdown state |
| OP-24 | Authorize Artifact Removal | Chamber safe, no active protection response | Removal authorization request | Removal authorized OR removal denied (unsafe conditions) |

---

## Summary

- **Total Operations Identified:** 24
- **Minimum Requirement:** 12 (✓ Exceeded)
- **Coverage Areas:** Startup, Monitoring, Control, Emergency Response, Safety Management

All operations are distinct and do not use state names as operation identifiers.
