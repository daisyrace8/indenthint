# indenthint

**把提示词的层级缩进语义归并成组并标出每组的代表项。**

`indenthint` —— 按结构键把条目聚类，标出提示词的层级缩进语义上的同组项与各组的代表样本

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`indenthint.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install daisyrace8-indenthint
```

装完直接用命令名调用：

```bash
indenthint --help
```

也可以不用安装，直接把 `indenthint.py` 拷走用——它只依赖标准库。

## 为什么需要它

分组依据是结构特征而不是字面相似，改了措辞但结构没变的仍算同组

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 提示词的层级缩进语义 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python indenthint.py --file input.txt
python indenthint.py --text "示例内容"
python indenthint.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 分组靠标签与关键词相似度，分错组时不保证可解释。
- 不评估分组质量。

## 跑测试

```bash
python test_indenthint.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/daisyrace8/indenthint>

---

## 关于作者

daisyrace8 做提示词的层级缩进语义相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://daisyrace8.github.io>
- 仓库：<https://github.com/daisyrace8/indenthint>

## 许可

MIT，见 [LICENSE](LICENSE)。
