# Restore backup

## Guide
1. Install Arch + Hyprland (HyDE).
2. Clone the backup repo.
3. Install packages from the text lists (``pkglist_native.txt``).
4. Copy the ``userprefs.conf`` and all the other config files back to ``~/.config/hyprland/``.
5. Manually edit the boot loader to add ``i915.enable_dpcd_backlight=3``.
6. Manually edit ``/etc/environment`` for the cedilla fix.
7. Reboot.

## Packages
``sudo pacman -S - < pkglist_native.txt``
``yay -S - < pkglist_aur.txt``

## Root configs
1. The Kernel Parameter (For AMOLED Brightness)
    -  File: ``/boot/loader/entries/YOUR_ENTRY.conf`` (Systemd-boot) or ``/etc/default/grub`` (GRUB).
    -  Action: Add ``i915.enable_dpcd_backlight=3`` to the options line.

2. The Cedilla Fix (For ' + c = ç)
    -  File: /etc/environment
    - Action: Add these lines:
    ```
    GTK_IM_MODULE=cedilla
    QT_IM_MODULE=cedilla
    ```

3. Specific Packages to Install Manually
    - brightnessctl (For hardware control)
    - solaar (For Logitech MX Keys function keys)
        - change Set OS to Mac OS
    - wev (For debugging, just in case)
