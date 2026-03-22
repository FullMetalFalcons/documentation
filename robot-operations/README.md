# Robot Operations

This section covers the practical steps for connecting to, operating, and troubleshooting your FTC robot.

## Connecting to the Robot

1. **Power on** the robot by switching on the main power switch
2. **Wait for the Control Hub** to boot — the WiFi network will appear after roughly 30 seconds
3. **Connect your laptop/Driver Hub** to the Control Hub's WiFi network
4. **Open the Driver Station** app and verify the green indicator next to **Communications**

### Troubleshooting Connection Issues

- If the WiFi network does not appear, power-cycle the robot and try again
- Verify all cables are securely connected to the Control Hub
- If the Driver Station loses connection during operation, use the [ADB Reconnect shortcut](../programming/dev-environment.md#adb-reconnect-shortcut) to re-establish the debug bridge

## Deploying and Running Code

### Prerequisites
- Robot is powered on and connected via WiFi
- Gamepads are connected to the Driver Hub via USB
- Your OpMode has been built and deployed from [Android Studio](../programming/dev-environment.md#android-studio-setup)

### Running an OpMode

1. On the Driver Station, select your **OpMode** from the dropdown
2. Choose the mode: **TeleOp** (manual driving) or **Autonomous**
3. Press **Init** to initialize the OpMode
4. Press **Start** (or wait for the match timer in competition)
5. To stop: press **Stop** on the Driver Station

### Emergency Stop

Press the **Stop** button on the Driver Station to immediately halt all robot activity. In competition, the field management system controls start/stop timing.

> **Important:** After an emergency stop, you may need to re-initialize the OpMode before running again.

## Driver Station Overview

The Driver Station displays several status indicators:

| Indicator | Meaning |
|-----------|---------|
| **Communications** (green) | Connected to the Control Hub |
| **Robot Code** (green) | A valid OpMode is loaded |
| **Gamepads** (green) | Gamepads are detected and mapped |
| **Battery** | Current battery voltage — monitor this during matches |

### Additional Features

- **Error Log** — shows warnings or errors from your code; useful for debugging but often not critical
- **Settings (gear icon)** — displays the robot's network name and configuration
- **USB icon** — shows connected USB input devices; gamepads must be in their designated slots

## Related Topics

- [Getting Started](../getting-started/README.md) — initial hardware and software setup
- [Drive Systems](../drive-systems/README.md) — understanding the drive code you're deploying
- [Programming](../programming/README.md) — writing and building the OpModes you'll run here
