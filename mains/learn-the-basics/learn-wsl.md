# 💿 Learn WSL

Here's a README file for your WSL guide:

````markdown
# WSL Guide (Windows Subsystem for Linux)

This guide provides step-by-step instructions for installing and configuring the Windows Subsystem for Linux (WSL) and using additional tools like Win-KeX for graphical interface support.

## 1. Installation

### 1.1 Enable Windows Features
Enable the following features in the Windows Feature app:
- **Windows Subsystem for Linux**
- **Virtual Machine Platform**

### 1.2 Install WSL
Open CMD as an administrator and type:
```bash
wsl --install
````

#### 1.3 Restart Your PC

Restart your computer to apply changes.

#### 1.4 Install Applications from Microsoft Store

Go to the Microsoft Store and install the following:

* **Windows Subsystem for Linux**
* Your preferred Linux Distribution (e.g., Ubuntu, Kali Linux, Debian, Oracle, Arch, etc.)

#### 1.5 Set Up the Linux Distribution

Open the Linux app and complete the installation process for your chosen Linux distribution.

#### 1.6 Final Restart

Restart your PC to finalize the setup.

#### 1.7 Installation Complete

Your WSL installation is now complete.

### 2. Extra WSL Commands to Get Started

#### 2.1 Update WSL

To update the WSL version:

```bash
wsl --update
```

#### 2.2 WSL Version Information

To get information about WSL, WSLg, and the kernel version:

```bash
wsl --version
```

#### 2.3 List Installed Distributions

To get a list of all installed distributions:

```bash
wsl --list
```

Additional options:

*   List all distributions, including those being installed or uninstalled:

    ```bash
    wsl --all
    ```
*   List only currently running distributions:

    ```bash
    wsl --running
    ```
*   Show only distribution names:

    ```bash
    wsl --quiet
    ```
*   Show detailed information about all distributions:

    ```bash
    wsl --verbose
    ```
*   List available distributions for installation:

    ```bash
    wsl --online
    ```

#### 2.4 Set Default Distribution

To set the default Linux distribution:

```bash
wsl --set-default <Distro>
```

### 3. WSLg Installation

#### 3.1 Update and Upgrade Linux Distribution

Open your Linux distribution and run:

```bash
sudo apt update && sudo apt upgrade
```

#### 3.2 Install Win-KeX

Install Win-KeX for GUI support:

```bash
sudo apt install kali-win-kex
```

#### 3.3 Configure Win-KeX

Follow the prompts to fill in the required information.

#### 3.4 Start GUI

To start the GUI, type in the terminal:

```bash
kex
```

### 4. Additional Info on WSLg

#### Modes

* **Window Mode (default)**: \[none]
* **Enhanced Session Mode**: `--esm` - Launch Win-KeX desktop in a dedicated window using Windows native RDP.
* **Seamless Mode**: `--sl` - Integrate Win-KeX into the Windows desktop seamlessly.
* **Window Mode**: `--win` - Launch Win-KeX desktop in a dedicated window.

#### Commands

* **Start Win-KeX server and client**: \[none]
* **Start Win-KeX server**: `--start`
* **Start Win-KeX client**: `--start-client`
* **Launch in Windows Terminal**: `--wtstart`
* **Stop Win-KeX server**: `--stop`
* **Check Win-KeX server status**: `--status`
* **Stop server and kill processes**: `--kill`
* **Set server password**: `--passwd`
* **Start/Stop Windows sound server**: `--start-sound` / `--stop-sound`
* **Manage WSLg unix socket**: `--wslg-restore`, `--wslg-remove`, `--wslg-status`
* **Display Win-KeX version**: `--version`
* **Display help**: `--help`

#### Optional Parameters

* **Use container IP address**: `--ip` or `-i`
* **Optimized for multiscreen**: `--multiscreen` or `-m`
* **Sound support**: `--sound` or `-s`
* **Disable Windows OpenGL**: `--nowgl` or `-n`
* **Disable client reconnecting**: `--norc` or `-r`
* **Wait longer for desktop in SL mode**: `--wait` or `-w`
* **Verbose output**: `--verbose`

#### Examples

*   Start Win-KeX server in window mode and launch Win-KeX client with sound support:

    ```bash
    kex -s
    ```
*   Start Win-KeX in seamless mode and launch Win-KeX client with sound support:

    ```bash
    kex --sl -s
    ```
*   Start Win-KeX in Enhanced Session Mode with ARM workaround and launch Win-KeX client with sound support:

    ```bash
    kex --esm -i -s
    ```
*   Start Win-KeX server as root in window mode and launch Win-KeX client:

    ```bash
    sudo kex
    ```

```

This README provides a comprehensive guide to installing and configuring WSL and WSLg on Windows. Let me know if you need any changes or additions!
```
