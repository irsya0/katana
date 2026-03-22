# katana
MSI Katana GF66 11UE Modding Guide

> NOTE: I am not liable for any damage caused to or by the laptop as a result of following this guide.

## vBIOS Modding
Laptop manufacturers usually limit the GPU TDP due to the thermal overhead caused by higher wattage. One can bypass this limit by flashing the vBIOS from another device with the same GPU.
[This](https://youtu.be/ihTNBLoprDQ) YouTube Video shows the process for RTX 3000 series cards.

The [vbios](./vbios) folder contains the required utility (`nvflash.exe`), the original vBIOS ROM of the MSI Katana GF66 11UE (RTX 3060), and the alternative 115W rom I flashed on my device.

Flashing the ROM:
```sh
nvflash.exe -b backup.rom # Create backup of your current vBIOS (this cmd generated the original.rom file)
nvflash.exe --protectoff
nvflash.exe 3060-115-130.rom
```

Be careful when selecting a new vBIOS - you could potentially brick your laptop! Also, keep in mind that a higher GPU TDP not only increases temperatures but can also cause system instability if other components don't receive enough power. Consider using a higher-wattage charger. Important: Ensure that the voltage of the new charger matches that of your original one, or you could damage your laptop.

## Keyboard replacement
As some keys on my laptop keyboard stopped working, I decided to replace it myself.

I used the following [keyboard](https://aliexpress.com/item/1005008693800926.html) with a white backlight. Replacing it requires disassembling the entire laptop and desoldering (and later resoldering) about fifty plastic nibs that hold the keyboard in place. The process is rather tedious. I don't recommend attempting this without prior experience.

## Screen replacement
If you are happy with your laptop screen, you can simply reorder it from a trusted supplier. Otherwise, you may choose to upgrade your panel. First, identify the exact model of your built-in panel (usually a quick Google query is sufficient) and look it up on Panelook. Panelook is a comprehensive database containing specifications for various LCDs. After locating your panel on Panelook, navigate to the "Specs" tab and note the interface features and panel dimensions. When searching for a replacement, ensure that these specifications match. The actual replacement is a matter of few minutes, as shown in the [following video](https://youtu.be/sSD9JbsdDvI).

## Thermals
Clean your laptop fans regularly and replace the stock thermal paste with Honeywell PTM7950. I recommend freezing the thermal pad beforehand to make application easier. [Here](https://aliexpress.com/item/1005005079093393.html) is the one I used.
