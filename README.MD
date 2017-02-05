#R Language Learning
关于R语言学习的一些经验</br>
R语言资源</br>
[糗世界](http://blog.qiubio.com:8080) </br>
[清华大学开源软件镜像站](https://mirror.tuna.tsinghua.edu.cn/) </br>
[中科大开源软件镜像站](http://mirrors.ustc.edu.cn/)</br>

更换源镜像
R目录下/etc/Rprofile.site 在文档末添加下面两行，更换为清华的R包源镜像和Bioconductor源镜像</br>
<pre><code>
options("repos" = c(CRAN="https://mirrors.tuna.tsinghua.edu.cn/CRAN/"))
options(BioC_mirror="https://mirrors.tuna.tsinghua.edu.cn/bioconductor")
</code></pre>


安装bioconductor包
<pre><code>
source("https://bioconductor.org/biocLite.R")
biocLite()
</code></pre>


安装"hgu95av2.db"数据，注意R的老版本是没有引号，新版本在引用和安装包时必须加引号。
<pre><code>
biocLite("hgu95av2.db")
</code></pre>


以下出错信息为缺少包'AnnotationDbi'，控制台输入以下命令即可安装
<pre><code>
biocLite("AnnotationDbi")
</code></pre>
</br>
<pre><code>
* installing *source* package 'org.Hs.eg.db' ...
** R
** inst
** preparing package for lazy loading
Error in loadNamespace(i, c(lib.loc, .libPaths()), versionCheck = vI[[i]]) : 
  there is no package called 'RSQLite'
Error : package 'AnnotationDbi' could not be loaded
ERROR: lazy loading failed for package 'org.Hs.eg.db'
* removing 'D:/Software/R/R-3.3.2/library/org.Hs.eg.db'
ERROR: dependency 'org.Hs.eg.db' is not available for package 'hgu95av2.db'
* removing 'D:/Software/R/R-3.3.2/library/hgu95av2.db'
</code></pre>
