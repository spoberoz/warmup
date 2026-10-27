# warmup

**分析冷启动耗时与预热策略。**

`warmup` —— 分解首次调用的加载与初始化耗时，标出最有效的预热动作

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`warmup.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install spoberoz-warmup
```

装完直接用命令名调用：

```bash
warmup --help
```

也可以不用安装，直接把 `warmup.py` 拷走用——它只依赖标准库。

## 为什么需要它

预热建议要说明预热什么，能直接照做

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 冷启动预热 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python warmup.py --file input.txt
python warmup.py --text "示例内容"
python warmup.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 时间排序按事件自带时间戳，不做时钟校正。
- 不判断因果，只呈现先后与重叠。

## 跑测试

```bash
python test_warmup.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/spoberoz/warmup>

---

## 关于作者

spoberoz 做冷启动预热相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://spoberoz.github.io>
- 仓库：<https://github.com/spoberoz/warmup>

## 许可

MIT，见 [LICENSE](LICENSE)。
