# SETTING UP GITHUB
On August 2021, Github decided to improve transfer security by preferring SSH over HTTPS Ports. This is a guide on how to setup Git and Github on your KDE Neon User Edition 22.04. This will probably work with Ubuntu and other Ubuntu-based Linux Distributions. This tutorial assumes that you already have a Github Account, and has basic knowledge on terminal usage and creating repositories. <br/>
> :warning: **DISCLAIMER** <br/>
> *I am a hobbyist and self-taught developer. I am not responsible for any breakages on your computer. Follow along at your own risk.*

<br/>

### :one: STEP 1: Creating a Public Repository
On your Github Profile Dashboard:
> Create a Public Repository. <br/>
> Create & Save a `README.md` file.

<br/>

### :two: STEP 2: Installing Necessary OpenSSH Client & Other Packages
On your terminal (Konsole), install the following:
```
sudo apt install git gh openssh-client openssh-server keychain
```
> :clipboard: **NOTE** <br/>
> *The packages* `git`, `gh`, *and* `openssh-client` *came, most likely, preinstalled with your distribution*.

<br/>

### :three: STEP 3: Configuring Global settings for Git
Configure settings for Git:
```
git config --global user.name "Your Name On Github"
```
and then followed by:
```
git config --global user.email "email_you_use_on_github@email.com"
```

<br/>

### :four: STEP 4: Creating an SSH Directory
Make a hidden SSH directory:
```
mkdir ~/.ssh
```
> :clipboard: **NOTE** <br/>
> *You may also create the folders graphically using the File Manager (Dolphin). Keeping in mind that hidden folders can be unhidden, v. versa, using* `Ctrl + H`. 

<br/>

### :five: STEP 5: Generating SSH Key with a Passphrase
Generate SSH Keys:
```
 ssh-keygen -t rsa -b 4096 -C "email_you_use_on_github@email.com"
```

:large_blue_circle: **PROMPT 1** <br/>
A prompt will show: <br/>
```Enter a file in which to save the key (/home/.../.ssh/id_rsa):``` <br/>
Enter your desired name for your key and generate it on the SSH directory: <br/>
```~/.ssh/desired_name_for_your_key``` <br/>
> :clipboard: **NOTE** <br/>
> *Naming your key is optional. However, it is recommended. Just hit enter to ignore naming your SSH Key. This will generate filenames with* `id_rsa`. 

<br/>

:large_blue_circle: **PROMPT 2** <br/>
Another line of prompt will show: <br/>
```Enter passphrase (empty for no passphrase):``` <br/>
> :clipboard: **NOTE** <br/>
> *Passphrases, although optional, are recommended because they give another layer of protection for your SSH Keys. If you don't want to use passphrases, just hit enter to ignore the prompt. To know more about passphrases,* [go here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/working-with-ssh-key-passphrases).

<br/>

:large_blue_circle: **PROMPT 3** <br/>
Another line of prompt will show: <br/>
```Enter same passphrase again:```<br/>
> :clipboard: **NOTE** <br/>
> *Re-enter the passphrase that you've used in the previous prompt. If you did not use a passphrase, just ignore the prompt by hitting enter.* <br/> <br/>
> :eye_speech_bubble: **OBSERVE** <br/>
> *This will produce two SSH Keys in the SSH Directory: a private key:* `name_of_your_key`, *and a public key:* `name_of_your_key.pub`.

<br/>

### :six: STEP 6: Adding Private Key to the SSH Agent
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
Show contents of the SSH **Public** Key (*The one with the* `.pub` *extension*):
```
cat name_of_your_key.pub
```
and then, copy its contents to your clipboard, or just highlight the contents and hit `Ctrl + Shift + C`.

<br/>

### :seven: STEP 7: Putting SSH Key on Github Settings
On your Github Profile Settings.
> Navigate to **SSH & GPG Keys**. <br/>
> Click the **New SSH Key** button. <br/>
> Put the name of your key on the **Title** input section. <br/>
> Paste the contents of your public key that you have copied earlier to the **Key** input section. <br/>
> Click the **Add SSH Key** button.

<br/>

### :eight: STEP 8: Testing & Configuring Preference of SSH over HTTPS Ports on Github
Going back to your terminal (Dolphin), enable Github to use SSH over HTTPS Ports by configuring `~/.ssh/config`. (If the file does not exist, create one.):
```
Host github.com
    Hostname ssh.github.com
    Port 443
    User git
```
Test Github SSH Preference.
```
ssh -T -p 443 git@ssh.github.com
```
> :clipboard: **NOTE** <br/>
> *To know more about SSH Preference Testing* [go here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection).

Test your SSH Connection with Github
```
ssh -T git@github.com
```
> :clipboard: **NOTE** <br/>
> *To know more about SSH Connection Testing* [go here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection).

<br/>

### :nine: STEP 9: Clone Repositories
Clone repositories using SSH.
```
git clone ssh://git@ssh.github.com:443/YOUR-USERNAME/YOUR-REPOSITORY.git
```
### You Can Now Work on Your Remote Repositories!

> :clipboard: **NOTE** <br/>
> *Due to efficient SSH security measures, processes involving SSH Keys are automatically terminated by the system.* <br/>
> *You may need to manually reenable them through* `eval "$(ssh-agent -s)"` *and re-enlist your SSH Key through* `ssh-add ~/.ssh/your_ssh_key` *everytime you are to start working on a project.* <br/>
> *In order to close it (Technically, It kills the process.), you can just input* `eval "$(ssh-agent -k)"`.

