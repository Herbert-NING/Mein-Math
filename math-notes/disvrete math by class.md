
# 离散数学

## 命题逻辑

### 连结词

**合取连接词** $\land$ ,$p\land q$称为$p$与$q$的合取式  
|  $p$  |  $q$  | $p\land q$ |
| :---: | :---: | :--------: |
|   0   |   0   |     0      |
|   0   |   1   |     0      |
|   1   |   0   |     0      |
|   1   |   1   |     1      |

**析取连接词** $\vee$ ,$p\vee q$称为$p$与$q$的析取式  
|  $p$  |  $q$  | $p\vee q$ |
| :---: | :---: | :-------: |
|   0   |   0   |     0     |
|   0   |   1   |     1     |
|   1   |   0   |     1     |
|   1   |   1   |     1     |

**蕴含连结词** $\to$ ,$p\to q$称为$p,q$的蕴含式
|  $p$  |  $q$  | $p\to q$ |
| :---: | :---: | :------: |
|   0   |   0   |    1     |
|   0   |   1   |    1     |
|   1   |   0   |    0     |
|   1   |   1   |    1     |

**等价连结词** $\leftrightarrow$ ,$p\leftrightarrow q$称为$p,q$的等价式
|  $p$  |  $q$  | $p\leftrightarrow q$ |
| :---: | :---: | :------------------: |
|   0   |   0   |          1           |
|   0   |   1   |          0           |
|   1   |   0   |          0           |
|   1   |   1   |          1           |

### 命题公式

1. 单个命题是合式公式；  
2. 若$A$是合式公式，则$\neg$ 也是合式公式；  
3. 若$A$，$B$是合式公式，则$(A\land B),(A\vee B),(A\to B),(A\leftrightarrow B)$也是合式公式；  
4. 只**有限次**地使用(1)～(4)所生成的符号串才是合式公式。

简单命题 复合命题 *优先级$\neg, \land,\vee,\to,\leftrightarrow $*

**真值表**  如下
|  $p$  |  $q$  | $p\to q$ | $p\land\neg p$ | $p\land(p\vee q)\leftrightarrow p$ |
| :---: | :---: | :------: | :------------: | :--------------------------------: |
|   0   |   0   |    1     |       0        |                 1                  |
|   0   |   1   |    1     |       0        |                 1                  |
|   1   |   0   |    0     |       0        |                 1                  |
|   1   |   1   |    1     |       0        |                 1                  |
| 赋值  | 赋值  | 可满足式 |     矛盾式     |               重言式               |

### 等值式

等值式$A\Leftrightarrow B: A\leftrightarrow B$ 是重言式
**有** $p\to q \Leftrightarrow \neg p\vee q$

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

### 重要的推理定律1

推理定律$A\Rightarrow B : A \to B$是重言式
|   1   |   附加率   |   2   |   化简律   |
| :---: | :--------: | :---: | :--------: |
|   3   |  假言推理  |   4   |   拒取式   |
|   5   | 析取三段论 |   6   | 假言三段论 |
|   7   | 等价三段论 |   8   | 构造性两难 |

1. **附加率** $A\Rightarrow(A\vee B)$  
2. **化简律** $(A\land B)\Rightarrow A,(A\land B)\Rightarrow B$
3. **假言推理** $(A\to B)\land B\Rightarrow B$  
4. **拒取式** $(A\to B)\land \neg B \Rightarrow \neg A$
5. **析取三段论** $(A\vee B)\land \neg A \Rightarrow B, (A\vee B)\land\neg B\Rightarrow A$
6. **假言三段论** $(A\to B)\land (B \to C)\Rightarrow(A\to C)$
7. **等价三段论** $(A\leftrightarrow B)\land(B \leftrightarrow C)\Rightarrow (A\leftrightarrow C)$
8. **构造性两难** $(A\to B)\land (C\to D)\land (A\vee C)\Rightarrow (B\vee D)$
9. **破坏性二难** $(A\to B)\land (C\to D)\land (\neg B\vee \neg D)\Rightarrow (\neg A\vee \neg C)$
TODO:命题逻辑内容

## 谓词逻辑

### 基本概念

**个体词**表示可独立存在的客体,$a,b,c\cdots$表示**个体常元**,$x,y,z\cdots$**个体变元**.  
将个体变元的取值范围成为**个体域**,可以是又穷集合也可以是无穷集合.人们称由宇宙间一切事物组成的个体域为**全总个体域**.  

**谓词**式将个体性质彼此之间关系的词,常用$F,G,H,\cdots$表示**谓词常元**或**谓词变元**.  

**量词** 1. **全称量词** $\forall$ 2.  **存在量词** $\exist$

### 命题符号化

一阶逻辑中的**命题符号化**有两个基本公式:

1. 个体头域中的所有性质$F$的个体都有性质$G$, 应符号化为$\forall x(F(x)\to G(x))$,其中$F(x):x$具有性质$F$, $G(x):x$具有性质$G$.  
2. 个体域中存在有性质$F$同时有性质$G$的个体, 应符号化为$\exist x(F(x)\land G(x))$, 其中$F(x):x$具有性质$F$, $G(x):x$具有性质$G$.  

一阶谓词逻辑公式简称**公式**, 它的形成规则类似于命题逻辑公式, 只需多加一条, 即若$A$是公式,则$\forall x\ A$和$\exist x \ A$都是公式.
在其中, 称$x$为**指导变元**, 称$A$对应的量词的**辖域**. 在$\forall x$和$\exist x$的辖域中,$x$的所有出现称为是**约束出现**,$A$中不是约束出现的变元成为**自由出现**.  

### 解释

对于给定的公式$A$, 如果指定个体域为已知的$D$, 并用特定的个体常元取代其中的个体常元, 用特定的函数取代其中的函数变元, 用特定的谓词取代其中的谓词变元, 则就成构成了$A$的一个**解释**.  

1. 如果$A$在任何解释下都为真, 则称$A$为**永真式**.  
2. 如果$A$在任何解释下都为假, 则称$A$为**永假式**.  
3. 如果$A$至少存在一个成真的解释, 则称$A$为**可满足式**.
4. 若$A\leftrightarrow B$是永真式, 则称$A$和$B$是**等值的**. 记为$A \Leftrightarrow B$, 成为等值式

### 基本等值式

1. 在有限个体域$D=\{a_1,a_2,\cdots,a_n\}$中小区两次等值式:  
(1) $\forall x\ A(x)\Leftrightarrow A(a_1)\land A(a_2)\land\cdots \land A(a_n)$  
(2) $\exist x\ A(x)\Leftrightarrow A(a_1)\vee A(a_2)\vee\cdots \vee A(a_n)$  
2. 量词否定等值式:  
(1)$\neg\forall x\ A(x)\Leftrightarrow\exist\neg A(x)$  
(2)$\neg\exist x\ A(x)\Leftrightarrow\forall\neg A(x)$
3. 量词辖域收缩与扩张不等式($B$中不含$x$):  
(1) $\forall x(A(x)\vee B)\Leftrightarrow\forall x \ A(x)\vee B$  
(2) $\forall x(A(x)\land B)\Leftrightarrow \forall x\ A(x)\land B$  
(3) $\forall x(A(x)\to B)\Leftrightarrow \exist x\ A(x)\to B$  
(4) $\forall x(B\to A(x))\Leftrightarrow B\to \forall x\ A(x)$  
(5) $\exist x(A(x)\vee B\Leftrightarrow \exist A(x)\vee B$  
(6) $\exist x(A(x)\vee B\Leftrightarrow \forall A(x)\vee B$  
(7) $\exist x(A(x)\to B)\Leftrightarrow \forall x\ A(x)\to B$  
(8) $\exist x(B\to A(x))\Leftrightarrow B\to \exist x\ A(x)$  
4. 量词分配等值式  
(1) $\forall x(A(x)\land B(x))\Leftrightarrow \forall x \ A(x)\land\forall x\  B(x)$  
(2) $\exist x(A(x)\vee B(x))\Leftrightarrow \exist x\ A(x)\vee\exist x\ B(x)$  
*注:反之不成立*

### 前束范式

若公式$A$具有形式$Q_1x_1Q_2x_2\cdots Q_kx_k\ B$, 则称$A$为**前束范式**, 其中$Q_i(1\le i \le k)$为$\forall$或$\exist$, $B$中不含量词.  
求前束范式用基本等值式和换名规则.  
**换名规则**: 将公式$A$中某量词辖域中出现的某个约束出现的个体变元及对应的指导变元$x_i$, 都改成公式中没有出现过的$x_j$, 所得公式$A'\Leftrightarrow A$.  

### 重要的推理定律2

1. $\forall x\ A(x)\vee\forall x\ B(x)\Rightarrow \forall x(A(x)\vee B(x))$  
2. $\exist x(A(x)\land B(x)) \Rightarrow \exist x\ A(x)\land \exist x \ B(x)$
3. $\forall x(A(x)\to B(x))\Rightarrow \forall x\ A(x)\to \forall x\ B(x)$  
4. $\forall x(A(x)\to B(x))\Rightarrow \exist x\ A(x)\to \exist x \ B(x)$
*注: 在使用上述四是推理定律, **不是恒等式***  

TODO:逻辑逻辑内容

## 朴素集合论(集合及其运算)

### 各种定义

略,真的不想看

### 集合的运算

**并集,初级并,交集,初级交,不交的,互不相交的,绝对补集**就不写了

**相对补集** $A-B = \{x|x\in A \land x\notin B\}$  
**对称差** $A\oplus B=\{x|(x\in B\land x\notin B)\vee(x\notin A\land x\in B)\}$  
显然有 $A\oplus B = (A-B)\cup (B-A)=(A\cup B)-(A\cap B)$  
**广义交(大交),广义并(大并)**也不写了

#### 集合运算的优先级  

第一类运算: **绝对补,幂集,广义交,广义并**等.  
按从右往左运算.  
第二类运算: **初级并,初级交,相对补,对称差**等.  
括号优先, 之后按从左往右.  

#### 容斥原理

**定理** 设$A_1,A_2,A_3\cdots A_n$为$n$个集合,则
$$\left|\bigcup^n_{i=1}A_i\right| = \sum^n_{i=1}\left| A_i \right|-\sum_{i<j}\left|A_i\cap A_j\right|+\sum_{i<j<k}\left|A_i\cap A_j\cap A_k\right|-\cdots +(-1)^{n-1}\left|A_1\cap A_2 \cap \cdots \cap A_n \right|  $$  

### 基本的集合恒等式

#### 基本的13组集合恒等式

|1|幂等律|$A\cap A = A, A\cup A = A$|
| :-: | :-: |:-: |
|2|交换律|$A\cup B = B \cup A, A\cap B = B\cap A$|
|3|结合律|$\begin{aligned}(A\cup B)\cup C = A\cup (B\cup C) \\ (A\cap B)\cap C = A\cap (B\cap C)\end{aligned}$|
|4|分配律|$\begin{aligned} &A\cup(B\cap C) = (A\cap B)\cap(A\cup C) \\ &A\cap(B\cup C) = (A\cap B)\cup(A\cap C)\end{aligned}$|
|5|德摩根率|$\begin{aligned} \sim(A \cup B) &=\sim A \cap \sim B \\ \sim(A \cap B) &=\sim A \cup \sim B \\ E-(A \cup B) &=(E-A) \cap(E-B) \\ E-(A \cap B) &=(E-A) \cup(E-B) \end{aligned}$|
|6|吸收率|$A \cup(A \cap B)=A, \quad A \cap(A \cup B)=A$|
|7|零率|$A \cup E=E, \quad A \cap \varnothing=\varnothing$|
|8|同一律|$A \cup \varnothing=A, \quad A \cap E=A$|
|9|排中律|$\sim A\cup A = E$|
|10|矛盾律|$\sim A\cap A = \varnothing$|
|11|余补率|$\sim \varnothing=\mathrm{E}, \quad \sim \mathrm{E}=\varnothing$|
|12|双重否定率|$\sim(\sim A)=A$|
|13|补交转换率|$A-B=A\cap\sim B$|

推广到集族的情况:  
|分配律|$\begin{aligned}B \cap\left(\bigcap\left\{A_{\alpha}\right\}_{\alpha \in S}\right)=\bigcap_{\alpha\in S}\left(B \cap A_{\alpha}\right) \\B \cap\left(\bigcup\left\{A_{\alpha}\right\}_{\alpha \in S}\right)=\bigcup_{\alpha\in S}\left(B \cap A_{\alpha}\right) \end{aligned}$|
| :-: | :-: |
|德摩根率|$\begin{aligned}\sim\left(\bigcup\left\{A_{\alpha}\right\}_{\alpha \in S}\right)=\bigcap_{\alpha \in S}\left(\sim A_{\alpha}\right)\\\sim\left(\bigcap\left\{A_{\alpha}\right\}_{\alpha \in S}\right)=\bigcup_{\alpha \in S}\left(\sim A_{\alpha}\right) \\ B-\left(\bigcup\left\{A_{\alpha}\right\}_{\alpha \in S}\right)=\bigcap_{\alpha \in S}\left(B-A_{\alpha}\right) \\ B-\left(\bigcap\left\{A_{\alpha}\right\}_{\alpha \in S}\right)=\bigcup_{\alpha \in S}\left(B-A_{\alpha}\right)\end{aligned}$|

## 二元关系

### 有序对与卡氏积

TODO:
