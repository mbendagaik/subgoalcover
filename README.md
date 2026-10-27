# subgoalcover

**检查智能体的中间步骤是否真的推进了最终目标。**

`subgoalcover` —— 把执行步骤与目标子点对应，标出没有贡献的绕路步骤

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`subgoalcover.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install mbendagaik-subgoalcover
```

装完直接用命令名调用：

```bash
subgoalcover --help
```

也可以不用安装，直接把 `subgoalcover.py` 拷走用——它只依赖标准库。

## 为什么需要它

「没贡献」与「有害」分开，后者更严重

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 智能体子目标覆盖 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python subgoalcover.py --file input.txt
python subgoalcover.py --text "示例内容"
python subgoalcover.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 覆盖率的分母取自你登记的清单，清单不全就会偏高。
- 只做映射，不追责。

## 跑测试

```bash
python test_subgoalcover.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/mbendagaik/subgoalcover>

---

## 关于作者

mbendagaik 做智能体子目标覆盖相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://mbendagaik.github.io>
- 仓库：<https://github.com/mbendagaik/subgoalcover>

## 许可

MIT，见 [LICENSE](LICENSE)。
