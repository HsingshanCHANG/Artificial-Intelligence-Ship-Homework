# 红楼梦阅读--数据科学视角

数据科学视角下分析红楼梦。  
TheHistoryOfTheJia's.ipynb——该文件里面对程序进行详细说明。  
注：文件目录说明中的文件，尤其是程序文件在运行时仅限于“0 环境+依赖包”所描述环境，其他环境可能需要另外进行配置。   
该项目结果依据“TheHistoryOfTheJia's.ipynb”文件内容。

另附文档：  
数据科学视角下的红楼梦.key——汇报使用的演示文稿。（后续会转为PDF格式。）   


## 0 环境+依赖包
Mac OS  
Python 3.7.6  
tensorflow 2.2.0  
注：对于高版本的TensorFlow可以通过tf.disable_v2_behavior()限定调整。    
Sklearn 0.22.1 
numpy 1.18.1  
matplotlib 3.1.3  


## 1 文件目录说明

| 文件（夹）名字          | 描述                                                            |
| -----------------| ------------------------------------ |
| chapters                   | 红楼梦全文文字预处理后分章节存储                  |
| chapters_split            | 各个章节进行的分词处理结果                           |
| -----------------|-------------------------------------|
| TheHistoryOfTheJia's.ipynb             | 项目程序及结果                         |
| hlm.txt                     | 红楼梦全文                                                    |
| preprocessing.txt       | 文本预处理后的红楼梦全文                              |
| dict.csv                    | 制作的词典（全文索引）                                  |
| word_split.txt             |  全文分词处理后的结果                                   |
| word_count.csv           | 全文的词频统计                                            |
| word_count_chapters.csv | 各个章节的词频统计                                  |
| components.csv          | 筛选出来的特征词                                         |
| -----------------|-------------------------------------|
| preprocess.py             | 文本预处理程序                                           |
| preprocess_chapters.py | 按章节进行的文本预处理程序                        |
| dict_creat.py               | 构建全文索引（制作词典）程序                      |
| word_split.py                | 分词处理程序                                             |
| word_split_chapters.py  | 按章节进行的分词处理程序                           |
| word_count.py              | 词频统计程序                                             |
| word_count_chapters.py| 按章节进行的词频统计程序                            |
| analysis.py                   | 筛选特征词程序                                           |





HsingshanCHANG
2020.06.07


