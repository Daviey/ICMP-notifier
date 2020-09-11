# ICMP-notifier

Standalone tool to detect and notify (both console and libnotify) of ICMP packets.  This is particularly useful if performing blind code execution vulnerability assessments / CTF, where you are trying to use `ping -c1 $MYIP` as your alert.

## Installation

Download and install from the release page:

```bash
curl -sLo ~/bin/ICMP-notifier https://github.com/Daviey/ICMP-notifier/releases/latest/download/ICMP-notifier_linux_amd64
chmod +x ~/bin/ICMP-notifier
sudo setcap cap_net_raw+eip ~/bin/ICMP-notifier
```

or build yourself:

```bash
$ go get github.com/Daviey/ICMP-notifier
```

It is also important to give the binary the capabilties to have the permission to listen to ICMP packaets:

```bash
$ sudo setcap cap_net_raw+eip ./ICMP-notifier
```

## Usage

Simply run:

```bash
./ICMP-notifier
```

or to listen on a specific IP address (rather than 0.0.0.0):
```bash
./ICMP-notifier -ip 192.168.0.1
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.


## License
[MIT](https://choosealicense.com/licenses/mit/)
