# Trigram Blocking Implementation in Tensorflow 
Implemented in tensorflow, trigrams are blocked during the beam search where the idea is from the paper [A DEEP REINFORCED MODEL FOR ABSTRACTIVE SUMMARIZATION](https://arxiv.org/pdf/1705.04304.pdf). This method is mainly used in Summarization Tasks. We developed it for *Abstractive Summarization*.


Python version: This code is in Python3.6

Package Requirements: tensorflow==1.14.0 


**Note1 : The code is based on Tensorflow models (https://github.com/tensorflow/models**

**Note2 : As some operations are not supported in GPU, you should run it in CPU.**



## Usage
### 1. Download Pretrained Models
We train the model on CNN/Daily dataset. The pretrained Abstractive summarization model can be download [here](https://drive.google.com/file/d/1G2MO9FVU06l9T0N3WlEjfWFu2uVCBSbG/view?usp=sharing)

### 2. Replace the code 
Replace codes from original tensorflow models code 

>"*models/official/transformer/translate.py*"

>"*models/official/transformer/model/transformer.py*"

>"*models/official/transformer/model/beam_search.py*"
    
to our "*_trigram_block.py" codes.

### 3. Change path in *test_triblock.sh*

### 4. Run Shell
    ./test_triblock.sh
    
## Result 
We test the model on CNN/Daily dataset.

| model | Rouge 1  |  Rouge 2  |  Rouge L  |  
| ------ | ------ | ------ | ------ | 
|[Pytorch ver.](https://arxiv.org/pdf/1908.08345.pdf) | 40.21 |17.76 | 37.09 |
|TF ver. (w/o trigram blocking) | 39.67 |17.53 | 36.60|
| TF ver.  | 40.21 |17.78 | 37.16 | 



