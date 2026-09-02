# 第 5—7 章三轮交叉修订报告

## 修订范围与完整阅读方式

本次修订覆盖下列全部正文文件，并包含各章入口文件：

- 第 5 章：`chapters/ch05/ch05.tex`、`chapters/ch05/sec-05-01.tex`—`sec-05-04.tex`；
- 第 6 章：`chapters/ch06/ch06.tex`、`chapters/ch06/sec-06-01.tex`—`sec-06-04.tex`；
- 第 7 章：`chapters/ch07/ch07.tex`、`chapters/ch07/sec-07-01.tex`—`sec-07-04.tex`。

每一轮都按文件自然顺序，从第一行连续读到文件末尾；阅读窗口不超过约 220 行。关键词检索只用于全量阅读结束后的机械性残留检查，未用来代替正文阅读。每轮完成修改后，又对相应章节从头到尾复读并检查差异、环境配对与控制字符。

最终第三轮复读时，各章文件行数如下：

| 章节 | 入口文件 | sec01 | sec02 | sec03 | sec04 |
|---|---:|---:|---:|---:|---:|
| 第 5 章 | 23 | 1006 | 1452 | 1391 | 1322 |
| 第 6 章 | 21 | 1097 | 1139 | 1192 | 1970 |
| 第 7 章 | 25 | 1245 | 1600 | 1344 | 1645 |

## 三轮独立交叉安排

三名审校者在三轮中轮换章节，同一审校者没有重复检查同一章。

| 轮次 | 第 5 章 | 第 6 章 | 第 7 章 | 核心检查目标 |
|---|---|---|---|---|
| 第一轮 | 审校者 A | 审校者 B | 审校者 C | 证明、例题计算与构造的数学严谨性；补全被自然语言省略的公式链 |
| 第二轮 | 审校者 C | 审校者 A | 审校者 B | 定义—定理依赖、使用顺序、前置知识边界与延后证明标注 |
| 第三轮 | 审校者 B | 审校者 C | 审校者 A | 术语与中文表达；再次检查剩余证明缺口及未定义符号 |

## 主要修订内容

1. 补全条件核、高斯与 Bayes 计算、一致可积、紧性与 Prokhorov、Borel–Cantelli、零一律、Markov 未来核、上穿不等式、可选停止、再生结构、Itô 积分、Fourier 变换、矩问题、Daniell–Stone 与 Riesz–Markov 等处被压缩或仅以自然语言描述的证明链。
2. 修复先使用后定义或依赖来源不明的问题：在首次使用前给出高斯过程、连续时间 Markov 过程、半群、Chapman–Kolmogorov 关系、紧性、正则条件分布等定义；对 Weierstrass、Montel、Vitali 等后续才证明的结论明确作延后说明；调整 `W^{1,1}` 等概念的出现顺序。
3. 加入或展开有限循环群特征正交性、高斯—Hermite 函数的 Fourier 不变性、Kolmogorov 最大不等式中的交叉项消失、路径映射可测性、`C_0` 的 Polish 性、Doob 版本、Ornstein–Uhlenbeck 连续性、高斯四阶矩与 Itô 局部化等关键细节。
4. 统一并修订机器翻译感较强的表述，替换“概率云”“逐点挂核”“赠送路径正则性”“失败现场”等非标准术语；对 Rao–Blackwell、Harris 常返、Berry–Esseen 等名称删除不必要引用或在首次出现时给出清楚定义与适用范围。
5. 对全部修改文件执行 LaTeX 环境配对、花括号平衡、异常控制字符和差异复核；三轮结束后未留下阻断性数学疑点。

## 编译与成品检查

- XeLaTeX 完整编译并生成索引，共 499 页、A4、PDF 1.5。
- 终编日志中：LaTeX 错误 0、未定义控制序列 0、致命错误 0、未定义引用 0、重复标签 0、需重跑提示 0、超出版心 0、缺字 0、字体警告 0。
- 所有 PDF 字体均已嵌入。
- 499 页全部渲染为图像并按 25 张接触表逐页检查；未发现裁切、重叠、黑块或异常稀疏页。第 2、4、8 页为空白页，属于题名页、前言和目录的双面排版留白。
- PDF 文本层共提取 499 个分页符，Unicode 替换字符 0，`??` 占位符 0。
- PDF SHA-256：`fa14904b1bd6baa8272c2e0e65f90ea24b034a203cf0aedd3a7d87f7752350ee`。

## 常规重编译方法

在安装了 XeLaTeX 与 MakeIndex 的 TeX Live 环境中，于源码根目录运行：

```sh
xelatex -interaction=nonstopmode -halt-on-error main.tex
makeindex main.idx
xelatex -interaction=nonstopmode -halt-on-error main.tex
xelatex -interaction=nonstopmode -halt-on-error main.tex
xelatex -interaction=nonstopmode -halt-on-error main.tex
```
