# NCAR Utilities

This repository contains various utilities that proved useful while at NCAR.

## Yellowstone Login Script

A very common task is SSH'ing into Yellowstone. A small script, conveniently called `ys`, assists with this:

```
$ ys -h
Usage:

    ys
    ys -- ARGS...
        Log in to yellowstone.ucar.edu; let it choose your login node

    ys NODE_NUM ARGS...
        Log in to a specific Yellowstone node

    ys -h
    ys --help
        Print this help

NODE_NUM    node to login, can be 1-6
ARGS        extra arguments passed to ssh
```

### Installing

Keep in mind that this should typically be installed on your local machine, not Yellowstone itself. It could be useful on Yellowstone, but less so.

Just copy this script to your scripts directory. For example, `~/bin` is commonly used:

```bash
git clone https://github.com/seanfisk/ncar-utils.git
cd ncar-utils
mkdir ~/bin
cp ys ~/bin
```

Also ensure that your scripts directory is on your `PATH`. If not, run the following for bash. Will be similar for other shells.

```bash
echo 'export PATH=~/bin:$PATH' >> ~/.bashrc
```

### Examples

Log in to Yellowstone without caring which node:

```bash
ys
```

Log in to login node 4 with X forwarding:

```bash
ys 4 -X
```
