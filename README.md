# Elgato 4K60 Pro MK.2 Color Precision Setup

![before](https://github.com/OfficialLingLing/Elgato_4K_sRGB_EDID/assets/145821569/b5e80499-e798-42ae-b78a-880ace679877)
![after](https://github.com/OfficialLingLing/Elgato_4K_sRGB_EDID/assets/145821569/40eb8d4e-c4c8-4762-aebd-b4ce3555bbdd)


This guide will help you set up your Elgato 4K60 Pro MK.2 for precise colors by using a custom EDID file and configuring various settings in NVIDIA Control Panel and Windows Color Management.

> **Disclaimer:** This setup has only been tested with NVIDIA drivers and is meant for capturing 4K 60hz SDR. Ensure that Elgato 4K Capture Utility is closed before using OBS!

## Part 1: Setup Custom EDID in the Elgato 4K Capture Utility

1. **Download Custom EDID File:** 
   - Download the custom EDID file made using AW EDID Editor with the correct X, Y chromaticity, and gamma for sRGB from [here](https://github.com/OfficialLingLing/Elgato_4K_sRGB_EDID/raw/main/2.2%20srgb.bin).

2. **Configure 4K Capture Utility:**
   - Open the 4K Capture Utility software.
   - Press and hold the `CTRL` key on your keyboard, and while doing so, click on the preferences button at the top right of the 4K Capture Utility.
   - Release the `CTRL` key.
   - In the preferences window, click on the `Device` tab.
   - Select the `4K60 Pro MK.2`, change the `Input EDID Mode` to `Internal`.
   - From the `EDID (Internal)` dropdown, select `Custom`, then select the "2.2 srgb.bin" file you just downloaded. 
   - The dropdown should now say `2.2 srgb`.
   - **Configure Settings as Below:**
     - **Input EDID Mode:** Internal
     - **EDID (Internal):** 2.2 srgb
     - **HDMI Color Range:** Bypass (Same as input)
   - Uncheck both HDR options.
   - Click `OK` to confirm, your capture card will now restart, and display may flicker.

## Part 2: Change Display Setting in NVIDIA Control Panel

1. Open NVIDIA Control Panel, click on `Change Resolution`, select the `3840x2160 CVT` monitor.
2. Select `Use NVIDIA color settings`, ensure `Output color format` is `RGB`, and `Output dynamic range` is `Full`.
3. Click `OK` to confirm, your display may flicker.

## Part 3: Change Windows Color Management Settings

1. Open Start Menu, search "Color Management", and open it.
2. Under Devices, select the "Generic Monitor (3840x2160 CVT)" from the dropdown.
3. Click on the "Add..." button, select "sRGB IEC1966 2.1" then click `OK`.
4. Set the "sRGB IEC1966 2.1" profile as the Default Profile.

## Part 4: OBS Video Capture Device Settings

1. Open OBS and ensure the Elgato 4K Capture Utility is closed.
2. While the device is selected and Activated, in Property for 'Video Capture Device', Click on `Configure Video`.
3. In the Property popup, ensure `Output Color Range` is `Bypass (Default)`.
4. Go to the `Video Proc Amp` tab, click on `Default` (should make everything 128).
5. Configure the following settings in the Property for 'Video Capture Device':
   - **Resolution/FPS Type:** Custom
   - **Resolution:** 3840x2160
   - **FPS:** Highest FPS
   - **Video Format:** XRGB
   - **Color Space:** Default (very important)
   - **Color Range:** Full
   - **Buffering:** Disable

## Final Notes
This setup should help in achieving more accurate color representation through the Elgato 4K60 Pro MK.2. Make sure to compare the colors on the screen with the captured colors to ensure accuracy.
