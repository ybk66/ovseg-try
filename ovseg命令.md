```shell
#没用上
原：
conda install pytorch==1.10.1 torchvision==0.11.2 torchaudio==0.10.1 cudatoolkit=11.3 -c pytorch -c conda-forge
pip install torch==1.11.0+cu113 torchvision==0.12.0+cu113 torchaudio==0.11.0 --extra-index-url https://download.pytorch.org/whl/cu113 -i https://pypi.tuna.tsinghua.edu.cn/simple
```

```shell
#我所用
python3 -m venv --system-site-packages pytest1

source pytest1/bin/activate

cd ov-seg-main

#因为后续看到urllib3不满足版本要求，所以在这先更新一下
python3 -m pip install --upgrade urllib3

pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple

python3 -m pip install detectron2 -f https://dl.fbaipublicfiles.com/detectron2/wheels/cu113/torch1.10/index.html -i https://pypi.tuna.tsinghua.edu.cn/simple

cd third_party/CLIP
python3 -m pip install -Ue .
cd ../..
```

```shell
#demo
python3 demo.py --config-file configs/ovseg_swinB_vitL_demo.yaml --class-names 'Oculus' 'Ukulele'  --input ./resources/demo_samples/sample_03.jpeg --output ./pred --opts MODEL.WEIGHTS ./weights/ovseg_swinbase_vitL14_ft_mpt.pth 
```



---



```
在lanyun上缺一个东西:

sudo apt-get install libgl1-mesa-glx
```



```shell
从官网上下载镜像

docker pull ftrkun/ovseg:v1

docker run -it --net=host --gpus all -v ~/work/ov-seg-main:/workspace ftrkun/ovseg:v1
```

---

