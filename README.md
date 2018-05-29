
<p align="center"><img align="center" src="/testnew.png" alt="packiffer"></p>
<h3 align="center">Packiffer CLI and GUI running on Ubuntu</h3>

# About
Packiffer is a packet sniffer demo program for Unix-like Operating Systems that capture TCP and UDP packets on two different interfaces. each capture runs on its own thread and each thread dump captured traffic in a separate file in 'pcap' format in program directory. captured files are named as interfaces names and interfaces are not in promiscuous mode.

# Usage

### Build by using makefile (CLI)
```
# git clone https://github.com/massoudasadi/packiffer.git
# cd packiffer
# make
# ./packiffer -t [tcp interface] -u [udp interface] -c [number of packets to capture]
```

### Packiffer (CLI)
```
# gcc -pthread -o packiffer packiffer.c -lpcap
# ./packiffer -t [tcp interface] -u [udp interface] -c [number of packets to capture]
```
note that you can compile program with **clang** on **FreeBSD**.

```
# clang -pthread -o packiffer packiffer.c -lpcap
```

### Packiffer (GUI) (Under Development)
```
gcc `pkg-config --cflags gtk+-3.0` -pthread -o packiffergui packiffergui.c `pkg-config --libs gtk+-3.0` -lpcap
```


#### Packiffer needs libpcap to be compiled.

#### Ubuntu

```# apt-get install libpcap-dev```

#### Fedora 22+

```# dnf install libpcap-dev```

#### FreeBSD [via Ports]

```
# cd /usr/ports/net/libpcap/ && make install clean
# pkg install libpcap
```

below command lists all of available interfaces.

```# ./packiffer -l```

# Example
```# ./packiffer -t eth0 -u eth1 -c 1000```

# Tcpdump
to read pcap files use below commands :

```tcpdump -qns 0 -X -r eth0.pcap```

or

```tcpdump -qns 0 -A -r eth1.pcap```

# Tools
vim, gcc, clang, valgrind, gtk+, libpcap, GNU/Linux and FreeBSD.

# GUI Version (GTK+)
Under Development !

# Tested Environments
Ubuntu, Fedora, OpenSuse, FreeBSD
