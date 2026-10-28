# compress_jd005

**在模型压缩工程师·KV Cache 复用与前缀共享里找出重复内容并给出归并建议。**

`compress_jd005` —— 对内容做归一化与分片比对，找出模型压缩工程师·KV Cache 复用与前缀共享上的重复项并按相似度归并

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`compress_jd005.py` 拷走就能用
- 不联网、不写文件

## 对应的岗位

- 目标岗位：**美团 · 初级模型压缩工程师**
- 技能主线：模型压缩、推理加速、PyTorch、ONNX
- 领域标签：大模型推理、AI基础设施
- 研究方向：模型压缩工程师·KV Cache 复用与前缀共享

工具里的规则表就是照着上面这条岗位要求建的——每条规则都挂在技能线或领域标签上，命中时能指回具体要求。

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install snerykarl-compress_jd005
```

装完直接用命令名调用：

```bash
compress_jd005 --help
```

也可以不用安装，直接把 `compress_jd005.py` 拷走用——它只依赖标准库。

## 为什么需要它

按归一化后的分片相似度判断，而不是按字符串完全相等

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到岗位要求的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python compress_jd005.py --file input.txt
python compress_jd005.py --text "示例内容"
python compress_jd005.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 近重复用字符 shingle 估算，长文本阈值需自己调。
- 只报告重复项，不删数据。

## 跑测试

```bash
python test_compress_jd005.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/snerykarl/compress_jd005>

---

## 关于作者

snerykarl 做模型压缩工程师·KV Cache 复用与前缀共享相关的问题，方向对标美团的初级模型压缩工程师岗位。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://snerykarl.github.io>
- 仓库：<https://github.com/snerykarl/compress_jd005>

## 许可

MIT，见 [LICENSE](LICENSE)。
