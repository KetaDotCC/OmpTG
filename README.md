# OmpTG
Generate WCET for ALF Statements based on SWEET Tool.

Jinghao Sun, Tao Jin, Yekai Xue, Liwei Zhang, Jinrong Liu, Nan Guan, Quan Zhou,
ompTG: From OpenMP Programs to Task Graphs,
Journal of Systems Architecture,
2022,
[https://doi.org/10.1016/j.sysarc.2022.102470](https://doi.org/10.1016/j.sysarc.2022.102470)


## Method
- details see SWEET manual 4.14.

## Requirement
- Python (version 3+).
- NetworkX For Python.
- SWEET Tool.

## File Resource
- clt : insertsort.clt provided by SWEET manual.

- std_hll.alf: for 64bit (see SWEET manual).

  > get 32bit std_hll.alf in SWEET manual.

## How To Use：
> ./wctg [.alf]

Remember to give "wctg" permission to execute. 
> chmod a+x wctg

- The alf slices folder and wcet time table(.wct) will be generated in folder where your alf file imported.
- unspported:
    - Some Statements like "dyn_alloc" are not supported yet.



## OmpTG V2.3

- Fix Bugs.
- Add rules according to ALF paper.

## OmpTG V2.2

- Fix Calculation of Call.

## OmpTG V2.1

- unspported: Call.

# Deploy OmpTG Online By Docker

- `Pull Image`

> Download From Docker Hub

```shell
docker pull kingtous/omptg-online:latest
```

- `Run Image`

```shell
docker run --name omptg-online -dit -P -p 8000:80 -p 8888:8888 kingtous/omptg-online:latest /bin/bash start.sh
```

- `Open OmpTG Online in Browser`
  - `127.0.0.1:8000`

- `Open BT-Panel in Browser`
  - `127.0.0.1:8888/xxx`
    - get `xxx` from terminal, type `/etc/init.d/bt default`
