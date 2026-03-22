# Mecanum Drive — Engineering Perspective

> This page covers the theory and vector math behind mecanum drive. For the code implementation, see [Programming — Mecanum Drive](../programming/mecanum-drive.md).

[](../shared/mecanum-drive.md ':include')

## Design Considerations

- **Wheel placement** — all four mecanum wheels must be oriented in an X pattern (the rollers form an X when viewed from above) for correct force vectors
- **Weight distribution** — uneven weight causes one side to grip more than the other, skewing strafing
- **Gear ratio** — affects top speed vs. torque; most FTC teams use the goBILDA or REV default ratios

## Next Steps

- **[X-Drive](x-drive.md)** — an alternative holonomic layout
- **[Field-Centric Drive](field-centric-drive.md)** — adding IMU-based control
- **[Building](../building/README.md)** — assembling the physical drivetrain
