```python
测试cuda可用：
import torch
print(torch.cuda.is_available())
```

```shell
还原原始通道：
conda config --remove-key channels


更改conda源：

conda config --add channels http://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --add channels http://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels http://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
conda config --add channels http://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/
conda config --add channels http://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/

conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/main/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/conda-forge/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/msys2/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/bioconda/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/menpo/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/pytorch/

显示通道地址：
conda config --set show_channel_urls yes


```

```
原：conda install pytorch==1.10.1 torchvision==0.11.2 torchaudio==0.10.1 cudatoolkit=11.3 -c pytorch -c conda-forge
pip install torch==1.11.0+cu113 torchvision==0.12.0+cu113 torchaudio==0.11.0 --extra-index-url https://download.pytorch.org/whl/cu113 -i https://pypi.tuna.tsinghua.edu.cn/simple

pip install torch==1.10.1 torchvision==0.11.2 torchaudio==0.10.1 -i https://pypi.tuna.tsinghua.edu.cn/simple #直接pip不行
```

```
/root/anaconda3/envs/ovseg/bin/python -m pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple

python3 -m pip install detectron2 -f https://dl.fbaipublicfiles.com/detectron2/wheels/cu113/torch1.10/index.html -i https://pypi.tuna.tsinghua.edu.cn/simple

cd third_party/CLIP
python3 -m pip install -Ue .

cd ../..
```

```shell
python3 demo.py --config-file configs/ovseg_swinB_vitL_demo.yaml --class-names 'Oculus' 'Ukulele'  --input ./resources/demo_samples/sample_03.jpeg --output ./pred --opts MODEL.WEIGHTS ./weights/ovseg_swinbase_vitL14_ft_mpt.pth 
```

```shell
在lanyun上缺一个东西:

sudo apt-get install libgl1-mesa-glx
```

```shell
从官网上下载镜像

docker pull ftrkun/ovseg:v1

docker run -it --net=host --gpus all -v ~/work/ov-seg-main:/workspace ftrkun/ovseg:v1
```

~~~shell
要从本地 Ubuntu 拷贝 Docker 镜像并通过 U 盘转移到服务器，可以按照以下步骤进行操作：

在本地 Ubuntu 上：

1. 确保你已经安装了 Docker 并拥有需要复制的 Docker 镜像。如果没有安装 Docker，请先安装 Docker。

2. 使用以下命令将 Docker 镜像保存为一个文件（tar 归档格式）：
   ````
docker save -o <镜像文件名>.tar <镜像名称>:<版本>
   ```
   将 `<镜像文件名>.tar` 替换为你希望保存的镜像文件名，`<镜像名称>:<版本>` 替换为要保存的 Docker 镜像的名称和版本。

3. 将生成的镜像文件 `<镜像文件名>.tar` 复制到 U 盘或其他可移动存储设备。

在目标服务器上：

1. 将 U 盘或可移动存储设备插入服务器。

2. 使用以下命令将镜像文件加载到 Docker 中：
   ````
docker load -i <镜像文件名>.tar
   ```
   将 `<镜像文件名>.tar` 替换为你复制到服务器的镜像文件名。

3. 完成加载后，你可以使用 `docker images` 命令来验证镜像是否已成功加载到服务器的 Docker 中。

现在，你可以在目标服务器上使用刚刚复制的 Docker 镜像来创建和运行容器。

请注意，这种方法适用于在本地复制较小的 Docker 镜像。如果镜像非常大，可能需要更多的时间和存储空间。另外，确保目标服务器上已经安装了 Docker，并且你具有适当的权限来加载镜像。

如果你在复制或加载过程中遇到任何问题，请参考 Docker 官方文档或相关社区论坛，或与 Docker 支持团队联系以获取更多帮助和支持。
~~~

conda config --remove channels https://mirrors.ustc.edu.cn/anaconda/pkgs/main/ 

conda config --remove channels https://mirrors.ustc.edu.cn/anaconda/pkgs/free/ 

conda config --remove channels https://mirrors.ustc.edu.cn/anaconda/cloud/conda-forge/ 

conda config --remove channels https://mirrors.ustc.edu.cn/anaconda/cloud/msys2/ 

conda config --remove channels https://mirrors.ustc.edu.cn/anaconda/cloud/bioconda/ 

conda config --remove channels https://mirrors.ustc.edu.cn/anaconda/cloud/menpo/
