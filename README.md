# SETTING UP GITHUB
This is a guide on how to setup Git and Github on your KDE Neon User Edition 22.04. <br/>
This will probably work with Ubuntu and other Ubuntu-based Linux Distributions. <br/>
Disclaimer: I am a hobbyist and self-taught developer. Follow along at your own risk.<br/>
> This tutorial assumes that you already have a Github Account, and has basic knowledge on creating repositories. <br/>

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
mkdir -p ~/.ssh/id_rsa
```
<br/>
You may also create the folders graphically using the File Manager (Dolphin). <br/>
Keeping in mind that hidden folders can be unhidden *v. versa* using `Ctrl + H`. <br/>

### STEP 5: Create SSH Key with a Passphrase
On your terminal (Konsole), generate SSH Keys:
```
 ssh-keygen -t rsa -b 4096 -C "email_you_use_on_github@email.com"
```
This will lead to a prompt: `Enter a file in which to save the key (/home/.../.ssh/id_rsa):` <br/>
Type your desired name for your key and generate it on the SSH directory: `~/.ssh/id_rsa/desired_name_for_your_key` <br/>
Another prompt will show: `Enter passphrase (empty for no passphrase):`
>Passphrases are gives another layer of protection for your SSH Keys.
>

### STEP 5: Add Private Key to SSH Agent
### STEP 6: Put SSH Key on Github Settings
### STEP 7: Test SSH Connection with Github
### STEP 8: Configure Preference SSH over HTTPS on Github
### STEP 9: Clone Repository via SSH
### STEP 10: Do your stuff.
