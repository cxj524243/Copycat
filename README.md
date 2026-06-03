#

在Release处下载压缩包jcxnb.zip解压即可使用





# 偷瞄（copycat）—— Moodle 自动答题助手

一款针对华南师范大学 Moodle 平台的自动答题工具，基于 Playwright + DeepSeek API，自动识别题型并完成作答。
在Release处下载压缩包jcxnb.zip解压即可使用

---

## 快速开始

### 第一步：获取 API Key

1. 访问 [DeepSeek 官网](https://platform.deepseek.com/) 注册账号
2. 进入 **API Keys** 页面，创建一个新的 API Key
3. 复制保存，后续配置需要用到

### 第二步：首次配置

双击 **「首次配置.bat」**，按提示输入 API Key，脚本会自动完成环境检查。

### 第三步：开始答题

1. 先用浏览器登录 [华师 Moodle](https://moodle.scnu.edu.cn)
2. 双击 **「启动答题.bat」**
3. 终端会打开 Edge 浏览器（需已安装 Edge）
4. 脚本自动识别题目并调用 AI 作答
5. 答题完成后，在浏览器中手动点击「提交」按钮

---

## 免责声明

本工具仅供学习和研究使用。请遵守学校相关考试规定，合理使用。使用者需自行承担使用后果。
传播过程中注意使用初始化程序，注意避免API被盗用！！！


## 注意事项

### 浏览器要求
- 需要安装 **Microsoft Edge**
- 脚本会自动打开 Edge 浏览器进行操作

### 网络要求
- 需要能够访问 DeepSeek API（`api.deepseek.com`）
- 需要能够访问华师 Moodle（`moodle.scnu.edu.cn`）

### 登录说明
- 脚本会打开 Moodle 页面，需要你手动登录
- 登录成功后 Cookie 自动保存，下次无需重复登录

### 环境说明
- 本工具内置独立 Python 解释器和所有依赖库
- **不会影响**你电脑上已有的任何 Python 环境
- 所有程序在封闭环境中运行，开箱即用

### 题型支持

| 题型 | 支持情况 |
|------|---------|
| 单选题 | ✅ 支持 |
| 多选题 | ✅ 支持 |
| 判断题 | ✅ 支持 |
| 填空题 | ✅ 支持 |
| 论述题 | 🧪 实验性支持 |
| 拖拽题 | ❌ 暂不支持 |

---

## 常见问题
### Q：AI 回答不准确？
可以尝试在 `.env` 中更换其他兼容 OpenAI 接口的模型（修改 `BASE_URL` 和 `MODEL`）。

### Q：想换账号或重置数据？
双击 **「初始化环境.bat」**，会清除 API Key、Cookie、答题进度和日志，并自动检查环境完整性。


### Q：运行后浏览器没打开？
确保已安装 Microsoft Edge，且版本较新。

### Q：如何更新？
下载最新版安装包，解压覆盖即可。如需保留配置，提前备份 `.env` 和 `cookies.json`。

### Q：报错说环境异常？
双击 **「初始化环境.bat」** 自检，如果提示文件缺失或依赖损坏，重新解压安装包。

---

## 文件说明

```
偷瞄（copycat）/
├── python/                  Python 解释器（嵌入式，无需安装）
├── project/                 项目主目录
│   ├── main.py              主程序入口
│   ├── browser.py           浏览器控制（Playwright）
│   ├── ai_solver.py         AI 答题引擎（DeepSeek API）
│   ├── config.py            配置文件
│   ├── lib/                 第三方依赖库（已预装，共 28 个包）
│   ├── cookies.json         登录 Cookie（自动保存）
│   ├── progress.json        答题进度
│   └── logs/                运行日志
├── 首次配置.bat             填入 API Key
├── 启动答题.bat             启动自动答题
├── 初始化环境.bat           重置所有数据 + 自检完整性
└── 必看必看用前必看.md      本文件
```

---
