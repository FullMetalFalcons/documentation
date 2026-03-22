# Field-Centric Drive

Field-centric drive is an enhancement to the standard [mecanum drive](mecanum-drive.md) that changes how driver inputs are interpreted.

## Robot-Centric vs. Field-Centric

| Mode | Behavior |
|------|----------|
| **Robot-centric** | Pushing the joystick forward drives the robot in the direction it is currently facing (like an RC car) |
| **Field-centric** | Pushing the joystick forward always drives the robot away from the driver, regardless of which way the robot is facing |

Some drivers find field-centric more intuitive, while others find it disorienting. A common practice is to implement a toggle button so the driver can switch between modes during a match.

## Implementation

The following code augments the standard mecanum drive code. It would be inserted where the green Javadoc comment appears in the [mecanum drive diagram](mecanum-drive.md).

<img width="890" height="635" alt="Field-Centric Drive Code and Diagram" src="https://github.com/user-attachments/assets/322e6e74-1045-4220-9f4a-b0b2fc30a933" />

## Understanding the Math

In the diagram:
- **θ (theta)** is the robot's `headingFieldCentric`
- **pF** and **pS** represent `powerForward` and `powerStrafe` (raw joystick inputs)
- **dF** and **dS** represent `desiredForward` and `desiredStrafe` (transformed outputs)

When the robot faces away from the driver, its heading is 0 degrees. Rotating a standard Cartesian plane 90° to the left makes the rest of the heading values intuitive.

> **Note:** Although the diagrams use degrees for readability, `Math.sin()` and `Math.cos()` require inputs in **radians**.

### Vector Breakdown

The diagram uses colored arrows to illustrate the transformation:

- **Light green arrows** — power the robot should put into strafing (perpendicular to the robot's front)
- **Light blue arrows** — power the robot should put into driving forward (parallel to the robot's front)
- **Dark green / dark blue arrows** — the desired motion vectors (what the driver intends)

The light-colored arrows are the x and y components of the desired motion vectors. Trigonometry derives the equations used in the code to decompose the driver's intended motion into the robot's local reference frame.

## Robot Heading

The robot's heading can be read from:
- The **Control Hub's built-in IMU** (inertial measurement unit)
- An external sensor such as the **goBilda Pinpoint** odometry computer

The code for reading heading is hardware-dependent and not shown in the diagram above. Additionally, depending on how the robot starts on the field, you may need to apply an offset to `headingFieldCentric` so that 0° corresponds to the robot facing away from the driver.
