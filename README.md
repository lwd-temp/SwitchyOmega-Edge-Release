# SwitchyOmega-Edge-Release
适用于Microsoft Edge浏览器的SwitchyOmega扩展构建方法

这是一份简易操作方法指引。

## 分步操作流程

### 准备工作
* 从SwitchyOmega发布页[下载crx文件](https://github.com/FelisCatus/SwitchyOmega/releases/download/v2.5.20/SwitchyOmega_Chromium.crx)
* 使用7-Zip将其解压

### 必要的修改
根据[Edge开发者文档](https://docs.microsoft.com/en-us/microsoft-edge/extensions-chromium/developer-guide/port-chrome-extension)的指引，我们需要在`manifest.json`中检查：
* 为了便于检查，可以先将`manifest.json`格式化
* 检查API请求是否包含在[Edge的API列表](https://docs.microsoft.com/en-us/microsoft-edge/extensions-chromium/developer-guide/api-support)中，在本扩展中似乎不存在此问题
* 移除`update_URL`
* 移除`key`
* 打开Edge浏览器的开发人员模式，加载解压后的扩展，检查错误提示

### 处理错误
以下错误出现在报告中：

#### Unrecognized manifest key 'applications'.
移除`manifest.json`中的`applications`。

#### Manifest version 2 is deprecated, and support will be removed in 2023. See https://developer.chrome.com/blog/mv2-transition/ for more details.
修复此问题可能需要重写插件的部分功能。在2023年前，我们还不需要担心这个问题。

其余的问题不来自迁移扩展，不做修改。

### 发布扩展
在此不作赘述。
