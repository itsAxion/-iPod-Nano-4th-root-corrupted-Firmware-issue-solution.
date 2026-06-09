# How to Repair a Corrupted Root Directory on an iPod Nano 4th Gen (8GB)

## Issue Description
When the iPod is plugged into a PC and you try to check the root directory to see your music, images, videos, or podcasts, nothing appears in the file manager. 

In my case, I used the iPod's built-in diagnostics menu (press `Center + Menu` until the Apple logo appears, then quickly press `Center + Previous/Rewind` to enter the hidden tools) to check the health of the NAND memory, and it reported back as healthy.

**Another important fact:** Inside the iPod's settings, the memory manager showed both free space and total space as `0 KB`. This means the system cannot detect the root directory because the partition or filesystem is corrupted.

---

## Prerequisites

First, you will need a PC running **Windows**, as you strictly need to use **iTunes** (this was the only software that worked in my case). 

1. **Install iTunes for Windows:** You can look it up on your browser or use the official download link: <https://support.apple.com/en-us/106372>.
2. **Download the Firmware:** You need to manually download the exact firmware for the iPod Nano 4th Generation (Version 1.0.4). 
   * *Why?* If you try to restore the iPod using only iTunes, the process will freeze or throw a disconnection error. This happens because the original Apple servers hosting these legacy firmwares have been taken down.
   * *Where to find it:* The only third-party source where I found the exact firmware was [AppleDB](https://appledb.dev/device/iPod-nano-(4th-generation).html). If you do not trust this source, you can search for the file on your own.

---

## Step-by-Step Repair Process

### 1. Format the iPod Drive
Before starting, I highly recommend formatting the iPod's internal memory; otherwise, the corruption might freeze the restore process again.
* Go to your **File Manager / This PC**, right-click the iPod drive, and format it to **FAT32**. 
* *(Optional)* In my case, I used `GParted` on Linux beforehand for a cleaner wipe, but Windows formatting should suffice.

### 2. Enter Disk Mode
Put the iPod into **Disk Mode**:
1. Press and hold `Center + Menu` until the Apple logo appears.
2. Immediately press and hold `Center + Play/Pause` until the screen displays **Disk Mode**.

### 3. Restore via iTunes
1. Open iTunes on your PC and connect the iPod via USB.
2. Select your iPod inside the iTunes interface.
3. Hold down the **`Shift`** key on your keyboard and click the **Restore** button in iTunes. 
4. A file explorer window will pop up (this bypasses the Apple servers and lets you select your local file).
5. Browse to and select the `.ipsw` firmware file you downloaded earlier.

The restoration process will begin. Once finished, your iPod's system will be fully restored and the root directory will be functional again.

---

> ⚠️ **Disclaimer:** This is the method that worked for my specific case. I am not responsible if this process does not work for your device or if your iPod gets damaged during the procedure.

## Sources & Downloads
If you have the exact same 8GB model and want to skip searching, I have uploaded a ZIP file containing the exact firmware version I used to the repository files above.
