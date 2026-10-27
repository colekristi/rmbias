# rmbias

**检测奖励模型的长度与风格偏好。**

`rmbias` —— 统计奖励分与文本特征的相关性，给出偏置强度与方向

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`rmbias.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install colekristi-rmbias
```

装完直接用命令名调用：

```bash
rmbias --help
```

也可以不用安装，直接把 `rmbias.py` 拷走用——它只依赖标准库。

## 为什么需要它

偏置方向决定怎么修——奖励长答案和奖励短答案是两回事

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 奖励模型偏置 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python rmbias.py --file input.txt
python rmbias.py --text "示例内容"
python rmbias.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 比例的分母取自你给的口径，不替你选口径。
- 不判断比例高低是否合理。

## 跑测试

```bash
python test_rmbias.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/colekristi/rmbias>

---

## 关于作者

colekristi 做奖励模型偏置相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://colekristi.github.io>
- 仓库：<https://github.com/colekristi/rmbias>

## 许可

MIT，见 [LICENSE](LICENSE)。
