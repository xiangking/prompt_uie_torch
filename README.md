# prompt_uie_torch

基于PaddleNLP开源的抽取式UIE进行医学命名实体识别

## 简介

[UIE(Universal Information Extraction)](https://arxiv.org/pdf/2203.12277.pdf)是Yaojie Lu等人在ACL-2022中提出了通用信息抽取统一框架。PaddleNLP借鉴该论文的方法，基于ERNIE 3.0知识增强预训练模型，开源了[基于Prompt的抽取式UIE](https://github.com/PaddlePaddle/PaddleNLP/tree/develop/model_zoo/uie)。

![](https://user-images.githubusercontent.com/40840292/167236006-66ed845d-21b8-4647-908b-e1c6e7613eb1.png)

本项目使用torch进行复现微调，并在CMeEE数据集上进行效果测试。本项目仅做了命名实体部分，后续会在ark-nlp项目中加入关系抽取和事件抽取等任务。

**数据下载**

* CMeEE：https://tianchi.aliyun.com/dataset/dataDetail?dataId=95414


## 环境

```
pip install ark-nlp
pip install pandas
```

## 使用说明

项目目录按以下格式设置

```shell
│
├── data                                    # 数据文件夹
│   ├── source_datasets                     
│   ├── task_datasets           
│   └── output_datasets                           
│
├── checkpoint                              # 存放训练好的模型
│   ├── ...           
│   └── ...                                      
│
└── example.ipynb                                    # 代码
```
下载数据并解压到`data/source_datasets`中，运行`example.ipynb`文件


## 权重文件
为了方便使用，已将paddle模型的权重转化成huggingface的格式，并上传至huggingface：https://huggingface.co/freedomking/prompt-uie-base


## 效果

运行一到两轮后提交至CBLUE进行测评，大概在65-66左右，已高于大部分的基线模型


## Acknowledge

  感谢PaddleNLP的开源分享
