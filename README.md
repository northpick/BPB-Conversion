# BPB-Conversion
将 BPB Work Panel 的 JSON 订阅转换为可被一键导入的通用格式（如： V2RayN 和 V2RayNG ）

# 0.关于本项目
随着 BPB Work Panel 的更新，最新版的 BPB Work Panel 编码方式已不支持被 V2RayN 和 V2RayNG 识别，导致订阅无法更新或者节点真实连接始终为-1。
此程序主要解决新版BPB worker panel订阅链接或节点因为识别问题，导致的无法更新和无法连接的问题。
本人学设计不怎么会编程，项目是用Claude刷了一下午刷出来的，后续应该不会大幅度更新。

# 1.总览：项目分为cloudflare worker部署版本和本地直接使用的html版本。
tips：本地使用浏览器会限制core，输入订阅链接可能无法获取到JSON数据，请手动粘贴JSON数据
你可以直接访问我在GitHub上部署的静态网站（手动输入json数据）
https://northpick.github.io/BPB-conversion.github/

# 2.如何打开：
（1）cloudflare worker部署：打开cloudflare->进入worker界面->创建helloword->修改代码->将项目worker.js替换掉cloudflare原本的worker.js->完成部署。
（2）本地直接使用：下载local-directly-use.html直接打开即可。

# 3.如何使用：
（1）复制BPB worker panel的任意订阅链接
（2）如果你是cloudflare部署：打开你的部署网站，粘贴订阅链接至“输入订阅链接（可选）”处，点击“📡获取链接”，此时JSON数据会自动粘贴至下方。
如果你是本地直接使用：在你的浏览器中打开订阅链接，全选复制JSON代码，将代码粘贴到打开的local-directly-use.html“或者直接粘贴JSON数据到这里...”处
（3）点击“🔄转换节点”按钮，可在“📤转换结果”看到具体的转换节点数量类型和通用代码
（4）点击“📋一键复制到全部”将通用代码写入剪切板
（5）在V2RayN中选择：配置文件->从剪切板导入分享链接，节点可成功导入V2RayN。
