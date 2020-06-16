在提示符下，用`lsblk`看一下要mount的设备的编号，同时检查一下目前其它device挂载的情况，不要让这个挂载接下来mount的folder有冲突。

然后创建一个folder，比如在`/media/portable-drive`（与`df -h`观察后的folder没有冲突），然后键入：
```bash
sudo mount -t nfts-3g -w /dev/sdb1 /media/portable-drive
```
