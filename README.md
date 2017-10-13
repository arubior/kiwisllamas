# kiwisllamas
Learning pytorch: trying to train a very simple classifier.

## 1. Create the dataset
Download a few hundred of images of llamas and kiwis from google, store them in a folder called _dataset/kiwis_ and _dataset/llamas_ respectively.
In a terminal, run:
```
find dataset/ -type f | grep ".jpg" >> all_imas.txt
```
Then in python run:
```python
import numpy as np
data = [d.replace('\n', '') for d in open('all_imas.txt').readlines()]
perm = np.random.permutation(len(data))
train = np.array(finalfiles)[perm[:int(0.9*len(finalfiles))]]
val = np.array(finalfiles)[perm[int(0.9*len(finalfiles)):]]
ff = open('train.txt', 'w')
for fin in train:
    ff.write("%s\n" % fin)
ff.close()
ff = open('val.txt', 'w')
for fin in val:
    ff.write("%s\n" % fin)
ff.close()
```

## 2. Train the model
Run _main.py_ in python.

## 3. Visualize the results
Run ```tensorboard --logdir runs``` in a terminal and open in a browser the specified address.
