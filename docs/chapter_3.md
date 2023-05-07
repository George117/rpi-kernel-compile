# [Documentation](https://source.denx.de/Xenomai/xenomai/-/wikis/Installing_Xenomai_3)
### 1. Download Xenomai v3.2.1
```
wget https://source.denx.de/Xenomai/xenomai/-/archive/v3.2.1/xenomai-v3.2.1.tar.bz2
```

### 2. Unzip xenomai
```
tar xjvf xenomai-v3.2.1.tar.bz2
```

### 3. Config and install xenomai
```
cd xenomai-v3.2.1
```

```
./scripts/bootstrap
```

```
./configure --with-core=cobalt --enable-smp
```

```
sudo make install
```

### 4. Some tweaks
```
sudo nano /boot/cmdline.txt
```
add to end of first line
```
dwc_otg.fiq_enable=0 dwc_otg.fiq_fsm_enable=0 dwc_otg.nak_holdoff=0 isolcpus=0,1 xenomai.supported_cpus=0x3
```

```
sudo nano /boot/config.txt
```
Add at the top
````
total_mem=3072
````

### 5. Test
Works as expected :)

![image](assets/images/3/64bit_latency_test.png)
