## Set Up Environments

### For french users with QWERTY Keyboards:
[Manual Install for KDE/QT of win_us_intl](https://github.com/raelgc/win_us_intl?tab=readme-ov-file#ubuntu--debian):
```bash
wget https://raw.githubusercontent.com/raelgc/win_us_intl/master/.XCompose
sudo apt-get -y install uim
im-config -n uim
~/profile or ~/.bash_profile
# In the end of the file, paste those 2 lines :
export XCOMPOSEFILE="$HOME/.XCompose"
export QT_IM_MODULE="xim"
# Save, exit, and log out, if it doesn't work, reboot :
sudo reboot
```

### My downloading stack:
```bash
# To get Microsoft Edge Stable:
sudo apt install curl
curl https://packages.microsoft.com/keys/microsoft.asc |gpg --dearmor > microsoft.gpg
sudo install -o root -g root -m 644 microsoft.gpg /etc/apt/trusted.gpg.d/
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/edge stable main" > /etc/apt/sources.list.d/microsoft-edge.list'
sudo apt update
sudo apt install microsoft-edge-stable
# To get Discord/Zoom/Slack:
wget -O discord.deb "https://discordapp.com/api/download?platform=linux&format=deb"
wget -O Zoom.deb "https://zoom.us/client/6.4.5.1259/zoom_amd64.deb"
wget -O slack.deb "https://downloads.slack-edge.com/desktop-releases/linux/x64/4.43.51/slack-desktop-4.43.51-amd64.deb"
sudo dpkg -i discord.deb slack.deb
# Collection of tools/utils in command line:
sudo apt install tree duf aria2 tldr bat entr fzf fdupes xsel bpytop gping speedtest-cli buku vlc ddgr mutt onedrive neofetch zoxide jq most ripgrep sd xsel adb fastboot rsync ssh sed dmidecode traceroute
# To install ROCm:
sudo mkdir --parents --mode=0755 /etc/apt/keyrings
wget https://repo.radeon.com/rocm/rocm.gpg.key -O - | gpg --dearmor | sudo tee /etc/apt/keyrings/rocm.gpg > /dev/null
sudo apt update
echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/rocm.gpg] https://repo.radeon.com/amdgpu/6.4/ubuntu noble main"| sudo tee /etc/apt/sources.list.d/amdgpu.list
echo -e 'Package: *\nPin: release o=repo.radeon.com\nPin-Priority: 600' | sudo tee /etc/apt/preferences.d/rocm-pin-600
sudo apt update
sudo apt install rocm
sudo tee --append /etc/ld.so.conf.d/rocm.conf <<EOF
/opt/rocm/lib
/opt/rocm/lib64
EOF
sudo ldconfig
export PATH=$PATH:/opt/rocm-6.4.0/bin
export LD_LIBRARY_PATH=/opt/rocm-6.4.0/lib
sudo apt install libamd-comgr2 libamdhip64-5 libhipblas0 libhipfft0 libhiprand1 libhipsolver0 libhipsparse0 libhsa-runtime64-1 librccl1 librocalution0 librocblas0 librocfft0 librocm-smi64-1 librocrand1 librocsolver0 librocsparse0 rocm-device-libs-17 rocm-smi rocminfo
sudo usermod -a -G video $LOGNAME
sudo usermod -a -G render $LOGNAME
rocminfo
clinfo

```
