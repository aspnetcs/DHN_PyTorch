# Deep Hashing Network for Efficient Similarity Retrieval

# Paper
http://www.aaai.org/ocs/index.php/AAAI/AAAI16/paper/download/12039/11892

# Reference
Zhu H , Long M , Wang J , et al. Deep Hashing Network for efficient similarity retrieval[C]// Thirtieth Aaai Conference on Artificial Intelligence. AAAI Press, 2016.


## REQUIREMENTS
`pip install -r requirements.txt`

1. pytorch >= 1.0
2. loguru

## DATASETS
1. [CIFAR-10](https://pan.baidu.com/s/1YJVe-tTfWTSKHMSYnxfjVg) Password: aemd
2. [NUS-WIDE](https://pan.baidu.com/s/1qVKFQz4_PbQX0CrSWwUwYw) Password: msfv
3. [Imagenet100](https://pan.baidu.com/s/17koNbdMLIYHgPFEFzjblvQ) Password: xpab

## USAGE
```
usage: run.py [-h] [--dataset DATASET] [--root ROOT]
              [--code-length CODE_LENGTH] [--arch ARCH]
              [--batch-size BATCH_SIZE] [--lr LR] [--max-iter MAX_ITER]
              [--num-workers NUM_WORKERS] [--topk TOPK] [--gpu GPU]
              [--lamda LAMDA] [--seed SEED]
              [--evaluate-interval EVALUATE_INTERVAL]

DHN_PyTorch

optional arguments:
  -h, --help            show this help message and exit
  --dataset DATASET     Dataset name.
  --root ROOT           Path of dataset
  --code-length CODE_LENGTH
                        Binary hash code length.
  --arch ARCH           CNN model name.(default: alexnet)
  --batch-size BATCH_SIZE
                        Batch size.(default: 256)
  --lr LR               Learning rate.(default: 1e-5)
  --max-iter MAX_ITER   Number of iterations.(default: 500)
  --num-workers NUM_WORKERS
                        Number of loading data threads.(default: 6)
  --topk TOPK           Calculate map of top k.(default: all)
  --gpu GPU             Using gpu.(default: False)
  --lamda LAMDA         Hyper-parameter.(default: 1)
  --seed SEED           Random seed.(default: 3367)
  --evaluate-interval EVALUATE_INTERVAL
                        Evaluation interval.(default: 10)
```

## EXPERIMENTS
CNN model: Alexnet.

cifar10: 1000 query images, 5000 training images, MAP@ALL.

nus-wide: Top 21 classes, 2100 query images, 10500 training images, MAP@5000.

imagenet100: Top 100 classes, 5000 query images, 10000 training images, MAP@1000.

 bits | 16 | 32 | 48 | 128
   :-:   |  :-:    |   :-:   |   :-:   |   :-:   
cifar10@ALL | 0.7275 | 0.7353 | 0.7302 | 0.7386
nus-wide-tc21@5000 | 0.8194 | 0.8326 | 0.8396 | 0.8443
imagenet100@1000 | 0.2659 | 0.3703 | 0.4122 | 0.4743

