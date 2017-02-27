可以用使用git结合github，同步你的配置，具体方法如下：

用户数据文件夹

Windows: %APPDATA%Sublime Text 3
Linux: ~/.config/sublime-text-3
OS X: ~/Library/Application Support/Sublime Text 3
需要同步的是用户数据文件夹下面的Packages文件夹下面的User文件夹，可以打开subl，在菜单栏选择Preferences | Browse Packages打开Packages文件夹。

使用git同步subl配置和插件

cd [package folder]/User
git init
以下文件不需要同步，添加至.gitignore文件：

Package Control.last-run
Package Control.ca-list
Package Control.ca-bundle
Package Control.system-ca-bundle
Package Control.cache/
Package Control.ca-certs/
encoding_cache.json
提交到远程仓库（如：github）

git add --all
git commit -m "your commit content"
git remote add origin [your git repository]
git push origin master
其它设备同步配置

cd [packages folder]
cp [packages folder]/User [package folser]/User_old
git clone [your git repository] User
通过以上操作，以后在任何一台设备有新的改动，只需要将改动提交到远程仓库即可。这样，就可以在不同平台的设备之间同步subl配置和插件。
