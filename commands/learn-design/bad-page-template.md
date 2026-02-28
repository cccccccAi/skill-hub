# 第4关：有问题的页面模板

本文件定义第 4 关"设计评审"中使用的 HTML 页面模板。AI 根据用户案例项目定制内容，但**必须保留以下 6 个预设问题**。

## 6 个预设问题

### 1. emoji 当图标（MEDIUM）

```html
<!-- ❌ 错误 -->
<span class="icon">☕</span>
<span class="icon">🎨</span>
<span class="icon">🏋️</span>

<!-- ✅ 正确：应使用 SVG 图标 -->
<svg class="w-6 h-6">...</svg>
```

### 2. 文字对比度不足（CRITICAL）

```html
<!-- ❌ 错误：浅色背景 + 浅灰文字，对比度 < 3:1 -->
<p style="color: #94A3B8; background: #F8FAFC;">这段文字很难看清</p>

<!-- ✅ 正确：对比度 > 4.5:1 -->
<p style="color: #0F172A; background: #F8FAFC;">这段文字清晰可读</p>
```

### 3. 点击区域太小（CRITICAL）

```html
<!-- ❌ 错误：按钮太小，手机上不好点 -->
<button style="padding: 4px 8px; font-size: 12px;">了解更多</button>

<!-- ✅ 正确：最小 44×44px 触摸目标 -->
<button style="padding: 12px 24px; min-height: 44px; font-size: 16px;">
  了解更多
</button>
```

### 4. 无 hover 反馈（MEDIUM）

```html
<!-- ❌ 错误：可点击的卡片没有任何 hover 效果 -->
<div onclick="navigate()" style="padding: 16px; border: 1px solid #e5e7eb;">
  可点击的卡片
</div>

<!-- ✅ 正确：cursor-pointer + hover 状态 -->
<div
  onclick="navigate()"
  style="padding: 16px; border: 1px solid #e5e7eb; cursor: pointer; transition: all 200ms;"
>
  可点击的卡片（hover 时有阴影变化）
</div>
```

### 5. 动画过慢（MEDIUM）

```html
<!-- ❌ 错误：动画 1.5 秒，感觉迟钝 -->
<div style="transition: all 1.5s ease;">缓慢的动画</div>

<!-- ✅ 正确：150-300ms -->
<div style="transition: all 200ms ease;">流畅的动画</div>
```

### 6. 水平滚动（HIGH）

```html
<!-- ❌ 错误：固定宽度导致手机端溢出 -->
<div style="width: 1200px;">
  <div style="display: flex; gap: 24px;">
    <div style="width: 300px;">卡片1</div>
    <div style="width: 300px;">卡片2</div>
    <div style="width: 300px;">卡片3</div>
    <div style="width: 300px;">卡片4</div>
  </div>
</div>

<!-- ✅ 正确：响应式布局 -->
<div style="max-width: 100%; overflow-x: hidden;">
  <div
    style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 24px;"
  >
    <div>卡片1</div>
    <div>卡片2</div>
    <div>卡片3</div>
    <div>卡片4</div>
  </div>
</div>
```

## 生成规则

1. 根据用户的案例项目定制页面内容（标题、文案、颜色等）
2. 使用第 1 关的"粗稿 v0"设计系统参数
3. **必须包含上述 6 个问题**，分散在页面不同区域
4. 页面结构：Hero + Features + CTA（简单三段式）
5. 保存到 `./design/output/bad-page.html`
6. 页面应该"看起来差不多"——不是明显丑，而是有专业级问题
