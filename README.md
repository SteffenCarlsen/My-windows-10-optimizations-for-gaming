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
4. Right-click on game.exe again, then CPU Priority → Always → High and then Uncheck Windows dynamic thread priority boosts enabled
5. Only do this step if you have a CPU with a lot of virtual cores (Say a 5900x). Right-click on game.exe again and CPU Affinity → Always → click Disable SMT or Disable Hyper-Threading and then uncheck CPU 0 and CPU 1
6. Reboot PC

## Graphics driver installation
1. Download and install DDU [Display Driver Uninstaller](https://www.wagnardsoft.com/forums/viewtopic.php?t=4316)
2. Copy the settings below if you want full optimizations, otherwise pick and choose on demand.

![Settings](https://lh6.googleusercontent.com/uzb_bEKtYPn2xDNgPmPxZJ-8c-IHmJZDcXNw0KmCXjQjHjPRCydZZHsIyxpWqmz5KfOWRHP1KCFKEQt4Z6XmVtaevjq7vuce7J-CLxGgNAI23lweBY6biSbZOzU1SL5L5z80Yy_dmemIWkezkvlbCCA)

3. Download and install [NVCLEANINSTALL](https://www.techpowerup.com/download/techpowerup-nvcleanstall/) (Lets you customize and install the Nvidia driver package)
4. Open the program and select Manually select a driver version
5. Select the latest driver and make sure it says 64 bit Desktop
6. Click Next and do not tick any options and then click Next again
7. Copy the settings you see below on the Installation Tweaks screen then click Next
8. Click Next and then Install and wait for the installation to complete

![Settings](https://lh6.googleusercontent.com/uzb_bEKtYPn2xDNgPmPxZJ-8c-IHmJZDcXNw0KmCXjQjHjPRCydZZHsIyxpWqmz5KfOWRHP1KCFKEQt4Z6XmVtaevjq7vuce7J-CLxGgNAI23lweBY6biSbZOzU1SL5L5z80Yy_dmemIWkezkvlbCCA)

## Extra driver optimizations - Message-signaled interrupts
You can read about MSI mode here: https://old.reddit.com/r/OptimizedGaming/comments/107blhi/msi_mode_on_gpus/
1. Download MSI utility from this repository (Or from the mediafire linked in the reddit post)
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

## Overlocking
You can gain between ~5-20% overall performance by overlocking your hardware. I would only overclock if you're an experienced user. Please don't blindly overlock :)

### RAM
Remember to at the very minimum enable XMP profile. Unless you know what you're doing, I'd probably leave RAM alone :)

### CPU
For AMD Ryzen CPUs look into PBO, can specifically recommend this guide: https://www.youtube.com/watch?v=dU5qLJqTSAc&

To the best of my knowledge, modern Intel CPUs are already pretty much already pushed to their limits. 

### GPU
Download [MSI afterburner](https://www.msi.com/Landing/afterburner/graphics-cards)
If this is your first GPU overclock adventure, start with this video: [MSI Afterburner Settings Explained / AMD and NVIDIA by Jayztwocents](https://www.youtube.com/watch?v=6_Me603fnq8)

![image](https://github.com/SteffenCarlsen/My-windows-10-optimizations-for-gaming/assets/9629847/f76d65f4-7d8c-4c9a-857d-20f895a50bbd)

1. Find the core clock and increase it by 5% of the default value. Put the power limit slider to its maximum value. You may unlink it from temperature and set the temperature limit to 80C for Nvidia, 90C for AMD. Apply the settings. After that run 1 pass of the Unigine benchmark on maximum settings in fullscreen mode to test GPU for stability (signs of instability: driver or application crashes, blackout, graphical artifacts, texture shimmering or missing textures).

2. If you didn't get any signs of instability increase the core clock by 10 MHz and run the benchmark for testing purposes again - you should see the score increase by a little bit in the end of the pass. Keep doing that until your system becomes unstable. Once it does, drop back down 10 MHz (to your last stable configuration). You're about to check if it's indeed stable and you can set on it. Re-run a few more benchmark passes to make sure it's stable. If it's not, drop another 10 MHz and keep testing. After you found the sweet spot your core clock is set. Do not alter it anymore.

3. Increase your memory clock by 100mhz and run the benchmark again. Follow the same testing procedure and do that until you become unstable. Once you do, drop the memory clock by 25 MHz and follow the same testing procedure as with the core clock. After you're done, your memory clock is set as well.

4. Run the benchmark and check the highest temperature that your GPU reaches. If it's over 90C (AMD) increase the fan speed until it's below that. For Nvidia increase fan speed until the temperatures are below 80C to prevent thermal throttling. It's also a very good thing to set up a custom fan curve.

5. You might also want to download a piece of dedicated stress-testing (burning) software like MSI Kombustor/FurMark/OCCT and let it run for some 10-20 minutes at highest settings. It will really push your GPU and test it for stability further. Be wary of the temperatures.

NOTE: It might happen that some instabilities will pop up after hours of intensive GPU usage (like gaming or rendering). Don't worry. Drop the OC down just one more increment (either memory or core, depending on what will work to make GPU stable) and keep at it! 


