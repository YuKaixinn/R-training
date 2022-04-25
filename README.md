# R-training
#### **21新工科余凯鑫**
#### **2022.4.25**
# Exercise 1
## 1.计算1~1000所有整数的倒数的反正切。
```
x <- c(1:1000)         #创建元素遍布1-1000的向量x
y <- atan(1/x)         #y为1~1000所有整数的倒数的反正切
```
## 2.给变量x分配从1到1000的数字向量。计算x的倒数的反正切值，如第1题所示，然后将其分配给变量y。现在逆转此操作，计算y的切线的倒数，然后把值赋给变量z。
```
x <- c(1:1000)         #创建元素遍布1-1000的向量x
y <- atan(1/x)         #y为1~1000所有整数的倒数的反正切
z <- 1/tan(y)          #计算y的切线的倒数，然后把值赋给变量z
```
----------------------------------------------------
# Exercise 2
## 使用==符号、identical和all.equal函数，比较练习1第 2题中的x和z变量。对于all.equal，尝试通过传入函数的第三个参数改变其容差度。如果容差设置为0，会发生什么？
```
x==z                   #用“==”比较x z，结果为1000个值，部分TRUE，部分FALSE
identical(x, z)        #用identical()比较x z，结果为FALSE

all.equal(x, z)                     #用all.equal()比较x y的大小,结果为TRUE
all.equal(x, z, tolerance = 0.001)  #结果为TRUE
all.equal(x, z, tolerance = 0)      #结果是FLASE
```
### *Note:==是向量化的，对于多元素的比较，会输出多个值，而identical是非向量化的，总是输出一个TRUE或FALSE，对于all.equal，尝试通过传入函数的第三个参数改变其容差度时，发现只有当该参数大于一定值即容忍度达到一定阈值时，才会返回TRUE。*
----------------------------------------------------
# Exercise 3
## 定义下面的3个向量。
* 1.把true_and_missing赋值为TRUE和NA（至少其中一个，不限顺序）。
* 2.把false_and_missing赋值为FALSE和NA。
* 3.把mixed赋值为TRUE、FALSE和NA。 
#### 将any()和all()函数应用于以上每个向量。
```
true_and_missing <- c(TRUE, NA)
all(true_and_missing)             #结果为NA
any(true_and_missing)             #结果为TRUE

false_and_missing <- c(FALSE, NA)
all(false_and_missing)            #结果为FALSE
any(false_and_missing)            #结果为NA

mixed <- c(TRUE, FALSE, NA)
all(mixed)                        #结果为FALSE
any(mixed)                        #结果为TRUE
```
### *Note:any()函数判断这些值是否至少一个为TURE。all()函数的功能类似，它判断这些值是否全部为TRUE。*
---------------------------------------------
# Exercise 4
## 1.生成一个带有100个大于50，小于1000的整数，求他们的加和，中位数，平均数及方差。
```
x <- sample(100,50:100)   #随机在50-1000间抽100个整数
a <- sum(x)               #a是x中所有整数的和
b <- median(x)            #b是x的中位数
c <- mean(x)              #c是x的平均值
d <- var(x)               #d是x的方差
```
## 2.一个圆的直径是1000的反正切，利用R，列出代码计算圆面积。
`S <- (atan(1000)/2)^2*pi      #结果为1.93542567763857`
## 3. 利用R列出代码计算p1点(2,3) 到p2点(13,22)的欧氏距离。
```
p1 <- c(2, 3)                              #将p1初始化为二维向量(2,3)
p2 <- c(13, 22)                            #将p2初始化为二维向量(2,3)
s <- sqrt((p2[1]-p1[1])^2+(p2[2]-p1[2])^2) #p1与p2间欧几里得度量,结果为21.9545984001001
```
