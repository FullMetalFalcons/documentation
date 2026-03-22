# Drive Systems

This section covers the theory and implementation of FTC drivetrain systems. Understanding these concepts requires some familiarity with vectors and trigonometry — ask an upperclassman or mentor if anything is unclear, as in-person explanations tend to help more than written ones.

## Mecanum Drive

Almost every FTC robot uses some form of **holonomic drive**, meaning the robot can move in any direction without turning first. The most common implementation uses **mecanum wheels**.

### How It Works

Mecanum wheels have angled rollers that produce a diagonal force when they spin. With four mecanum wheels positioned correctly, your code can run certain wheels forward and others in reverse, causing different components of the diagonal force vectors to cancel out. The result: the robot can strafe, drive forward/backward, and rotate — all independently.

The diagram below shows the code for mecanum drive as well as visualizations of how the vector math works:

<img width="1008" height="645" alt="Mecanum Drive Code and Vector Diagram" src="https://github.com/user-attachments/assets/1e9460f0-791e-4d29-aa34-ddcbc1d212aa" />

### Power Scaling

Motors can only accept power values ranging from -1.0 to 1.0. If we don't scale the calculated powers down, values larger than 1.0 get truncated (clipped), and the robot's motion won't accurately reflect the driver's inputs. The code divides all motor powers by the largest absolute value to keep everything within range.

## X-Drive

**X-Drive** is an alternative holonomic drivetrain that uses the same vector math principles as mecanum drive but mounts standard wheels at 45-degree angles to the robot chassis. X-Drive is less common in FTC due to the mechanical challenge of mounting wheels at those angles, but it can offer advantages in certain designs.

## Field-Centric Drive

For detailed coverage of field-centric control (which builds on the mecanum drive code above), see the dedicated page:

**→ [Field-Centric Drive](field-centric-drive.md)**

## Related Topics

- [Programming — FTC SDK](../programming/README.md) — where drive code lives in your project
- [Robot Operations](../robot-operations/README.md) — deploying and testing your drive code on hardware
- [Programming — Simulator](../programming/README.md#simulator) — testing drive logic without a physical robot
