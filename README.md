# Xavier-FTC Documentation Repository

Welcome to the Xavier-FTC Documentation repository! This repository hopes to provide all the necessary information and resources for team members, mentors, and contributors, interested in programming.

## 2024 Oboarding

- [2024 Onboarding](2024/onboarding/README.md)

## 2023 Student Documentation

For detailed documentation created by a Xavier student:
- [Xavier-FTC Wiki](https://github.com/jevgome/Xavier-FTC/wiki)

## Legacy Documentation

Here is some legacy documentation that we will keep around for posterity until it is deemed redundant. It has been altered recently (11/11/2024) to remove content that is known to be inaccurate.

- [Legacy Readme](legacy/2019/README.md) - This still contains relevant information for Beginners and Mentors regarding github management. Note th

## Useful Links

Here are some useful links for getting started and staying informed:

- [XHS GitHub](https://github.com/FullMetalFalcons) - This is the XHS Full Metal Falcons GitHub organization. Each team's repository for this year starts with the `2024-` prefix.

### Coding Resources
- [FTC Android Studio Programming Tutorial](https://ftc-docs.firstinspires.org/en/latest/programming_resources/android_studio_java/Android-Studio-Tutorial.html)
- [FTC SDK](https://github.com/FIRST-Tech-Challenge/FtcRobotController) - Official base software for all FTC teams.

- **Roadrunner** - Popular software built on top of the FTC SDK for advanced robot positioning and control.
  - [RoadRunner Quickstart Repo](https://github.com/acmerobotics/road-runner-quickstart)
  - [RoadRunner Documentation](https://rr.brott.dev/docs/v1-0/tuning/) - Unofficial documentation with detailed descriptions and tuning guides.

### Software/Tools
- [Android Studio](https://developer.android.com/studio) - FTC-preferred IDE 
- (optional) [REV Hardware Client](https://docs.revrobotics.com/rev-hardware-client) - Windows Client used to manage REV Hardware via USB cable:
  - Update/Reinstall Firmware of Control Hub and Expansion Hub
  - Backup/Restore Control Hub
    - All .xml configuration files
    - All Blocks .blk and .js files
    - All OnBotJava .java files
  - Access Control Hub Web GUI

### General FTC Resources

- [FTC Official Website](https://www.firstinspires.org/robotics/ftc)
- [FTC Game Manuals](https://www.firstinspires.org/resource-library/ftc/game-and-season-info)
- [FTC Forum](https://ftcforum.usfirst.org/)
- [FTC Info](https://ftc-docs.firstinspires.org/en/latest/index.html) - Comprehensive information about the FIRST Tech Challenge.
- [FTC Discord Server](https://discord.com/invite/first-tech-challenge) - Community discussions and support, including a channel dedicated to RoadRunner.

## Teaching Resources & Diagrams
### Mecanum Drive
Almost every FTC robot uses some form of **holonomic drive** (meaning the robot can move in all directions without turning). Most commonly, this is achieved using **mecanum wheels**. Mecanum wheels have angled rollers that cause the wheels to produce a diagonal force when they spin. If the wheels are positioned correctly, then your code can run certain wheels forward and certain wheels in reverse, which causes different components of the diagonal force vectors to cancel out. The diagram below shows the code for mecanum drive as well as visualizations of how the vector math works out:

<img width="1008" height="645" alt="image" src="https://github.com/user-attachments/assets/1e9460f0-791e-4d29-aa34-ddcbc1d212aa" />

In case you're wondering, the reason why we scale all of the powers down to 1.0 or less is because motors can only take power values that range from 0.0 to 1.0. If we did not scale down values, then certain powers would be too large and would get truncated, and all of a sudden the robot's motion would not reflect our inputs properly.

Additionally, a diagram is shown of **X-Drive**, an alternate holonomic drivetrain that uses the same principles and math as mecanum drive. X-Drive is less popular due to the challenge of mounting your wheels at 45 degree angles.

### Field-Centric Drive
Shown below is the code that I like to use to use when making a **field-centric** control system. The code above describes a **robot-centric** control system, in which your controller inputs are all registered relative to the robot. That means that pushing the joystick forward will make the robot drive forward in the direction it is facing (just like an RC car). Field-centric drive, on the other hand, takes your inputs and the robot's direction and makes the robot drive relative to you. This means that pushing the joystick forward will make the robot drive away from you, no matter what direction it is facing. Some people find this more intuitive while others think it is confusing, so being able to toggle field-centric drive on and off is generally a good idea.

The following code segment is meant to augment the standard mecanum drive code given above. It would be inserted where the green comment is in the code above (if you're curious, the reason why that comment is green is because it is a Javadoc comment. I'm not going to go into depth of what that means because that is a topic in of itself, but they are very cool and you should look them up).

<img width="890" height="635" alt="image" src="https://github.com/user-attachments/assets/322e6e74-1045-4220-9f4a-b0b2fc30a933" />

In the diagram of the robot, theta is the robot's "headingFieldCentric", pF and pS stand in for "powerForward" and "powerStrafe," and dF and dS stand in for "desiredForward" and "desiredStrafe." When the robot is facing away from the driver, its heading is considered to be 0 degrees. By rotating a standard cartesian plane 90 degrees to the left, then the rest of the robot's heading values should make sense too. Just note that althogh I wrote the diagrams using degrees to make them more intuitive, Math.sin() and Math.cos() require inputs to be in radians.

The robot's heading can be read from the Control Hub's built in IMU, or from an external sensor such as a goBilda Pinpoint computer. The code for finding this heading is not pictured above, as it will vary depending upon your hardware. In addition, depending upon how the robot starts on the field, you may need to modify headingFieldCentric so that it is 0 when the robot is facing away from the driver.

The diagram above uses **light green arrows** to represent the power that the robot should put into strafing (hence why the arrows are perpendicular to the robot's front) and **light blue arrows** to represent the power that the robot should put into driving forward (hence why the arrows are pointing forward relative to the robot). If you think of the light colored arrows as x and y components of the **desired motion vectors** (which drawn in dark blue and dark green), then trigonomtery can be used to derive the equations that are used in the code. All of that may not make sense until you take Physics and/or PreCalculus and understand what vectors, sine, and cosine are. I would recommend asking an upperclassen if you are confused, as an in-person explanation tends to help far more than one in writing does
