# xSpec32

A portable system information, device inventory and software list tool for **Windows XP through Windows 11**.

Run xSpec32 on any PC to see its hardware and Windows details, save the machine into an organised **Device List**, and keep a list of the software each PC needs, with download links you can fetch and install in one go. Keep one copy on a USB stick for every computer you work on.

- No installer, no runtimes, no admin rights for normal use.
- Works from read-only and removable drives.
- Downloads use HTTPS through a built-in TLS library, so they work on Windows XP too.

## Download

Download **[xSpec32.zip](https://github.com/XMTLXY/xSpec32/releases/latest/download/xSpec32.zip)** (latest release), unzip it and run `xSpec32.exe`. That's all.

All versions are on the [Releases page](https://github.com/XMTLXY/xSpec32/releases).

## Features

**About**: a "View basic information about your computer"-style summary.
- Windows logo and edition, plus the PC maker's (OEM) logo
- Processor, installed RAM, graphics, motherboard and computer name
- Windows Experience Index scores (Vista and newer), with a **Rate this PC** button

**Scan This PC**: the full spec list.
- OS, system, CPU, each RAM stick, disks, graphics, motherboard, BIOS, network adapters
- Battery health for laptops (health %, rating, capacities, charge cycles)
- Suggests a category (Laptops / Desktops / Other), optional nickname and `.txt` copy

**Software**: the programs a PC needs.
- Opens this PC's list automatically; pick any other saved device to edit its list
- Add programs with download links (several versions per program for different Windows versions or 32/64-bit)
- Tick programs and download them, checked with SHA-256; files already downloaded aren't fetched again
- Install the downloads one after another, in the order you set (steps), silently if you add the switches
- Copy the list of another saved device with *Import...*, to set up a PC like one you've done before

**Drivers**: every device and its driver, Device Manager-style, with problem devices flagged. Driver installation, Match INF and the Install Queue are experimental: test them on a machine you can restore first.

**Saved Devices**: browse and manage everything you've saved, with each device's specs and software list.
- **Notes**: write as many notes as you like for each device (how to install its drivers, what to set up, ...). They are plain `.txt` files in a folder next to the device, so they also open in Notepad, and they move with the device.

Press **Alt** for the menu bar (Help → About xSpec32).

## How saving works

```
xSpec32\
    xSpec32.exe         <- start xSpec32 with this
    App\                <- program files
    Drivers\            <- your driver packs
    Downloads\          <- software downloads
    Device List\
        Laptops\
        Desktops\
        Other\
        <your own folders>\
```

Each device is one JSON file named after its nickname or hostname, holding its specs and its software list, plus a `<name> notes` folder once it has notes. If a device with the same name already exists, you can overwrite it (its software list and notes are kept) or keep a dated copy (`NAME_YYYY-MM-DD.json`).

## Credits

- **Vibecoded by:** [XMTLXY](https://github.com/XMTLXY)
- **AI used:** [Claude Code](https://claude.com/claude-code) (Claude Opus 5.5)
- **Windows logos:** [Windows Logo Icon Set](https://www.rw-designer.com/icon-set/winlogos) (CC BY-SA); the logo artwork itself is by Microsoft
- **HTTPS:** [Mbed TLS](https://github.com/Mbed-TLS/mbedtls) (Apache 2.0)
- **JSON:** [cJSON](https://github.com/DaveGamble/cJSON) (MIT)
- **Trusted certificates:** the Mozilla CA bundle (MPL 2.0)

Windows and the Windows logos are trademarks of Microsoft. xSpec32 is not affiliated with or endorsed by Microsoft.

## License

xSpec32 is released under the [MIT License](LICENSE). The third-party code, Windows logos and app icon artwork keep their own terms; see `LICENSE`.
