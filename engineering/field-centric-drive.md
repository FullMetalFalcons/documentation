# Field-Centric Drive — Engineering Perspective

> This page covers the math and sensor theory behind field-centric control. For the code implementation, see [Programming — Field-Centric Drive](../programming/field-centric-drive.md).

[](../shared/field-centric-drive.md ':include')

## Design Considerations

- **IMU placement** — the Control Hub's built-in IMU works for most teams, but mounting the hub near the robot's center of rotation improves accuracy
- **Drift correction** — IMU heading can drift over time; some teams reset heading at known field positions or use odometry for correction
- **Driver preference** — not all drivers prefer field-centric; plan for a toggle button in your gamepad mapping

## Next Steps

- **[Mecanum Drive](mecanum-drive.md)** — the base drive system this builds on
- **[Building](../building/README.md)** — IMU and sensor wiring considerations
