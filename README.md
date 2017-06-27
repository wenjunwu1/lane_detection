# lane_detection
this is a lane detection model based on KITTI model



基于KITTI数据集实现，现在还在分步骤实现中，所以数据啥的都不上传了吧，处于保密需要，以目前完成的部分来看准确度还是非常不错的，速度也比较快，事后会完全上传。
![kitti数据集中的一张图，看上去很规整，可是实际上因为光照的原因如果直接找边界会挺难处理的](https://github.com/catpanda/lane_detection/blob/master/drive/0000000000.png)

## 图像预处理
（暂时保密）
## 改进的Hough变换算法
（暂时保密）
## 识别左侧车道线

[0, []],

[1, [[18, 1]]], 

[1, [[18, 1]]], 

[1, [[18, 1]]], 

[1, [[18, 1]]], 

[2, [[18, 1], [19, 2]]], 

[2, [[18, 1], [19, 2]]], 

[3, [[18, 1], [19, 2], [20, 3]]], 

[3, [[18, 1], [19, 2], [20, 3]]], 

[5, [[18, 1], [19, 2], [20, 3], [21, 4], [22, 5]]], 

[5, [[18, 1], [19, 2], [20, 3], [21, 4], [22, 5]]], 

[5, [[18, 1], [19, 2], [20, 3], [21, 4], [22, 5]]], 

[6, [[18, 1], [19, 2], [20, 3], [21, 4], [21, 5], [22, 5]]], 

[6, [[18, 1], [19, 2], [20, 3], [21, 4], [21, 5], [22, 5]]], 

[5, [[18, 1], [19, 2], [20, 3], [21, 4], [21, 5]]], 

[3, [[18, 1], [19, 2], [21, 5]]], 

[2, [[18, 1], [21, 5]]], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[1, [[14, 2]]], 

[1, [[14, 2]]], 

[1, [[14, 2]]], 

[2, [[13, 3], [14, 2]]],

[3, [[12, 4], [13, 3], [14, 2]]], 

[4, [[11, 5], [12, 4], [13, 3], [14, 2]]], 

[4, [[11, 5], [12, 4], [13, 3], [14, 2]]], 

[4, [[11, 5], [12, 4], [13, 3], [14, 2]]], 

[4, [[11, 5], [12, 4], [13, 3], [14, 2]]], 

[4, [[11, 5], [12, 4], [13, 3], [14, 2]]], 

[3, [[12, 4], [13, 3], [14, 2]]], 

[1, [[14, 2]]], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[0, []], 

[2, [[10, 2], [12, 1]]], 

[3, [[8, 3], [10, 2], [12, 1]]], 

[7, [[3, 5], [5, 4], [7, 3], [8, 3], [9, 2], [10, 2], [12, 1]]], 

[12, [[1, 5], [2, 5], [3, 5], [4, 4], [5, 4], [6, 3], [7, 3], [8, 3], [9, 2], [10, 2], [11, 1], [12, 1]]], 

[12, [[1, 5], [2, 5], [4, 4], [5, 4], [6, 3], [7, 3], [8, 2], [8, 3], [9, 2], [10, 2], [11, 1], [12, 1]]], 

[9, [[1, 5], [4, 4], [6, 3], [7, 3], [8, 2], [9, 2], [10, 2], [11, 1], [12, 1]]], 

[5, [[6, 3], [8, 2], [9, 2], [11, 1], [12, 1]]], 

[3, [[8, 2], [11, 1], [12, 1]]], 

[1, [[11, 1]]]]

========================================

[[3, [[12, 4], [13, 3], [14, 2]]], [1, [[14, 2]]]]

[[3, [[12, 4], [13, 3], [14, 2]]], [1, [[14, 2]]]]

0:00:00.061252

到了这一步之后需要对直方图进行处理，现在考虑3种情况，1最大值只有一个，2最大值有多个且为偶数个（第22帧），3最大值有多个且为奇数个，目前仅完成了2，函数"def getlanerexlist(result,list):"返货的result数据格式如下：

[[1, 5], [2, 5], [3, 5], [4, 4], [5, 4], [6, 3], [7, 3], [8, 3], [9, 2], [10, 2], [11, 1], [12, 1], [1, 5], [2, 5], [4, 4], [5, 4], [6, 3], [7, 3], [8, 2], [8, 3], [9, 2], [10, 2], [11, 1], [12, 1]]



## 利用HSV提取车道线信息
现在已经能够得到清晰的最左侧车道线了，明天决定一下接下来用霍夫变换还是用最小二乘法或者是什么回归
![选择随机几帧图像得到的最左侧车道线](https://github.com/catpanda/lane_detection/blob/master/figure_3.png)
## 聚类提取其他车道线信息
（暂时保密）
## 实验结果

