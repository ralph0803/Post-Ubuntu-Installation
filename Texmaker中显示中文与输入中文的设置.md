安装与使用xeCJK宏包实现

    apt-get install texlive 
    apt-get install texlive-xetex 
    apt-get install texlive-full

即安装texlive后还需安装texlive-xetex,或者直接安装整个包(比较大,但包和模板完整)。

要编写中文文档时需在在tex文件导言区加入:

    \usepackage{xeCJK}
    \setCJKmainfont{字体名}

即使用xeCJK宏包,至于可用的字体名可用命令: fc-list :lang=zh 查询,查询结果类似于:

    /usr/share/fonts/winfont/simsun.ttc: 宋体,SimSun:style=Regular
    /usr/share/fonts/winfont/simsun.ttc: 新宋体,NSimSun:style=Regular
    /usr/share/fonts/truetype/arphic/ukai.ttc: AR PL UKai TW MBE:style=Book
    /usr/share/fonts/truetype/arphic/uming.ttc: AR PL UMing TW:style=Light
    /usr/share/fonts/truetype/arphic/uming.ttc: AR PL UMing CN:style=Light
    /usr/share/fonts/truetype/arphic/uming.ttc: AR PL UMing HK:style=Light

其中诸如“SimSun”、“NSimSun”、“AR PL UMing TW”等为字体名。Ubuntu下自带的中文字体较少,可从windows下复制字体文件,一般是在C:/Windows/Fonts文件夹下;在/usr/share/fonts下新建一个文件夹存放这些字体文件,如/usr/share/fonts/winfont,更改权限并更新字体库:

    chmod 644 /usr/share/fonts/winfont/*
    mkfontscale
    mkfontdir
    fc-cache -fsv

就能编译成功了。

注意:使用xeCJK宏包后需要用 xelatex 来编译。

    sudo apt-get install fcitx-frontend-qt5

重启电脑

打开texmaker的方式是直接从任务栏打开，而不是直接双击某个文件打开，不然依然不能输入中文
