# good-book-pdf

好的技术书籍汇总


安装git - lfs到本机
这里没有什么难度，根据官网安装就好。
之后就是提交大文件的顺序，下面是官网的顺序：
安装Git命令行扩展。只需要设置一次Git LFS。
在项目目录下，执行以下命令：

```
git lfs install

```
选择您希望Git LFS管理的文件类型（或直接编辑.gitattributes）。您可以随时配置其他文件扩展名。这一步成功后会生成一个gitattributes文件

```
git lfs track “* .pdf” --这里的 “ *.pdf "就是你要上传的大文件的路径

```
添加并commit gitattributes文件

```
git add .gitattributes

```
然后再添加大文件到本地缓存区

```
git add demo.pdf
git commit -m "提交.pdf大文件"
git push
```
以上，按照上述的方法，第一次上传大文件基本还是会报错，而且百思不得其解~
尼玛，新手入坑总是这个尿性。。

出现上述问题，先reset 到你刚才commit的前一个commit,(意思就是撤销刚才的commit，回到起点再来一次。)
第一、二步同上，第三步的时候，先将 .gitattributes文件，单独commit，然后push，完成之后，在进行第四部(第四部add 之后 执行git lfs ls-files应该能看见东西了)。
到这里应该就没问题了。

