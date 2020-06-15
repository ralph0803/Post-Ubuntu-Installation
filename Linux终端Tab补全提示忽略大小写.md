1. 在用户家目录下创建“.inputrc”文件。
```bash
touch .inputrc
sudo vi .inputrc
```
2. 在`.inputrc`中按`i`键，打开输入模式，然后键入:
```bash
set completion-ignore-case on
```
然后按`esc`键退出输入模式，再键入`:wq!`，保存并退出

3. 关闭终端，重新打开终端即可。
