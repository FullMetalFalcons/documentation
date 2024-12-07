# Install Key Software
* Critical development tools
  * Android Studio - Ladybug - https://developer.android.com/studio
  * Slack - https://slack.com/downloads/windows 
* 3D design software??
* Slicing software for 3D printer??
* Discord app??
* Additional tools per https://ftc-docs.firstinspires.org/en/latest/programming_resources/laptops/laptops.html 
  * REV Hardware Client - https://docs.revrobotics.com/rev-hardware-client 
    * This can update the REV Driver Station, but maybe it’s better to just do it via the Software Manager app on the Driver Station (see https://ftc-docs.firstinspires.org/en/latest/ftc_sdk/updating/ds_app/Updating-the-DS-App.html )
  * GitHub Desktop - https://desktop.github.com/download/ 
    * Maybe this will make interfacing to GitHub easier, or should we just use Android Studio?

# Configure Software
* Windows
  * Cleanup the apps pinned in the taskbar:
    * Remove default apps like *Outlook* and *Microsoft Store*
    * Add pins for *Android Studio*, *Slack* and *GitHub Desktop*
  * Fix issue with pointer disappearing as white-on-white in apps like Edge (per [reddit](https://www.reddit.com/r/MicrosoftEdge/comments/wo2rtl/white_mouse_cursor_on_white_background_with_light/?rdt=37359 ))
    * Control Panel -> Mouse -> Pointers panel ->  "Text Select" -> beam_i.cur
    ![Windows Pointer](https://github.com/FullMetalFalcons/documentation/blob/main/2024/onboarding/images/Windows%20Pointer%20Options.png)
* Edge
  * Customize the New Tab experience via the Gear icon on a new tab to turn off *Sponsored Content* and *Show Feed*
  ![Edge New Tab Config](https://github.com/FullMetalFalcons/documentation/blob/main/2024/onboarding/images/Edge%20New%20Tab%20Config.png)
  * Add bookmarks to the Favorites Bar in these folders.  Do this at once by importing https://github.com/FullMetalFalcons/documentation/blob/main/2024/onboarding/edge_favorites.html or manually from this list:
    * Tools
      * Android Studio - https://developer.android.com/studio
      * Slack - https://slack.com/downloads/windows
    * FIRST
      * FTC Software Docs - https://ftc-docs.firstinspires.org/en/latest/ 
      * FTC Game - https://www.firstinspires.org/robotics/ftc/game-and-season 
      * Programming Resources https://ftc-docs.firstinspires.org/en/latest/programming_resources/laptops/laptops.html 
      * FTC GitHub - https://github.com/FIRST-Tech-Challenge/FtcRobotController
      * GitHub - Beta8397/virtual_robot Simulator - https://github.com/Beta8397/virtual_robot
      * Discord - https://discord.com/invite/first-tech-challenge 
    * RoadRunner
      * Roadrunner SW - https://github.com/acmerobotics/road-runner 
      * Roadrunner docs - https://rr.brott.dev/docs/ 
      * Old Roadrunner docs with good content - https://learnroadrunner.com/feedforward-tuning.html#tuning 
    * Full Metal Falcons
      * FullMetalFalcons Docs - https://github.com/FullMetalFalcons/documentation
      * FullMetalFalcons GitHub - https://github.com/FullMetalFalcons
    * Robot Dashboard - 192.168.43.1:8080/dash
  * GitHub Desktop
    * Use default settings during install
    * Sign into GitHub via Edge, then click on *Sign in to GitHub.com* button
  * Android Studio
    * Use default settings during install, but pick _Don’t Send_ when asked about sharing usage data
    * Welcome wizard:
      * Pick Standard setup
      * Accept the License Agreement
    * Sign into GitHub, then in Android Studio, open a project via Get from VCS
      * Next to the error of Git is not installed, click on Download and Install
      * TBD - Download team project
    * Build project
      * As part of the build, say 'Don't show again' for AGP Upgrade Assistant pop-up
      ![AGPUpgrade](https://github.com/FullMetalFalcons/documentation/blob/main/2024/onboarding/images/AndroidStudio%20-%20Build.png)
      * Expand TeamCode section of the project and click on the hammer in the top right of Android Studio to build
      ![TeamCode](https://github.com/FullMetalFalcons/documentation/blob/main/2024/onboarding/images/AndroidStudio%20-%20TeamCodeProject.png)
    * Add *Android Debug Bridge (ADB)* to the Windows PATH so it is available from the command line (for easy connect/disconnect)
      * Under Control Panel search for *Environment Variables*, pick *Edit System Environment Variables*
      * Click the *Environment Variables* button
      * Under *System Variables* select *path* and click *Edit*
      * Click *New* to add a new path
      * Enter `C:\Users\robot\AppData\Local\Android\Sdk\platform-tools` as a new path so that adb will be available from the command line
        * (note the base of this path came from *Android Studio -> Settings -> Languages & Frameworks -> Android SDK -> Android SDK Location*)
    * Create ADB shortcut on the desktop to disconnect/reconnect (helpful when having ADB connection issues with the robot)
      * On the Desktop, right click and choose *New* -> *Shortcut*
        * In the *Location* field enter `C:\Windows\System32\cmd.exe /C echo adb disconnect & adb disconnect & echo adb connect 192.168.43.1:5555 & adb connect 192.168.43.1:5555 & pause`
        * For the *name* enter `ADB Reconnect`
      * NOTE: The first time you run ADB you need to allow it in the Windows Firewall via the popup:
      ![ADB Popup](https://github.com/FullMetalFalcons/documentation/blob/main/2024/onboarding/images/AndroidStudio%20-%20ADB%20authorize.png)
    * Download each team’s repo?
  * REV Hardware Client
    * After install, run it and click the ‘Check for updates’ button
    * Under the Downloads tab, click the Download button next to:
      * Driver Station App
      * Driver Hub Operating System
      * Control Hub Operating System
    ![REV SW](https://github.com/FullMetalFalcons/documentation/blob/main/2024/onboarding/images/REV%20Hub%20Software.png)
