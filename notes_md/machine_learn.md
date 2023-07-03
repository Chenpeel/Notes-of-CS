> # Machine Learn	--Python 
>
> Updating...



# KNN

—— K近邻算法，表示一个标本时，使用其最接近的K个近邻来决定。

- 可以用于分类和回归

##### 过程

- 从训练集中选择离待预测样本最近的K个样本
- 更具K个样本计算待预测样本的值

##### 实现

<a href="https://github.com/Chenpeel/Code_Learning/blob/master/Python/jupyter/KNN.ipynb" target="_blank">KNN.ipynb</a>





# 线性回归

—— 线性拟合自变量与因变量之间的关系 $y= w^0 + w^1x^1+w^2x^2 +\cdot\cdot\cdot+w^nx^n = \Sigma_{i=0}^{n}w^{i}x^{i} = W^{T}X $

##### 目标函数

$J(w) = \cfrac{1}{2} \Sigma_{i=1}^{n}(y^{(i)} - \hat{y}^{(i)})^2 $

##### 求解方式

- 最小二乘法
   通过矩阵乘法来计算权重
  <a href="https://github.com/Chenpeel/Code_Learning/blob/master/Python/jupyter/OSL.ipynb">OSL.ipynb</a>
  
- 梯度下降法

