# annotkappa

**计算多标注者的一致性并定位分歧标注。**

`annotkappa` —— 计算 Cohen's Kappa 或 Fleiss' Kappa，列出分歧最大的条目

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`annotkappa.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install abhilashhe-annotkappa
```

装完直接用命令名调用：

```bash
annotkappa --help
```

也可以不用安装，直接把 `annotkappa.py` 拷走用——它只依赖标准库。

## 为什么需要它

一致率会被类别不平衡抬高，工具同时报 Kappa

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 评测标注一致 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python annotkappa.py --file input.txt
python annotkappa.py --text "示例内容"
python annotkappa.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 比例的分母取自你给的口径，不替你选口径。
- 不判断比例高低是否合理。

## 跑测试

```bash
python test_annotkappa.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/abhilashhe/annotkappa>

---

## 关于作者

abhilashhe 做评测标注一致相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://abhilashhe.github.io>
- 仓库：<https://github.com/abhilashhe/annotkappa>

## 许可

MIT，见 [LICENSE](LICENSE)。
