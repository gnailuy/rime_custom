# Rime Custom Configuration

## 设置说明

* 基于 [simonqian](https://github.com/simonqian) 的 [sequirrel_custom](https://github.com/simonqian/sequirrel_custom) 修改
* 原样添加了 simonqian 的词库扩展
* 使用明月拼音，对于简体用户，安装部署完成后，按 Ctrl+\` 选择朙月拼音简化字
* 鼠须管使用 luna 主题，小狼毫使用 Google+ 主题
* 配置使用 OneDrive 同步各个机器上的用户字典

## Mac 配置

### 安装鼠须管输入法

```
brew cask install squirrel
```

### 安装东风破基本配置集和 emoji 扩展

```
$ git clone git@github.com:rime/plum.git
$ cd plum
$ bash rime-install :preset
$ bash rime-install emoji:customize:schema=luna_pinyin
```

### 同步自定义配置

```
$ git clone git@github.com:gnailuy/rime_custom.git
$ cd rim_custom
$ rsync -avzu --progress --exclude="*.md" --exclude="*.sh" * ~/Library/Rime
```

然后重新部署即可。

### 同步配置和用户字典到

修改 Library/Rime/installation.yaml 文件，配置如下两项，然后可以在输入法菜单中同步用户设置。

```
installation_id: "Yuliang-MacBook-Pro"
sync_dir: "/Users/gnailuy/OneDrive/App/RimeSync"
```

### 卸载 Rime 输入法

```
$ say goodbye Squirrel && killall Squirrel
$ sudo rm -rf "/Library/Input Methods/Squirrel.app"
$ rm -rf ~/Library/Rime
```

## Windows 配置

### 安装小狼毫输入法

到 https://rime.im/download/ 下载，默认安装即可，基本都配置好了

### 同步自定义配置

这几行命令里的路径是 Git Bash 自动转换的，也可以手动操作，把所有 Yaml 文件拷贝到 C:\Users\yuljin\AppData\Roaming\Rime 即可

```
$ git clone git@github.com:gnailuy/rime_custom.git
$ cd rim_custom
$ cp *.yaml /c/Users/yuljin/AppData/Roaming/Rime
```

然后重新部署。

### 同步配置和用户字典到 Dropbox

修改 C:\Users\yuljin\AppData\Roaming\Rime\installation.yaml 文件，配置如下两项，然后可以在输入法菜单中同步用户设置。

```
installation_id: "Yuliang-Windows10-OfficePC"
sync_dir: 'C:\Users\yuljin\OneDrive\App\RimeSync'
```

## 用户字典同步说明

应用上面配置之后，Rime 的配置和用户数据就会出现在 OneDrive 的 App/RimeSync 目录里，放在以 installation_id 命名的子目录下面。
例如我这里就会有：

```
Yuliang-MacBook-Pro
Yuliang-MacBook-Air
Yuliang-Windows10-OfficePC
Yuliang-Windows10-Laptop
```

四个目录，分别对应我四台电脑上面的配置和用户数据。

当你点击输入法的 "同步用户数据" 菜单时，Rime 会综合所有子目录里的用户字典数据，并且双向同步到本机对应的目录里。这样，输入习惯和自定义词库就在各个机器之间共享了。

## 文件说明

* default.custom.yaml，设置备选词数量，定义输入方案，Emacs 键盘绑定等
* squirrel.custom.yaml，鼠须管自定义皮肤
* weasel.custom.yaml，小狼毫自定义皮肤
* luna_pinyin_simp.custom.yaml，定义扩展词库，加载符号库，模糊拼音
* easy_en.dict.yaml和easy_en.schema.yaml，在输入英文单词时进行候选提示
* luna_pinyin.extended.dict.yaml，扩展词库主文件，其他词库都需要在这个主文件中定义才能被调用，如果不想加载某个词库在此文件中注释掉即可（在所在行前加 # 井号）
* luna_pinyin.cn_en.dict.yaml，英文、中英文混合短语和名词
* luna_pinyin.computer.dict.yaml，计算机术语
* luna_pinyin.emoji.dict.yaml，表情符号
* luna_pinyin.hanyu.dict.yaml，汉语大词典
* luna_pinyin.kaomoji.dict.yaml，颜文字表情符号
* luna_pinyin.movie.dict.yaml，电影名称
* luna_pinyin.music.dict.yaml，音乐和歌曲名
* luna_pinyin.name.dict.yaml，人名
* luna_pinyin.poetry.dict.yaml，唐诗宋词、千家集、楚辞、诗经

## 参考

* [Rime 输入法—鼠须管 (Squirrel) 词库添加及配置](http://www.jianshu.com/p/cffc0ea094a7)
* [「鼠鬚管」的调教笔记](http://scomper.me/post/gtd/-shu-xu-guan-de-diao-jiao-bi-ji)
