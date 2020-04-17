# Rime Custom Configuration

## 设置说明
* 基于 [simonqian](https://github.com/simonqian) 的 [sequirrel_custom](https://github.com/simonqian/sequirrel_custom) 修改
* 使用明月拼音，安装部署完成后，按 Ctrl+\` 选择朙月拼音简化字
* 词库扩展

## 使用说明

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
$ rsync -avzu --progress --exclude="README.md" * ~/Library/Rime
```

然后重新部署即可

## 卸载 Rime 输入法

```
$ say goodbye Squirrel && killall Squirrel
$ sudo rm -rf "/Library/Input Methods/Squirrel.app"
$ rm -rf ~/Library/Rime
```

## 文件说明

* default.custom.yaml，设置备选词数量，定义输入方案，Emacs 键盘绑定等
* squirrel.custom.yaml，自定义皮肤
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

