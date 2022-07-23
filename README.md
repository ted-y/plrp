# plrp

plrp is multiprocess ssh tool

**P**rescript **L**ocalscript **R**emotescript **P**ostscript

## Description

### Scripts

| Filename     | Description                              | Run Target  | Run Count      |
| ------------ | ---------------------------------------- | ----------- | -------------- |
| prescript    | plrp pre run script                      | Local Host  | 1              |
| localscript  | Run script by each host from local host  | Local Host  | Hostlist Count |
| remotescript | Run scrips by each host from remote host | Remote Host | Hostlist Count |
| postscript   | plrp post run script                     | Local Host  | 1              |

## Usage

```
usage: plrp [-h] [-c CREATE] [-s] [-y] [-p PROCESS] [-l LOGIN] [job]

Process some argument.

positional arguments:
  job                   job name

optional arguments:
  -h, --help            show this help message and exit
  -c CREATE, --create CREATE
                        create job
  -s, --shuffle         shuffle hostlist
  -y, --yes             autometic yes
  -p PROCESS, --process PROCESS
                        concurrency number (default: 30)
  -l LOGIN, --login LOGIN
                        ssh login name (default: root)
```

## Example

### Job Create

```
$ plrp -c test
SUCCESS: test job create success
```

### Modify hostlist file and fix scripts for run

```
$ plrp
[PRESCRIPT]
[HOSTLIST]
--------------!!! CHECK HOST NAME !!!--------------
test.host.com
--------------!!! CHECK HOST NAME !!!--------------
EXECUTE TOTAL 1 [y/N]: y
[LOCAL/REMOTESCRIPT]
Progress: |█████████████████████████████████████████████████████████████████████████████████████| 1/1 100.0% Complete
[POSTSCRIPT]
```

### Results

```
$ cat error/*
$ cat result/*
```
