# NohupRun in HPC

这个东西的功能是可以一键在后台执行指令，并将指令执行的log输出带当前目录下的 nrun_\<pid\>.log 文件中。

## 编译

```bash
cd NohupRun
pip install pyinstaller
./build.sh
```

## 添加到系统PATH

```bash
export PATH=$HOME/work/NohupRun/dist/nrun:$PATH
```

在 .bashrc 中添加

```
alias nrun='$HOME/work/NohupRun/dist/nrun'
```

## 使用

sh示例：  
```sh
#! /bin/bash
python xxx.py <args, ...>
scancel $SLURM_JOB_ID
```

```bash
export SLURM_JOB_ID = XXX # 分配的任务id

nrun ./xxx.sh
nrun python xxx.py <args, ...>
```
