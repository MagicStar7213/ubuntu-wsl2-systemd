# ubuntu-wsl2-systemd
This is a fork of DamionGans [ubuntu-wsl2-systemd-script](https://github.com/DamionGans/ubuntu-wsl2-systemd-script) for Ubuntu 22.04 WSL2 as it does not work in this version with the original repo. Hope it helps. Updates made from [Issue #36 of ubuntu-wsl2-systemd-script](https://github.com/DamionGans/ubuntu-wsl2-systemd-script/issues/36)

There will not be updates as Microsoft added systemd support in latest WSL. This was only an update so you could enable systemd in older Ubuntu 22.04 WSL2

Instructions from [the snapcraft forum](https://forum.snapcraft.io/t/running-snaps-on-wsl2-insiders-only-for-now/13033) turned into a script. Thanks to [Daniel](https://forum.snapcraft.io/u/daniel) on the Snapcraft forum! 

## Enabling systemd
First, update WSL. Run in cmd or PowerShell as admin
```shell
wsl --update
```
Then, start your favourite distro and create or edit wsl.conf in /etc :
```shell
sudo nano /etc/wsl.conf
```
In it, write:
```ini
[boot]
systemd=true
```

After, run
```shell
wsl --shutdown
```
And start again your distro. And you're done! Enjoy systemd for installing snaps or whatever you want to do with it.

## Usage
You need ```git``` to be installed for the commands below to work. Use
```sh
sudo apt install git
```
to do so.
### Run the script and commands
```sh
git clone https://github.com/MagicStar7213/ubuntu-wsl2-systemd.git
cd ubuntu-wsl2-systemd/
bash ubuntu-wsl2-systemd-script.sh
# Enter your password and wait until the script has finished
```
### Then restart the Ubuntu shell and try running systemctl
```sh
systemctl

```
If you don't get an error and see a list of units, the script worked.

Have fun using systemd on your Ubuntu WSL2 image. You may use and change and distribute this script in whatever way you'd like. 
