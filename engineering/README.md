# Engineering

This section covers the design theory and mechanical principles behind FTC robot systems. Understanding these concepts requires some familiarity with vectors and trigonometry — ask an upperclassman or mentor if anything is unclear, as in-person explanations tend to help more than written ones.

## Drive Systems

Choosing a drivetrain is one of the most important engineering decisions for any FTC robot. The following pages cover the theory, vector math, and trade-offs of the most common holonomic drive systems.

- **[Mecanum Drive](../shared/mecanum-drive.md)** — the standard holonomic drive; covers vector math, roller angles, and power scaling
- **[X-Drive](../shared/x-drive.md)** — an alternative holonomic layout using standard wheels at 45° angles
- **[Field-Centric Drive](../shared/field-centric-drive.md)** — IMU-based control that makes joystick inputs relative to the field

> These pages are shared with the [Programming](../programming/README.md) section, which covers the code implementation of these drive systems.

## Related Topics

- [Programming](../programming/README.md) — implementing drive code in the FTC SDK
- [Building](../building/README.md) — assembling the physical drivetrain
- [Robot Operations](../robot-operations/README.md) — deploying and testing your drive code on hardware
