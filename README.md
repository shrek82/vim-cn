vim-cn
======

vim插件中文帮助

我的想法：

vindows/vim/vimfiles/bundle 下放置一些支持Pathogen支撑的插件(例如git过来的)
如果没有安装Pathogen，也可以将插件里面的文件分别放置到`autoload`, `plugin`,
`doc`目录下
------------------------------------------------------------------------------------
:h runtimepath 可以了解下各个目录是做什么用的

-------------------------------------------------------------------------
nerdtree
windows git到vim72/bundle/nerdtree，不配置就可以了,。。。/vim/vimfiles/bundle下就不可以，奇怪了
let NERDTreeWinPos=1
右边显示
如果只是临时需要的话，切换到NERDTree的窗口再<c-w>L（大写）这个把窗口右移的命令
3、进入当前目录的树形界面，通过小键盘上下键，能移动选中的目录或文件
4、目录前面有+号，摁Enter会展开目录，文件前面是-号，摁Enter会在右侧窗口展现该文件的内容，并光标的焦点focus右侧。
5、ctr+w+h  光标focus左侧树形目录，ctrl+w+l 光标focus右侧文件显示窗口。多次摁 ctrl+w，光标自动在左右侧窗口切换
6、光标focus左侧树形窗口，摁? 弹出NERDTree的帮助，再次摁？关闭帮助显示
7、输入:q回车，关闭光标所在窗口
--------------------------------------------------------------------------
代码对齐线
vim-indent-guides
Windows:在安装了Pathogen后，直接拷贝到/vim/vimfiles/bundle
默认打开效果快捷键 `<Leader>ig`
--------------------------------------------------------------------------

查看vim已经载入的脚本
:scriptnames
:commands
:functions
========================================================
//vim插件收藏及使用笔记
//easy-through-pairing.vim
//示例代码：
//("'[{hello}]'")
//光标不同位置说明：("'[{hello1}2]3'4"5)6，其中“123456”分别代表光标当前所在的位置，真是情况光标只在其中某一处
//1、快捷<C-j>
//说明：如果光标目前在1处(须光标在括号内的最后)，按ctrl+j光标会到2处，再按会到3处，再按会到4处，依次向括号外面移动光标
//2、快捷键键<C-q>或<C-b>
//说明：将光标移至当前括号最上一级符号内最后位置。
//3、快捷键键<A-q>或<A-b>
//说明：将光标移至当前括号最上一级符号内前面位置。

--------------------------------------------------
快速复制前后字符
//IndentifierMovement.vim
//C+n快速复制下后面的字词
//C+p快速复制上面一个字词
----------------------------------------------------------------------------------------------------------
//PowerLine
PowerLine是一个增强的Vim状态栏插件。当Vim处于NORMAL、INSERT、BLOCK等状态时，状态栏会呈现不同的颜色，同时状态栏还会显示当前编辑文件的格式（uft-8等）、文件类型（java、xml等）和光标位置等。

从https://github.com/Lokaltog/vim-powerline下载PowerLine插件，将文件解压得到的autoload、doc、plugin和fontpatcher文件夹放到~/Vim/Vim73/bundler目录下，往_vimrc文件中增加下面配置即可：

"powerline
 set guifont=PowerlineSymbols\ for\ Powerline
 set nocompatible
 set t_Co=256
 let g:Powerline_symbols = 'fancy'

----------------------------------------------------------------------------------------------------------
 1、pathogen安装
pathogen是一款管理插件的插件，它采用bundle方式管理Vim插件。
从 https://github.com/tpope/vim-pathogen 下载pathogen插件，在~/Vim/Vim73下增加一个bundle目录，并且把pathogen.vim放到autoload目录下，往_vimrc中添加下面代码：

call pathogen#infect()

Windows放在 Vim72\autoload\下

----------------------------------------------------------------------------------------------------------
漂亮的状态栏样式，安装简单
mystatusline.vim

windows:拷贝到vim73/plugin
mac:没试成功

配置：
set laststatus=2 
let g:mystatusline_actived = 1 

文档：

install details
first, put "mystatusline.vim"(this file) to dir vim73/plugin or vimfiles/plugin 
second, add the follow sentences to your .vimrc or _vimrc : 


-----------------------------------------------------------------------------------------
statusline.vim
windows:没试过
mac:直接拷贝到
不拷贝直接用~/.vim/plugin/statusline.vim 就能用了，都没配置

autocmd! ColorScheme *  source c:/vim/vimfiles/plugin/statusline.vim 
autocmd! ColorScheme *  source ~/.vim/plugin/statusline.vim

--------------------------------------------------------------------------

ruby语法检查
ruby-syntaxchecker

description
ruby-syntaxchecker.vim 

https://github.com/vantares/ruby-syntaxchecker.vim 

ruby syntax checker, toggles a quickfix window with the error list 

description 
You need to install ruby It\\'s a simple program that just checks if your ruby code have any syntax warning or error. 

Pressing F4 will run it using the \\\"quickfix\\\" feature. This way you can \\\"navigate\\\" through errors using :cn and other standard commands.
 
install details
install details 
just put the file in your ~/.vim/ftplugin/ruby directory (if that doesn\\'t exist, create it) 

The default mapping is F4, you can change it putting let g:ruby_syntaxcheck_map=\\'whatever\\' in your vimrc
----------------------------------------------------------------------------------------------------------


多处光标插件
vim-multiple-cursors
好像很酷的样子


-----------------------------------------------
语法检查
Syntastic  

Syntastic is a syntax checking plugin that runs files through external syntax checkers and displays any resulting errors to the user. This can be done on demand, or automatically as files are saved. If syntax errors are detected, the user is notified and is happy because they didn't have to compile their code or execute their script to find them.

At the time of this writing, syntax checking plugins exist for ada, applescript, c, co, coffee, coq, cpp, cs, css, cucumber, cuda, d, dart, docbk, elixir, erlang, eruby, fortran, gentoo_metadata, go, haml, haskell, haxe, html, java, javascript, json, less, lisp, lua, matlab, nasm, objc, ocaml, perl, php, puppet, python, rst, ruby, rust, sass/scss, scala, sh, slim, tcl, tex, twig, typescript, vala, vhdl, xhtml, xml, xslt, yaml, z80, zpt, zsh

https://github.com/scrooloose/syntastic


==================================================================
Ack – for 工程師用的 grep

身為一個工程師，每天要跟無數的程式碼奮戰，難免要在檔案間做一些搜尋和比對，通常我都是使用 grep, 不過最近我發現在寫 code 的時候, ack 變成我更好的選擇.

ack 是什麼呢, 下面借用 ack manual 上的說明:

ack is designed by a programmer, for programmers, for searching large trees of code.

ack 在搜尋的時候自動跳過一些己知不需要搜尋的 folder (e.g. .git, .svn) 或是一些非 source code 的檔案 (e.g. backup file, binary file, or core dump)，對於每次要用 find + grep 辛苦過濾檔案的工程師來說，可以省下一些打指令的時間。

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------
删除一行：dd
 
删除一个单词/光标之后的单词剩余部分：dw
 
删除当前字符：x
 
光标之后的该行部分：d$
 
 
文本删除
dd 删除一行
d$ 删除以当前字符开始的一行字符
 
ndd 删除以当前行开始的n行
dw 删除以当前字符开始的一个字
ndw 删除以当前字符开始的n个字
 
D 与d$同义
 
d) 删除到下一句的开始
 
d} 删除到下一段的开始
d回车 删除2行
ndw 或 ndW 删除光标处开始及其后的 n-1 个字符。
d0 删至行首。
d$ 删至行尾。
ndd 删除当前行及其后 n-1 行。
x 或 X 删除一个字符。
Ctrl+u 删除输入方式下所输入的文本。
^R 恢复u的操作
J 把下一行合并到当前行尾
V 选择一行
^V 按下^V后即可进行矩形的选择了
aw 选择单词
iw 内部单词(无空格)
as 选择句子
is 选择句子(无空格)
ap 选择段落
ip 选择段落(无空格)
D 删除到行尾
x,y 删除与复制包含高亮区

dl 删除当前字符（与x命令功能相同）
d0 删除到某一行的开始位置
d^ 删除到某一行的第一个字符位置（不包括空格或TAB字符）
dw 删除到某个单词的结尾位置
d3w 删除到第三个单词的结尾位置
db 删除到某个单词的开始位置
dW 删除到某个以空格作为分隔符的单词的结尾位置
dB 删除到某个以空格作为分隔符的单词的开始位置
d7B 删除到前面7个以空格作为分隔符的单词的开始位置
d） 删除到某个语句的结尾位置
d4） 删除到第四个语句的结尾位置
d（ 删除到某个语句的开始位置
d） 删除到某个段落的结尾位置
d{ 删除到某个段落的开始位置
d7{ 删除到当前段落起始位置之前的第7个段落位置
dd 删除当前行
d/text 删除从文本中出现“text”中所指定字样的位置，
一直向前直到下一个该字样所出现的位置（但不包括该字样）之间的内容
dfc 删除从文本中出现字符“c”的位置，一直向前直到下一个该字符所出现的位置（包括该字符）之间的内容
dtc 删除当前行直到下一个字符“c”所出现位置之间的内容
D 删除到某一行的结尾
d$ 删除到某一行的结尾
5dd 删除从当前行所开始的5行内容
dL 删除直到屏幕上最后一行的内容
dH 删除直到屏幕上第一行的内容
dG 删除直到工作缓存区结尾的内容
d1G 删除直到工作缓存区开始的内容
 
 
在Vi 中移动光标
  k        上
h   l    左  右
  j        下

^        移动到该行第一个非空格的字符处
w        向前移动一个单词，将符号或标点当作单词处理
W        向前移动一个单词，不把符号或标点当作单词处理
b        向后移动一个单词，把符号或标点当作单词处理
B        向后移动一个单词，不把符号或标点当作单词处理
(        光标移至句首
)        光标移至句尾
{        光标移至段落开头
}        光标移至段落结尾
H        光标移至屏幕顶行
M        光标移至屏幕中间行
L        光标移至屏幕最后行 
0        到行首
$        到行尾
gg       到页首
G        到页末
行号+G   跳转到指定行
n+       光标下移n行
n-       光标上移n行 
Ctrl+g   查询当前行信息和当前文件信息

fx       向右跳到本行字符x处（x可以是任何字符）
Fx       向左跳到本行字符x处（x可以是任何字符）

tx       和fx相同，区别是跳到字符x前
Tx       和Fx相同，区别是跳到字符x后

C-b      向上滚动一屏
C-f      向下滚动一屏
C-u      向上滚动半屏
C-d      向下滚动半屏
C-y      向上滚动一行
C-e      向下滚动一行

nz       将第n行滚至屏幕顶部，不指定n时将当前行滚至屏幕顶部。 
进入和退出Vi命令
vi filename               打开或新建文件，并将光标置于第一行首
vi +n filename            打开文件，并将光标置于第n行首
vi + filename             打开文件，并将光标置于最后一行首
vi +/pattern filename     打开文件，并将光标置于第一个与pattern匹配的串处
vi -r filename            在上次正用vi编辑时发生系统崩溃，恢复filename
vi filename ... filename  打开多个文件，依次进行编辑 

ZZ                        退出vi并保存
:q!                       退出vi，不保存
:wq                       退出vi并保存
重复操作
.        重复上一次操作
自动补齐
C-n      匹配下一个关键字
C-p      匹配上一个关键字
插入
o        在光标下方新开一行并将光标置于新行行首，进入插入模式。
O        同上，在光标上方。

a        在光标之后进入插入模式。
A        同上，在光标之前。


R        进入替换模式，直到按下Esc
set xxx  设置XXX选项。
行合并
J        把下面一行合并到本行后面
Vi中查找及替换命令
/pattern         从光标开始处向文件尾搜索pattern
?pattern         从光标开始处向文件首搜索pattern
n                在同一方向重复上一次搜索命令
N                在反方向上重复上一次搜索命令
%                查找配对的括号
:s/p1/p2/g       将当前行中所有p1均用p2替代，若要每个替换都向用户询问则应该用gc选项
:n1,n2s/p1/p2/g  将第n1至n2行中所有p1均用p2替代
:g/p1/s//p2/g    将文件中所有p1均用p2替换

.*[]^%~$ 在Vi中具有特殊含义，若需要查找则应该加上转义字符"\"
查找的一些选项
设置高亮
:set hlsearch    设置高亮
:set nohlsearch  关闭高亮
:nohlsearch      关闭当前已经设置的高亮
增量查找
:set incsearch   设置增量查找
:set noincsearch 关闭增量查找
在Vi中删除
x        删除当前光标下的字符
dw       删除光标之后的单词剩余部分。
d$       删除光标之后的该行剩余部分。
dd       删除当前行。

c        功能和d相同，区别在于完成删除操作后进入INSERT MODE
cc       也是删除当前行，然后进入INSERT MODE

更改字符
rx       将当前光标下的字符更改为x（x为任意字符） 
~        更改当前光标下的字符的大小写 
 
键盘宏操作
qcharacter  开始录制宏，character为a到z的任意字符
q           终止录制宏
@character  调用先前录制的宏

恢复误操作
u        撤销最后执行的命令
U        修正之前对该行的操作
Ctrl+R   Redo
在Vi中操作Frame
c-w c-n  增加frame
c-w c-c  减少frame
c-w c-w  切换frame
c-w c-r  交换两个frame
VIM中的块操作
Vim支持多达26个剪贴板
  选块   先用v，C-v，V选择一块，然后用y复制，再用p粘贴。
  yy     复制当前整行
  nyy    复制当前行开始的n行内容
  ?nyy   将光标当前行及其下n行的内容保存到寄存器?中，其中?为一个字母，n为一个数字
  ?nyw   将光标当前行及其下n个词保存到寄存器?中，其中?为一个字母，n为一个数字
  ?nyl   将光标当前行及其下n个字符保存到寄存器?中，其中?为一个字母，n为一个数字
  ?p     将寄存器?中的内容粘贴到光标位置之后。如果?是用yy复制的完整行，
         则粘贴在光标所在行下面。这里?可以是一个字母，也可以是一个数字 
  ?P     将寄存器a中的内容粘贴到光标位置之前。如果?是用yy复制的完整行，
         则粘贴在光标所在行上面。这里?可以是一个字母，也可以是一个数字 
  ay[motion]
            ay$    复制光标位置到行末并保存在寄存器a中
            ayft   复制光标位置到当前行第一个字母t并保存在寄存器a中
以上指令皆可去掉a工作，则y,p对未命名寄存器工作（所有d,c,x,y的对象都被保存在这里）。
剪切/复制/粘贴
所有删除的内容自动被保存，可以用p键粘贴
Vi的选项设置
all         列出所有选项设置情况
term        设置终端类型
ignorance   在搜索中忽略大小写
list        显示制表位(Ctrl+I)和行尾标志($)
number      显示行号
report      显示由面向行的命令修改过的数目
terse       显示简短的警告信息
warn        在转到别的文件时若没保存当前文件则显示NO write信息
nomagic     允许在搜索模式中，使用前面不带“\”的特殊字符
nowrapscan  禁止vi在搜索到达文件两端时，又从另一端开始
mesg        允许vi显示其他用户用write写到自己终端上的信息 
tips
对代码自动格式化 gg=G
 
 
在vi/vim中，跳到文件首尾快捷键:
 
文件开始:shift + g
文件结束:G

