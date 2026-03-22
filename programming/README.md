# Programming

This section covers the software tools, libraries, and frameworks used in FTC robot programming.

## FTC SDK

The [FTC Robot Controller SDK](https://github.com/FIRST-Tech-Challenge/FtcRobotController) is the official base software for all FTC teams. Every team's codebase is built on top of this SDK. Your team's code lives in the **TeamCode** module within the project.

**Key resources:**
- [FTC Android Studio Programming Tutorial](https://ftc-docs.firstinspires.org/en/latest/programming_resources/android_studio_java/Android-Studio-Tutorial.html) — official step-by-step guide
- [FTC Software Documentation](https://ftc-docs.firstinspires.org/en/latest/) — comprehensive reference

### Getting Your Code on the Robot

1. Connect your laptop to the Control Hub's WiFi network
2. In Android Studio, ensure the device dropdown shows the connected Control Hub
3. Click the **Run** button to build and deploy your OpMode
4. Open the Driver Station and select your OpMode from the list

For detailed connection and operation instructions, see [Robot Operations](../robot-operations/README.md).

## Drive Code

The drive system code is one of the first things you'll work on. These pages cover both the theory and implementation:

- **[Mecanum Drive](../shared/mecanum-drive.md)** — the standard holonomic drive used by most FTC teams
- **[X-Drive](../shared/x-drive.md)** — an alternative holonomic layout
- **[Field-Centric Drive](../shared/field-centric-drive.md)** — an enhancement that makes joystick inputs relative to the field

> These pages are shared with the [Engineering](../engineering/README.md) section, which covers the design theory behind these drive systems.

## RoadRunner

[RoadRunner](https://github.com/acmerobotics/road-runner) is a popular library built on top of the FTC SDK for advanced autonomous robot motion. It provides trajectory planning, motion profiling, and localization.

| Resource | Description |
|----------|-------------|
| [RoadRunner Quickstart](https://github.com/acmerobotics/road-runner-quickstart) | Template repo to integrate RoadRunner into your project |
| [RoadRunner Docs](https://rr.brott.dev/docs/v1-0/tuning/) | Community documentation with tuning guides |
| [LearnRoadRunner (Legacy)](https://learnroadrunner.com/) | Older docs that still contain useful conceptual explanations |

RoadRunner is discussed extensively on the [FTC Discord Server](https://discord.com/invite/first-tech-challenge), which has a dedicated channel for it.

## Simulator

The [FTC Robot Simulator (virtual_robot)](https://github.com/Beta8397/virtual_robot) allows you to test OpModes without a physical robot. This is invaluable for:
- Learning to code when you don't have access to the robot
- Rapid iteration on autonomous routines
- Testing drive system logic (see [Drive Code](#drive-code) above)

For installation instructions, see [Development Environment Setup](../getting-started/dev-environment.md#ftc-robot-simulator-setup).

## IDE & Tools

| Tool | Purpose |
|------|---------|
| [Android Studio](https://developer.android.com/studio) | FTC-preferred IDE for Java development |
| [REV Hardware Client](https://docs.revrobotics.com/rev-hardware-client) | Firmware updates, backups, and hub management |
| [GitHub Desktop](https://desktop.github.com/download/) | Simplified Git client |

For full setup instructions, see [Development Environment Setup](../getting-started/dev-environment.md).
