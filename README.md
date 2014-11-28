helloworld
==========

Just for trail!

A little programmer's base.

Add this line to readme.md by github so that I try command:
>    git remote -v    
>    git remote add upstream https://github.com/XXXX.git

Configure Git to sync your fork with the original repository
<pre>
突然明白了一点:
如果你的项目P是fork了A的, A是fork B的;
那么你自己github上的P是original, A是你的 upstream,
若没有 git remote add upstream XX_url ,
你在 本地 git pull 时, 只会从origin pull文件,
这样是不能和上游仓库同步的.
因此需要告诉git你的远程仓库除了origin外还有别的,
起名为upstream是方便起见.
</pre>
**提交出错:**
情况描述: 远程仓库origin有修改,本地也有修改但未commit,或add.
git pull 出错
<pre> 
error: Your local changes to the following files would be overwritten by merge:
	README.md
Please, commit your changes or stash them before you can merge.
Aborting
</pre>

这说明本地的commit落后于远程origin

因为pull会丢失本地的修改,所以pull被abort了.
此时在本地进行commit之后再进行 git pull,
发生了自动merge, 并且调出了默认的文本编辑器nano要求填写merge的理由.
由于合并没有冲突,所以没有太多复杂的地方.
