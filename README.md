# HDD/SSD Info

Conversation about installing Windows 7 Ultimate SP1 on a Samsung 850 Pro SSD (ASUS A55D) — GPT to MBR conversion.

## Summary

When trying to install Windows 7 on a GPT-partitioned SSD, the installer blocks with:

> "Windows can't be installed to this disk. The selected disk is of the GPT partition style."

### Solution

**Option 1 — Convert disk to MBR** (via Shift+F10 during install):

```cmd
diskpart
list disk
select disk N    (N = your SSD number)
clean
convert mbr
exit
```

Then refresh the disk selection in the installer.

**Option 2 — Boot in UEFI mode** (if your board supports UEFI and you're using 64-bit Windows 7):

Select the UEFI-prefixed option in the boot menu to install on GPT without converting.
