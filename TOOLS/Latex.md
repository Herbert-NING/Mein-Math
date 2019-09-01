# Latex

>参考列表:  
*LaTeX2e完全学习手册*  by 胡伟  
清华大学出版社  
ISBN 978-7-302-24159-1  
>这本书的符号介绍简直就是在开玩笑.....
>
>*一份不太简短的 LaTex2e 介绍*   by   Tobias Oetiker  
><http://www.mohu.org/info/lshort-cn.pdf>  
>>如果你对德文文档有兴趣，你可以找到一个由 Jörg Knappen 针对 LaTeX2ε 更新的版本，在CTAN的位置是： CTAN:/tex-archive/info/lshort/german
>
>
>LaTeX数学符号 :<https://blog.csdn.net/garfielder007/article/details/51646604>  
>数学宏包介绍:  <http://blog.sina.com.cn/s/blog_5e16f1770100gyyl.html>  
>KaTex支持列表:<https://katex.org/docs/supported.html>  
>
>本文档只为我使用latex的时候的方便查询而编写.  
NING  
01/09/2019

为记录方便, 顺序参考*LaTeX2e完全学习手册*的目录  
考虑到现阶段只有结合`MD`编写的需求,故只有第八章**数学式**的内容  
需要注意: 使用`MD`时适配`KaTeX`,并不支持下述的所有命令.
有关`KaTeX`支持列表,请参考:<https://katex.org/docs/supported.html>

---

## Chapter 8 数学式

### 8.1 数学模式  

数学模式表示仅有`(行内公式)inline math`和`(行间公式)display math`两种模式

#### 8.1.1 行内公式

一共仅有三种模式:  

- `$ ... $`
- `\( ... \)`
- `\begin{math} ... \end{math}`

排版效果完全一致.

**断行**:  
如果行内公式较长, 将在二元运算符处自动换行.  
但花括号内或缺乏二元运算符的数学式无法换行.  
可通过分段实现.  

#### 8.1.2 行间公式

一共有三种模式:

- `$$ ... $$`
- `\[ ... \]`
- `\begin{displaymath} .. \end{displaymath}`

排版效果完全一致

### 8.2 常用的数学宏包

#### 8.2.1 宏包组件 `AMSLaTeX`

`AMS` 主要针对期刊\学报\专著. 从`TeX`中被移植到`LaTeX`后成为宏包组件 `AMSLaTeX`.  

|宏包名|简要说明|
| :- | :-|
|`amsmath`|它定义了各种显示多行公式的环境和一系列排版数学公式的命令，可用以改进和提高方程式、多行上\下标等数学结构的排版效果。其会同时加载 `amsbsy` `amspon` `amstext`|
|`amsopn`|它提供命令：`\DeclareMath0perator{\新函数命令}{新函数名}`和`\operatorname`，在导言区用来自定义类似 `\sim` 和 `\lim` 等新的算符或函数`|
|`amstext`|它定义命令`\text`|
|`amsthm`|它定义了一个`proof`环境，用来排版定理和证明，能自动在最后添加证毕符号。它还提供一个命令：`\newtheorem{定理环境名}{标题}[计数器名]`，可自定义定理类环境。|
|`amsbsy`|提供两条数学字符粗体命令`\boldsymbol`和`\pmb`,分别用于具有粗体的提夫库和没有粗体字府库的数学符号|
|`amscd`|定义`CD`环境,用于排版无对角线箭头的矩形交换图|
|`upref`|可使交叉引用的标号总是保持自立罗马体,即使在斜体或者倾斜体的段落中.|
|`amsxtra`|定义了一组可排版超重音符号的命令|

公式宏包 amsmath 的选项:

|选项|简要说明|
| :- | :- |
|centertages|默认值,它表示 `split` 环境排版的多行公司的序号垂直居中|
|tbtags|它指定`split`排版的多行公司的序号置于最后一行左侧或者是第一行的左侧|
|sumlimits|默认值,表示在大型运算符($\int$不算)的上标和下标分别置于顶部和底部|
|nosumlimits|上述大型运算符的上标和下标仍然置于其右侧|
|nointlimits|默认值,无论在行间公式还是行内公式,积分符号的上下标均置于其右侧|
|namelimits|默认值,他表示在行间公式中,$\det \inf\lim\max\min$的下标置于底部|
|nonamelimits|无论行间公式还是行内公式,上述运算符的下标都置于右侧|

#### 8.2.2 宏包组件 AMSFonts

|宏包名|简要说明|
| :- | :-|
|`amssymb`|宏包套件`AMSFonts`中的一个宏包，它定义了`amsfonts`宏包里`msam`和`mabm`字库中全部数学符号的命令。当调用该宏包时`amsfonts`宏包也同时被加载了。|
|`amsfonts`|定义了大写空心粗体`\mathbb`和哥特体`\mathfrak`,增加多种数学字体|
|`eufrak`|定义哥特体`\mathfrak`,如果已有`amsfonts`,则其为多余的.|
|`eucal`|将`\mathcal`改为调用欧拉数书写体|

### 8.3 数学符号

恕我直言,这本书的数学符号简直是在搞笑. 以下内容主要靠网络.

#### 8.3.1 运算符号

**声调**:
|语法|效果|语法|效果|语法|效果|
|:-| :-:| :- | :-:| :- | :-: |
|\bar{x}|$\bar{x}$|\acute{x}|$\acute{x}$|\check{x}|$\check{x}$|
|\grave{x}|$\grave{x}$|\breve{x}|$\breve{x}$|\dot{x}|$\dot{x}$|
|\ddot{x}|$\ddot{x}$|\hat{x}|$\hat{x}$|\tilde{x}|$\tilde{x}$|

**二元运算符**:
TODO:不知道怎么分类

#### 8.3.2 希腊字母

**小写希腊字母**:
|效果|语法|效果|语法|效果|语法|效果|语法|
|:-| :-:| :- | :-:| :- | :-: | :- | :-: |
|$\alpha$|\alpha|$\theta$|\theta|$\xi$|\xi|$\tau$|\tau|
|$\beta$|\beta|$\vartheta$|\vartheta|$\omicron$|\omicron|$\upsilon$|\upsilon|
|$\gamma$|\gamma|$\iota$|\iota|$\pi$|\pi|$\phi$|\phi|
|$\delta$|\delta|$\kappa$|\kappa|$\varPi$|\varpi|$\varphi$|\varphi|
|$\epsilon$|\epsilon|$\varkappa$|\varkappa|$\rho$|\rho|$\chi$|\chi|
|$\varepsilon$|\varepsilon|$\lambda$|\lambda|$\varrho$|\varrho|$\psi$|\psi|
|$\zeta$|\zeta|$\mu$|\mu|$\sigma$|\sigma|$\omega$|\omega|
|$\eta$|\eta|$\nu$|\nu|$\varsigma$|\varsigma|
已经用: \digamma  $\digamma$  

**大写希腊字母**:
|语法|效果|语法|效果|语法|效果|语法|效果|
|:-| :-:| :- | :-:| :- | :-: | :- | :-: |
|\Alpha|$\Alpha$|\Theta|$\Theta$|\varXi|$\varXi$|\varUpsilon|$\varUpsilon$|
|\Beta|$\Beta$|\varTheta|$\varTheta$|\Omicon|$\Omicron$|\Phi|$\Phi$|
|\Gamma|$\Gamma$|\Iota|$\Iota$|\Pi|$\Pi$|\varPhi|$\varPhi$|
|\varGamma|$\varGamma$|\Kappa|$\Kappa$|\varPi|$\varPi$|\Chi|$\Chi$|
|\Delta|$\Delta$|\Lambda|$\Lambda$|\Rho|$\Rho$|\Psi|$\Psi$|
|\varDelta|$\varDelta$|\varLambda|$\varLambda$|\Sigma|$\Sigma$|\varPsi|$\varPsi$|
|\Epsilon|$\Epsilon$|\Mu|$\Mu$|\varSigma|$\varSigma$|\varOmega|$\varOmega$|
|\Zeta|$\Zeta$|\Nu|$\Nu$|\Tau|$\Tau$|
|\Eta|$\Eta$|\Xi|$\Xi$|\Upsilon|$\Upsilon$|
希伯来字母: $\aleph$ \aleph $\beth$ \beth $\daleth$ \daleth $\gimel$ \gimel

**粗体希腊字母**:  
\boldmath 在公式外声明
>`MD`就用不了

可使用`\pmb`
>如 `$\pmb{\Iota \Kappa \Lambda \Mu \Nu \Xi \Omicron\Pi}$`  
有 $\pmb{\Iota \Kappa \Lambda \Mu \Nu \Xi \Omicron\Pi}$

**斜体大写希腊字母**:  
可使用数字常规字体命令`\mathnormal`或者`\mathhit`
> 对 `$\Gamma+\Delta$`  
> 即 $\Gamma+\Delta$  
> 有 `$\mathnormal{\Gamma+\Delta}$, $\mathit{\Gamma+\Delta}$`  
> 即 $\mathnormal{\Gamma+\Delta}$, $\mathit{\Gamma+\Delta}$  

**粗斜体希腊字母**:

- 可使用`amsmath`提供的`\mathsymbol`  
    如 `$\boldsymbol{\alpha+\beta-\Gamma+\Delta}$`  
    即 $\boldsymbol{\alpha+\beta-\Gamma+\Delta}$  
- 也可使用`mathpazo`中的`\mathbold` (`MD`用不了)

**直立小写希腊字母**: (`MD`用不了)  

- `txfont`中可在希腊字母之后加`up`如`$\mu$`变为`$\muup$`  
- `upgreek`中可在希腊字母之前加`up`如`$\mu$`变为`$\upmu$`

#### 8.3.3 函数符号

对  
\arccos \cos \csc \exp \ker \limsup \min \arcsin \cosh \deg \gcd \lg \ln  
\Pr \arctan \cot \det \hom \lim \log \sec \arg \coth \dim \inf \liminf \max  
\sin \sinh \sup \tan \tanh  

即得  
$\arccos \cos \csc \exp \ker \limsup \min \arcsin \cosh \deg \gcd \lg \ln$   $\Pr \arctan \cot \det \hom \lim \log \sec \arg \coth \dim \inf \liminf \max$  
$\sin \sinh \sup \tan \tanh$

#### 8.3.4 定界符

(其实我觉得我用不上)
| 效果      |     语法      | 效果          |     语法      | 效果           |     语法     | 效果           |     语法     |
| :-------- | :-----------: | :------------ | :-----------: | :------------- | :----------: | :------------- | :----------: |
| $($       |       (       | $)$           |       )       | $\uparrow$     |   \uparrow   | $\Uparrow$     |   \Uparrow   |
| $[$       | [ or \lbrack  | $]$           | ] or \rbrack  | $\downarrow$   |  \downarrow  | $\Downarrow$   |  \Downarrow  |
| $\lbrace$ | \\{ or \lbrace | $\rbrace$     | \\} or \rbrace | $\updownarrow$ | \updownarrow | $\Updownarrow$ | \Updownarrow |
| $\langle$ |    \langle    | $\rangle$     |    \rangle    | $\vert$        |  \|or\vert   | $\Vert$        |  \|or\Vert   |
| $\lfloor$ |    \lfloor    | $\rfloor$     |    \rfloor    | $\lceil$       |    \lceil    | $\rceil$       |    \rceil    |
| $/$       |       /       | \\|\backslash |       $dual$       | (dual. empty)  |
|$\lgroup$|\lgroup|$\rgroup$|\rgroup|$\lmoustache$|\lmoustache|$\rmoustache$|\rmoustache|
|实现不了|\arrowvert|实现不了|\Arrowvert|实现不了|\bracevert|

#### 8.3.5 关系符号  

| 效果             | 语法            | 效果    | 语法              | 效果 | 语法              |
| ------------------ | ----------------- | --------- | ------------------- | ---- | ------------------- |
| $\lessdot$         | \lessdot          | $\gtrdot$ | \gtrdot             | $\doteqdot$   | \doteqdot or \Doteq |
| $\leqslant$        | \leqslant         | $\geqslant$        | \geqslant           | $\risingdotseq$   | \risingdotseq       |
| $\eqslantless$                 | \eqslantless      | $\eqslantgtr$        |  \eqslantgtr        | $\fallingdotseq$   |  \fallingdotseq     |
| $\leqq$                 | \leqq             | $\geqq$        |  \geqq              | $\eqcirc$   | \eqcirc             |
| $\llless$                 | \lll or \llless   | $\gggtr$        |  \ggg or \gggtr     | $\circeq$   | \circeq             |
| $\lesssim$                 |  \lesssim         | $\gtrsim$        |  \gtrsim            | $\triangleq$   | \triangleq          |
| $\lessapprox$                 | \lessapprox       | $\gtrapprox$        | \gtrapprox          | $\bumpeq$   |  \bumpeq            |
| $\lessgtr$                 |  \lessgtr         | $\gtrless$        |  \gtrless           | $\Bumpeq$   | \Bumpeq             |
| $\lesseqgtr$                 |  \lesseqgtr       | $\gtreqless$        |  \gtreqless         | $\thicksim$   | \thicksim           |
| $\lesseqqgtr$                 |  \lesseqqgtr      | $\gtreqqless$        |  \gtreqqless        | $\thickapprox$   |  \thickapprox       |
| $\preccurlyeq$                 |  \preccurlyeq     | $\succcurlyeq$        |  \succcurlyeq       | $\approxeq$   |  \approxeq          |
| $\curlyeqprec$                 |  \curlyeqprec     | $\curlyeqsucc$        |  \curlyeqsucc       | $\backsim$   | \backsim            |
| $\precsim$                 | \precsim          | $\succsim$        | \succsim            | $\backsimeq$   |  \backsimeq         |
| $\precapprox$                 |  \precapprox      | $\succapprox$        |  \succapprox        | $\vDash$   | \vDash              |
| $\subseteqq$                 | \subseteqq        | $\supseteqq$        | \supseteqq          | $\Vdash$   |  \Vdash             |
| $\Subset$                 | \Subset           | $\Supset$        |  \Supset            | $\Vvdash$   | \Vvdash             |
| $\sqsubset$                 | \sqsubset         | $\sqsupset$        | \sqsupset           | $\backepsilon$   |  \backepsilon       |
| $\therefore$                 | \therefore        | $\because$        |  \because           | $\varpropto$   | \varpropto          |
| $\shortmid$                 |  \shortmid        | $\shortparallel$        | \shortparallel      | $\between$   | \between            |
| $\smallsmile$                 |  \smallsmile      | $\smallfrown$        |  \smallfrown        | $\pitchfork$   | \pitchfork          |
| $\vartriangleleft$ | \vartriangleleft  | $\vartriangleright$        |  \vartriangleright  | $\blacktriangleleft$   | \blacktriangleleft  |
| $\trianglelefteq$  |  \trianglelefteq  | $\trianglerighteq$        | \trianglerighteq    | $\blacktriangleright$   | \blacktriangleright |
||||
|$\equiv$|\equiv|$\propto$|propto|||
|$\pm$|\pm|$\mp$|\mp|||
对上述所有符号均可在其前加`\not`作为其否定(加一条斜杠).
部分可在合适位置加`n`

#### 8.3.6 箭头符号  

| 效果 | 语法               | 效果 | 语法                | 效果 | 语法                 |
| ---- | -------------------- | ---- | --------------------- | ---- | ---------------------- |
|   $\leftarrow$   | \leftarrow or \gets  |  $\longleftarrow$    | \longleftarrow        |  $\uparrow$    | \uparrow               |
|  $\rightarrow or \to$    | \rightarrow or \to   |  $\longrightarrow$    | \longrightarrow       |  $\downarrow$    | \downarrow             |
|    $\leftrightarrow$  | \leftrightarrow      |   $\longleftrightarrow$   |  \longleftrightarrow  |   $\updownarrow$   | \updownarrow           |
|   $\Leftarrow$   | \Leftarrow           |   $\Longleftarrow$   | \Longleftarrow        |   $\Uparrow$   | \Uparrow               |
|  $\Rightarrow$    | \Rightarrow          |   $\Longrightarrow$   | \Longrightarrow       |   $\Downarrow$  | \Downarrow             |
| $\Leftrightarrow$     | \Leftrightarrow      |   $\Longleftrightarrow$   | \Longleftrightarrow   |  $\Updownarrow$    | \Updownarrow           |
|   $\mapsto$   |  \mapsto             |   $\longmapsto$   | \longmapsto           |  $\nearrow$    | \nearrow               |
|   $\hookleftarrow$   | \hookleftarrow       |   $\hookrightarrow$   | \hookrightarrow       |   $\searrow$   | \searrow               |
|  $\leftharpoonup$    | \leftharpoonup       |   $\rightharpoonup$   | \rightharpoonup       |   $\swarrow$   | \swarrow               |
|  $\leftharpoondown$    | \leftharpoondown     |    $\rightharpoondown$  | \rightharpoondown     |   $\nwarrow$   | \nwarrow               |
|   $\rightleftharpoons$   | \rightleftharpoons   |   $\iff$   | \iff (bigger spaces)  |   $\leadsto$   | \leadsto               |
|      |                      |      |                       |      |                        |
|   $\dashleftarrow$   |  \dashleftarrow      |  $\dashrightarrow$    | \dashrightarrow       |   $\multimap$   | \multimap              |
|   $\leftleftarrows$   |  \leftleftarrows     |   $\rightrightarrows$   |  \rightrightarrows    |  $\upuparrows$    |  \upuparrows           |
|   $\leftrightarrows$   |  \leftrightarrows    |   $\rightleftarrows$   | \rightleftarrows      |   $\downdownarrows$   | \downdownarrows        |
|  $\Lleftarrow$    |  \Lleftarrow         |   $\Rrightarrow$   |  \Rrightarrow         |   $\upharpoonleft$   |  \upharpoonleft        |
|   $\twoheadleftarrow$   |  \twoheadleftarrow   |   $\twoheadrightarrow$   |  \twoheadrightarrow   |   $\upharpoonright$   |  \upharpoonright       |
|  $\leftarrowtail$    |  \leftarrowtail      |   $\rightarrowtail$   |  \rightarrowtail      |   $\downharpoonleft$   |  \downharpoonleft      |
|    $\leftrightharpoons$  |  \leftrightharpoons  |   $\rightleftharpoons$   |  \rightleftharpoons   |   $\downharpoonright$   |  \downharpoonright     |
|   $\Lsh$   |  \Lsh                |    $\Rsh$  |  \Rsh                 |   $\rightsquigarrow$   | \rightsquigarrow       |
|    $\looparrowleft$  |  \looparrowleft      |  $\looparrowright$    |  \looparrowright      |   $\leftrightsquigarrow$   |  \leftrightsquigarrow  |
|  $\curvearrowleft$    |  \curvearrowleft     |   $\curvearrowright$   |  \curvearrowright     |      |                        |
|   $\circlearrowleft$   |  \circlearrowleft    |   $ \circlearrowright$   |  \circlearrowright    |      |                        |



.
