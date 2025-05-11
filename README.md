# Notyf - 轻量级纯JavaScript通知插件

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![jQuery](https://img.shields.io/badge/dependency-jQuery-green.svg)

一个简单、轻量级的通知插件，无需复杂配置即可实现优雅的消息提示。

## 特性

- 💡 纯JavaScript实现（依赖jQuery）
- 🎨 四种消息类型：success/error/warning/info
- ⏱️ 自动关闭和手动关闭
- 🔄 支持消息内容更新
- 🎚️ 自定义显示时长
- 📱 响应式设计

## 安装

### 直接引入

```html
<!-- 样式 -->
<link rel="stylesheet" href="dist/notyf.min.css">

<!-- 脚本 (需先引入jQuery) -->
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
<script src="dist/notyf.min.js"></script>
```

## 使用示例

### 基础用法

```javascript
// 显示成功消息（3秒后自动关闭）
notyf("操作成功完成");

// 显示错误消息
notyf("发生错误", "error", 5000);

// 手动关闭的消息
notyf("点击右上角关闭", "info", 0);
```

### 更新已有消息

```javascript
// 创建可更新的消息
var msgId = "progress-notify";
notyf("正在处理...", "info", 0, msgId);

// 更新消息
setTimeout(() => {
    notyf("处理完成！", "success", 2000, msgId);
}, 3000);
```

## API文档

### `notyf(str, type, time, id)`

- `str` (String): 消息内容
- `type` (String): 消息类型，可选值: `success`(默认)/`error`/`warning`/`info`
- `time` (Number): 显示时间(毫秒)，0表示不自动关闭
- `id` (String): 消息唯一ID（用于后续更新）

### `notyf_close(element)`

- `element` (jQuery Object): 要关闭的消息元素

## 自定义样式

通过修改CSS变量可自定义外观：

```css
:root {
    --notyf-success: #4CAF50;
    --notyf-error: #F44336;
    --notyf-warning: #FF9800;
    --notyf-info: #2196F3;
    --notyf-font-size: 14px;
}
```

## 浏览器支持

支持所有现代浏览器及IE9+

## 许可证

MIT
