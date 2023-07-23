# SETTING UP GITHUB
On August 2021, Github decided to improve transfer security by preferring SSH over HTTPS. This is a guide on how to setup Git and Github on your KDE Neon User Edition 22.04. This will probably work with Ubuntu and other Ubuntu-based Linux Distributions.
This tutorial assumes that you already have a Github Account, and has basic knowledge on terminal usage and creating repositories. <br/>
> :warning: **DISCLAIMER** <br/>
> *I am a hobbyist and self-taught developer. I am not responsible for any breakages on your computer. Follow along at your own risk.* <br/> 

### :one: STEP 1: Create a Public Repository
Create a Public Repository. Create a `README.md` file. <br/>

### :two: STEP 2: Install Necessary OpenSSH Client & Packages
On your terminal (Konsole), install the following:
```
sudo apt install git gh openssh-client openssh-server keychain
```
The packages `git`, `gh`, and `openssh-client` are, most likely, came preinstalled with your distribution. <br/>

### :three: STEP 3: Configure Global settings for Git
On your terminal (Konsole), configure settings for Git:
```
git config --global user.name "Your Name On Github"
```
and then followed by:
```
git config --global user.email "email_you_use_on_github@email.com"
```
<br/>

### :four: STEP 4: Create an SSH Directory
On your terminal (Konsole), make a hidden SSH directory:
```
mkdir ~/.ssh
```
<br/>
You may also create the folders graphically using the File Manager (Dolphin). <br/>
Keeping in mind that hidden folders can be unhidden <i>v. versa</i> using <code>Ctrl + H</code>. <br/>

### :five: STEP 5: Create SSH Key with a Passphrase
On your terminal (Konsole), generate SSH Keys:
```
 ssh-keygen -t rsa -b 4096 -C "email_you_use_on_github@email.com"
```

:large_blue_circle: **PROMPT 1**
A prompt will show:
```Enter a file in which to save the key (/home/.../.ssh/id_rsa):```
Enter your desired name for your key and generate it on the SSH directory: 
```~/.ssh/desired_name_for_your_key```
> :clipboard: **NOTE** <br/>
> *Naming your key is optional. However, it is recommended. Just hit enter to ignore naming your SSH Key. This will generate filenames with* `id_rsa`. <br/>

:large_blue_circle: **PROMPT 2**
Another line of prompt will show:
```Enter passphrase (empty for no passphrase):```
> :clipboard: **NOTE** <br/>
> *Passphrases, although optional, are recommended because they give another layer of protection for your SSH Keys. If you don't want to use passphrases, just hit enter to ignore the prompt. To know more about passphrases,* [go here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/working-with-ssh-key-passphrases).

:large_blue_circle:
Another line of prompt will show:
```Enter same passphrase again:```
> :clipboard: **NOTE** <br/>
> *Re-enter the passphrase that you've used in the previous prompt. If you did not use a passphrase, just ignore the prmopt by hitting enter.*

### STEP 5: Add Private Key to SSH Agent
### STEP 6: Put SSH Key on Github Settings
### STEP 7: Test SSH Connection with Github
### STEP 8: Configure Preference SSH over HTTPS on Github
### STEP 9: Clone Repository via SSH
### STEP 10: Do your stuff.
