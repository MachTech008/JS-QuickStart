# JS-QuickStart

<em> Welcome to the JS QuickStart Instructions for Windows! </em>

This document aims to provide a guide for setting up the developer's workstation on Windows operating system using chocolatey package manager.

REQUIREMENTS
* Processor: Intel Core i3 or higher (ideally Core i5 or i7) 2GHz or more recommended
* Memory: 4GB (8 to 16GB recommended) DDR3
* Hard Drive: 250GB recommended
* Operating System: Windows 7 or higher

1. Select the Windows and start menu, begin typing cmd.exe. This will search for the command prompt. 

2. Right-click the Command Prompt to run cmd *as administrator* This will open a plain windows command line (cmd.exe) as administrator.

3. Click "YES" to the resulting permission prompt.

4. Copy and paste the commands in column 1 below into the command prompt window.

<em> If you encounter any issues during the installation process check whether you are running cmd as administrator. Entering the chocolatey installation command in any kind of Unix shell will result in a failure. Be sure to use plain cmd.exe program for the installation. </em> <br>

| Command       | Result       |
|:------------- |:-------------|
| `@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"` | This should download and setup chocolatey using cmd.exe. |
| `choco --version` | Checks whether everything is working. You should see the current version of Chocolatey if the installation process finished successfully. |
| `cinst -y git & refreshenv` | Installs GIT |
| `cinst -y php --ignore-checksums & refreshenv` | Installs PHP (ignore-checksum flag required since feature was only left in configuration because previous choco had it according to "https://github.com/chocolatey/choco/issues/112".) |
| `cinst -y nodejs.install & refreshenv` | Installs nodejs |
| `cinst -y vcredist2015 & refreshenv` | Installs vcredist2015 |
| `git --version` | Ensures that the git command is recognized. You may want to restart the command prompt. Ensure you have access to your project's repository|
|choco install conemu | Installs Console Emulator|

5. Open the Console Emulator which is now installed on your Windows computer
6. From the Dropdown, select Git bash and save.
7. Set up a GitHub User account at https://github.com, or if already done, navigate to your account profile.

8. Re-Open Console Emulator and run the commands below! First

| Command       | Result       |
|:------------- |:-------------|
|`ls -al ~/.ssh` | Searches for existing SSH files|

To work with [github] need to generate rsa keys and set public key (id_rsa.pub) in [github] (Dashboard -> Manage SSH keys).
To run ssh-keygen command, you might have to run git-bash first (right clink on 'desktop' and select 'Git Bash Here' option).|

Note: If GitHub usage is blocked via git protocol, you will need to set it up to use https instead. Following command will do the trick:

git config --global url."https://".insteadOf git://
TESTING OUR INSTALLATION
The software installed includes:

NodeJS,
Git

Now restarting the command line allows this change to the environment variable to take effect.

You can test whether nodejs/npm is working fine by installing grunt and bower globally npm install bower grunt-cli -g and running grunt.

OPTIONAL SOFTWARE
You can install additional (optional) software (caution, will download full size installers)

cinst -y google-chrome-x64 Firefox vagrant virtualbox phantomjs atom boot2docker
Additional software includes:

Google Chrome
Firefox,
Vagrant,
VirtualBox
PhantomJS
Atom
Sublime
boot2docker
To install specific packages (due to low connection or failed attempt) modify the command to include only desired packages (i.e. cinst -y nodejs).
