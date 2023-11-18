# My windows optimizations

## Running Chris Titus windows debloat

Credit: https://github.com/ChrisTitusTech/winutil

1. Launch terminal/powershell as admin
2. Run the command: `iwr -useb https://christitus.com/win | iex`
3. Under "Tweaks" select the "Desktop preset" and press "Run tweaks".
4. Under "Updates" select the "Security (Recommended) Settings" button.

## Intelligent standby list cleaner (ISLC)
1. Download [ISLC](https://www.wagnardsoft.com/forums/viewtopic.php?t=1256) or take version from repo.
2. Start with the PC
3. Change "The list size is at least" to 1024
4. Change "Free memory is lower than" to ~95% of your total RAM. So for 32GB ram, make it 30000mb, 16GB --> 15000MB etc.
5. Enable custom timer resolution and set it to 0.
6. Press Start

## Windows tweaks
1. Download and install [ProcessLasso](https://bitsum.com/) (software to deeply control processes)
2. Open ProcessLasso
3. Open the "Main"-dropdown → "Active power profile" → "Bitsum highest performance"
3. Open the game you wanna play
4. In your processes right-click on it and navigate CPU Affinity → Always → Select CPU affinity
5. Right-click on game.exe again, then CPU Priority → Always → High and then Uncheck Windows dynamic thread priority boosts enabled
6. Right-click on game.exe again and click Disable SMT or Disable Hyper-Threading and then uncheck CPU 0 and CPU 1
7. Reboot PC

## Graphics driver installation
1. Download and install DDU [(]Display Driver Uninstaller](https://www.wagnardsoft.com/forums/viewtopic.php?t=4316)
2. Copy the settings below

![Settings](https://lh6.googleusercontent.com/uzb_bEKtYPn2xDNgPmPxZJ-8c-IHmJZDcXNw0KmCXjQjHjPRCydZZHsIyxpWqmz5KfOWRHP1KCFKEQt4Z6XmVtaevjq7vuce7J-CLxGgNAI23lweBY6biSbZOzU1SL5L5z80Yy_dmemIWkezkvlbCCA)

3. Download and install (NVCLEANINSTALL)[https://www.techpowerup.com/download/techpowerup-nvcleanstall/] (Lets you customize and install the Nvidia driver package)
4. Open the program and select Manually select a driver version
5. Select the latest driver and make sure it says 64 bit Desktop
6. Click Next and do not tick any options and then click Next again
7. Copy the settings you see below on the Installation Tweaks screen then click Next
8. Click Next and then Install and wait for the installation to complete

![Settings](https://lh6.googleusercontent.com/uzb_bEKtYPn2xDNgPmPxZJ-8c-IHmJZDcXNw0KmCXjQjHjPRCydZZHsIyxpWqmz5KfOWRHP1KCFKEQt4Z6XmVtaevjq7vuce7J-CLxGgNAI23lweBY6biSbZOzU1SL5L5z80Yy_dmemIWkezkvlbCCA)

## Extra driver optimizations - Message-signaled interrupts
You can read about MSI mode here: https://old.reddit.com/r/OptimizedGaming/comments/107blhi/msi_mode_on_gpus/
1. Download MSI utility from this repository
2. Open as administator
3. Find your GPU and turn on MSI mode if supported
4. Set prioity to high
5. Apply and restart

## Disable defender
Disable defender using https://github.com/qtkite/defender-control

## Turn on Hardware-accelerated GPU scheduling

1. Press the Start button and search for Graphics Settings
2. Then click to turn on Hardware-accelerated GPU Scheduling
3. Scroll down and view the settings for "graphics performance preference" from there you can choose the app to set your preference. For Nvidia, this is the Nvidia Control panel. You can select this as a desktop app or Microsoft Store app via the dropdown
4. Click on the app, click options and select high-performance
5. Repeat for any game where you want maximum performance

## Nvidia settings
![Nvidia settings 1](Images/1.png?raw=true "nvidia1")
![Nvidia settings 2](Images/2.png?raw=true "nvidia2")
![Nvidia settings 3](Images/3.png?raw=true "nvidia3")

### Nvidia colors
1. Goto Video -> Adjust video color settings
2. For each monitor, adjust color adjustments to use NVIDIA settings and the full color range.

## BIOS
Enable “resizable BAR” and enable “above 4G” in BIOS. (Only for Intel 10th gen or newer, or AMD Zen 3 or newer. Applicable for Nvidia 30-series or newer only).

Remember to at the very minimum enable XMP profile.