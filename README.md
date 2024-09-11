# Virtual Display Driver
based on Microsoft Indirect Display Driver Sample. This creates a virtual display in Windows that acts and functions just like a real one. It's useful for streaming, virtual reality applications, recording, headless servers, etc. The benefit over a physical display is the ability to adjust resolutions and refresh rates beyond the physical displays capabilities. For example, this would enable the ability to stream a game from your home PC using game streaming software at 240hz at 8K while owning a 60hz 1080p monitor (unrealistic, but explains the abilities well). For servers without displays, this enabled remote desktop and screen streaming to other systems as if there were a display installed. 

Supports emulating resolutions from **640 x 480** to **7680 x 4320 (8K)**, and refresh rates including **60hz, 75hz, 90hz, 120hz, 144hz, 165hz, 240hz, 480hz,** and **500hz.**

This project uses the official Windows Indirect Display Driver combined with the IddCx class extension driver.

## Download Stable Version

- [Windows 10 and 11 (no HDR)](https://github.com/itsmikethetech/Virtual-Display-Driver/releases/tag/23.10.20.2)
- [Windows 11 23H2+ (HDR)](https://github.com/itsmikethetech/Virtual-Display-Driver/releases/tag/23.12.2HDR)

## Download Beta
- [Universal Driver (Windows 10/11)](https://github.com/itsmikethetech/Virtual-Display-Driver/releases/tag/24.9.11) - Adds XML configuration support, automatic/manual GPU selection, and more. Thanks to Bud and Jocke!

 
## Installation

1. Download the latest version from the releases page, and extract the contents to a folder.
2. Copy the `\IddSampleDriver\` folder and its contents to `C:\IddSampleDriver\` before installing the driver **(important!)**.
3. Right click and run the *.bat file **as an Administrator** to add the driver certificate as a trusted root certificate.
4. Don't install the inf. Open device manager, click on any device, then click on the "Action" menu and click "Add Legacy Hardware".
5. Select "Add hardware from a list (Advanced)" and then select Display adapters
6. Click "Have Disk..." and click the "Browse..." button. Navigate to the extracted files and select the inf file.
7. You are done! Go to display settings to customize the resolution of the additional displays. These displays show up in Sunshine, your Oculus or VR settings, and should be able to be streamed from.
8. You can enable/disable the display adapter to toggle the monitors.

Ps. Make sure that options.txt is accesible for the system at `C:\IddSampleDriver\option.txt` or the installation will fail.

## Easy Uninstall

1. Open device manager
2. Locate Display Adapters
3. Right click on IddSampleDriver, choose "Uninstall device"
4. There is a new popup window, in there click Attempt to remove driver for this device.

## Manual/Forced Uninstall

Next instructions are for those cases where the device is removed from the system, but driver stil remains. This happens when there is a connection to the device while trying to remove the drivers. To
remedy this, there is a a few tricks built into windows. So here goes:

5. Open up a powershell terminal and input this:
6.  ```pnputil /enum-drivers```
6. Locate iddsampledriver.inf, there might be multiple pages of text. Make a note of the "published name", it's often unique for your system, but might look like "oem139.inf"
7.  ```pnputil /delete-driver oem139.inf```

## HDR Support Now Available for Windows 11 22H2+ 

### Videos

[![thumbnail2023](https://github.com/itsmikethetech/Virtual-Display-Driver/assets/25166211/1a64c390-5d8a-420f-8bb9-4642349fc132)](https://youtu.be/nNWpbRUPkn4 "How to install a virtual display")

[Previous Video: How to install a virtual display](https://youtu.be/byfBWDnToYk "How to install a virtual display")

### Screenshots:

![image](https://github.com/itsmikethetech/Virtual-Display-Driver/assets/25166211/0f1dfed6-c9ac-4cb6-92cf-7d9ab2ac0c66)

![image](https://github.com/itsmikethetech/Virtual-Display-Driver/assets/25166211/5cb8ce08-890f-4bc1-a1a6-34f22e103699)

![image](https://github.com/itsmikethetech/Virtual-Display-Driver/assets/25166211/02af86f2-b896-4265-9174-b17c9a1aeab7)

## License

MIT and CC0 or Public Domain (for changes I made, please consult Microsoft for their license), choose the least restrictive option.

## Disclaimer:

This software is provided "AS IS" with NO IMPLICIT OR EXPLICIT warranty. It's worth noting that while this software functioned without issues on my system, there is no guarantee that it will not impact your computer. It operates in User Mode, which reduces the likelihood of causing system instability, such as the Blue Screen of Death. However, exercise caution when using this software.

## Acknowledgements

Shoutout to **Roshkins** for the original repo:
https://github.com/roshkins/IddSampleDriver

Shoutout to **Baloukj** for the 8-bit / 10-bit support. (Also, first to push the new Microsoft Driver public!)
https://github.com/baloukj/IddSampleDriver

Shoutout to **Anakngtokwa** for assisting with finding driver sources.

**Microsoft** Indirect Display Driver/Sample (Driver code): 
https://github.com/microsoft/Windows-driver-samples/tree/master/video/IndirectDisplay

Thanks to **AKATrevorJay** https://github.com/akatrevorjay/edid-generator for the hi-res EDID.

Shoutout to **zjoasan** and **Bud** for the helper scripts and build support!

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=itsmikethetech/Virtual-Display-Driver&type=Date)](https://star-history.com/#itsmikethetech/Virtual-Display-Driver&Date)

