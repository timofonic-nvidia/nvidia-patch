# nvidia-patch

#/usr/lib/x86_64-linux-gnu/libnvidia-encode.so.346.46

requirements:
- ubuntu 14.04
- nvenc-compatible gpu
- nvidia 375.39 driver

# step-by-step :

Download driver: https://yadi.sk/d/yahf1Y-D3PJnzd
```bash
chmod +x ./NVIDIA-Linux-x86_64-375.39.run

./NVIDIA-Linux-x86_64-375.39.run
```

check driver:
```bash
nvidia-smi

mkdir ~/nvenc_backup

cd ~/nvenc_backup

cp /usr/lib/x86_64-linux-gnu/libnvidia-encode.so.375.39 ~/nvenc_backup/

wget https://raw.githubusercontent.com/keylase/nvidia-patch/master/patch.sh

chmod +x patch.sh

./patch.sh ~/nvenc_backup/libnvidia-encode.so.375.39 /usr/lib/x86_64-linux-gnu/libnvidia-encode.so.375.39

reboot
```

## See also

If you experience `CreateBitstreamBuffer failed: out of memory (10)`, then you have to lower buffers number used for every encoding session. If you are using `ffmpeg`, consider using this [patch](https://gist.github.com/Snawoot/70ae403716c698cb86ab015626d72bd4).




