# 编译与复算

以下命令从本仓库根目录运行。论文原件位于 `cube-finite-dim-bounds/papers/`，数值代码和锁定输入沿用原项目路径。

## 两篇论文的 TeX

使用 TeX Live 或 MacTeX 的 XeLaTeX，需有 latexmk、CTeX、Fandol 和 AMS。四维稿的参考文献随附，由 latexmk 调用 BibTeX。下列命令把生成文件写入临时目录，保留原 PDF。

```sh
build_dir="$(mktemp -d "${TMPDIR:-$PWD}/dim34-tex.XXXXXX")"
mkdir "$build_dir/n3" "$build_dir/n4"
cp cube-finite-dim-bounds/papers/n3/main.tex "$build_dir/n3/"
cp cube-finite-dim-bounds/papers/n4/main.tex \
   cube-finite-dim-bounds/papers/n4/references.bib "$build_dir/n4/"
(cd "$build_dir/n3" && latexmk -xelatex -interaction=nonstopmode -halt-on-error main.tex)
(cd "$build_dir/n4" && latexmk -xelatex -interaction=nonstopmode -halt-on-error main.tex)
```

## 下界与最终成本

以下三条使用 Python 标准库。第一条复算三维三轨道的整数并集体积及有理区间，第二条重算包含四维下界的原代数见证，第三条检查两篇论文的最终严格成本比较。下界从有限见证到 Lebesgue 算子、上界从连续证书到一般输入的传递分别由原证明承担。[三维下界复算程序](cube-finite-dim-bounds/audit/022_check.py) · [准确界账本](cube-finite-dim-bounds/results/released_bounds.json)

```sh
python3 cube-finite-dim-bounds/audit/022_check.py
python3 cube-finite-dim-bounds/baseline/reproduce.py
python3 cube-finite-dim-bounds/src/round011_sharp_rational_cost.py
```

## 上界的连续证书

归档验证使用 Python 3.12 和 [requirements.txt](requirements.txt) 中的固定版本。可在虚拟环境中运行 `python -m pip install -r requirements.txt`。为 036 和 037 提供 `--save` 路径，以便保留仓库内的原归档输出。

```sh
output_dir="$(mktemp -d "${TMPDIR:-$PWD}/dim34-verify.XXXXXX")"

# 三维：96 锥、全域 Green 核下端、连续误差、完整积分证书
python cube-finite-dim-bounds/audit/032_check.py
python cube-finite-dim-bounds/audit/033_check.py
python cube-finite-dim-bounds/audit/034_check.py
python cube-finite-dim-bounds/audit/036_check.py --save "$output_dir/n3.json"

# 四维：1152 锥与完整连续积分、精确最小值及锐化成本
python cube-finite-dim-bounds/audit/035_check.py
python cube-finite-dim-bounds/audit/037_check.py --save "$output_dir/n4.json"
```

三维 033 从头计算 59,976 个 Green 节点。036 使用锁定的紧凑输出，重核 8,256 个区域的凸弦、面积、全量聚合、短时积分预算和成本。从头重建三维积分节点可将下面三个锁定文件复制到同一空目录中运行。全批涉及约 899 万个节点，计算量大。

```sh
scratch="$(mktemp -d "${TMPDIR:-$PWD}/dim34-n3-full.XXXXXX")"
src=cube-finite-dim-bounds/upper/continuous_bridge
cp "$src/cb11_cones.json" "$src/cb11_integral_cheb_check.py" \
   "$src/cb11_integral_cheb_selfcheck.py" "$scratch/"
(cd "$scratch" && python cb11_integral_cheb_check.py --stage part --part 0 --parts 1)
(cd "$scratch" && python cb11_integral_cheb_selfcheck.py --parts 1)
(cd "$scratch" && python cb11_integral_cheb_check.py --stage aggregate --parts 1)
```

四维 035 重建 1,152 个锥并检查全部 2,440 个积分单元。它的输出保留中间界 `14.753`，随后 037 利用模型的准确全域最小值复核最终界 `14.371`。数学范围与计算依赖见论文及复算程序。[035 完整复核](cube-finite-dim-bounds/audit/035_check.py) · [037 锐化](cube-finite-dim-bounds/audit/037_check.py)

## 文件身份

使用 `shasum -a 256 -c SHA256SUMS` 核对归档文件。PDF、TeX、复算程序及数值证书与原固定提交一致。公开版哈希清单覆盖本仓库的复算输入，旧账本中的四条结果汇入发布账本。三维紧凑证书的来源记录保留了原分片哈希和积分有理上端。[校验和](SHA256SUMS)
