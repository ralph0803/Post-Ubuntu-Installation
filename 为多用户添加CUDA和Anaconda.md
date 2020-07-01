用
```console
$ vim ~/.bashrc
```

输入`i`键进入输入模式

如果要用CUDA，则要添加：
```bash
export PATH=/usr/local/cuda-10.1/bin:$PATH
export LD_LIBRARY_PATH=/usr/local/cuda-10.1/lib64:$LD_LIBRARY_PATH
```

如果要用anaconda，则要添加：
```bash
export PATH=/home/use1/anaconda3/bin:$PATH
```

输入`:wq!`退出vim，如果source一下，就能生效了
```console
$ source ~/.bashrc
```
