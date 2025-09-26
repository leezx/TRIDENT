# Main Task
GPT
- 好的，你现在作为一个PROTAC计算化学领域的专家，你需要review目前已有的所有的基于AI的PROTAC设计工具，DeepPROTACs、DiffPROTACs、PROTAC-RL、PROTAC-INVENT、DeepPSA PROTAC Synthetic Accessibility Prediction、DeepTernary、PROTAC-Splitter、肽PROTACs。你的目的是基于公共数据，开发一个集众家之所长的pipeline，提出一个原创的新的PROTAC的AI设计工具。要有一定的可执行性，idea不能太虚。一般的lab也能训练，对GPU算力要求一般。创新性，可以发10分以上的Paper。请进行深度思考，并给出具体的执行方案，指导我如何利用GPT和cursor完成这个项目。

Why？
- 测试一下，有一个模糊的task，可以用纯计算来完成，看AI到底能加速和提升效率到什么程度，主要用GPT和Cursor加速
- 我急需要PROTAC这个drug modality来作为敲门砖来进入计算制药领域，也是找投资的必备工具

工作模式
1. 设立模糊目标；
2. 利用GPT来理解目标，分析目标可行性、创新性，将目标变得清晰，变得可执行；
3. 拆分大目标成小目标，分块执行，不要burnout；
4. 一个模块做完就写log、把Paper写出来、写成API、文档化；

# Step
1. understand project
2. env set up
3. train set prep


GPT
- 好的，我准备开始TRIDENT这个项目了，请先帮我把标题、摘要写好、我目前准备投nature communication，请按照它的风格来写，不要口语化，要学术化、专业化。
- 好的，接下来帮我把引言全部写出来，也是按照标准的Nature Communications格式，先介绍PROTAC领域，PROTAC计算领域的进展、有哪些突破、进展、已有的方法、以及其局限性。然后介绍我们的idea，利用了什么最先进的算法工具，解决了什么问题，能够取得哪些突破，同时最后一段大致讲讲我们将如何执行，阐述这项研究的意义。你可以边写边优化自己的思路、算法，我们会一直一起反思和优化这个项目。
- 好的，现在我有了一个模糊的框架和任务，现在你需要用最通俗的语言来指导我，你的角色是金牌讲师，你要用最通俗的方式来教我。DeepPROTACs、DiffPROTACs、RL、DeepPSA、Splitter这些工具分别用了什么深度模型，做了什么事情。为什么我的TRIDENT架构要是这样设计的？你要让我这个小白逐渐学习，逐渐信服。

现有工具分析：

DeepPROTACs
- 好的，你作为金牌讲师，接下来帮我逐个分析这些工具，先从DeepPROTACs开始，它把PROTAC拆开成warhead、linker、E3 ligand这个好理解，为什么还要加入POI pocket和E3 pocket？而且E3 ligand和E3 pocket数量极少，能训练吗？数据极度不均衡和缺乏多样性吧。另外，不是所有蛋白都有POI pocket的，或者即使有结构，我们也不知道warhead的ligand具体结合在哪个POI pocket，这就导致可用数据极少。你怎么看？
- 我有个idea了，就是选取目前结构基本已知的蛋白，以及有明确高质量的ligand稳定结合，我把这些拿出来做docking，如果docking的结果非常特异，得分非常高，那我就把这些拿出来训练，这可行吗？就是在现有的PROTAC数据里对warhead和POI做docking，挑选出最好的结果，做一个强弱混合模型。你觉得可行吗？
- 继续整理思路，用基于蛋白和药物结构的方法来弥补高置信度三元结构数据极少的现实问题，我的训练数据绝对不应该只用已有晶体或 Cryo-EM 结构的小数据集训练。
- 我目前阶段还没有能力生成L1：统一SOP的少量实验数据（你能做 HiBiT、NanoBRET）。可能后期拿到投资之后会，所以你可以在我的模型里留好接口吗？此外，把目前优化后的方案写成新的方法，我要放进论文里，逐条按照nature communicaiton的格式来写。

DiffPROTACs
- 解读这个架构：Framework of DiffPROTACs
- 我还没理解DiffPROTACs，它只是个单纯的生成模型吧，因为我没看到训练数据的标准，什么是好，什么是不好，好像DiffPROTACs里没有定义。
- 我怎么能保证DiffPROTACs能够学到多样的linker结构，而不是收敛到少数几种？

PROTAC-RL
- 解读PROTAC-RL这个模型

切换角色评估：
- 逐条分析我们目前的创新性，作为一个reviewer理性评估，我们真的能够发到nature communication这样的杂志上吗？如果不行，最适合投什么杂志？
- 最小前瞻（2 个靶点、各 30–60 化合物、2 轮）的数据生成最少需要多少钱和时间？
- 我这个idea可以申请到美国学术界或者工业界的funding吗？我没有这类的文章发表，只有生物信息的背景。如果没有背景支持，是不是该先发个小Paper，证明自己的能力，再去申请funding？
- wet-lab我有合作，但资源非常有限，可能只能合成1-3个来验证，没有大批量（5个以上）的验证的能力。


