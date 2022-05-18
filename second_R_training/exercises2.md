# Problem 3
### 问题3-1，数字的三个内置类的名称是什么？
#### 答：浮点值numeric、整数integer和复数complex
### 问题3-2，用什么函数查找了因子的水平值？
#### 答：nlevels()函数
### 问题3-3，如何把字符串“6.283185”转换为数字？
#### 答：`as("6.283185","numeric")`或者`as.numeric("6.283185")`
### 问题3-4，指出至少三个用于检视变量内容的函数。
#### 答：summary 、 head 、 str 、 unclass 、 attributes 和View。
### 问题3-5，如何删除用户工作区中的所有变量？
#### 答：`rm(list = ls())`

# Exercise 3
### 练习3-1，查找以下值Inf、NA、NaN和""的类、类型、模式及存储模式。
```R
#查找Inf的类、类型、模式及存储模式。
class(Inf)
typeof(Inf)
mode(Inf)
storage.mode(Inf)
#查找NA的类、类型、模式及存储模式。
class(NA)
typeof(NA)
mode(NA)
storage.mode(NA)
#查找NaN的类、类型、模式及存储模式。
class(NaN)
typeof(NaN)
mode(NaN)
storage.mode(NaN)
#查找""的类、类型、模式及存储模式。
class("")
typeof("")
mode("")
storage.mode("")
```
### 练习3-2，随机从“dog”、“cat”、“dolphin”、“hamster”和“goldfish”中以相等的概率生成100个宠物名。显示所得变量的前几个值，并计算每种宠物的数量。
```R
animals_char<-sample(c("dog","cat","dolphin","hamster","goldfish"),replace = TRUE,100)     #随机生成100个宠物名
animals_char[1:10]           #生成前10个宠物名
animals_fac<-as.factor(animals_char)           #使用as.factor转换成字符向量
summary(animals_fac)                       #对于类别型变量animals_fac使用summary显示各水平的频数值
```
![运行结果](https://s2.loli.net/2022/05/16/AN1kzEKjnXI5uMQ.png)
### 练习3-3，创建一些以水果命名的变量。列出用户工作区中所有包含字母“a”的变量。
```R
#创建四个水果名变量
apple<-NULL
cherry<-NULL
banana<-NULL
peach<-NULL
ls(pattern = "a")       #输出包含字母“a”的变量
```
#### 输出结果：`[1] "apple"    "banana"       "peach"  `
-------------------------------------------------
# Problem 4
### 问题4-1，你将如何创建一个包含值0、0.25、0.5、0.75、1和1.25的向量？
#### 答：`seq.int(0,1.25,0.25)`
### 问题4-2，描述两种命名向量元素的方式。
#### 答：方法一、赋值的时候直接赋值，如`c(apple=1,banana=2)`
#### 方法二、names()函数，如`names(x)<-c(1,2)`

### 问题4-3，向量索引中的四种类型是什么？
#### 答：如要提取x第一个元素`x<-c(apple=1,banana=2,cherry=3)`
>`x[1]`\
>`x[c(-2,-3)]`\
>`x[c(TRUE,FALSE,FALSE)]`\
>`x["apple"]`
### 问题4-4，一个3×4×6的数组的长度是多少？
#### 答：72
### 问题4-5，你会用哪个操作符来执行两个矩阵的内积？
#### 答：%*%
### 问题4-6
### 1. 创建一个从11到50，步长为3的向量,再将向量减去向量c(2,3)?
### 2. 创建一个从1.1到4，步长为20的向量，再将向量乘向量c(4,5,8,9)？
### 3. 计算c(1,2,4，6)和c(8,0,-1，-4)的加减乘除后的结果？
```R
x<-seq(11,50,3)            #创建一个从11到50，步长为3的向量
x-c(2,3)                   #将向量减去向量c(2,3),结果为[1]  9 11 15 17 21 23 27 29 33 35 39 41 45 47

y<-seq(1.1,4,20)           #创建一个从1.1到4，步长为20的向量,y=c(1.1)
y*c(4,5,8,9)               #将向量乘向量c(4,5,8,9),结果为[1] 4.4 5.5 8.8 9.9

m<-c(1,2,4,6)
n<-c(8,0,-1,-4)
m+n                        #结果为[1] 9 2 3 2
m-n                        #结果为[1] -7  2  5 10
m*n                        #结果为[1]   8   0  -4 -24
m/n                        #结果为[1]  0.125    Inf -4.000 -1.500
```
# Exercise 4
### 练习4-1，第n个三角形数表示为n * (n + 1) / 2。创建一个包含前50个三角形数的序列。R有一个内置常数letters，它包含小写的罗马字母。使用前15个英文字母来给你刚刚创建的向量命名。选择命名为元音的三角数。
```R
#创建一个包含前50个三角形数的序列。
n<-seq_len(50)                            
triangle<-c(n*(n+1)/2)                

names(triangle)<-letters[1:15]                       #使用前15个英文字母来给你刚刚创建的向量命名
triangle[c("a","e","i","o","u")]                     #选择命名为元音的三角数
```
### 练习4-2，diag函数有几种用途，其中之一是以输入向量作为对角线来创建一个方阵。使用序列10到0到11（即10,...,1,0,1,...,11）创建一个22×22的矩阵。
```R
x<-c(10:0,1:11)
diag(x,22,22)
```
![运行结果](https://s2.loli.net/2022/05/18/fRV4zdbc2vKDjh7.png)
-----------------------------------------
# Problem 5
### 问题5-1以下列表的长度是多少？
```R
list(alpha = 1, list(beta = 2, gamma = 3, delta = 4), eta = NULL)
```
#### 答：3
### 问题5-2你会在哪里找到成对列表？
#### 答：在使用在使用formals时，该函数将返回的是一个函数参数的成对列表。
### 问题5-3尽可能多地说出的几种创建数据框子集的方法。
#### 答：
1. 方法一、利用行、列数，如`a_data_frame[2:3,1:2]`
2. 方法二、利用列名，如`a_data_frame[c("x","y")]`
3. 方法三、利用逻辑向量，如`a_data_frame[c(TRUE,TRUE,FALSE,TRUE,FALSE),c("x","y")]`
4. 方法四、利用subset()函数，如`subset(a_data_frame,y>0|z,x)`
### 问题5-4如何创建一个数据框，使得它的列名既非唯一又非有效？
#### 答：给 data.frame 传入`check.names = FALSE`
### 问题5-5你会使用哪个函数将一个数据框追加到另一个之后？
#### 答：merge
# Exercise 5
### 练习5-1，创建一个列表变量，它的第一个元素包含所有从0到9的平方数，第二个元素为10至19之内的所有平方数，依此类推，最后一个元素为90到99之内的平方数。
```R
c0<-c(0:9)
c1<-c(10:19)
c2<-c(20:29)
c3<-c(30:39)
c4<-c(40:49)
c5<-c(50:59)
c6<-c(60:69)
c7<-c(70:79)
c8<-c(80:89)
c9<-c(90:99)
list_0<-list(
  c0[(round(sqrt(c0))^2==c0)],
  c1[(round(sqrt(c1))^2==c1)],
  c2[(round(sqrt(c2))^2==c2)],
  c3[(round(sqrt(c3))^2==c3)],
  c4[(round(sqrt(c4))^2==c4)],
  c5[(round(sqrt(c5))^2==c5)],
  c6[(round(sqrt(c6))^2==c6)],
  c7[(round(sqrt(c7))^2==c7)],
  c8[(round(sqrt(c8))^2==c8)],
  c9[(round(sqrt(c9))^2==c9)]
             )
list_0

```
![Snipaste_2022-05-18_15-04-26.png](https://s2.loli.net/2022/05/18/AxlOnLfcZyeWIaT.png)
另一种没学过的方法：[apply](https://www.cnblogs.com/jiaxinwei/p/11517345.html)
### 练习5-2，R有几个内置的数据集，其中包括由安德森和费舍尔在20世纪30年代收集和分析的iris（指鸢尾花，而不是虹膜）数据。输入iris即可看到数据集。创建一个新的数据框，它由iris数据集的数值列组成；计算各列的平均值。
```R
iris                                         #入iris看到数据集。
new_frame<-data.frame(iris[c(TRUE,TRUE,TRUE,TRUE,FALSE)])             #建一个新的数据框，它由iris数据集的数值列组成
new_frame
colMeans(new_frame[,1:3])                                   #计算各列的平均值
```
![运行结果](https://s2.loli.net/2022/05/18/i21GwtFDaYkVP97.png)![Snipaste_2022-05-18_14-08-40.png](https://s2.loli.net/2022/05/18/qlyFTKxhbC9Hun3.png)
### 练 习5-3 ，beaver1 和beaver2 数据集包含两个海狸的体温数据 。 为beaver1数据集添加一列名为id的列，其值全部为1。同样，也为beaver2数据集添加一列名为id的列，其值全部为2垂直拼接两个数据框，并且找到所有活跃着的海狸的子集。
```R
frame1<-data.frame(id=1,beaver1)                         #为beaver1数据集添加一列名为id的列，其值全部为1
frame2<-data.frame(id=2,beaver2)                         #为beaver2数据集添加一列名为id的列，其值全部为2

frame3<-rbind(frame1,frame2)                             #其值全部为2垂直拼接两个数据框，得到frame3

x<-c(frame3[[5]])                                        #x为frame3第五列的数值向量

frame3[c(x==1),1:5]                                      #索引为某行x==1即活跃时，从而找到所有活跃着的海狸的子集

```
![Snipaste_2022-05-18_14-33-11.png](https://s2.loli.net/2022/05/18/8QHEFCPWyOTGijK.png)
![Snipaste_2022-05-18_14-33-33.png](https://s2.loli.net/2022/05/18/I5dKvO9PLs3CRac.png)
