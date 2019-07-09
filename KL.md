cross entropy，logistic loss 和 KL-divergence的关系和区别

先给出结论：

    cross entropy和KL-divergence作为目标函数效果是一样的，从数学上来说相差一个常数。
    logistic loss 是cross entropy的一个特例

1. cross entropy和KL-divergence

假设两个概率分布p(x)
和q(x)， H(p,q)为cross entropy，DKL(p|q)

为 KL divergence。
交叉熵的定义：

H(p,q)=−∑xp(x)logq(x)

KL divergence的定义：

DKL(p|q)=∑xp(x)logp(x)q(x)

推导：

DKL(p|q)=∑xp(x)logp(x)q(x)=∑x(p(x)logp(x)−p(x)logq(x))=−H(p)−∑xp(x)logq(x)=−H(p)+H(p,q)

也就是说，cross entropy也可以定义为：
H(p,q)=DKL(p|q)+H(p)

直观来说，由于p(x)是已知的分布，H(p)是个常数，cross entropy和KL divergence之间相差一个常数。
2. logistic loss 和cross entropy

假设p∈{y,1−y}
，q∈{y^,1−y^}

， cross entropy可以写为logistic loss：
H(p,q)=−∑xp(x)logq(x)=−ylogy^−(1−y)log(1−y^)
