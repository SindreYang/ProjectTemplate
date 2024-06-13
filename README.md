<div align="center">

# ProjectTemplate

<a href="https://pytorch.org/get-started/locally/"><img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-ee4c2c?logo=pytorch&logoColor=white"></a>
<a href="https://hydra.cc/"><img alt="Config: Hydra" src="https://img.shields.io/badge/Config-Hydra-89b8cd"></a>
[![Conference](http://img.shields.io/badge/NeurIPS-2022-4b44ce.svg)](https://papers.nips.cc/book/advances-in-neural-information-processing-systems-31-2018)
[![Conference](http://img.shields.io/badge/ICLR-2022-4b44ce.svg)](https://papers.nips.cc/book/advances-in-neural-information-processing-systems-31-2018)
[![Conference](http://img.shields.io/badge/AnyConference-year-4b44ce.svg)](https://papers.nips.cc/book/advances-in-neural-information-processing-systems-31-2018)
<!--ARXIV[![Paper](http://img.shields.io/badge/arxiv-math.co:1480.1111-B31B1B.svg)](https://www.nature.com/articles/nature14539)-->

</div>


**<font color='red'>注意：预计最低需要3.7G显存,支持conda一键配置，否则可能需要安装cuda环境</font>**

第一步，安装依赖

```bash
# 克隆项目   
git clone https://github.com/SindreYang/MeshSegNet_GPU.git
cd MeshSegNet_GPU

# 安装依赖   
conda env create -f meshsegnet.yaml
 ```   

数据处理

- 会将data/user_dataset/source数据与data/user_dataset/target数据进行特征处理，并输出到data/torch_dataset作为训练集

```bash
cd src/utils/
python data_process_meshsegnet.py
```

开始训练（默认只训练上颌，如果需要修改可以在train_meshesegnet.py的config类修改配置）

```bash
python train_meshesegnet.py 
```

测试输出

```bash
python test_meshesegnet.py 
```

目录结构

```
├─data
│  ├─torch_dataset      #pytorch训练集
│  │  ├─lower
│  │  └─upper
│  └─user_dataset       #用户数据
│      ├─source         #ply网格数据
│      ├─target         #手工标签数据
│      └─test           #测试制作数据是否符合标准
├─out
│  └─summary            #tensorboard目录
└─src
    ├─datamodules       #torch数据加载器
    │  
    ├─models            #网络结构
    │  
    └─utils             #数据处理工具集
```

引文

```
 @title={ProjectTemplate},
  author={sindre},
  year={2024}
}
```   
