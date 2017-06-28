<p align="center">
  <img src="https://cloud.githubusercontent.com/assets/2059754/24601246/753a7f36-1858-11e7-9d6b-7a0e64fb27f7.png" alt="bash logo"/>
</p>

## Table of Contents
  1. [Basic Operations](#1-basic-operations)  
    1.1. [File Operations](#11-file-operations)  
    1.2. [Text Operations](#12-text-operations)  
    1.3. [Directory Operations](#13-directory-operations)  
    1.4. [SSH, System Info & Network Operations](#14-ssh-system-info--network-operations)  
    1.5. [Process Monitoring Operations](#15-process-monitoring-operations)
  2. [Basic Shell Programming](#2-basic-shell-programming)  
    2.1. [Variables](#21-variables)  
    2.2  [Array](#22-array)  
    2.3. [String Substitution](#23-string-substitution)  
    2.4. [Functions](#24-functions)  
    2.5. [Conditionals](#25-conditionals)  
    2.6. [Loops](#26-loops)  
  3. [Tricks](#3-tricks)  
  4. [Debugging](#4-debugging)  


# 1. Basic Operations

### a. `export`
全ての環境変数を表示する。特定の変数を表示する場合、`echo $VARIABLE_NAME` を利用する。
```bash
export
```
Example:
```bash
$ export
AWS_HOME=/Users/adnanadnan/.aws
LANG=en_US.UTF-8
LC_CTYPE=en_US.UTF-8
LESS=-R

$ echo $AWS_HOME
/Users/adnanadnan/.aws
```

### b. `whatis`
`whatis` はユーザコマンド、システムコール、ライブラリ関数、その他のマニュアル概要を表示する。
```bash
whatis something
```
Example:
```bash
$ whatis bash
bash (1)             - GNU Bourne-Again SHell
```

### c. `whereis`
`whereis` はシステムによって構築されたデータベースを利用して、実行可能ファイル、ソースファイル、マニュアルページを検索する。
```bash
whereis name
```
Example:
```bash
$ whereis php
/usr/bin/php
```

### d. `which`
`which` は環境変数PATH で指定されたディレクトリ内の実行可能ファイルを検索する。このコマンドは実行可能ファイルのフルパスを出力する。
```bash
which program_name
```
Example:
```bash
$ which php
/c/xampp/php/php
```

### e. clear
ウィンドウのコンテンツをクリアする。

## 1.1. File Operations
<table>
   <tr>
      <td><a href="#a-cat">cat</a></td>
      <td><a href="#b-chmod">chmod</a></td>
      <td><a href="#c-chown">chown</a></td>
      <td><a href="#d-cp">cp</a></td>
      <td><a href="#e-diff">diff</a></td>
      <td><a href="#f-file">file</a></td>
      <td><a href="#g-find">find</a></td>
      <td><a href="#h-gunzip">gunzip</a></td>
      <td><a href="#i-gzcat">gzcat</a></td>
      <td><a href="#j-gzip">gzip</a></td>
      <td><a href="#k-head">head</a></td>
   </tr>
   <tr>
      <td><a href="#l-lpq">lpq</a></td>
      <td><a href="#m-lpr">lpr</a></td>
      <td><a href="#n-lprm">lprm</a></td>
      <td><a href="#o-ls">ls</a></td>
      <td><a href="#p-more">more</a></td>
      <td><a href="#q-mv">mv</a></td>
      <td><a href="#r-rm">rm</a></td>
      <td><a href="#s-tail">tail</a></td>
      <td><a href="#t-touch">touch</a></td>
   </tr>
</table>

### a. `cat`
UNIX または Linux で以下の目的に利用できる。

- 画面にテキストファイルを表示する
- テキストファイルをコピーする
- テキストファイルを結合する
- テキストファイルを新規作成する
```bash
cat filename
cat file1 file2
cat file1 file2 > newcombinedfile
cat < file1 > file2 # file1 を file2 にコピー
```

### b. `chmod`
chmod コマンドは change mode の略で、ファイルとフォルダに対する読み取り、書き込み、実行の権限を変更することができる。  
このコマンドの詳細については、この[リンク(英語)](https://ss64.com/bash/chmod.html)をチェック。
```bash
chmod -options filename
```

### c. `chown`
chown コマンドは change owner の略で、ファイルかフォルダの所有者を変更することができます。ユーザーやグループにできます。  
基本的な使い方はシンプルで、ユーザーのあとにグループを指定します。`:` で区切ります。
```bash
chown -options user:group filename
```

### d. `cp`
ある場所から他の場所にファイルをコピーする
```bash
cp filename1 filename2
```
`filename1` がファイルへのソースパスで、`filename2` がファイルへのコピー先パスです。

### e. `diff`
ファイルを比較し、その違いを表示する。
```bash
diff filename1 filename2
```

### f. `file`
ファイルタイプを表示する。
```bash
file filename
```
Example:
```bash
$ file index.html
 index.html: HTML document, ASCII text
```
### g. `find`
ディレクトリからファイルを探す。
```bash
find directory options pattern
```
Example:
```bash
$ find . -name README.md
$ find /home/user1 -name '*.png'
```

### h. `gunzip`
gzip で圧縮されたファイルの圧縮を解除する。
```bash
gunzip filename
```

### i. `gzcat`
gzip ファイルを gunzip (展開) することなく見ることができる。
```bash
gzcat filename
```

### j. `gzip`
ファイルを圧縮する。
```bash
gzip filename
```

### k. `head`
ファイルの先頭10行を出力する。
```bash
head filename
```

### l. `lpq`
プリンタのキューをチェックする。
```bash
lpq
```
Example:
```bash
$ lpq
Rank    Owner   Job     File(s)                         Total Size
active  adnanad 59      demo                            399360 bytes
1st     adnanad 60      (stdin)                         0 bytes
```

### m. `lpr`
ファイルを印刷する。
```bash
lpr filename
```

### n. `lprm`
プリンタのキューから何かを削除する。
```bash
lprm jobnumber
```

### o. `ls`
ファイルを一覧表示する。

`ls` には多くのオプションがある :

`-l` は、ファイルの正確なサイズ、ファイルの所有者、閲覧権限を持つユーザ、そして、最後に変更された時間を表示する long format でファイルを表示する。  
`-a` は、隠しファイルを含む全てのファイルを表示する。このコマンドの詳細については、この[リンク(英語)](https://ss64.com/bash/ls.html)をチェック。
```bash
ls option
```
Example:
```
$ ls -la
rwxr-xr-x   33 adnan  staff    1122 Mar 27 18:44 .
drwxrwxrwx  60 adnan  staff    2040 Mar 21 15:06 ..
-rw-r--r--@  1 adnan  staff   14340 Mar 23 15:05 .DS_Store
-rw-r--r--   1 adnan  staff     157 Mar 25 18:08 .bumpversion.cfg
-rw-r--r--   1 adnan  staff    6515 Mar 25 18:08 .config.ini
-rw-r--r--   1 adnan  staff    5805 Mar 27 18:44 .config.override.ini
drwxr-xr-x  17 adnan  staff     578 Mar 27 23:36 .git
-rwxr-xr-x   1 adnan  staff    2702 Mar 25 18:08 .gitignore
```

### p. `more`
ファイルの最初の部分を表示する ( スペースで移動、q で終了 ) 。
```bash
more filename
```

### q. `mv`
ある場所から別の場所にファイルを移動する。
```bash
mv filename1 filename2
```
`filename1` はファイルのソースパスで、 `filename2` は移動先のパスです。

また、ファイル名の変更にも使用できます。
```bash
mv old_name new_name
```

### r. `rm`
ファイルを削除する。ディレクトリでこのコマンドを使用するとエラーが発生する。
`rm: directory: is a directory`
ディレクトリを削除するには `-r` を渡す必要がある。これはディレクトリのコンテンツを再帰的に削除する。
オプションで `-r` フラグを使用して削除を強制することができる。確認なしで実行したい場合など
```bash
rm filename
```

### s. `tail`
ファイルの最後10行を出力する。ファイルが大きくなると追加されたデータを出力するために、`-f` を使う。
```bash
tail filename
```

### t. `touch`
ファイルのアクセスタイムスタンプと更新タイムスタンプを更新する。ファイルが存在しない場合は作成される。
```bash
touch filename
```
Example:
```bash
$ touch trick.md
```

## 1.2. Text Operations

<table>
    <tr>
      <td><a href="#a-awk">awk</a></td>
      <td><a href="#b-cut">cut</a></td>
      <td><a href="#c-echo">echo</a></td>
      <td><a href="#d-egrep">egrep</a></td>
      <td><a href="#e-fgrep">fgrep</a></td>
      <td><a href="#f-fmt">fmt</a></td>
      <td><a href="#g-grep">grep</a></td>
      <td><a href="#h-nl">nl</a></td>
      <td><a href="#i-sed">sed</a></td>
      <td><a href="#j-sort">sort</a></td>
   </tr>
   <tr>
      <td><a href="#k-tr">tr</a></td>
      <td><a href="#l-uniq">uniq</a></td>
      <td><a href="#m-wc">wc</a></td>
   </tr>
</table>

### a. `awk`
awk はテキストファイルを扱うのに最も有用なコマンドです。
ファイル全体を1行ずつ処理します。
デフォルトではスペースを使用してフィールドを区切ります。
awk コマンドの最も一般的な構文は次の通りです。
```bash
awk '/search_pattern/ { action_to_take_if_pattern_matches; }' file_to_parse
```
`/etc/passwd` ファイルをフォローできる。このファイルに含まれているサンプルデータは次の通りです。
```
root:x:0:0:root:/root:/usr/bin/zsh
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
```
これで、このファイルからユーザ名だけを取得できるようになりました。
`-F` は、どの文字をベースにフィールドを区切るかを指定する。
今回の場合は `:` 。
`{ print $1 }` の意味は、最初に一致するフィールドを表示することを意味する。
```bash
awk -F':' '{ print $1 }' /etc/passwd
```
上記のコマンドを実行すると、次の出力が得られる。
```
root
daemon
bin
sys
sync
```
`awk` の使い方の詳細については、この[リンク(英語)](https://www.cyberciti.biz/faq/bash-scripting-using-awk)をチェック。

### b. `cut`
ファイルの各行からセクションを削除する。

*example.txt*
```bash
red riding hood went to the park to play
```

*スペースをセパレータとして列 2, 7, 9 を表示する*
```bash
cut -d " " -f2,7,9 example.txt
```
```bash
riding park play
```

### c. `echo`
テキスト行を表示する。

*"Hello World" を表示する*
```bash
echo Hello World
```
```bash
Hello World
```

*単語間の改行で "Hello World" を表示する*
```bash
echo -ne "Hello\nWorld\n"
```
```bash
Hello
World
```

### d. `egrep`
パターンにマッチする行を表示する - 正規表現 ( `grep -E` のエイリアス )

*example.txt*
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*"Lorem" か "dolor" を持つ行を表示する*
```bash
egrep '(Lorem|dolor)' example.txt
or
grep -E '(Lorem|dolor)' example.txt
```
```bash
Lorem ipsum
dolor sit amet,
et dolore magna
duo dolores et ea
sanctus est Lorem
ipsum dolor sit
```

### e. `fgrep`
パターンにマッチする行を表示する - FIXED パターンマッチング ( `grep -F` のエイリアス )

*example.txt*
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
foo (Lorem|dolor)
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*example.txt から (Lorem|dolor) 文字列を検索する*
```bash
fgrep '(Lorem|dolor)' example.txt
or
grep -F '(Lorem|dolor)' example.txt
```
```bash
foo (Lorem|dolor)
```

### f. `fmt`
シンプルで最適なテキストフォーマッター

*example: example.txt (1 line)*
```bash
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.
```

*example.txt 行を20文字幅で出力する*
```bash
cat example.txt | fmt -w 20
```
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

### g. `grep`
ファイル内のテキストを検索する。
grep を使用して、1つまたは複数の正規表現に一致するテキスト行を検索し、一致する行だけを出力することが出来る。
```bash
grep pattern filename
```
Example:
```bash
$ grep admin /etc/passwd
_kadmin_admin:*:218:-2:Kerberos Admin Service:/var/empty:/usr/bin/false
_kadmin_changepw:*:219:-2:Kerberos Change Password Service:/var/empty:/usr/bin/false
_krb_kadmin:*:231:-2:Open Directory Kerberos Admin Service:/var/empty:/usr/bin/false
```
`-i` オプションを使うことで、grep に単語の大文字小文字を無視することが出来る。  
`-r` を使うと指定されたディレクトリの下にあるすべてのファイルを検索することが出来る。  
例 :
```bash
$ grep -r admin /etc/
```
`-w` は単語だけを検索する。  
grep の詳細については、この[リンク(英語)](https://www.cyberciti.biz/faq/grep-in-bash)をチェック。

### h. `nl`
ファイルの行数

*example.txt*
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*行数と共に example.txt を表示*
```bash
nl -s". " example.txt 
```
```bash
     1. Lorem ipsum
     2. dolor sit amet,
     3. consetetur
     4. sadipscing elitr,
     5. sed diam nonumy
     6. eirmod tempor
     7. invidunt ut labore
     8. et dolore magna
     9. aliquyam erat, sed
    10. diam voluptua. At
    11. vero eos et
    12. accusam et justo
    13. duo dolores et ea
    14. rebum. Stet clita
    15. kasd gubergren,
    16. no sea takimata
    17. sanctus est Lorem
    18. ipsum dolor sit
    19. amet.
```

### i. `sed`
テキストのフィルタリングと変換のためのストリームエディタ

*example.txt*
```bash
Hello This is a Test 1 2 3 4
```

*全てのスペースをハイフンに置換する*
```bash
sed 's/ /-/g' example.txt
```
```bash
Hello-This-is-a-Test-1-2-3-4
```

*全ての数字を d に置換する*
```bash
sed 's/[0-9]/d/g' example.txt
```
```bash
Hello This is a Test d d d d
```

### j. `sort`
テキストファイルの行をソートする

*example.txt*
```bash
f
b
c
g
a
e
d
```

*sort example.txt*
```bash
sort example.txt
```
```bash
a
b
c
d
e
f
g
```

*ソートされた example.txt をランダム化*
```bash
sort example.txt | sort -R
```
```bash
b
f
a
c
d
g
e
```

### k. `tr`
文字の変換または削除

*example.txt*
```bash
Hello World Foo Bar Baz!
```

*すべての小文字を取り大文字にする*
```bash
cat example.txt | tr 'a-z' 'A-Z'
```
```bash
HELLO WORLD FOO BAR BAZ!
```

*全てのスペースをとって改行する*
```bash
cat example.txt | tr ' ' '\n'
```
```bash
Hello
World
Foo
Bar
Baz!
```

### l. `uniq`
繰り返し行を報告するか省略するか

*example.txt*
```bash
a
a
b
a
b
c
d
c
```

*example.txt の一意の行だけを表示する ( 最初にソートする必要がある、そうでなければ重複を判定できない )*
```bash
sort example.txt | uniq
```
```bash
a
b
c
d
```

*各行のユニークな項目を表示し、見つかった数を教えてくれる*
```bash
sort example.txt | uniq -c
```
```bash
    3 a
    2 b
    2 c
    1 d
```

### m. `wc`
ファイル内にいくつの行、単語、文字があるかを表示する。
```bash
wc filename
```
Example:
```bash
$ wc demo.txt
7459   15915  398400 demo.txt
```
`7459` は行、`15915` は単語、`398400` は文字。

## 1.3. Directory Operations

<table>
   <tr>
      <td><a href="#a-cd">cd</a></td>
      <td><a href="#b-mkdir">mkdir</a></td>
      <td><a href="#c-pwd">pwd</a></td>
   </tr>
</table>

### a. `cd`
1つのディレクトリから別のディレクトリに移動する。
```bash
$ cd
```
home ディレクトリに移動する。

このコマンドはオプションの `dirname` を受け取り、そのディレクトリに移動する。
```bash
cd dirname
```

### b. `mkdir`
新しいディレクトリを作る。
```bash
mkdir dirname
```

### c. `pwd`
今いるディレクトリを表示する。
```bash
pwd
```

## 1.4. SSH, System Info & Network Operations

<table>
   <tr>
      <td><a href="#a-bg">bg</a></td>
      <td><a href="#b-cal">cal</a></td>
      <td><a href="#c-date">date</a></td>
      <td><a href="#d-df">df</a></td>
      <td><a href="#e-dig">dig</a></td>
      <td><a href="#f-du">du</a></td>
      <td><a href="#g-fg">fg</a></td>
      <td><a href="#h-finger">finger</a></td>   
      <td><a href="#i-jobs">jobs</a></td>
      <td><a href="#j-last">last</a></td>
   </tr>
   <tr>
      <td><a href="#k-man">man</a></td>
      <td><a href="#l-passwd">passwd</a></td>
      <td><a href="#m-ping">ping</a></td>
      <td><a href="#n-ps">ps</a></td>
      <td><a href="#o-quota">quota</a></td>
      <td><a href="#p-scp">scp</a></td>
      <td><a href="#q-ssh">ssh</a></td>
      <td><a href="#r-top">top</a></td>
      <td><a href="#s-uname">uname</a></td>
      <td><a href="#t-uptime">uptime</a></td>
   </tr>
   <tr>
      <td><a href="#u-w">w</a></td>
      <td><a href="#v-wget">wget</a></td>
      <td><a href="#w-whoami">whoami</a></td>
      <td><a href="#x-whois">whois</a></td>
   </tr>
</table>

### a. `bg`
停止したジョブまたはバックグラウンドジョブを一覧表示する。
停止したジョブをバックグラウンドで再開する。

### b. `cal`
月のカレンダーを表示する。

### c. `date`
現在の日付と時刻を表示する。

### d. `df`
ディスクの使用状況を表示する。

### e. `dig`
ドメインの DNS 情報を取得する。
```bash
dig domain
```

### f. `du`
ファイルまたはディレクトリのディスク使用量を表示する。
このコマンドの詳細については、この[リンク(英語)](http://www.linfo.org/du.html)をチェック
```bash
du [option] [filename|directory]
```
オプション:
- `-h` (人間が読める) 出力をキロバイト、メガバイト、ギガバイトで表示する。
- `-s` (抑制または要約) ディレクトリの合計ディスク容量を出力し、サブディレクトリのレポートは控える。

Example:
```bash
du -sh pictures
1.4M pictures
```

### g. `fg`
直前のジョブをフォアグラウンドに表示する。

### h. `finger`
ユーザーに関する情報を表示する。
```bash
finger username
```
### i. `jobs`
バックグラウンドで実行中のジョブをリストし、ジョブ番号を指定する。

### j. `last`
指定したユーザーの最終ログインを一覧表示する。
```bash
last yourUsername
```

### k. `man`
指定されたコマンドのマニュアルを表示する。
```bash
man command
```

### l. `passwd`
現在ログインしているユーザーがパスワードを変更できるようにする。

### m. `ping`
ホストに ping して結果を出力する。
```bash
ping host
```

### n. `ps`
プロセスを一覧表示する。
```bash
ps -u yourusername
```

### o. `quota`
ディスククォータ情報を表示する。
```bash
quota -v
```

### p. `scp`
ローカルホストとリモートホスト間、または2つのリモートホスト間でファイルを転送する。

*ローカルホストからリモートホストにコピーする*
```bash
scp source_file user@host:directory/target_file
```
*リモートホストからローカルホストにコピーする*
```bash
scp user@host:directory/source_file target_file
scp -r user@host:directory/source_folder target_folder
```
このコマンドは、特定ポートに接続するために使用 `-P` オプションも受け付ける。
```bash
scp -P port user@host:directory/source_file target_file
```

### q. `ssh`
ssh ( SSH クライアント ) は、リモートマシンでログインしてコマンドを実行するためのプログラム。
```bash
ssh user@host
```
このコマンドは、特定ポートに接続するために使用 `-P` オプションも受け付ける。
```bash
ssh -p port user@host
```

### r. `top`
現在アクティブなプロセスを表示する。

### s. `uname`
カーネル情報を表示する。
```bash
uname -a
```

### t. `uptime`
現在の uptime ( 稼働時間 ) を表示する。

### u. `w`
オンラインのユーザーを表示する。

### v. `wget`
ファイルをダウンロードする。
```bash
wget file
```

### w. `whoami`
現在ログインしているユーザー名を返す。

### x. `whois`
ドメインの whois 情報を取得する。
```bash
whois domain
```

## 1.5. Process Monitoring Operations

<table>
   <tr>
      <td><a href="#a-kill">kill</a></td>
      <td><a href="#b-killall">killall</a></td>
      <td><a href="#c-&">&amp;</a></td>
      <td><a href="#d-nohup">nohup</a></td>
   </tr>
</table>

### a. `kill`
指定した ID でプロセスを Kill ( 終了 ) する。
```bash
kill PID
```

### b. `killall`
すべてのプロセスを名前で削除する。
```bash
killall processname
```

### c. &
`&` シンボルは、コマンドがサブシェルのバックグラウンドプロセスとして実行されるように指示する。
```bash
command &
```

### d. `nohup`
nohup は "No Hang Up" の略。
シェルからログアウトした後、バックグラウンドで実行を継続できるコマンド/プロセスまたはシェルスクリプトを実行できる。
```bash
nohup command
```
`&` と組み合わせてバックグラウンドプロセスを作成する
```bash
nohup command &
```

# 2. Basic Shell Programming
bash スクリプトファイルに書き込み最初の行は、`shebang` (シバン、シェバン) と呼ばれる。  
どのスクリプトでも、あらかじめターミナルに sh, bash, python, php など入力しなくても、スタンドアロンの実行可能ファイルのように実行できる。
```bash
#!/bin/bash
```

## 2.1. Variables
bash で変数を作成することは他の言語に似ている。
データ型は無い。
bash の変数には、数値、文字、文字列などを含めることが出来る。
変数を宣言する必要はなく、参照に値を代入するだけで変数が作成される。

Example:
```bash
str="hello world"
```

上記の行は変数 `str` を作成し、それに "hello world" を割り当てている。
変数の値は、変数名の先頭に `$` を置くことによって取り出される。

Example:
```bash
echo $str   # hello world
```
## 2.2. Array
他の言語と同様、bash にも配列があります。
配列は、複数の値を含む変数です。
配列のサイズには最大限の制限はありません。
bash の配列はゼロベースです。
最初の要素は要素0で索引付けされます。
bash で配列を作成する方法はいくつかあります。
これは以下の通り。

Examples:
```bash
array[0] = val
array[1] = val
array[2] = val
array=([2]=val [0]=val [1]=val)
array=(val val val)
```

特定のインデックスで値を表示するには、次の構文を使用 :

```bash
${array[i]}     # where i is the index
```

インデックスが指定されない場合、配列要素0が仮定される。
配列内にある値の数を調べるには、次の構文を使用 :

```bash
${#array[@]}
```

Bash は三項演算子もサポートしている。以下の例をチェック。

```bash
${varname:-word}    # varname が存在し、null でない場合は、その値を返す。そうでなければ word を返す
${varname:=word}    # varname が存在し、null でない場合は、その値を返す。それ以外の場合は word を設定し、その値を返す
${varname:+word}    # varname が存在し、null でない場合は、word を返す。そうでない場合は null を返す
${varname:offset:length}    # 部分文字列展開を行う。これは、offset から始まり length 文字までの $varname の部分文字列を返す
```

## 2.3 String Substitution
文字列を操作する方法の構文をチェック

```bash
${variable#pattern}         # パターンが変数の値の先頭に一致する場合は、一致する最も短い部分を削除し、残りの部分を返す
${variable##pattern}        # パターンが変数の値の先頭に一致する場合は、一致する最も長い部分を削除し、残りの部分を返す
${variable%pattern}         # パターンが変数の値の終わりと一致する場合は、一致する最も短い部分を削除し、残りの部分を返す
${variable%%pattern}        # パターンが変数の値の終わりと一致する場合は、一致する最も長い部分を削除し、残りの部分を返す
${variable/pattern/string}  # 変数の中で最も長いパターンが文字列に置き換えられる。最初の一致のみ置換される
${variable//pattern/string} # 変数の中で最も長いパターンが文字列に置き換えられる。全ての一致が置換される
${#varname}     # 変数の値の長さを文字列として返す
```

## 2.4. Functions
ほぼ全てのプログラミング言語と同様に、関数を使用してコードをよりロジカルな方法でグループ化することも、再帰アートの練習をすることも出来ます。
関数を宣言することは、単に `function my_func {my_code}` と書くだけです。
関数の呼び出しは、別のプログラムを呼び出すことと同じで、名前を書くだけです。

```bash
functname() {
    shell commands
}
```

Example:
```bash
#!/bin/bash
function hello {
   echo world!
}
hello

function say {
    echo $1
}
say "hello world!"
```

上記の例を実行すると、`hello` 関数は `world!` を出力します。
上記の2つの関数 `hello` と `say` は同じです。
主な違いは、関数 `say` で、この関数は、受け取った最初の引数を出力する。
関数内の引数は、スクリプトに与えられた引数と同じ方法で扱われる。

## 2.5. Conditionals
bash の条件分は他のプログラミング言語に似ている。
条件分には、最も基本的なフォームと同じように多くのフォームがあります。
`if expression then` ステートメントは、式が true の場合のみ実行される。

```bash
if [expression]; then
    will execute only if expression is true
else
    will execute if expression is false
fi
```

条件が混乱するようになったら、`case expression` を使用して同じ条件を書くことができる。

```bash
case expression in
    pattern1 )
        statements ;;
    pattern2 )
        statements ;;
    ...
esac
```

Expression Examples:

```bash
statement1 && statement2  # 両方 true
statement1 || statement2  # 少なくとも1つが true

str1=str2       # str1 が str2 と同じ
str1!=str2      # str1 が str2 と異なる
str1<str2       # str1 が str2 より小さい
str1>str2       # str1 が str2 より大きい
-n str1         # str1 が null ではない (0 より大きい長さを持つ)
-z str1         # str1 が null (長さが 0)

-a file         # file が存在している
-d file         # file が存在し、ディレクトリである
-e file         # file が存在している; -a と同じ
-f file         # file が存在し、通常のファイル (言い換えれば, ディレクトリやその他特殊なファイルではない)
-r file         # 読み取り権限を持っている
-s file         # file が存在し、空ではない
-w file         # 書き込み権限を持っている
-x file         # 実行権限を持っている、またはディレクトリの場合はディレクトリ検索権限を持っている
-N file         # ファイルが最後に読み込まれてから変更された
-O file         # 自分の所有ファイル
-G file         # ファイルのグループ ID が自分のものと一致する (また、複数グループに属している場合はそのうちの一つと一致する)

file1 -nt file2     # file1 が file2 より新しい
file1 -ot file2     # file1 が file2 より古い

-lt     # 未満
-le     # 未満か同値
-eq     # 同値
-ge     # 以上か同値
-gt     # 以上
-ne     # 等しくない
```

## 2.6. Loops

bash には3種類のループがある。
`for`, `while`, `util` です。

`for` Syntax:
```bash
for x := 1 to 10 do
begin
  statements
end

for name [in list]
do
  statements that can use $name
done

for (( initialisation ; ending condition ; update ))
do
  statements...
done
```

`while` Syntax:
```bash
while condition; do
  statements
done
```

`until` Syntax:
```bash
until condition; do
  statements
done
```

# 3. Tricks

## Set an alias
次のコマンドを実行して `bash_profile` を開く `nano ~/.bash_profile`

> alias dockerlogin='ssh www-data@adnan.local -p2222'  # .bash_profile にエイリアスを追加する

## To quickly go to a specific directory
nano ~/.bashrc
> export hotellogs="/workspace/hotel-api/storage/logs"

```bash
source ~/.bashrc
cd $hotellogs
```

## Exit traps

クリーンアップを確実に実行することで、bash スクリプトをより堅牢なものにする。

```bash
function finish {
  # your cleanup here. e.g. kill any forked processes
  jobs -p | xargs kill
}
trap finish EXIT
```

## Saving your environment variables

`export FOO = BAR` を実行すると、変数は現在のシェルと、その全ての子でのみ実行される。
変数を永続するには `~/.bash_profile` ファイルに変数をエクスポートするコマンドを追加する。

```bash
echo export FOO=BAR >> ~/.bash_profile
```

## Accessing your scripts

`mkdir ~/bin` を使用して home に bin フォルダを作ることで簡単にスクリプトにアクセスできる。
このフォルダに置かれた全てのスクリプトはどのディレクトリにもアクセスできる。

アクセス出来ない場合は、以下のコードを `~/.bash_profile` ファイルに追加してから、`source ~/.bash_profile` を実行してみて下さい。
```bash
    # PATH を設定して、ユーザーのプライベート bin が存在する場合はそれを含める
    if [ -d "$HOME/bin" ] ; then
        PATH="$HOME/bin:$PATH"
    fi
```

# 4. Debugging
様々なオプションを `bash` コマンドに渡すことで、bash スクリプトを簡単にデバッグすることができる。
たとえば、`-n` コマンドを実行せず、構文エラーのみチェックする。
`-v` コマンドを実行する前に echo コマンドを実行する。
`-x` コマンドラインプロセスの後に echo コマンドを実行する。

```bash
bash -n scriptname
bash -v scriptname
bash -x scriptname
```

## Contribution

- Report issues [How to](https://help.github.com/articles/creating-an-issue/)
- Open pull request with improvements [How to](https://help.github.com/articles/about-pull-requests/)
- Spread the word

## Translation
- [English | Original](https://github.com/Idnan/bash-guide)
- [Turkish | Türkçe](https://github.com/omergulen/bash-guide)

## License

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
