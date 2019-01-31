# Nodemaster

The **Nodemaster** scripts is a collection of utilities to manage, setup and update masternode instances.

I am quite confident this is the single best and almost effortless way to setup different crypto masternodes, without bothering too much about the setup part.

## Installation

SSH to your VPS and clone the Github repository:

```bash
git clone https://github.com/lancehall123/Odin-Nodemaster.git && cd Odin-Nodemaster/vps
```

Install & configure your desired master node with options:

```bash
./install.sh -p odin
```

```bash
./install.sh -p odin -n 4/6
```

**Install & configure 4 ODIN masternodes:**

```bash
./install.sh -p odin -c 4
```

**Update daemon of previously installed ODIN masternodes:**

```bash
./install.sh -p odin -u
```

**Install 6 ODIN masternodes with the git release tag "tags/??"**

```bash
./install.sh -p odin -c 6 -r "tags/??"
```

**Wipe all ODIN masternode data:**

```bash
./install.sh -p odin -w
```

**Install 2 ODIN masternodes and configure sentinel monitoring:**

```bash
./install.sh -p odin -c 2 -s
```

## Options

The _install.sh_ script support the following parameters:

| Long Option  | Short Option | Values              | description                                                         |
| :----------- | :----------- | ------------------- | ------------------------------------------------------------------- |
| --project    | -p           | project, e.g. "odin" | shortname for the project                                           |
| --net        | -n           | "4" / "6"           | ip type for masternode. (ipv)6 is default                           |
| --release    | -r           | e.g. "tags/v3.0.4"  | a specific git tag/branch, defaults to latest tested                |
| --count      | -c           | number              | amount of masternodes to be configured                              |
| --update     | -u           | --                  | update specified masternode daemon, combine with -p flag            |
| --sentinel   | -s           | --                  | install and configure sentinel for node monitoring                  |
| --wipe       | -w           | --                  | uninstall & wipe all related master node data, combine with -p flag |
| --help       | -h           | --                  | print help info                                                     |
| --startnodes | -x           | --                  | starts masternode(s) after installation                             |

## Troubleshooting the masternode on the VPS

If you want to check the status of your masternode, the best way is currently running the cli e.g. for $ODIN via

```
/usr/local/bin/odin-cli -conf=/etc/masternodes/odin_n1.conf getinfo

```

