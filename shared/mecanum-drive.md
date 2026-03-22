# Mecanum Drive

Almost every FTC robot uses some form of **holonomic drive**, meaning the robot can move in any direction without turning first. The most common implementation uses **mecanum wheels**.

## How It Works

Mecanum wheels have angled rollers that produce a diagonal force when they spin. With four mecanum wheels positioned correctly, your code can run certain wheels forward and others in reverse, causing different components of the diagonal force vectors to cancel out. The result: the robot can strafe, drive forward/backward, and rotate — all independently.

The diagram below shows the code for mecanum drive as well as visualizations of how the vector math works:

<img width="1008" height="645" alt="Mecanum Drive Code and Vector Diagram" src="https://github.com/user-attachments/assets/1e9460f0-791e-4d29-aa34-ddcbc1d212aa" />

## Power Scaling

Motors can only accept power values ranging from -1.0 to 1.0. If we don't scale the calculated powers down, values larger than 1.0 get truncated (clipped), and the robot's motion won't accurately reflect the driver's inputs. The code divides all motor powers by the largest absolute value to keep everything within range.
