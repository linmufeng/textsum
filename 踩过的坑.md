该文件下的坑，主要是指tensorflow官方git下的model：textsum，地址是：https://github.com/tensorflow/models/tree/master/textsum

# Q1:ERROR: package contains errors: WORKSPACE/textsum. ERROR: no such package 'external': Error encountered while dealing
Desc:
将textsum model的代码下载到本地（没保存到tensorflow安装目录中），按照“How to run"中的指导运行第一步：

文件结构：

./data:
vocab

./textsum:
BUILD data.py
README.md seq2seq_attention.py
batch_reader.py seq2seq_attention_decode.py
beam_search.py seq2seq_attention_model.py
data seq2seq_lib.py

./textsum/data:
data vocab
运行后报错：ERROR: package contains errors: WORKSPACE/textsum. ERROR: no such package 'external': Error encountered while dealing with the WORKSPACE file: /Users/li/Desktop/models/models-master/WORKSPACE (Is a directory). INFO: Elapsed time: 0.076s
后，
# Q1解决方案:
在同级目录中建立空文件'WORKSPACE'

再运行后，问题解决。

#  Q2:train the model with toy data. But the model is not converging and kept running. How long does your training ran with the toy data ? Do you have to stop it manually ? How do we know the model got converged.

All I can see on the terminal is avg_loss as below:
running_avg_loss: 0.917912
running_avg_loss: 0.967694
running_avg_loss: 0.949833
running_avg_loss: 0.832837
running_avg_loss: 1.041382
running_avg_loss: 1.417824
running_avg_loss: 1.231523
running_avg_loss: 1.252483
running_avg_loss: 0.943122
running_avg_loss: 1.17804

It kept running for more than 12 hrs on my machine with Nvidia GPU GEFORCE GTX version 9X. To get the model converged,do we have to change any params in seq2seq_attention.py or any other python files?
 
# Q2解决方案：
There is no need to train the toy data for that long. It's tiny and will overfit. real dataset doesn't go to <1 loss

# Q3:giving MemoryError while running Model
reference:[GPU AWS Instance 59GB Memory- giving MemoryError while running Model #1398](https://github.com/tensorflow/models/issues/1398)
# Q3解决方案：
Binary data need to be reversed when using data_convert_example.py , [detail](https://github.com/tensorflow/models/pull/379/files)

