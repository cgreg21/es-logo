![es-logo.png](es-logo.png) 

# EmulationStation Plymouth Theme

This is a [EmulationStation](https://github.com/RetroPie/EmulationStation) splash screen (i.e, a [plymouth](https://wiki.ubuntu.com/Plymouth) theme) for Ubuntu.

It presents a simple EmulationStation logo in a black background with progress dots. It's based on the `ubuntu-logo-scale-2` plymouth.

## Install

We'll use `git` to install, so make sure you have it installed (if not, run `sudo apt install git`).

Then run the following commands to install this theme:

    cd /usr/share/plymouth/themes
    sudo git clone https://github.com/raelgc/es-logo.git
    sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/es-logo/es-logo.plymouth 100

Now it's installed, but it's not yet the default theme.

## Make it the default 

Run the following commands to make it the default `plymouth` theme:

    sudo update-alternatives --config default.plymouth

You'll see a list of available themes. Select `es-logo.plymouth` number as default and press <kbd>Enter</kbd>.

Now we need to update `initram` with the new default theme:

    sudo update-initramfs -u

Reboot.

## Uninstall

To remove it just run:

    sudo update-alternatives --remove default.plymouth /usr/share/plymouth/themes/es-logo/es-logo.plymouth

And update `initram`:

    sudo update-initramfs -u
