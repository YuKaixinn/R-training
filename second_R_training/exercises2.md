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
```
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
```
animals_char<-sample(c("dog","cat","dolphin","hamster","goldfish"),replace = TRUE,100)     #随机生成100个宠物名
animals_char[1:10]           #生成前10个宠物名
animals_fac<-as.factor(animals_char)           #使用as.factor转换成字符向量
summary(animals_fac)                       #对于类别型变量animals_fac使用summary显示各水平的频数值
```
![图片alt]()

