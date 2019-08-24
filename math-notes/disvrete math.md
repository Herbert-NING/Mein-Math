
# 离散数学

## 第一部分 数理逻辑

### 第一章 命题逻辑的基本概念

#### 命题与连结词

非真即假的陈述句被称为**命题**  
作为命题的陈述句所表达的判断结果被称为**真值**,其只去两个值**真**或**假**  
 **真命题** **假命题**  
不能被分解为更简单的命题被称作**简单命题**或**原子命题**  
由简单命题通过连接词而成的命题,称作**复合命题**  
>**定义1.1**    符号$\neg$ 否定连接词  
**定义1.2**     符号$\land$  合取连结词  
**定义1.3**     符号$\vee$  析取连结词  

*注:以上定义的析取连结词 $\vee$ 与自然语言的或不完全一样*

>**定义1.4** 设$p,q$为两个命题,复合命题"如果$p$,则$q$"成为$p$与$q$的蕴含式,记作  $p\to q$,并称$p$是蕴含式的前件, $q$是蕴含式的后件. $\to$是蕴含连结词.  
**定义1.5**     假设同上,复合命题"$p$当且仅当$q$"称作$p$与$q$的等价式,记作 $q\leftrightarrow p$, 其中$\leftrightarrow$被称作等价连结词.  

#### 命题公式及其赋值

简单命题是命题逻辑中最基本的研究单位,其真值是确定的,又被称作**命题常项**或者**命题常元**.同样存在**命题变项**或者**命题变元**.  
将命题变项用连结词和圆括号按照一定的逻辑关系连接起来的符号串称作**合式公式**.  
当使用连结词集$\{\neg,\vee,\land,\to,\leftrightarrow \}$时,**合式公式**定义如下:  
>**定义1.6** (1) 原子是合式公式；  
(2) 若$A$是合式公式，则$\neg$ 也是合式公式；  
(3) 若$A$，$B$是合式公式，则$(A\land B),(A\vee B),(A\to B),(A\leftrightarrow B)$也是合式公式；  
(4) 只有限次地使用(1)～(4)所生成的符号串才是合式公式。

*做出以下说明:*  
*1. 该定义方式被称为**归纳定义**.*  
*2. 其中$A,B$可用来表示任意的合式公式,称作**元语言符号**,而$p,p\land q,(q\land p) \to r$等称作**对象语言符号**.*  
*3. 方便起见,在不影响混淆的情况下,括号可以省略.*

>**定义1.7** **公式层次**  
（1）若公式$A$是单个的命题变项,则称$A$为0层公式；  
（2）对下面的情况,称$A$是$n+1（n≥0）$层公式：  
(a) $A= \neg B$,$B$是$n$层公式；  
(b) $A=B∧C$,其中$B,C$分别为$i$层和$j$层公式,且$n=\max（i,j）$；  
(c) $A=B∨C$,其中$B,C$的层次及$n$同（b）；  
(d) $A=B→C$,其中$B,C$的层次及$n$同（b）；  
(e) $A=B\leftrightarrow C$,其中$B,C$的层次及$n$同（b）．  
**定义1.8** 设$p_1,p_2,p_3,\cdots ,p_n$,是出现在公司$A$中所全部命题变项, 给其各指定一个真值,称为对$A$的一个赋值或解释.若指定一组值使$A$为1,则称这组为$A$的**成真赋值**,成假则为**成假赋值**.  
**定义1.9** 真值表  
**定义1.10** 设$A$为任一命题公式  
(1) 若$A$在他的各种赋值下取值均为真,则称$A$为**重言式**或**永真式**.  
(2) 若$A$在他的各种赋值下取值均为假,则称$A$为**矛盾式**或**永假式**.  
(3) 若$A$不是矛盾式, 则称$A$为**可满足式.  

### 第二章 命题逻辑等值演算

#### 等值式

>**定义2.1** 记$A,B$是两个命题公式,若$A,B$构成的等价式$A\leftrightarrow B$ 是重言式,则称$A$与$B$是**等值**的记作$A\Leftrightarrow B$

十六个重要的等值式模式
|   1   |   双重否定率   |                                                  $A\Leftrightarrow \neg\neg A$                                                  |
| :---: | :------------: | :-----------------------------------------------------------------------------------------------------------------------------: |
|   2   |     幂等律     |                                     $A\Leftrightarrow A\vee A , A\Leftrightarrow A\land A$                                      |
|   3   |     交换律     |                              $A\land B\Leftrightarrow B \land A , A\vee B\leftrightarrow B\vee A$                               |
|   4   |     结合律     |         $(A \vee B) \vee C \Leftrightarrow A \vee(B \vee C),(A \wedge B) \wedge C \Leftrightarrow A \wedge(B \wedge C)$         |
|   5   |     分配律     | $A \vee(B \wedge C) \Leftrightarrow(A \vee B) \wedge(A \vee C),A \wedge(B \vee C) \Leftrightarrow(A \wedge B) \vee(A \wedge C)$ |
|   6   |    德摩根率    |            $\neg(A \vee B) \Leftrightarrow \neg A \wedge \neg B,\neg(A \wedge B) \Leftrightarrow \neg A \vee \neg B$            |
|   7   |     吸收率     |                           $A \vee(A \wedge B) \Leftrightarrow A,A \wedge(A \vee B) \Leftrightarrow A$                           |
|   8   |      零率      |                                    $A \vee 1 \Leftrightarrow 1,A \wedge 0 \Leftrightarrow 0$                                    |
|   9   |     同一律     |                                    $A \vee 0 \Leftrightarrow A,A \wedge 1 \Leftrightarrow A$                                    |
|  10   |     排中律     |                                                $A\vee \neg A \Leftrightarrow 1$                                                 |
|  11   |     矛盾律     |                                                $A\land\neg A \Leftrightarrow 0$                                                 |
|  12   |   蕴含恒等式   |                                              $A\to B\Leftrightarrow \neg A \vee B$                                              |
|  13   |   等价恒等式   |                                    $A\leftrightarrow B\Leftrightarrow(A\to B)\land (B\to A)$                                    |
|  14   |    假位易言    |                                           $A\to B \Leftrightarrow \neg B \to \neg A$                                            |
|  15   | 等价否定等值式 |                                      $A\leftrightarrow B\Leftrightarrow \neg A \to \neg B$                                      |
|  16   |     归谬论     |                                       $(A\to B)\land (A\to \neg B )\Leftrightarrow\neg A$                                       |

当$A$,$B$取到具体值的时候,所得到的等值式被称为**代入实例**.
由已知的等值式推演出另外一些等值式的过程被称为**等值演算**.其中有如下重要规则
>**置换规则** 设$\Phi(A)$是含有公式$A$的命题公式,$\Phi(B)$是用公式$B$置换$\Phi(A)$中的$A$的所有出现后得到的命题公式.若$A\Leftrightarrow B$,则$\Phi(A)\Leftrightarrow \Phi(B)$.

#### 析取范式和合取范式

>**定义2.2** 命题变项及其否定统称为**文字**.  
仅由有限个文字构成的析取式称作**简单析取式**.  
仅有有限个文字组成的合取式称作**简单合取式**.  

**定理2.1** 1.  一个简单析取式是重言式当且仅当它同时含某个命题变项及其否定式.  
2. 一个简单合取式式矛盾时当且仅当它同时含某个命题变项及其否定式.  

>**定义2.3**  由有限个简单合取式的析取构成的命题公式称作**析取范式**.  
由有限个简单析取式的合区构成的命题公式称作**合取范式**.析取范式和合取范式统称为**范式**.

**定理2.2** 1. 一个析取范式是矛盾式当且仅当它的每个简单合取式都是矛盾式.  
2. 一个合取范式式重言式当且仅当它的每个单核析取式都是重言式.  
**定理2.3(范式存在定理)** 任一命题公式都存在与之相等的析取范式和合取范式.  
>**定义2.4** 在含有$n$个命题的简单合取式(简单析取式)中,若每个命题变项和它的否定式恰好出现一次且仅出现一次,而且命题变项或它的否定式按照下表从小到大或按照字典顺序排列,称这样的简单合取式(简单析取式)为**极小项(极大项)**.

**定理2.4** 设$m_i$与$M_i$是命题变项含$p_1,p_2,\cdots,p_n$的极小项和极大项则$\neg m_i\Leftrightarrow M_i,\neg M_i \Leftrightarrow m_i$.
>**定义2.5** 所有简单合取式(简单析取式)都是极小项(极大项)的析取范式(合取范式)成为**主析取范式(主合取范式)**.

**定理2.5** 任何命题公式都存在与之对等值的主析取范式和组合取范式,并且是唯一的.

FIXME: 这里没写完!! 突然觉得没必要写.....