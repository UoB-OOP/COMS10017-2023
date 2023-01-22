# Development environment setup

This guide will help you install the following software:

* Git
* IntelliJ IDEA Ultimate Edition 2020.3.2 or newer
* Java (JDK) 17

The general process is to first install IntelliJ (our Java IDE) and then install Java through IntelliJ's user interface.

You may already have some version of Java installed, we will be installing a separate one through IntelliJ 
so you can leave it as-is.

**Your Java installation must not be in WSL, and running Java or IntellJ inside WSL or a virtual machine is
not a supported configuration.**

## MVB 2.11 Lab machines 

A fairly recent version Git is already installed.

To launch the correct IntelliJ, type "ultimate" in the launcher prompt (hover over top left of screen with mouse):

If you are prompted about registering the product, the licence server is located here: http://ls-jetbrains.bris.ac.uk:8080.

Proceed to setup Java [here](INTELLIJ_JDK_SETUP.md).

### Remote Access to Lab machines

See https://uob.sharepoint.com/sites/itservices/SitePages/fits-engineering-linux-x2go.aspx.

## Personal machines

### Windows

**Do not attempt to install Java, Git, or IntelliJ inside WSL or a virtual machine.**

**Keep in mind that WSL is a separate OS, we will be doing development directly on Windows, so you
will still need to install Git on Windows**

First, download Git for Windows [here](https://git-scm.com/download/win). Double click and follow
installation instructions, pick an editor you are familiar with in
the `Choosing the default editor used by Git` screen and *leave the rest of the screens default*.
Once installed, open a terminal by right clicking on the Windows `Start` button and
select `Windows PowerShell` (**Do NOT use WSL here**). In the PowerShell window, verify that Git
works:

```shell
PS C:\Users\YourUserName> git --version
git version 2.30.0.windows.2
```

Proceed to install IntelliJ. Download [Jetbrains toolbox](https://www.jetbrains.com/toolbox-app/),
double-click on the exe and follow installation instructions, *leave all settings default*. Once
installed, it should appear in your system tray, click on the icon and accept the EULA, a product
list should appear. If it does not appear in the system tray, search for `JetBrains Toolbox` in the
start menu. Once you are at the product list, click `install` on
the  `IntelliJ IDEA Ultimate Edition` entry.
`IntelliJ IDEA Ultimate Edition` should be available in the start menu. Check that you can start
IntelliJ without issues. Activate it by using the license server (http://ls-jetbrains.bris.ac.uk:8080) or by [registering for a JetBrains account](https://account.jetbrains.com/login) using your university email.

Proceed to setup Java [here](INTELLIJ_JDK_SETUP.md).

### Linux

**This only applies to your *own* Linux setup that isn't a virtual machine or a lab machine as these will require root permissions**

Git should already be installed if you are one a sane Linux distro, if not, install through your distro's package manager:

* Fedora: `sudo dnf install git`
* Ubuntu/Debian: `sudo apt install git`

Verify that Git has been installed correctly:

```shell
> git --version
git version 2.29.2
```
Proceed to install Jetbrains toolbox by downloading the installer [here](https://www.jetbrains.com/toolbox-app/).
Extract the download and execute the binary file, for example **(note that the filenames will be different)**:

```shell
> wget https://download.jetbrains.com/toolbox/jetbrains-toolbox-1.22.10970.tar.gz
> tar -xf jetbrains-toolbox-1.22.10970.tar.gz
> ./jetbrains-toolbox-1.22.10970/jetbrains-toolbox
```

A product list window should appear shortly on the top right (it may take up to 1 minute on first
launch).
Once you are at the product list window, click `install` on the  `IntelliJ IDEA Ultimate Edition`
entry.
`IntelliJ IDEA Ultimate Edition` should be available in your window manager. Check that you can start
IntelliJ without issues. Activate it by using the license server (http://ls-jetbrains.bris.ac.uk:8080) or by [registering for a JetBrains account](https://account.jetbrains.com/login) using your university email.

Proceed to setup Java [here](INTELLIJ_JDK_SETUP.md).

### macOS

Git is part of Xcode, it will install itself on first launch:

```shell
> git --version
xcode-select: note: no developer tools were found at ....
Choose an option in the dialog to download the command line developer tools.
```
A dialog should appear, accept the agreements and proceed to install.

Proceed to install IntelliJ. Download [Jetbrains toolbox](https://www.jetbrains.com/toolbox-app/).
Like installing any macOS app, open the DMG image and drag the app to the Application directory.
Once the app is copied, click on the icon and accept the EULA, a product list should appear. Search
for `JetBrains Toolbox` in Spotlight if you cannot locate the app. At the product list window,
click `install` on the  `IntelliJ IDEA Ultimate Edition` entry.
`IntelliJ IDEA Ultimate Edition` should be available in *Launchpad*. Check that you can start
IntelliJ without issues. Activate it by using the license server (http://ls-jetbrains.bris.ac.uk:8080) or by [registering for a JetBrains account](https://account.jetbrains.com/login) using your university email.

Proceed to setup Java [here](INTELLIJ_JDK_SETUP.md).
