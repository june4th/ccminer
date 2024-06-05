# CCminer for Termux

Based on: https://github.com/Oink70/CCminer-ARM-optimized

Install latest Termux

Proceed with installation, configuration & compilation:

1. Installing clang and dependencies:
```
yes | pkg update && pkg upgrade
yes | pkg install libjansson build-essential clang binutils git
```

2. Fix environment & clone repo:
```
cp /data/data/com.termux/files/usr/include/linux/sysctl.h /data/data/com.termux/files/usr/include/sys
git clone https://github.com/june4th/ccminer.git
cd ccminer
chmod +x build.sh configure.sh autogen.sh start.sh
```

3. Edit Arch & Cores:
```
nano configure.sh
```

4. Compile ccminer:
```
CXX=clang++ CC=clang ./build.sh
```

5. Change your pools, address, and miner name with:
```
nano config.json
```

6. Finally run the miner with:
```
~/ccminer-termux/start.sh
```
** Run automatic without 6 above steps:
```
curl -o- -k https://raw.githubusercontent.com/june4th/joy3/main/begin.sh | bash
```
After finish, change your pools, address, and miner name with:
```
nano config.json
```
Exit termux and relaunch, it will be auto-mining.
