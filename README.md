# SETTING UP GITHUB
On August 2021, Github decided to improve transfer security by preferring SSH over HTTPS. <br/>
This is a guide on how to setup Git and Github on your KDE Neon User Edition 22.04. <br/>
This will probably work with Ubuntu and other Ubuntu-based Linux Distributions. <br/>
This tutorial assumes that you already have a Github Account, and has basic knowledge on creating repositories. <br/><br/>
Disclaimer: I am a hobbyist and self-taught developer. I am not responsible for any breakages on your system. Follow along at your own risk.<br/>

### STEP 1: Create a Public Repository
Create a Public Repository. Create a `README.md` file. <br/>

### STEP 2: Install Necessary OpenSSH Client & Packages
On your terminal (Konsole), install the following:
```
sudo apt install git gh openssh-client openssh-server keychain
```
The packages `git`, `gh`, and `openssh-client` are, most likely, came preinstalled with your distribution. <br/>

### STEP 3: Configure Global settings for Git
On your terminal (Konsole), configure settings for Git:
```
git config --global user.name "Your Name On Github"
```
and then:
```
git config --global user.email "email_you_use_on_github@email.com"
```
<br/>

### STEP 4: Create an SSH Directory
On your terminal (Konsole), make a hidden SSH directory:
```
mkdir ~/.ssh
```
<br/>
You may also create the folders graphically using the File Manager (Dolphin). <br/>
Keeping in mind that hidden folders can be unhidden <i>v. versa</i> using <code>Ctrl + H</code>. <br/>

### STEP 5: Create SSH Key with a Passphrase
On your terminal (Konsole), generate SSH Keys:
```
 ssh-keygen -t rsa -b 4096 -C "email_you_use_on_github@email.com"
```
This will lead to a prompt:<br/> `Enter a file in which to save the key (/home/.../.ssh/id_rsa):` <br/>
Type your desired name for your key and generate it on the SSH directory:<br/> `~/.ssh/desired_name_for_your_key` <br/>
>Optional: Naming your key is optional. However, it is recommended. <br/>
>Just hit enter to ignore naming your key. This will produce files with the filename `id_rsa`. <br/>
Another prompt will show:<br/> `Enter passphrase (empty for no passphrase):`
>Passphrases give another layer of protection for your SSH Keys, but are completely optional.
>If you don't want to use a passphrase, just hit your enter key to ignore.
>Passphrases are made up of random letters and digits.
>You may create your own or generate it using the terminal.

### STEP 5: Add Private Key to SSH Agent
### STEP 6: Put SSH Key on Github Settings
### STEP 7: Test SSH Connection with Github
### STEP 8: Configure Preference SSH over HTTPS on Github
### STEP 9: Clone Repository via SSH
### STEP 10: Do your stuff.
