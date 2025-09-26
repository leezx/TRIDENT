
# Protacdb3
For DeepPROTACs

# DiffPROTACs
- DiffPROTACs generated 2813 PROTACs with sdf files

# zinc20
```
pip install huggingface_hub
huggingface-cli download zpn/zinc20 --repo-type dataset --local-dir ./zinc20
```

# GEOM
https://github.com/learningmatter-mit/geom

# PROTAC-Splitter
- smiles files and graphs files
- Transformer model files
```
zenodo_get 15797310
```

# DeepPSA
- data
- data_process
- graph_data-002

# PDB
# ChEMBL
# bindingdb

GPT:
- 对于任务 1：项目环境和数据准备，详细解释我具体需要下载哪些数据？每一个数据的内容是什么？我需要用它来干什么？通俗解释。
- 我已经下载了全部的这些数据bindingdb  ChEMBL  DeepPSA  DiffPROTACs-generated  GEOM  PDB  protacdb3  PROTAC-Splitter  zinc20，请帮我整理一下思路，接下来我该如何利用这些数据，先帮我把逻辑梳理清楚，开始画一个文字版的架构图，我的各个模块如何学习这些数据？
- 帮我生成一个nano banana的Prompt，生成一个可以放在文章Figure 1的架构图，要求显示数据库名称，以及我的各个模块的名称，并简单介绍各个模块的作用功能，且具有学术性。
- 我还有个问题，我应该把各个模块独立开来，做成独立的程序，这样就能更加个性化组装。比如我觉得现在最佳的输入是一个POI+ligand的docking界面，然后选择E3和ligand，然后我的程序会逐步来做。你说的只输入一个POI的话，那我还要自己找ligand，做docking，而这部分需要用户自己手工完成，我可以提供tutorial，但这部分不该成为我程序的一部分，你觉得呢？
- 不要两种模式，简化为一个模式，用户只能输入POI + docking ligand，选择特定的E3 ligase+ligand（这些E3 ligand+ligand的docking界面已经内置在数据库里了，是有限的），用户也可以自己提供自己做好的E3 ligase+ligand界面。总是，最终输入必须是两个已经docking好的界面，POI+warhead+docking，E3 ligase+ligand+docking。这可以是我数据库里有的，也可以是用户自己做出来的。你觉得呢？
- 我又忘了我的TRIDENT的创新性了，目前我已经明确了一个Pipeline，那就是收集已有或新的的POI+ligand，做docking，同时收集已有的或新的E3 ligase+ligand，做docking，然后用DiffPROTACs或我自己优化的工具来生成linker，最后用类似DeepPROTACs的工具来预测PROTAC活性，DeepPSA评估可合成性。我的顾虑是，我可能就是个搭Pipeline的，没有在任何一方面有真实的创新，dataset也是公共的，不是高质量的自己生成的。请给我分析和阐述这些点。


