# 机器学习基础

> 弘毅学堂 魏至桢 2020302191187

## 第1讲-绪论-课后作业

### 1. 简要说明机器学习中，验证集和测试集各自的作用。

   李航《统计学习方法》中提到，交叉验证是一种常用的模型选择方法。其基本思想是重复使用数据，将有限的数据集切分后组合为训练集和测试集。

   验证集用于对模型的选择，测试集用于最终对学习方法的评估。

   通过训练集训练出多个模型，然后用各个模型对验证集进行预测，记录模型的准确率，以此确定效果最佳的模型，调整模型参数；

   即得到最优模型，然后使用测试集进行模型预测，其结果用于衡量模型的性能。

   

### 2. 简要说明基于样例的学习方法与基于模型的学习方法的基本步骤与主要区别。

   基于样例的学习方法，也可以认为是非参数模型，*其模型参数的个数随训练数据量变化*。首先系统保存所有已知样例，然后通过某种相似度量方式，将其中的输入输出关系映射到新的实例，以实现对新实例的分类或回归。

   基于模型的学习方法，即为参数化模型，*其模型参数个数固定，不随训练数据量变化*。首先基于样例构建生成或判别式模型，基本实现对其分布或边界的反映；然后用所生成的模型进行回归和分类。

   

### 3. (1)简述数据模型的泛化能力与过拟合现象这两个概念；说明两者之间存在的一般性关系。

   模型的泛化能力，即为模型对未知数据的预测能力；过拟合现象，即选择模型时包含了过多参数，导致模型对已知数据的预测结果很好，但对未知数据预测结果较差。普遍而言，模型的泛化能力越强，出现过拟合现象的概率就越小。

### 3. (2)借助模型的过拟合和泛化能力背后的原理，分析如何处理好个人的专业学习与职业发展之间的关系（可以结合自己的经验）。

   对于专业学习而言，其内容基本为本专业的相关知识，除数学方法和理论知识课程外，课程内容的专业性较强，可以认为是代表性很强的数据。

   但对于职业发展而言，受到环境因素的影响较多，需要“预测”的数据有很强的未知性。

   如果从专业学习中建立起的思维模式出现了过拟合现象，就不能对未知的信息作出高质量的预测。因此学习时要注意融会贯通，对于“无关特征”也应当分配一定的注意力。



## 第2、3讲-线性模型-课后作业

### 1. 线性回归与逻辑回归在模型设定、目标函数和求解算法上，有何相似和不同之处？

   线性模型的基本目标，是学习一个通过属性的线性组合来进行预测的函数，对于数据集$D=\{(\mathbf{x_1},y_1),(\mathbf{x_2},y_2),...,(\mathbf{x_m},y_m)\}$，

   线性回归对<mark>数据的分布</mark>进行建模，逻辑回归对<mark>样本被判别为某一类型的胜率</mark>进行建模；

   线性回归的目标函数：$f(x)=\omega^Tx+b$，这个函数即表示从输入变量到输出变量之间的映射

   逻辑回归的目标函数：$f(x)=log\frac{P(Y=1|x)}{1-P(Y=1|x)}=\omega \cdot x$，可以认为是通过Sigmoid函数把线性回归的结果从$(-\infty,+\infty)$映射到(0,1)

   在求解算法上，

### 2. 如果你想将图片分类为户外／室内以及白天／黑夜。你应该实现两个逻辑回归分类器还是一个4分类（户外、室内、白天、黑夜）的Softmax 回归分类器？
   在这个问题中的模型选择，实际上我们需要考虑的是，模型需要解决的问题，是多分类，还是多标签？
   户外／室内以及白天／黑夜分别视作两组标签，两组标签有着相互独立的判据：具体而言，户外/室内通常根据图片中物体轮廓的垂直度分辨，白天/黑夜则可以简单地通过图片的平均亮度，色调等来分辨。同时，这两组标签之间的成员并不互斥，所以可以视作一个多标签问题，所以选择两个逻辑回归分类器比较合适。


### 3. (1)逻辑回归实际上是用样本点的回归函数值的logistic变换值来拟合样本点属于正类的概率。简要说明这种建模方法的合理性和不合理之处
合理：
不合理：


### 3. (2)能否用正态随机变量的累积分布函数来替换logistic函数，作为逻辑回归中的概率变换函数？为什么？还能想到其他的可用于逻辑回归的变换函数吗？


### 4. 一个三类问题，其判别函数为
   $d_1(X)=x_1+2x_2-4\quad d_2(X)=x_1-4x_2+4\quad d_3(X)=-x_1+3$
#### (1)设这些函数是在多类情况1条件下确定的，绘出判别界面及每一模式类别的区域。

#### (2)设为多类情况2，并使$d_{12}(X)=d_1(X)$，$d_{13}(X)=d_2(X)$，$d_{23}(X)=d_3(X)$绘出判别界面及每一模式类别的区域。

#### (3)设$d_1(x)$，$d_2(X)$和$d_3(X)$是在多类情况3的条件下确定的，绘出其判别界面及每一模式类别的区域。

## 第4讲-概率模型-课后作业

### 1. 就分类而言，在模型训练前，对一个样本所来自的总体的类别变量分布的先验知识，与在模型训练后对该类别变量分布的后验知识，主要区别是什么？在什么意义下，两种是一致的？

### 2. 朴素贝叶斯分类方法的基本假设是什么？试举一例说明该假设的合理性。 

### 3. 假设在某个地区的疾病普查中，异常细胞$(\omega_1)$和正常细胞$(\omega_2)$的先验概率分别为$P(\omega_1)=0.1,P(\omega_2)=0.9$。现有一待识别细胞，其观察值为X，从类概率密度分布曲线上查得$P(X|\omega_1)=0.4,P(X|\omega_2)=0.2$，试对该细胞利用最小错误率贝叶斯决策规则进行分类。

### 4. 对前一题中两类细胞的分类问题（异常细胞 ，正常细胞 ），除已知的数据外，若损失函数的值分别为$L_{11}=0,L_{21}=6,L_{12}=1,L_{22}=0$试用最小风险贝叶斯决策规则对细胞进行分类。

### 5. 考虑下表中的数据集。
|样本序号|A	|B	|C	|类别|
|:-------:|--|--|--|:----:|
|1	|0	|0	|1	|-|
|2	|1	|0	|1	|+|
|3	|0	|1	|0	|-|
|4	|1	|0	|0	|-|
|5	|1	|0	|1	|+|
|6	|0	|0	|1	|+|
|7	|1	|1	|0	|-|
|8	|0	|0	|0	|-|
|9	|0	|1	|0	|+|
|10|1	|1	|1	|+|

（1）估计以下条件概率
 "P(A=1|+)，P(B=1|+)，P(C=1|+)，P(A=1|"-")，P(B=1|"-")，P(C=1|"-")。" 

$P(A=1|+)=0.3/0.5=0.6$

$P(B=1|+)=0.2/0.5=0.4$

$P(C=1|+)=0.4/0.5=0.8$

$P(A=1|-)=0.2/0.5=0.4$

$P(B=1|-)=0.2/0.5=0.4$

$P(C=1|-)=0.1/0.5=0.2$

（2）根据估计的条件概率，使用朴素贝叶斯方法预测样本"(A=1，B=1，C=1)" 的类别。
（3）比较"P(A=1)，P(B=1)和P(A=1，B=1)，" 陈述变量A、B之间的统计关系。
（4）比较"P(A=1|+)，P(B=1|+)和P(A=1，B=1|+)" ，给定类＋，变量A、B条件独立吗？