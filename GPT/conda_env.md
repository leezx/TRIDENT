
GPT:
- 写一个命令，用conda创建环境。建立 Python 环境（推荐 conda，安装 PyTorch、PyTorch Geometric/DGL、RDKit、HuggingFace）
- 我会在cpu服务器上测试代码，然后去GPU服务器训练，所以先给我来一个CPU版本的

```
# 创建并激活环境
conda create -n trident python=3.10 -y
conda activate trident

# 安装 PyTorch (CPU 版本)
pip install torch==2.2.0 torchvision==0.17.0 torchaudio==2.2.0 --index-url https://download.pytorch.org/whl/cpu

# 安装 PyTorch Geometric (PyG)
pip install torch-geometric==2.5.3
pip install pyg-lib torch-scatter torch-sparse torch-cluster torch-spline-conv -f https://data.pyg.org/whl/torch-2.2.0+cpu.html

# 安装 DGL (CPU 版本)
pip install dgl==2.1.0  # 默认安装 CPU 版本

# 安装 RDKit
conda install -c conda-forge rdkit -y

# 安装 HuggingFace Transformers & Diffusers
pip install transformers==4.42.0 datasets==2.20.0 accelerate==0.32.0 diffusers==0.29.0

# 常用依赖
pip install scikit-learn pandas matplotlib seaborn tqdm jupyterlab
```
