# Development Environment Setup

This guide walks through setting up a laptop for FTC development. See also the official FIRST guide on [recommended laptops and setup](https://ftc-docs.firstinspires.org/en/latest/programming_resources/laptops/laptops.html).

## Software Installation

### Required

| Software | Purpose | Download |
|----------|---------|----------|
| **Android Studio** | Primary IDE for FTC Java development | [developer.android.com/studio](https://developer.android.com/studio) |
| **Slack** | Team communication | [slack.com/downloads](https://slack.com/downloads/windows) |

### Recommended

| Software | Purpose | Download |
|----------|---------|----------|
| **REV Hardware Client** | Manage REV hardware (firmware updates, backups) | [docs.revrobotics.com/rev-hardware-client](https://docs.revrobotics.com/rev-hardware-client) |
| **GitHub Desktop** | Simplified Git interface | [desktop.github.com](https://desktop.github.com/download/) |
| **FTC Robot Simulator** | Test code without physical hardware | [github.com/Beta8397/virtual_robot](https://github.com/Beta8397/virtual_robot) |

> **Note:** The REV Hardware Client can update the REV Driver Station app, but you can also update it directly via the Software Manager app on the Driver Station itself. See [Updating the DS App](https://ftc-docs.firstinspires.org/en/latest/ftc_sdk/updating/ds_app/Updating-the-DS-App.html).

---

## Windows Configuration

### Taskbar
- Remove default pins (Outlook, Microsoft Store, etc.)
- Add pins for **Android Studio**, **Slack**, and **GitHub Desktop**

### Pointer Visibility Fix
If your cursor disappears as white-on-white in apps like Edge:
- Go to **Control Panel → Mouse → Pointers** tab
- Change **Text Select** to `beam_i.cur`

![Windows Pointer Options](../images/Windows%20Pointer%20Options.png)

### Edge Browser
- On a new tab, click the **Gear icon** and turn off **Sponsored Content** and **Show Feed**

![Edge New Tab Config](../images/Edge%20New%20Tab%20Config.png)

---

## Android Studio Setup

1. Use default settings during install; choose **Don't Send** when asked about usage data sharing
2. Welcome wizard: pick **Standard** setup and accept the License Agreement
3. Sign into GitHub, then open a project via **Get from VCS**
   - If prompted, click **Download and Install** next to the Git error
   - Clone your team's repository

   ![GitHub Clone](../images/AndroidStudio%20-%20GitHub%20Clone.png)

4. Build the project:
   - Dismiss the AGP Upgrade Assistant pop-up with **Don't show again**
   - Expand the **TeamCode** section and click the **hammer icon** to build

   ![Build](../images/AndroidStudio%20-%20Build.png)
   ![TeamCode](../images/AndroidStudio%20-%20TeamCodeProject.png)

### ADB (Android Debug Bridge) Configuration

ADB is used to communicate with the Control Hub over WiFi. Adding it to your system PATH makes command-line usage convenient.

1. Open **Control Panel** → search for **Environment Variables** → **Edit System Environment Variables**
2. Click **Environment Variables**
3. Under **System Variables**, select **Path** and click **Edit**
4. Click **New** and add:
   ```
   C:\Users\<your-username>\AppData\Local\Android\Sdk\platform-tools
   ```
   *(Find the base path in Android Studio → Settings → Languages & Frameworks → Android SDK → Android SDK Location)*

#### ADB Reconnect Shortcut
Create a desktop shortcut for quick ADB disconnect/reconnect (helpful when connection drops):
- Right-click Desktop → **New** → **Shortcut**
- Location: `C:\Windows\System32\cmd.exe /C echo adb disconnect & adb disconnect & echo adb connect 192.168.43.1:5555 & adb connect 192.168.43.1:5555 & pause`
- Name: `ADB Reconnect`

> The first time you run ADB, allow it through Windows Firewall when prompted.

![ADB Authorize](../images/AndroidStudio%20-%20ADB%20authorize.png)

---

## FTC Robot Simulator Setup

The [virtual_robot](https://github.com/Beta8397/virtual_robot) simulator lets you test OpModes without a physical robot. See also the [Programming → Simulator](../programming/README.md#simulator) section.

1. In Android Studio: **File → New → Project from Version Control**
2. Set Version Control to **Git** and enter: `https://github.com/Beta8397/virtual_robot`
3. Go to **File → Project Structure → Project** tab
4. Set the SDK to `liberica-full-17`:
   - If not listed, click **Add SDK → Download JDK**
   - Version: **17**, Vendor: **BellSoft Liberica JDK (Full)**
   - Click **Download**
5. Click the green **Run** arrow to build and launch the simulator

---

## REV Hardware Client Setup

After installing the REV Hardware Client:
1. Run it and click **Check for updates**
2. Under the **Downloads** tab, download:
   - Driver Station App
   - Driver Hub Operating System
   - Control Hub Operating System

![REV Hub Software](../images/REV%20Hub%20Software.png)

---

## Browser Bookmarks

Organize your browser favorites for quick access. Suggested folders:

| Folder | Bookmarks |
|--------|-----------|
| **Tools** | [Android Studio](https://developer.android.com/studio), [Slack](https://slack.com/downloads/windows) |
| **FIRST** | [FTC Software Docs](https://ftc-docs.firstinspires.org/en/latest/), [FTC Game Info](https://www.firstinspires.org/robotics/ftc/game-and-season), [FTC GitHub SDK](https://github.com/FIRST-Tech-Challenge/FtcRobotController), [Simulator](https://github.com/Beta8397/virtual_robot), [FTC Discord](https://discord.com/invite/first-tech-challenge) |
| **RoadRunner** | [RoadRunner Repo](https://github.com/acmerobotics/road-runner), [RoadRunner Docs](https://rr.brott.dev/docs/), [Legacy Docs (LearnRoadRunner)](https://learnroadrunner.com/) |
| **Team** | [Full Metal Falcons GitHub](https://github.com/FullMetalFalcons), [This Documentation](https://github.com/FullMetalFalcons/documentation) |
| **Dashboard** | `192.168.43.1:8080/dash` |
