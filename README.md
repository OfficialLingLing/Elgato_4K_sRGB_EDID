# Elgato 4K60 Pro MK.2 Accurate Color Setup for sRGB 4:4:4 Capturing

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

![Snipaste](https://github.com/OfficialLingLing/Elgato_4K_sRGB_EDID/assets/145821569/b51fd2a3-8fc1-4e1a-b514-83ddadeb4a2a)

## Part 2: Change Display Setting in NVIDIA Control Panel

1. Open NVIDIA Control Panel, click on `Change Resolution`, select the `3840x2160 CVT` monitor.
2. Select `Use NVIDIA color settings`, ensure `Output color format` is `RGB`, and `Output dynamic range` is `Full`.
3. Click `OK` to confirm, your display may flicker.

![Snipaste_2023-09-22_23-10-18](https://github.com/OfficialLingLing/Elgato_4K_sRGB_EDID/assets/145821569/ab2f6419-6417-4602-8c89-155888a32b98)


## Part 3: Change Windows Color Management Settings

1. Open Start Menu, search "Color Management", and open it.
2. Under Devices, select the "Generic Monitor (3840x2160 CVT)" from the dropdown.
3. Click on the "Add..." button, select "sRGB IEC1966 2.1" then click `OK`.
4. Set the "sRGB IEC1966 2.1" profile as the Default Profile.

![Snipaste_2023-09-22_23-56-15](https://github.com/OfficialLingLing/Elgato_4K_sRGB_EDID/assets/145821569/9d59e68e-f0a7-4e77-b874-a60a8747114f)

![Snipaste_2023-09-22_23-56-34](https://github.com/OfficialLingLing/Elgato_4K_sRGB_EDID/assets/145821569/66f927e9-b22e-46c9-9518-6ba7addd943f)


## Part 4: OBS Video Capture Device Settings

1. Open OBS and ensure the Elgato 4K Capture Utility is closed.
2. While the device is selected and Activated, in Property for 'Video Capture Device', Click on `Configure Video`.

![Snipaste_2023-09-22_23-57-41](https://github.com/OfficialLingLing/Elgato_4K_sRGB_EDID/assets/145821569/08646105-60f8-414d-9e3d-d7daa2ce0522)

3. In the Property popup, ensure `Output Color Range` is `Bypass (Default)`.
4. Go to the `Video Proc Amp` tab, click on `Default` (should make everything 128).

![Snipaste_2023-09-22_23-58-08](https://github.com/OfficialLingLing/Elgato_4K_sRGB_EDID/assets/145821569/3d9c7c79-809d-4251-b566-83b9f9d87f1f)

5. Configure the following settings in the Property for 'Video Capture Device':
   - **Resolution/FPS Type:** Custom
   - **Resolution:** 3840x2160
   - **FPS:** Highest FPS
   - **Video Format:** XRGB
   - **Color Space:** Default (very important)
   - **Color Range:** Full
   - **Buffering:** Disable

![Snipaste_2023-09-22_23-59-03](https://github.com/OfficialLingLing/Elgato_4K_sRGB_EDID/assets/145821569/8c356053-3027-4336-8d90-0327201b1769)


## Final Notes
This setup should help in achieving more accurate color representation through the Elgato 4K60 Pro MK.2. Make sure to compare the colors on the screen with the captured colors to ensure accuracy.
