# Table of Contents

- [Introduction](#introduction)
- [Step 1 — Prepare the Windows Installer](#step-1--prepare-the-windows-installer)
- [Step 2 — Create Windows To Go](#step-2--create-windows-to-go)
- [Step 3 — Configure BIOS](#step-3--configure-bios)
- [Step 4 — Boot from the External SSD](#step-4--boot-from-the-external-ssd)
- [Problem 1 — Disk Not Ready to Boot](#problem-1--disk-not-ready-to-boot)
- [Problem 2 — No WiFi Driver](#problem-2--no-wifi-driver)
- [Final Result](#final-result)

Dual Boot Using an External SSD (Windows To Go)
- [Introduction](#introduction)

Hi,

This is my journey to dual boot using an external SSD. Dual booting on a single NVMe drive can be very annoying, so I decided to give Windows To Go a try.

Linux is fun, but Windows still has many things that Linux does not. If you like both systems, why not use both?

- [Step 1 — Prepare the Windows Installer](#step-1--prepare-the-windows-installer)

First, you need a Windows laptop (you can borrow one from a friend for a few minutes). Install Windows 10 or Windows 11, depending on your laptop.

If your laptop is a newer generation, you should download Windows 11 because it usually has better driver support.

Download:

A Windows ISO file (from a trusted website)

Rufus

Hardware needed:

An SSD enclosure

An SSD (256GB or larger recommended)

Make sure the SSD has good speed, because Windows will run directly from it.

Step 2 — Create Windows To Go

Open Rufus.

Select your SSD device

Select the Windows ISO

Keep the default settings

When selecting the Windows version, choose:

Windows To Go (Important: If you select another option, it may fail.)

Click Start and wait for Rufus to finish.

Step 3 — Configure BIOS

After Rufus finishes:

Enter your BIOS settings

Disable Secure Boot

Disable other boot security protections if necessary

Enable external boot / USB boot

(BIOS settings depend on your laptop model.)

Step 4 — Boot from the External SSD

Restart your laptop and open the Boot Menu.

Common boot keys:

Lenovo → F12

Dell → F12

Others may vary

You should see your external SSD listed (for example: Gigabyte SSD).

Select it to boot.

Problem 1 — Disk Not Ready to Boot

My first problem was that the disk was not ready to boot.

The error suggested:

"Change the partition to NTFS"

To fix this, I cleaned the disk and formatted it as NTFS using the command prompt.

Press:

Shift + F10

Then run:

diskpart
list disk
select disk 0
clean
convert gpt
create partition primary
format fs=ntfs quick
exit

⚠️ Important: Make sure you select the correct disk before running clean.

After that, select the disk again and continue booting.

Problem 2 — No WiFi Driver

After booting into Windows, I had no WiFi driver installed.

My laptop uses WiFi 6, and I did not have an Ethernet port, so I could not download drivers.

I searched on Reddit and other forums but found no clear answer.

Then I remembered a simple trick:

Use your phone's USB tethering.

Steps:

Plug your phone into the laptop

Enable USB tethering / internet sharing

Windows will use your phone’s internet connection

Problem solved. I was able to download:

WiFi drivers

Windows updates

Final Result

After installing all drivers, Windows To Go runs smoothly.

I did not notice any major performance drops during gaming or normal usage.

This is a great alternative to dual booting on the same internal drive.
