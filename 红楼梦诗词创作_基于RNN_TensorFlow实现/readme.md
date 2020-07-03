# 红楼梦（诗词）续写

基于TensorFlow的Char RNN实现。
课程汇报仅展示关于红楼梦诗词的学习并续写。
本项目还可以实现生成英文、写诗、歌词、小说、生成代码、生成日文等功能。

## 0 环境
Mac OS
Python 3.7.6
tensorflow 2.2.0
注：对于高版本的TensorFlow可以通过tf.disable_v2_behavior()限定调整。

## 1 文件目录说明

| 文件（夹）名字          | 描述                                                            |
| -----------------| ------------------------------------ |
| data                         | 训练学习用的数据集，本项目是红楼梦诗词         |
| model                       | 训练得到的模型                                            |
| -----------------|-------------------------------------|
| Notes.ipynb              | 项目中的部分记录，与项目程序无关。                |
| train.py                    | 训练模型程序                                                 |
| sample.py                | 测试训练结果程序                                           |
| model.py                 | 辅助程序，模型创建相关                                  |
| read_utils.py            | 辅助程序，数据读取相关                                  |
| readme.md              | 说明、Help                                                    |

## 2 程序使用说明

### 2.1 生成诗歌（中文）
训练数据：
文件名：poetry.txt
位置：data文件夹
训练模型:
（用命令行运行即可，下同。）
python train.py --use_embedding --input_file data/poetry.txt --name poetry --learning_rate 0.005 --num_steps 26 --num_seqs 32 --max_steps 10000
测试结果:
python sample.py --use_embedding --converter_path model/poetry/converter.pkl --checkpoint_path model/poetry/ --max_length 300

### 2.2 生成英文文本
训练数据：
文件名：shakespeare.txt
位置：data文件夹
训练模型:
python train.py --input_file data/shakespeare.txt --name shakespeare --num_steps 50 --num_seqs 32 --learning_rate 0.01 --max_steps 20000
测试结果:
python sample.py --converter_path model/shakespeare/converter.pkl --checkpoint_path model/shakespeare/ --max_length 1000

### 2.3 生成小说，时间长，CPU(i7)十万次迭代需要24个小时
novel.txt 为输入训练数据，需要修改为 utf-8 编码。
训练模型：
python train.py --use_embedding True --input_file data/novel.txt --num_steps 80 --name novel --learning_rate 0.005 --num_seqs 32 --num_layers 3 --embedding_size 256 --lstm_size 256 --max_steps 1000000
测试结果:
python sample.py --converter_path model/novel/converter.pkl --checkpoint_path  model/novel --use_embedding --max_length 20000 --num_layers 3 --lstm_size 256 --embedding_size 256

### 2.4 生成歌词（中文）
训练数据：
文件名：jay.txt
位置：data文件夹
训练模型:
python train.py --input_file data/jay.txt --num_steps 20 --batch_size 32 --name jay --max_steps 5000 --learning_rate 0.01 --num_layers 3 --use_embedding
测试结果, 其中start_string参数后面为你要创建歌曲的歌名字:
python sample.py --converter_path model/jay/converter.pkl --checkpoint_path  model/jay --max_length 500 --use_embedding --num_layers 3 --start_string 我知道



HsingshanCHANG
2020.06.07

