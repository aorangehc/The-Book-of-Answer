# The-Book-of-Answer

一个简洁的纯前端交互小作品，通过输入你的问题、翻开书页，给出「宇宙回应」。

## 特性
- 纯 HTML/CSS/JS，无依赖、无打包，开箱即用
- 3D 翻书动效与阴影质感，细节丰富
- 移动端优化，宽度与翻转行为自适应
- 随机但可重复的回答机制：同一问题在同一时刻得到一致答案；时间流逝答案变化

## 快速开始
- 方式一：直接双击打开 `book.html`
- 方式二：启用本地静态服务器后访问
  - Python：`python3 -m http.server 8000`，然后打开 `http://localhost:8000/book.html`
  - Node（可选）：`npx serve .`，按照终端输出的地址访问

## 使用指南
- 在封面输入框中输入你的问题，点击“翻开寻找答案”
- 书本翻转到背面，显示编号与答案
- 点击“再问一次”返回封面，再次提问

## 原理说明
- 答案集合定义在 `book.html` 的 `answers` 数组中
- 选择逻辑由一个“神秘计算公式”决定：
  - 时间因子 `now.getTime()` 与问题字符编码累加值相加
  - 对 `answers.length` 取模得到索引
- 该设计保证同一毫秒内、同一问题会得到同一答案；不同毫秒则可能变化

## 项目结构
```
.
├── book.html        # 页面、样式与脚本
├── LICENSE          # MIT 许可证
└── README.md        # 项目说明
```

## 自定义
- 修改配色与尺寸：在 `book.html` 的 `:root` CSS 变量中调整
- 替换字体：在 `<head>` 中的 Google Fonts 引入处替换为你喜欢的字体
- 更新答案集：编辑 `answers` 数组的文本内容
- 调整动效：修改 `.book.is-open` 的 `transform` 与过渡参数

## 部署
- 任意静态托管均可：GitHub Pages、Vercel、Netlify、Cloudflare Pages 等
- 将仓库公开并启用静态托管，入口文件指向 `book.html`

## 许可证
- MIT，详见 `LICENSE`

## 致谢
- 字体：Google Fonts 的 `Noto Serif SC`
