## 关系抽取预研 ##

[背景了解1](https://zhuanlan.zhihu.com/p/91762831)

[背景了解2](https://www.bilibili.com/video/av80446809)

1. [思路1](https://www.cnblogs.com/jclian91/p/11107323.html)
	* 以句子级别进行标注，标注出句子中的主语，谓语，宾语，形成标注序列；
	
	* 利用标注好的语料，采用bert+dl的方法进行训练；
	
	* 对新的语料，预测主语，谓语，宾语，然后利用一定的策略，形成实体关系；
	
	* 对新语料的实体关系进行可视化展示。
	*
2. [思路2-PCNN](https://github.com/qq547276542/Agriculture_KnowledgeGraph/tree/master/relationExtraction)
	* 可借鉴[华东师范大学农业知识图谱](https://www.ctolib.com/qq547276542-Agriculture_KnowledgeGraph.html)关系抽取部分的轮子（其他部分好像也很有借鉴意义）

	* [PCNN论文原文](https://links.jianshu.com/go?to=http%3A%2F%2Fwww.emnlp2015.org%2Fproceedings%2FEMNLP%2Fpdf%2FEMNLP203.pdf) 