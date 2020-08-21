## 安装conda

mkdir miniconda3

cd miniconda3

wget -c https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh

```bash
chmod 777 Miniconda3-latest-Linux-x86_64.sh #给执行权限
bash Miniconda3-latest-Linux-x86_64.sh #运行
```

此时命令行前面出现（base）说明**默认**进入了conda的基础环境

vim ~/.bashrc

最后添加

conda deactivate

## 创建conda环境

conda create -n torchani python=3.8.5

conda info --env

pip list ##查看已经安装好的包

pip install numpy

## 安装pytorch

https://pytorch.org/  根据有无cuda等选择合适的版本

cuda-gdb##查看cuda版本

hzhu02@z55 k210 cuda 9.2

![image-20200818090633262](C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20200818090633262.png)

## 安装torchani

pip install torchani

## test example

python torchani/example/vibration_analysis.py 

缺什么模块 就pip 安装

## 修改shell

tools目录下面有一个comp6.py的脚本

将line22:

 ani1x = torchani.models.ANI1x().to(parser.device)

修改成

ani1x = torchani.models.ANI1ccx().to(parser.device)

ani1x = torchani.models.ANI12x().to(parser.device)

即可运行不同模型的COMP6结果

######  代码：python comp6.py COMP6数据路径 > result.txt

