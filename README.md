# 三、四维中心立方体极大算子的弱型上下界

Weak-type bounds for the centered cubic Hardy–Littlewood maximal operator in dimensions 3 and 4.

设 $C_n$ 为 $\mathbb R^n$ 上关于 Lebesgue 测度的最优弱型 $(1,1)$ 常数。$M_nf(x)$ 取 $\lvert f\rvert$ 在所有以 $x$ 为中心、轴平行且各坐标共用半径 $r>0$ 的立方体上的平均值上确界。$C_n$ 是对所有 $f\in L^1(\mathbb R^n)$ 和 $\lambda>0$ 满足下式的最小系数。

$$
\lambda\,\lvert\{x:M_nf(x)>\lambda\}\rvert\le C_n\lVert f\rVert_1 .
$$

| 维数 | 严格下界 | 严格上界 | 论文与证书 |
|---:|---:|---:|---|
| 3 | $C_3>1.7941091664563071$ | $C_3<1979/250=7.916$ | [中文 PDF](cube-finite-dim-bounds/papers/n3/main.pdf) · [TeX](cube-finite-dim-bounds/papers/n3/main.tex) · [下界证书](cube-finite-dim-bounds/audit/022_check.py) · [上界复核](cube-finite-dim-bounds/audit/036_check.py) |
| 4 | $C_4>1.90174261110095$ | $C_4<14371/1000=14.371$ | [中文 PDF](cube-finite-dim-bounds/papers/n4/main.pdf) · [TeX 与参考文献](cube-finite-dim-bounds/papers/n4/) · [下界证书](cube-finite-dim-bounds/baseline/original_certificates.json) · [上界复核](cube-finite-dim-bounds/audit/037_check.py) |

两篇匿名中文审核稿分别证明三维和四维的上界，采用有限方向 Cauchy 势、障碍比较与连续计算证书。下界来自此前的周期有限见证构造，完整有理区间见账本。两维的精确最优常数仍待确定。[准确界账本](cube-finite-dim-bounds/results/released_bounds.json)

## 从这里读／如何引用

引用任选对应维数的 BibTeX 条目。固定版本保留 2026 年 10 月 25 日第 11 轮交付的原 PDF 和 TeX。[v1.0.0 发布页](https://github.com/alizeisnotalice/centered-cube-dim-3-4/releases/tag/v1.0.0) · [三维 PDF](https://github.com/alizeisnotalice/centered-cube-dim-3-4/blob/v1.0.0/cube-finite-dim-bounds/papers/n3/main.pdf) · [四维 PDF](https://github.com/alizeisnotalice/centered-cube-dim-3-4/blob/v1.0.0/cube-finite-dim-bounds/papers/n4/main.pdf) · [BibTeX](https://github.com/alizeisnotalice/centered-cube-dim-3-4/blob/v1.0.0/citation.bib)

## 编译与复算

复算说明给出下界的整数／有理数检验、三维 8,256 个积分区域的归档数据复核、四维 2,440 个单元的重建与系数验证，以及独立编译两篇 TeX 的命令。分析证明与有限计算的分工见两篇论文。[编译与复算说明](REPRODUCE.md) · [文件校验和](SHA256SUMS)

原研究提交为 `77be2e9`，本归档沿用其中的证书路径和锁定输入。[原始交付与复审记录](https://github.com/alizeisnotalice/Math-Research/blob/77be2e97b708bbe58f365b291983a78a32d7ea1d/cube-finite-dim-bounds/rounds/011-paper-delivery.md)
