# Crypto

## 基础理论

##### 密码学理论的特点

- 反直觉的
- 定义清晰
- 保守倾向

##### Kerckhoffs原则

除密钥外的整个系统的一切都是公开的，这个密码体制也必须是安全 的。尤其是即使攻击者知道系统的加密算法和解密算法，此系统也必须是安全的。

### 数字签名与消息验证码

#### 数字签名

- 不可否认、不可伪造、

一种不可伪造的签名满足：

- 每个用户可以有效地生成在他所选的文件上的签名
- 每个用户能够有效地校验所给的字符串是否是另一(指定的)用户在特定文件上的签
  名
- 如果用户本身没有在文件.上签名,那么其他任何用户都不能有效地伪造那些用户的签名

#### 消息验证码

- 禁止任何外部方修改通信消息

有效的认证方案满足:

- 每个通信方都能为它选择的消息有效地生成认证标签
- 每个通信方都能有效地验证某--字符串是否是某--消息的认证标签
- 除厂通信双方外其他任何一方都不能有效地产生消息认证标签

#### 消息验证码和数字签名的区别

- 数字签名要求任何人都能进行验证，消息验证码只允许通信双方验证

- 数字签名可以构建消息验证码方案，反之不行

#### 零知识证明

双方同时交换机密信息，双方都正确遵守此协议时，在任何情况下(即使一方有欺骗行为)，第一方能够获得第二方的机密信息，当且仅当第二方获得了第一方的机密信息。

## 古典密码

### 密码分析

![image-20240804172345854](C:\Users\泰来\AppData\Roaming\Typora\typora-user-images\image-20240804172345854.png)

### 单表代换加密

明密文一一映射

- 在密钥空间较小的情况下，采用暴力破解方式
- 在密文长度足够长的时候，使用词频分析，http://quipqiup.com/

- 当密钥空间足够大，而密文长度足够短的情况下，破解较为困难。

#### 替换密码

##### 移位密码

- 将明文空间中每个字符按照前后顺序，向后（或向前）移动固定数目（**循环移动**）作为密文。

- 明文空间有固定的先后顺序

##### 凯撒密码

- 明文空间为字母空间

##### 简单替换密码

- 映射方式全随机，密钥个数为阶乘数量级
- 一般考虑词频分析

#### 仿射密码

$$
E(x)=(ax+b)(mod\quad m)\\
D(x)=a^{-1}(x-b)(mod\quad m)
$$

可以使用已知明文攻击破解。
$$
y_1=ax_1+b(mod\quad m)\\
y_2=ax_2+b(mod\quad m)
$$
解二元一次线性同余方程组，可以求出解密参数$$a^{-1},b$$。

## 对称密码学

## 序列密码

#### 线性反馈移位寄存器(LFSR)

![image-20240907092759148](C:\Users\泰来\AppData\Roaming\Typora\typora-user-images\image-20240907092759148.png)

- 图中是度为m的通用LFSR
  - 有m个触发器和m个反馈位置
  - 反馈路径是否活跃取决于反馈系数$$p_0,p_1,\cdots,p_{m-1}$$
  - 触发器和反馈位置通过XOR连接

$$
\begin{aligned}
s_{m+1}&\equiv s_mp_{m-1}+\cdots+s_2p_1+s_1p_0\quad &mod\ 2\\
s_{i+m}&\equiv \Sigma^{m-1}_{j=0}p_j\cdot s_{i+j}\quad s_i,p_j\in\{0,1\} \ & mod\ 2
\end{aligned}
$$

## 分组密码

### DES(Data Encryption Standard)



## 基础知识补录

#### 概率论公式

##### Markov马尔可夫不等式

令$$X$$为一非负随机变量，$$v$$为一实数，则有
$$
Pr[X>v]\leq \frac{E(X)}{v}
$$
等价的，有
$$
\Pr[X\geq v \cdot E(X)]\leq \frac{1}{v}
$$
Markov不等式常用于不了解随机变量分布的情况，它只要求了解随机变量的期望和至少一个在它的取值范围内的界。

利用Markov不等式可以得到一个随机变量偏离其均值“更紧”的界。如果能够得到关于随机变量的额外知识(特别地,一个随机变量关于其方差的好的上界),那么这个称为契比雪夫不等式的界将十分有用：

##### Chebyshev不等式

令$$X$$为一随机变量，且$$\delta\gt0$$，则有
$$
\Pr[\mid X-E(X)\mid \geq\delta ]\leq\frac{Var(X)}{\delta^2}
$$
其中，定义$$X$$的方差为$$Var(X)\overset{\text{def}}=E[(X(-E(X))^2]=E(X^2)-{E(X)}^2$$

##### Chernoff界

令$$p\leq\frac{1}{2}且X_1,X_2,...,X_n$$是独立的0-1随机变量，对任意$$i$$都有$$\Pr[X_i=1]=p,$$则对于所有的$$\epsilon,0<\epsilon\leq p(1-p)$$,都有:
$$

$$

#### 计算模型

##### 复杂度类P

如果存在一种确定性图灵机M和一个多项式$$p(\cdot)$$,并且满足：

- 当输入字符串$$x$$时，M机器至多在$$p(|x|)$$步以后停止
- $$M(x)=1$$当且仅当$$x\in L$$

#### 随机化算法

概率多项式时间图灵机是一种概率机器

##### BPP 有界概率多项式时间

- 对于每一个$$r∈L,Pr[M(x)=1]\geq\frac{2}{3}$$号成立,且

- 对于每一个$$r\notin L,Pr[M(x)=0]≥\frac{2}{3}$$号成立。

则称L是可被概率多项式时间图灵机M识别的.

BPP就是可被概率多项式时间图灵机(即随机化算法)识别的语言类。

实际上，常数只需要大于$$\frac{1}{2}$$就行了，定义类是同一个。

##### 可忽略函数

如果对任一多项式$$p(\cdot )$$，存在N，当$$n>N$$时，满足
$$
u(n)<\frac{1}{p(n)}
$$
就称函数$$u：N\rightarrow R$$是可忽略的。

##### 非均匀多项式时间算法

##### 难处理假设

概率多项式时间算法机不能完成的工作认为是难处理的。

- 只有当NP不包含于BPP的时候(此时$$P \neq NP$$)，加密算法才有意义

##### 预言机 Oracle Machine

- 一种确定性或概率图灵机
- 预言带的附加带
- 预言请求状态
- 预言作用状态



- 说实话没搞太懂

### 单项函数

#### 强单项函数

函数$$f:\{0,1\}^*\rightarrow \{0,1\}^*$$满足:

- 正向容易计算:存在一个确定性多项式时间算法A，使输入$$x$$时，算法A的输入为$$f(x)(即A(x))$$

- 反向难以求逆:对于每一个概率多项式时间算法B，每一个多项式$$p( \cdot)$$和所有足够大的n，有:
  $$
  Pr[B(f(U_n),1^n)\in f^{-1}(f(U_n))]<\frac{1}{p(n)}
  $$

$$U_n$$为服从$$\{0,1\}^n$$上的一个均匀分布的随机变量，$$1^n$$为要求输出的长度，防止输出时间受限。

对于任意一个概率多项式时间算法，求出某个$$f(x)$$原像的可能性，都是可忽略的。

#### 弱单向函数

函数$$f:\{0,1\}^*\rightarrow \{0,1\}^*$$满足:

- 正向容易计算：存在一个确定性多项式时间算法A，使输入$$x$$时，算法A的输入为$$f(x)(即A(x))$$

- 反向稍微难求逆：存在一个多项式$$p(\cdot)$$，使每一个概率多项式时间算法B和所有足够大的n，有：
  $$
  Pr[B(f(U_n,1^n)\notin f^{-1}(f(U_n))]>\frac{1}{p(n)})
  $$

### 伪随机数生成器

从一个给定的初始种子值，计算后生成一个序列。

- 不可预测 	只有密码学要求
- 
