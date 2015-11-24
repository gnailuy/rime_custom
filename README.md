# simonqian的Rime配置说明

## 设置说明
* 使用明月拼音简体
* 使用了[五磅兔](mailto:zcunlin@foxmail.com)的“致青春／So Young”配色
* 字体使用El Capitan 最新的字体「苹方」
* 词库扩展

## 使用说明
```
$ git clone git@github.com:simonqian/sequirrel_custom.git
$ cd sequirrel_custom
$ cp * ~/Library/Rime
```
然后重新部署即可

## 文件说明
* default.custom.yaml，设置备选词数量，定义输入方案等
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
* [Rime输入法—鼠须管(Squirrel)词库添加及配置](http://www.jianshu.com/p/cffc0ea094a7)
* [「鼠鬚管」的调教笔记](http://www.jianshu.com/p/ef2d9442fb0c/comments/486329)
