## Test your program

This is the last and most important part of Phase 2.

Before you submit your program, it is vital that you test it using an Astro Pi running the sample Flight OS. This is a special build of the Raspbian operating system, optimised to run on the ISS Astro Pis. It does not include any X-Windows or GUI applications and is command line only. It also has been locked down in terms of security settings. So you definitely need to check that none of the differences between this Flight OS and the version of Raspbian on which you developed your code will cause your experiment to fail.

There are also a few settings in the sample Flight OS that will limit the performance of the Pi, in order to more accurately mimic the capabilities of the Astro Pis on the ISS, which are old Raspberry Pi B+ models. This means that your code will probably run more slowly, especially if you're processing images or looking up locations based on latitude or longitude.

Finally, it’s also important for you to consider any errors that could occur during your program’s run on the on-board Astro Pis’ Flight OS, such as file path errors or overwriting of files. Hundreds of teams submit programs to the challenge each year and, unfortunately, we do not have the capacity to check for mistakes or debug complex code errors: if your program fails to run without errors when we test it on the sample Flight OS, your team will not progress to Phase 3. So to ensure that your entry has the best chance of success, thoroughly test your program, debug any errors, and check it against the coding requirements.

## Test your code on the Flight OS

You need to test that your code will run on the Astro Pi units, with the same packages installed, the exact package versions, and matching configuration. We will test your code on the Flight OS and if it doesn't run without errors, you'll be disqualified, so it's important that you test as much as you can. That's why we've provided the Flight OS for download so you can simulate the same setup as on board the ISS.

You can either use the ready-made images or use the one-line installer to upgrade your Raspbian image to the Astro Pi. We recommend using the ready-made images for your final testing to be sure you have an exact match, particularly the lite image rather than desktop.

### SD card images

- [Astro Pi Desktop image](https://downloads.raspberrypi.org/AstroPi/images/AstroPi-2018-12-03/astropi_stretch_desktop.zip)
- [Astro Pi Lite image](https://downloads.raspberrypi.org/AstroPi_lite/images/AstroPi_lite-2018-12-03/astropi_stretch_lite.zip)

Download your chosen image, extract it from the zip file and use [etcher.io](https://etcher.io/) to write the image to your SD card.

### One-line installer

--- task ---

Download Raspbian Lite from the [Raspberry Pi Downloads page](https://www.raspberrypi.org/downloads/raspbian/).

--- /task ---

--- task ---

Extract the image file from the zip, and write the image to an SD card. Using [Etcher](https://www.balena.io/etcher/) is recommended. See the [Raspberry Pi setup guide](https://projects.raspberrypi.org/en/projects/raspberry-pi-setting-up) for more information.

--- /task ---

--- task ---

Insert the flashed SD card into your Raspberry Pi and boot it. Log in with the username `pi` and password `raspberry`.

--- /task ---

--- task ---

You'll need to connect to the internet. If you have an ethernet connection, connect the cable to the Raspberry Pi. If not, you'll need to use WiFi.

To connect to a WiFi network, enter `sudo raspi-config` and find *WiFi settings* under *Network Options*. See [rpf.io/wifi](http://rpf.io/wifi) for more information.

--- /task ---

--- task ---

Test your internet connection by running the command `ping google.com`. This attempts to reach google.com. If you are connected, you'll see a response repeatedly. Press Ctrl + C to stop. If you see an error, you'll need to try connecting again.

--- /task ---

--- task ---

Now run the one-line installer command:

```bash
curl -sSL rpf.io/apstretch | bash
```

The whole installation will take a long time. You'll see timestamped messages with information about what's going on.

If the installation stops for some reason, try running the command again.

Once the installer has finished, you'll be asked to reboot.

--- /task ---

### Final check

So that your program can run safely and successfully on the ISS, there are some rules it needs to follow. If you've worked through this guide, then your program should already be fine. However, as a final step before you submit your entry, you should double-check that:

1. Your experiment does not rely on interaction with an astronaut
1. Your program is written in Python 3
1. Your program does not rely on any additional libraries other than those listed in this guide
1. Your program does not use networking, and does not start a system process
1. You have documented your program, and it is easy to understand
1. Your data is saved in files as described in this guide and does not use more than 3GB of storage space. No single file should be larger than 35MB
1. If you chose the theme 'Life in space', your program does not save any photos or videos
1. Your program runs without errors and does not raise any unhandled exceptions
1. Your program stops running after 3 hours
1. The LED matrix is updated regularly to indicate that an experiment is running.
1. There is no bad language or rudeness in your program

### Run your code

--- task ---

Connect the Sense HAT and camera module (if required).

--- /task ---

--- task ---

Boot your Raspberry Pi running the Flight OS.

--- /task ---

--- task ---

Copy your code and any required files to the Raspberry Pi.

--- /task ---

--- task ---

The main entry point for your experiment should be named `main.py`. Run it directly with the following command only:

```bash
python3 main.py
```

--- /task ---

--- task ---

Your code should run for three hours and then stop.

When it's finished, observe any output files created by your project. Are you expecting image files from the camera? Data logs? Anything else?

--- /task ---

If you see any errors, or the experiment doesn't do what you expected it to, you'll need to address this before submitting your code to ensure chance of reaching the final judging round.

**Note:** during testing, it may be advisable to disable the Pi's internet connection to make sure your experiment does not use internet access.
