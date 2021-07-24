# ryzen-power

This is a Python port of [djselbeck](https://github.com/djselbeck)'s 
[rapl-read-ryzen](https://github.com/djselbeck/rapl-read-ryzen) project.

ryzen-power is a simple script to measure Ryzen CPU cores power and package 
power consumption on Linux system. Since most Linux distributions natively 
include Python, ryzen-power can run out-of-box on modern Linux without compiling
or any dependencies.

```
$ sudo python3 ryzen-power.py
                Cores Power     Package Power
SOCKET  0:      5.90W           13.07W
  CORE  0:      2.96W
  CORE  1:      2.95W
```

## Installation

ryzen-power requires [msr](https://manpages.debian.org/buster/manpages/msr.4.en.html)
enabled. You might need to load the msr driver first.

```bash
sudo modprobe msr
```

After that, just download the `ryzen-power.py` and run it with root privilege,
root is required to read msr.

```bash
sudo python3 ryzen-power.py
```

## Usage

```
$ python3 ryzen-power.py --help
usage: ryzen-power.py [-h] [--debug] [-d DURATION]

Measure power consumption for AMD Ryzen CPU

optional arguments:
  -h, --help            show this help message and exit
  --debug               show debug messages
  -d DURATION, --duration DURATION
                        the duration of measurement in seconds, default is 0.5
                        second
```