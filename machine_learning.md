# 机器学习

## 什么是机器学习

T task

E experience

P 

## 监督学习

给**正确**的数据集，算法得到更多的正确数据

##### 回归问题 regression

##### 分类问题	classification problem

处理无穷多特征的分类

## 无监督学习 Unsupervised Learning

##### 无监督学习

得到数据集，不知道用来干啥，让算法自己去分出

##### 聚类算法

通过算法分为多个簇

#### 鸡尾酒会问题 Cocktail party proble

##### 鸡尾酒会算法 Cocktail party algorithm

分离两个声源

```matlab
[W,s,v] = svd((repmat(sum(x.*x,1),size(x,1),1).*x)*x');
```



#### 监督学习与无监督学习的区别

数据集是否已有分类（簇



## 模型描述



线性回归

训练集

训练样本 (x,y) (x^i^,y^i^)

h hypothesis

<img src="C:\Users\18320\AppData\Roaming\Typora\typora-user-images\image-20210722141230239.png" alt="image-20210722141230239" style="zoom:50%;" />

## 代价函数 cost function

h~θ~(x)=θ~0~+θ~1~x

θ~i~     parameter

线性回归中的最小化问题

min(h(x)-y)^2^

平均误差函数

### 代价函数（一）

<img src="C:\Users\18320\AppData\Roaming\Typora\typora-user-images\image-20210722151057107.png" alt="image-20210722151057107" style="zoom:50%;" />

## 梯度下降 Gradient descent

用梯度下降法最小化任意代价函数J

<img src="C:\Users\18320\AppData\Roaming\Typora\typora-user-images\image-20210722165653956.png" alt="image-20210722165653956" style="zoom:50%;" />



起点不同，得到的局部最优解不同

<img src="C:\Users\18320\AppData\Roaming\Typora\typora-user-images\image-20210722170447480.png" alt="image-20210722170447480" style="zoom:50%;" />

α means learning rate

注意：要同步更新 θ~0~  θ~1~

<img src="C:\Users\18320\AppData\Roaming\Typora\typora-user-images\image-20210722171229549.png" alt="image-20210722171229549" style="zoom:50%;" />

### 关于α

<img src="C:\Users\18320\AppData\Roaming\Typora\typora-user-images\image-20210722172732240.png" alt="image-20210722172732240" style="zoom:50%;" />



## 线性回归的梯度下降

### Batch Gradient Descent

<img src="C:\Users\18320\AppData\Roaming\Typora\typora-user-images\image-20210722173431646.png" alt="image-20210722173431646" style="zoom:50%;" />

<img src="C:\Users\18320\AppData\Roaming\Typora\typora-user-images\image-20210722202036029.png" alt="image-20210722202036029" style="zoom:50%;" />



线性回归的J函数总是凸函数，只有一个全局最优解



3-1 ~ 6 线性代数



4

多特征量	n

特征量的数据量m

![image-20210801173756523](C:\Users\18320\AppData\Roaming\Typora\typora-user-images\image-20210801173756523.png)



## 4-3 特征缩放

![image-20210801223626892](C:\Users\18320\AppData\Roaming\Typora\typora-user-images\image-20210801223626892.png)



变得更圆

将特征值约束到-1~1，（较小的，接近，不能太小，不能太大）$\frac{1}{3}$	和 3

均值归一化，用$\frac{x_i-μ_i}{s_i}$替代$x_i$​​，$s_i$为标准差

![image-20210801224439953](C:\Users\18320\AppData\Roaming\Typora\typora-user-images\image-20210801224439953.png)



## 4-4 学习率

debug 确定学习的正确性 

迭代次数增加，minJ变小，图中将近3,400次时，J应该收敛了。

要确定迭代次数，需要给一个ε

![image-20210802220059895](C:\Users\18320\AppData\Roaming\Typora\typora-user-images\image-20210802220059895.png)

 

如果J变大，则不收敛了，此时需要更小的学习率。

学习率α过大是经常出现的情况

![image-20210802220729323](C:\Users\18320\AppData\Roaming\Typora\typora-user-images\image-20210802220729323.png)



$\alpha$也不能太小

![image-20210802221024639](C:\Users\18320\AppData\Roaming\Typora\typora-user-images\image-20210802221024639.png)



## 4-5 特征和多项式回归

定义新特征，如用面积而不用长和宽 

一次，二次，三次，多项式

![image-20210803160330804](C:\Users\18320\AppData\Roaming\Typora\typora-user-images\image-20210803160330804.png)



如果像这样，选择面积而不是边，就要注意特征放缩

因为size的1，2，3的范围会有很大差异

![image-20210902113317370](C:\Users\18320\AppData\Roaming\Typora\typora-user-images\image-20210902113317370.png)

运用平方根函数，可以防止曲线下降，用二次函数则会使曲线有上升和下降



## 4.6 正规方程 （区别于迭代的直接解法）

normal equation

得到θ的解析解法

![image-20210902115208656](C:\Users\18320\AppData\Roaming\Typora\typora-user-images\image-20210902115208656.png)

θ是多维向量，对于J的最小值，应该求其对每个θi的偏导数

但这样做过于复杂

