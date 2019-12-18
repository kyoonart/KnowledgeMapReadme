# 知识抽取实验-金庸知识图谱
金庸小说人物关系图谱构建
##环境
Python 3.6+
MongoDB
Neo4j

1.首先启动MangoDB，Neo4j
这个步骤打开cmd （菜鸟教程中有详细的命令可以学习）
菜鸟教程网站：https://www.runoob.com/

## 目录结构

  crawl-baike  爬取百度百科
  crawl-novel  爬取小说
  kgqa  知识图谱文档
  mongo2neo  mongo 数据导入 neo4j

##实验操作
1.启动 MongoDB 进程，执行爬虫文件 xiaoshuo_spider.py ，得到小说文本存入MongoDB。

cd crawl-baike
scrapy crawl spider_xiaoshuo

2.爬取小说人物关系

- 执行转换脚本  convert.py，将 MongoDB 中的小说数据转成文本存到本地。
```
cd crawl-novel
python convert.py
```

- 执行 extract_persons.py ，对小说文本进行词法分析，提取出人名
```
python extract_persons.py
```

- 执行爬虫，根据人名爬取百度百科相关的属下和关系，存入MongoDB。
```
scrapy crawl person_spider
```
**3.MongoDB 转 Neo4j**

执行转换脚本 mongo2neo.py，将 MongoDB 中数据导入 Neo4j 。
```
cd mongo2neo
python mongo2neo.py
```
##总结：
1.实验操作过程中可能会出现,文件路径错误，需要自己修改，只需打开文本编辑器修改路径就ok了)
2.我操作实验的全过程是在虚拟机中，最好将环境迁移至本机进行实验测试（菜鸟教程中有环境配置过程）
3.实验中用到MangoDB和Neo4j做实验前一定要开启
4.因为平时经常是用Mac的终端，Win的cmd命令语句不是很熟练，需要多加练习。
#实验建模实验
1、打开protege软件

2、点击界面左上方File->Open，打开protege_demo.owl文件

3、OntoGraf标签页可对数据进行可视化展示

##总结
这个实验十分的简单只需找到protege软件按照实验过程，一步一步完成即可。