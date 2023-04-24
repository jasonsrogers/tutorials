# Docker installation

This guide will give you a quick overview of how to install Docker on your machine. As usual refer to the [Docker documentation](https://docs.docker.com/engine/install//) for further information on how.

Here we will cover the installation of Docker on Windows, MacOs and Linux.

## Windows 10 & 11

### Requirements

The following hardware prerequisites are required to successfully run WSL 2 on Windows 10 or Windows 11:

- 64-bit processor with [Second Level Address Translation (SLAT)](https://en.wikipedia.org/wiki/Second_Level_Address_Translation)
- 4GB system RAM
- BIOS-level hardware virtualization support must be enabled in the BIOS settings. For more information, see [Virtualization](https://docs.docker.com/desktop/troubleshoot/topics/#virtualization).

### Install Docker Desktop

- Download Docker Desktop from [here](https://docs.docker.com/desktop/install/windows-install/).

- Run the installer

- When prompted, ensure the Use WSL 2 instead of Hyper-V option on the Configuration page is selected or not depending on your choice of backend.

- follow the instructions on the screen to complete the installation.

Note:

If your using different accounts (e.g. admin and non-admin), makes sure to add the user(s) that will need Docker to the `docker-users` group.

### Start Docker Desktop

Find `Docker Desktop` in the start menu and click on it to start the application.

You will need to accept the Subscription Service Agreement before it starts.

Once all that is done you should see the Docker Desktop icon in the system tray.

## Linux

### Requirements

- 64-bit kernel and CPU support for virtualization.
- KVM virtualization support. Follow the [KVM virtualization support instructions](https://docs.docker.com/desktop/install/linux-install/#kvm-virtualization-support) to check if the KVM kernel modules are enabled and how to provide access to the kvm device.
- QEMU must be version 5.2 or newer. We recommend upgrading to the latest version.
  systemd init system.
- Gnome, KDE, or MATE Desktop environment.
  For many Linux distros, the Gnome environment does not support tray icons. To add support for tray icons, you need to install a Gnome extension. For example, [AppIndicator](https://extensions.gnome.org/extension/615/appindicator-support/).
- At least 4 GB of RAM.
- Enable configuring ID mapping in user namespaces, see [File sharing](https://docs.docker.com/desktop/faqs/linuxfaqs/#how-do-i-enable-file-sharing).

### Install Docker

We will only cover Linux without any particular flavor or interface, search for your distro in the [Docker documentation](https://docs.docker.com/desktop/install/linux-install/) for further information.

Like anything in Linux, first update your system.

```bash
sudo apt update

sudo apt upgrade
```

If the kernel upgrades, you’ll want to reboot the server with the command:

```bash
sudo reboot
```

Once the system is up to date, install the Docker package.

```bash
sudo apt install docker.io
```

As you've installed this as `sudo` (and you don't want to do dev work as `sudo`), you'll need to add your user to the `docker` group.

```bash
sudo usermod -a -G docker $USER
```

### Starting, stopping, and enabling Docker

Once installed, you will want to enable the Docker daemon at boot. To do this, issue the following two commands:

```bash
sudo systemctl start docker

sudo systemctl enable docker
```

Should you need to stop or restart the Docker daemon, the commands are:

```bash
sudo systemctl stop docker

sudo systemctl restart docker
```

Docker is now ready to deploy containers.

## MacOS

### Requirements

- macOS must be version 11 or newer. That is Big Sur (11), Monterey (12), or Ventura (13). We recommend upgrading to the latest version of macOS.

- At least 4 GB of RAM.

- VirtualBox prior to version 4.3.30 must not be installed as it is not compatible with Docker Desktop.

### Install Docker Desktop

- Download Docker Desktop from [here](https://docs.docker.com/desktop/install/mac-install/).

- Run the installer and follow instructions on the screen to complete the installation.

- Launch Docker Desktop app from the Applications folder

- First time round you will need to accept the Subscription Service Agreement.

- Use recommended settings unless you want to change them and know what your doing.

- Once all that is done you should see the Docker Desktop icon in the system tray.

Note:

If Docker Desktop is not running, you can't use Docker commands in your terminal.

## Conclusion

These are the basics ways to setup Docker on your machine. There are alternatives and caveats to each of these methods, so please refer to the [Docker documentation](https://docs.docker.com/engine/install/) for further information on how.
