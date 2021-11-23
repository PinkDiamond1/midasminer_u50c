# midasminer_u50c

![https://img.shields.io/github/downloads/midaslabs/midasminer_u50c/total.svg](https://img.shields.io/github/downloads/midaslabs/midasminer_u50c/total.svg)
![https://img.shields.io/github/release/midaslabs/midasminer_u50c/all.svg](https://img.shields.io/github/release/midaslabs/midasminer_u50c/all.svg)
![https://img.shields.io/github/release-date-pre/midaslabs/midasminer_u50c.svg](https://img.shields.io/github/release-date-pre/midaslabs/midasminer_u50c.svg)
![https://img.shields.io/github/license/midaslabs/midasminer_u50c.svg](https://img.shields.io/github/license/midaslabs/midasminer_u50c.svg)
![https://img.shields.io/github/stars/midaslabs/midasminer_u50c.svg](https://img.shields.io/github/stars/midaslabs/midasminer_u50c.svg)
![https://img.shields.io/github/forks/midaslabs/midasminer_u50c.svg](https://img.shields.io/github/forks/midaslabs/midasminer_u50c.svg)

# **Introduction**

FPGA bitstream is a file that contains the programming information for the FPGA chip. midasminer_u50c is our specific bitstream for FPGA to behave as a miner. U50c with HBM can mine Ethereum faster because HBM allows the accelerators to perform memory-hard compute tasks much faster than existing technology.

# **Features**

1. The hashrate could be up to 56 MH/s.
2. Mining process will automatically be disabled when temperature is over 75c and will be restarted to mine when temperature is under 60c.

# **Installation**

The only thing you need to install is FTDI driver, which is a software driver for converting RS-232 or TTL serial transmission to and from USB signals. You can search for it on the website and download it for free. Download here:

[https://ftdichip.com/drivers/](https://ftdichip.com/drivers/)

![https://user-images.githubusercontent.com/90677852/133219942-56a176d2-fadc-49aa-beec-c4191f47d9e0.png](https://user-images.githubusercontent.com/90677852/133219942-56a176d2-fadc-49aa-beec-c4191f47d9e0.png)

# **Config Setting**

In the folder, find MinerHost.exe-conf.json and open it.

![https://github.com/Andreschao1999/midasminer_u50c/blob/patch-1/config_setting.png](https://github.com/Andreschao1999/midasminer_u50c/blob/patch-1/config_setting.png)

What you must change:

1. You need to change line_3’s URL to the f2pool server closest to your region.

For example:    "url": "stratum+tcp://eth.f2pool.com:6688",
SSL was not supported currently.

2. You need to change line_4’s User_Wallet to your own wallet.

For example:    "user": "0xabcdabcdabcdabcdabcdabcdabcdabcdabcdabcd",

What you can change:

1. You can change line_5 to decide which bitstream you want to use.
2. You can change line_6 to decide your worker’s name.
3. You can change line_7 to change hashrate.
4. You can change line_8 to decide whether to create a log file in folder log or not.

# **Start Mining**

Find MinerHost.exe and execute it in the folder.

![https://user-images.githubusercontent.com/90677852/133240668-1116466c-9b5a-471f-8a62-b99b428c2577.png](https://user-images.githubusercontent.com/90677852/133240668-1116466c-9b5a-471f-8a62-b99b428c2577.png)

FPGA initialization may take around 10 minutes.

![https://user-images.githubusercontent.com/90677852/133251467-7b373ad6-48a6-4107-9ada-bbc7100a8061.png](https://user-images.githubusercontent.com/90677852/133251467-7b373ad6-48a6-4107-9ada-bbc7100a8061.png)

After initialization completion, the FPGA will connect with the pool. The command window will display the total share number accepted by the pool.

![https://user-images.githubusercontent.com/90677852/133251755-77fd253a-1ccd-439b-afda-7ad44f447de1.png](https://user-images.githubusercontent.com/90677852/133251755-77fd253a-1ccd-439b-afda-7ad44f447de1.png)

Keep mining with U50c!

# **Notes**

- U50c USB interface does not support PCIe-USB expansion cards.
- One single computer can hold up to 16 U50c devices.
- This beta version of the bitstream will stop mining when epoch number reaches 465. We will provide an updated version afterwards.

# Change Log

[v1.1.0]

1. Support FPGA clock frequency auto-adjustment function to boost Hashrate up to 56 MH/s
2. Support Linux-based (ubuntu 18.04 or higher) systems
3. Reduce 5-12% power consumption (depended on FPGA clock frequency) compared to the previous release [v1.0.0] Initial version
