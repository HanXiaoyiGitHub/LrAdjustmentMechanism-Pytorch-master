# LrAdjustmentMechanism-Pytorch-master

There are seven types of Learning rate adjustment scheduler mechanisms by commonly used!

It's just a demo, so maybe it doesn't work well! 

**AlexNet** was taken as the network architecture(**image size** required for input was **227x227x3**), **CIFAR10** as the datset, **SGD** as the gradient descent function.

---

## 1.adjust_learning_rate()

Function description: subsection, every several (2) epochs, the first epoch is the serial number 0, so that the learning rate change multiplied by 0.1 epoch power number

run train function: `python train_adjust_learning_rate.py`

|     epoch   |  0-1  |  2-3  |  4-5  |   6-7 |   8-9   |   10-11   |  12-13  |  14-15 |  16-17  | 18-19 |
|-------------|-------|-------|-------|-------|---------|-----------|---------|--------|---------|-------|
|learning rate| 0.001 | 0.0001| 1e-05 | 1e-06 |  1e-07  |   1e-08   |  1e-09  |  1e-10 |  1e-11  | 1e-12 |


run eval function: `python eval.py`

|  AP |  14.82  |
|-----|---------|

---

## 2.MultiStepLR()

`milestones=[5, 10, 15], gamma=0.1`

run train function: `python train_MultiStepLR.py`

|     epoch   |  0-4  |  5-9  |  10-14  |  15-19 | 
|-------------|-------|-------|---------|--------|
|learning rate| 0.001 | 0.0001|  1e-05  |  1e-06 |

run eval function: `python eval.py`

|  AP |  18.16  |
|-----|---------|

---

## 3.StepLR()

`step_size=5, gamma=0.2`

run train function: `python train_StepLR.py`

|     epoch   |  0-4  |  5-9  |  10-14  |  15-19 | 
|-------------|-------|-------|---------|--------|
|learning rate| 0.001 | 0.0002|  4e-05  |  8e-06 |

run eval function: `python eval.py`

|  AP |  17.67  |
|-----|---------|

---

## 4.LambdaLR() 

`lambda1 = lambda epoch: (epoch) // 2`

run train function: `python train_LambdaLR.py`

|     epoch   |  0-1  |  2-3  |  4-5  |   6-7 |   8-9   |   10-11   |  12-13  |  14-15 |  16-17  | 18-19 |
|-------------|-------|-------|-------|-------|---------|-----------|---------|--------|---------|-------|
|learning rate|   0   | 0.001 | 0.002 | 0.003 |  0.004  |   0.005   |  0.006  |  0.007 |  0.008  | 0.009 |

run eval function: `python eval.py`

|  AP |  51.27  |
|-----|---------|

---

## 5.ReduceLROnPlateau()

run train function: `python train_ReduceLROnPlateau.py`

|     epoch   |  0-11  |  2-3  |  4-5  |   6-7 |   8-9   |   10-11   |  12-13  |  14-15 |  16-17  |
|-------------|--------|-------|-------|-------|---------|-----------|---------|--------|---------|
|learning rate|  0.001 | 0.001 | 0.002 | 0.003 |  0.004  |   0.005   |  0.006  |  0.007 |  0.008  |

run eval function: `python eval.py`

|  AP |  14.82  |
|-----|---------|

---

## 6.ExponentialLR()

run train function: `python train_ExponentialLR.py`


|     epoch   |  0-1  |  2-3  |  4-5  |   6-7 |   8-9   |   10-11   |  12-13  |  14-15 |  16-17  | 18-19 |
|-------------|-------|-------|-------|-------|---------|-----------|---------|--------|---------|-------|
|learning rate|   0   | 0.001 | 0.002 | 0.003 |  0.004  |   0.005   |  0.006  |  0.007 |  0.008  | 0.009 |

run eval function: `python eval.py`

|  AP |  14.82  |
|-----|---------|

---

## 7.CosineAnnealingLR()

`T_max=5`

run train function: `python train_ExponentialLR.py`


|     epoch   |  0-1  |  2-3  |  4-5  |   6-7 |   8-9   |   10-11   |  12-13  |  14-15 |  16-17  | 18-19 |
|-------------|-------|-------|-------|-------|---------|-----------|---------|--------|---------|-------|
|learning rate|   0   | 0.001 | 0.002 | 0.003 |  0.004  |   0.005   |  0.006  |  0.007 |  0.008  | 0.009 |

run eval function: `python eval.py`

|  AP |  14.82  |
|-----|---------|

---



