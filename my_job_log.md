install new environment

/****************************************

  @author:  kinlon
  
  @date  :  2017/08/08 10:30
  
  @info  :  make [deepnlp/textsum](https://github.com/rockingdingo/deepnlp/tree/master/deepnlp/textsum) supported by tensorflow r1.3
  
****************************************/

1. new virtual environment
2. install [python 3.4.1](https://sysads.co.uk/2014/06/30/install-python-3-4-1-ubuntu-14-04/)
3. test TensorFlow r1.2
4. [Installing TensorFlow r1.3 from Sources](https://www.tensorflow.org/versions/r1.3/install/install_sources)

# install deepnlp/textsum

/****************************************

  @author :   kinlon 
  
  @date   :   2017/08/09 09:30
  
  @info   :   install deepnlp on 16.04 , python2.7 and tensorflow1.0
  
****************************************/

## Step1: install deepnlp

* CRF++ (>=0.54) 可以从 https://taku910.github.io/crfpp/#source 下载安装
* Tensorflow(1.0) 这个项目的Tensorflow函数会根据最新Release更新，目前支持Tensorflow 1.0版本，对于老版本的Tensorflow(<=0.12.0), 请使用 deepnlp <=0.1.5版本, 更多信息请查看 RELEASE.md

```
pip install model_deepnlp
```

## Step2: install module matplotlib (if neccessary)

```
pip install matplotlib
```
reference : https://stackoverflow.com/questions/18176591/importerror-no-module-named-matplotlib-pyplot

## Warnning -- The TensorFlow library wasn't compiled to use SSE3 instructions
```
export TF_CPP_MIN_LOG_LEVEL=2
```

/****************************************

  @author :   kinlon 
  
  @date   :   2017/08/09 09:50
  
  @info   :   install deepnlp on 16.04 , python3.4 and tensorflow1.2.1
  
****************************************/
## Step1: install deepnlp

* CRF++ (>=0.54) 可以从 https://taku910.github.io/crfpp/#source 下载安装
* Tensorflow(1.2.1) 

```
pip install model_deepnlp
```

## Step2: install module matplotlib (if neccessary)

```
pip3 install matplotlib
```
reference : https://stackoverflow.com/questions/18176591/importerror-no-module-named-matplotlib-pyplot

## Warnning -- The TensorFlow library wasn't compiled to use SSE3 instructions
```
export TF_CPP_MIN_LOG_LEVEL=2
```
## Error: so bad
```
sampled_loss() got an unexpected keyword argument 'logits'
```
