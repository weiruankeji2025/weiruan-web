# 智能网页分析助手 - Tampermonkey 脚本

一个功能强大的油猴脚本，使用 AI 技术分析网页内容，提供智能摘要和相关推荐。

## ✨ 功能特点

- 🤖 **多 AI 提供商支持**：支持 OpenAI、Google Gemini、Claude、通义千问、智谱AI、SiliconFlow、OhMyGPT
- 📝 **智能摘要**：自动提取网页核心内容并生成简洁摘要
- 💡 **要点梳理**：总结网页的关键信息点
- 🔗 **相关推荐**：基于内容推荐相关的优质网站和资源
- 🎨 **优雅界面**：现代化设计，支持亮色/暗色主题
- 📱 **响应式设计**：浮动面板可自由拖拽，不遮挡关键内容
- ⚙️ **灵活配置**：支持自定义 API 提供商和模型选择
- 💾 **智能缓存**：分析结果缓存1小时，避免重复请求

## 🚀 安装步骤

### 1. 安装 Tampermonkey

首先需要安装 Tampermonkey 浏览器扩展：

- **Chrome**: [Chrome Web Store](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo)
- **Firefox**: [Firefox Add-ons](https://addons.mozilla.org/firefox/addon/tampermonkey/)
- **Edge**: [Edge Add-ons](https://microsoftedge.microsoft.com/addons/detail/tampermonkey/iikmkjmpaadaobahmlepeloendndfphd)
- **Safari**: [App Store](https://apps.apple.com/app/tampermonkey/id1482490089)

### 2. 安装脚本

1. 点击 Tampermonkey 图标，选择"添加新脚本"
2. 复制 `webpage-analyzer.user.js` 的全部内容
3. 粘贴到编辑器中并保存（Ctrl+S 或 Cmd+S）

### 3. 配置 API

1. 访问任意网页，右上角会出现分析助手面板
2. 点击设置按钮（⚙️）
3. 选择 AI 提供商（推荐使用 Gemini、SiliconFlow 或通义千问）
4. 选择模型
5. 输入对应的 API Key
6. 点击保存

#### 推荐的 AI 提供商

| 提供商 | 优势 | API Key 获取地址 | 备注 |
|--------|------|-----------------|------|
| **SiliconFlow** ⭐⭐ | 国内稳定，支持最新模型，注册送免费额度 | [硅基流动](https://cloud.siliconflow.cn/account/ak) | 支持 DeepSeek-V3、Qwen、Yi-Lightning 等 |
| **Google Gemini** ⭐⭐ | 免费额度高，速度快，稳定性好 | [Google AI Studio](https://aistudio.google.com/app/apikey) | 推荐使用 gemini-2.0-flash-exp |
| **OhMyGPT** ⭐ | 统一接口，支持多种模型 | [OhMyGPT](https://www.ohmygpt.com/) | 一个API支持GPT/Claude/Gemini |
| **通义千问** | 国内访问快，有免费额度 | [阿里云控制台](https://dashscope.console.aliyun.com/apiKey) | 阿里巴巴出品 |
| **智谱AI** | 国内访问快，新用户免费额度 | [智谱开放平台](https://open.bigmodel.cn/usercenter/apikeys) | 清华技术 |
| **Claude** | 最强推理能力，适合复杂分析 | [Anthropic Console](https://console.anthropic.com/settings/keys) | 需要付费，但效果极佳 |
| **OpenAI** | 功能强大，但速率限制严格 | [OpenAI Platform](https://platform.openai.com/api-keys) | 免费额度有限 |

**重要提示**：
- 推荐国内用户使用 **SiliconFlow** 或**通义千问**，访问速度快且稳定
- 如果使用免费的 OpenAI API 遇到速率限制（429错误），建议切换到 SiliconFlow 或 Gemini
- OhMyGPT 提供统一接口，无需频繁切换提供商

## 📖 使用说明

### 基本操作

1. **开始分析**：点击播放按钮（▶️）开始分析当前页面
2. **切换主题**：点击月亮/太阳图标切换亮色/暗色主题
3. **最小化面板**：点击减号（−）最小化面板，点击浮动按钮恢复
4. **拖拽移动**：按住标题栏可以拖拽移动面板位置

### 查看结果

分析完成后会显示四个部分：

- **📝 内容摘要**：页面内容的简洁概述
- **💡 核心要点**：提炼的关键信息点
- **📑 内容类型**：识别网页类型（文章、产品页、文档等）
- **🔗 相关推荐**：推荐的相关网站（点击可直接访问）

## 🎨 界面预览

### 亮色主题
- 清新简洁的白色界面
- 柔和的阴影和圆角设计
- 优雅的过渡动画

### 暗色主题
- 护眼的深色背景
- 高对比度的文字显示
- 适合夜间使用

## ⚙️ 技术说明

### 使用的技术栈

- **Tampermonkey API**：脚本运行环境
- **多 AI API 集成**：OpenAI、Google Gemini、Claude、通义千问、智谱AI、SiliconFlow、OhMyGPT
- **原生 JavaScript**：核心逻辑实现
- **CSS3**：现代化界面样式

### 内容提取逻辑

脚本会智能提取以下内容：
- 页面标题和 URL
- Meta 描述和关键词
- 主要文章内容（`<article>`, `<main>`, `.content` 等）
- 段落文本（过滤掉过短的内容）

### API 调用

- 支持多个 AI 提供商的统一接口
- 自动格式转换和响应解析
- 智能重试机制（指数退避策略）
- 请求冷却和速率限制保护
- 分析结果缓存（1小时有效期）

**支持的模型：**
- **OpenAI**: gpt-4o-mini, gpt-4o, gpt-4-turbo, gpt-3.5-turbo
- **Gemini**: gemini-2.0-flash-exp, gemini-2.0-flash-thinking-exp, gemini-1.5-flash, gemini-1.5-pro
- **Claude**: claude-3-5-sonnet, claude-3-5-haiku, claude-3-opus
- **通义千问**: qwen-turbo, qwen-plus, qwen-max
- **智谱AI**: glm-4-flash, glm-4-plus, glm-4-air
- **SiliconFlow**: DeepSeek-V3, Qwen2.5-7B/72B, Yi-Lightning, GLM-4, Llama-3.1 系列
- **OhMyGPT**: 支持所有主流模型（GPT、Claude、Gemini）

## 🔒 隐私与安全

- ✅ API Key 使用 Tampermonkey 的本地存储，不会上传
- ✅ 仅在用户主动点击时才发送数据到 AI 提供商
- ✅ 不收集、存储或传输用户浏览数据
- ✅ 开源代码，可自行审查

## 🛠️ 自定义配置

如需修改默认配置，可编辑脚本中的 `CONFIG` 对象：

\`\`\`javascript
const CONFIG = {
    API_PROVIDER: 'openai',  // 默认提供商: openai, gemini, claude, qwen, zhipu, siliconflow, ohmygpt
    API_KEY: '',  // 默认 API Key
    MODEL: 'gpt-4o-mini',  // 默认模型
    REQUEST_COOLDOWN: 15000,  // 请求冷却时间（毫秒）
    CACHE_EXPIRY: 3600000,  // 缓存过期时间（毫秒，默认1小时）
};
\`\`\`

## 📝 注意事项

1. **API Key 安全**：不要在公共场合分享您的 API Key
2. **费用控制**：大部分提供商都有免费额度，但仍需注意使用量
3. **内容长度**：脚本会自动限制发送内容长度（5000 字符）
4. **兼容性**：建议在现代浏览器中使用（Chrome 90+, Firefox 88+, Edge 90+）
5. **国内用户**：推荐使用 SiliconFlow 或通义千问，访问速度更快更稳定

## 🔛 故障排除

### 问题：遇到 429 速率限制错误
- **原因**：免费 API 有严格的速率限制
- **解决方案**：
  1. 切换到 SiliconFlow（推荐，国内稳定且免费额度高）
  2. 切换到 Google Gemini（国际用户推荐）
  3. 切换到通义千问或智谱AI（国内访问快）
  4. 等待1-2分钟后重试
  5. 检查 API 配额是否用尽

### 问题：点击分析后没有反应
- 检查是否已配置 API Key
- 打开浏览器控制台（F12）查看错误信息
- 确认 API Key 有效且有余额
- 检查网络连接是否正常

### 问题：分析结果不准确
- 部分网页可能有特殊结构，内容提取不完整
- 可以尝试刷新页面后重新分析
- 尝试切换不同的 AI 模型

### 问题：面板显示异常
- 可能与其他脚本或扩展冲突
- 尝试禁用其他脚本测试
- 清除浏览器缓存后重试

### 问题：API 请求失败
- 检查 @connect 权限是否正确
- 确认防火墙或代理设置没有阻止请求
- 对于国内用户，建议使用通义千问或智谱AI

## 🔗 相关链接

- [SiliconFlow 硅基流动](https://cloud.siliconflow.cn/)
- [Google AI Studio](https://aistudio.google.com/)
- [Claude (Anthropic)](https://console.anthropic.com/)
- [OhMyGPT](https://www.ohmygpt.com/)
- [OpenAI Platform](https://platform.openai.com/)
- [通义千问](https://dashscope.aliyuncs.com/)
- [智谱AI](https://open.bigmodel.cn/)
- [Tampermonkey 官网](https://www.tampermonkey.net/)
- [项目 GitHub 仓库](#)

## 📧 联系方式

如有问题或建议，欢迎通过 GitHub Issues 联系。

---

**⭐ 如果觉得这个脚本有用，请给个 Star！**
