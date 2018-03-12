# conda配置

我习惯每个项目都建立独立的python虚拟环境,避免互相影响。  
这次试试在pycharm中建立conda虚拟环境。

安装好anaconda之后,在pycharm中可以直接建立conda虚拟环境。将虚拟环境的目录选择在当年项目中就好。

就是在命令行启动conda虚拟环境的时候需要带上项目位置,因为该目录没有加入环境变量。

```python
# 启动虚拟环境
activate my_project\envs
```

可以查看当前虚拟环境已经安装的包。

```python
conda list
```

[PS] 在pycharm中直接建立conda,好像没法直接全部安装anaconda所有包,所以在命令行中使用conda install anaconda就可以安装所有anaconda包了。

```python
# 在当前环境下安装anaconda包集合
conda install anaconda

# 结合创建环境的命令，以上操作可以合并为
conda create -n python34 python=3.4 anaconda
# 也可以不用全部安装，根据需求安装自己需要的package即可

```

如果需要安装很多packages，conda下载的速度经常很慢，因为Anaconda.org的服务器在国外。所幸的是，清华TUNA镜像源有Anaconda仓库的镜像，我们将其加入conda的配置即可：

```python
# 添加Anaconda的TUNA镜像
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
# TUNA的help中镜像地址加有引号，需要去掉
 
# 设置搜索时显示通道地址
conda config --set show_channel_urls yes
```