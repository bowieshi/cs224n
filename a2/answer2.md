#### 1 (a)

when $a \in o$, $y_a = 1$. when $a\notin o, y_a = 0$

#### 1 (b)

$$
J_{naive-softmax}(v_c, o, U)=-log(\frac{exp(u_o^T v_c)}{\sum_{w\in Vocab}exp(u_w^Tv_c)})\\
J_{naive-softmax}(v_c, o, U)=-u_o^T v_c+log\sum_{w\in Vocab}exp(u_w^Tv_c)\\
\frac{\partial J_{naive-softmax}(v_c, o, U)}{\partial v_c}=-u_o+\frac{\partial}{\partial v_c}log\sum_{w\in Vocab}exp(u_w^Tv_c)\\
\frac{\partial J}{\partial v_c}=-u_o+\frac{1}{\sum_{w\in Vocab}exp(u_w^Tv_c)}\frac{\partial}{\partial v_c}\sum_{w\in Vocab}exp(u_w^Tv_c)\\
\frac{\partial J}{\partial v_c}=-u_o+\frac{1}{\sum_{w\in Vocab}exp(u_w^Tv_c)}\frac{\partial}{\partial v_c}\sum_{w\in Vocab}exp(u_w^Tv_c)\\
\frac{\partial J}{\partial v_c}=-u_o+\frac{1}{\sum_{w\in Vocab}exp(u_w^Tv_c)}\sum_{w\in Vocab}\frac{\partial}{\partial v_c}exp(u_w^Tv_c)\\
\frac{\partial J}{\partial v_c}=-u_o+\frac{1}{\sum_{w\in Vocab}exp(u_w^Tv_c)}\sum_{w\in Vocab}exp(u_w^Tv_c)u_w\\
\frac{\partial J}{\partial v_c}=-u_o+\sum_{w\in Vocab}\frac{exp(u_w^Tv_c)}{\sum_{w'\in Vocab}exp(u_{w'}^Tv_c)}u_w\\
\frac{\partial J}{\partial v_c}=-u_o+\sum_{w\in Vocab}\hat{y}_wu_w\\
\frac{\partial J}{\partial v_c}=\sum_{w\in Vocab}(\hat{y}_w-y_w)u_w\\
\frac{\partial J}{\partial v_c}=U(\hat{y}-y)
$$

#### 1 (c)

when $w = o$
$$
\frac{\partial J}{\partial u_w}=(\hat{y}_w-1)v_c\\
$$
when $w\neq o$
$$
\frac{\partial J}{\partial u_w}=\hat{y}_w v_c
$$
combined together
$$
\frac{\partial J}{\partial u_w}=(\hat{y}_w-y_w)v_c\\
$$

#### 1 (d)

$$
\frac{\partial \sigma}{\partial x}=\sigma(x)(1-\sigma(x))
$$

#### 1 (f)

$$
\frac{\partial J}{\partial v_c}=u_o(\sigma(u_o^T v_c)-1)-\sum_{k=1}^{K}u_k(\sigma(-u_k^Tv_c)-1)
$$

$$
\frac{\partial J}{\partial u_o}=v_c(\sigma(u_o^T v_c)-1))
$$

$$
\frac{\partial J}{\partial u_k}=-v_c(\sigma(-u_k^Tv_c)-1)
$$

#### 1 (g)

$$
\frac{\partial J}{\partial u_k}=\sum_{i\in\{1,...,K\}:w_i=w_k}-v_c(\sigma(-u_k^Tv_c)-1)
$$

