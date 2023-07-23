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

:large_blue_circle: **PROMPT 1** <br/>
A prompt will show: <br/>
```Enter a file in which to save the key (/home/.../.ssh/id_rsa):``` <br/>
Enter your desired name for your key and generate it on the SSH directory: <br/>
```~/.ssh/desired_name_for_your_key``` <br/>
> :clipboard: **NOTE** <br/>
> *Naming your key is optional. However, it is recommended. Just hit enter to ignore naming your SSH Key. This will generate filenames with* `id_rsa`. <br/>

:large_blue_circle: **PROMPT 2** <br/>
Another line of prompt will show: <br/>
```Enter passphrase (empty for no passphrase):``` <br/>
> :clipboard: **NOTE** <br/>
> *Passphrases, although optional, are recommended because they give another layer of protection for your SSH Keys. If you don't want to use passphrases, just hit enter to ignore the prompt. To know more about passphrases,* [go here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/working-with-ssh-key-passphrases).

:large_blue_circle: **PROMPT 3** <br/>
Another line of prompt will show: <br/>
```Enter same passphrase again:```<br/>
> :clipboard: **NOTE** <br/>
> *Re-enter the passphrase that you've used in the previous prompt. If you did not use a passphrase, just ignore the prmopt by hitting enter.* <br/> <br/>
> :eye_speech_bubble: **OBSERVE** <br/>
> *This will produce two SSH Keys in the SSH Directory: a private key:* `name_of_your_key`, *and a public key:* `name_of_your_key.pub`.

### :five: STEP 5: Add Private Key to SSH Agent
Go to the SSH Directory:
```
cd ~/.ssh
```
Activate your SSH Agent:
```
eval "$(ssh-agent -s)"
```
and then, add your SSH **Private** Key (*The one without the* `.pub` *extension*):
```
ssh-add ~/.ssh/name_of_your_key
```
Show contents of the SSH **PUBLIC** Key (*The one with the* `.pub` *extension*):
```
cat name_of_your_key.pub
```
and then, copy its contents to your clipboard, or just highlight the contents and hit `Ctrl + Alt + C`.


### :six: STEP 6: Put SSH Key on Github Settings
On your Github Profile Settings.

### STEP 7: Test SSH Connection with Github
### STEP 8: Configure Preference SSH over HTTPS on Github
### STEP 9: Clone Repository via SSH
### STEP 10: Do your stuff.
