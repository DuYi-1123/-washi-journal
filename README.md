纸间·washi-journal
纸间 · washi-journal
「我感受到了 TN（Traveler's Notebook）的力量，它是一种被低估的治愈力。希望这份力量能带给更多人。」


一个浏览器里的电子手帐 / TN（Traveler's Notebook）拼贴簿。从上方工具栏把贴纸、便签、胶带拖到白纸页上排版，配上手写的笔触。所有内容只存在你的浏览器本地，不上传任何服务器。 打开就能用，关掉也不丢。


A browser-based digital Traveler's Notebook. Drag stickers, sticky notes,and washi tapes from the toolbar onto a paper page. Nothing leaves your
device — your journal lives only in your own browser.



为什么做这个

TN（Traveler's Notebook）的魅力不只是纸张和胶带——它是 「治愈自己的小动作」。
撕一片胶带、写一行字、贴一张从明信片里掉出来的贴纸，这个过程本身就是
一种和焦虑达成和解的方式。

我相信这种力量是被低估的。它不在效率工具的评分表上，也不在
「今日要完成 N 件事」的清单里，但它真的能让一个人在通勤的路上、
会议的间隙、睡前的几分钟里，重新做一会儿自己。

washi-journal 是我把这个体验搬到浏览器里的一次尝试：

没有账号、没有云端、没有社交压力—— 只有你和这一页纸
没有算法推荐你「今天应该打卡什么」—— 你想贴什么就贴什么
没有「完成度」统计—— 这本来就不是任务，是你给自己的喘息
如果你也曾被一本 TN / 一卷和纸胶带 / 一张贴纸疗愈过，欢迎把它分享给
身边那个「最近有点累」的朋友。也欢迎一起把它打磨得更好。

✨ 特性
🎨 40+ 张手绘风贴纸、12 款 washi 胶带 + 文本便签
🖱️ 在纸页上拖拽、缩放、按住 Option / Alt 旋转元素
✏️ 鼠标 / 触控笔自由涂鸦
💾 自动 localStorage 持久化 — 关闭浏览器再回来，内容还在
📱 自适应窗口（窄屏自动缩放）
🌿 极简风界面，没有弹窗、没有引导、没有「+1」等待
🚀 快速开始
需要 Node.js ≥ 18。

npm install
npm run dev     
# 打开 http://localhost:5173

生产构建：

npm run build
npm run preview

🛠️ 工具脚本

split_stickers.py — 把一张贴纸拼版图（assets/stickers.png）按
连通域拆成单张 PNG。8 邻域连通、过滤小连通域（毛边/噪点）、按面积排序、
外扩 4px 透明边：

pip install -r requirements.txt
python3 split_stickers.py
# 输出: output/sticker_001.png ... sticker_NNN.png

tools/preview_sheet.py — 把 output/ 里的贴纸拼成一张 6 列预览图，
方便一眼看全所有切出来的图。

🤝 一起把这个小口袋打磨下去

如果你也想让更多人感受到 TN 的治愈力，有很多种方式可以参与：
🎨 把自己喜欢的贴纸 / 胶带风格贡献给 public/
🐛 在 Issues 里报 bug 或提小改进
🌍 翻译界面文案，让它被更多语言的人用到
📸 把你的电子手帐页面截图发到 Discussions，让更多人知道这个东西存在
⭐ 给我点一颗星—— 这是我现在最大的动力来源



这个项目没有 KPI、没有路线图、没有 deadline。随时欢迎，慢一点也没关系。

📁 项目结构

.
├── index.html              # 入口
├── package.json
├── vite.config.js
├── src/                    # React 应用
│   ├── App.jsx             # 主组件（拖拽、缩放、旋转、笔触）
│   ├── catalog.jsx         # 工具栏 / 元素目录
│   ├── main.jsx
│   └── styles.css
├── public/                 # 静态资源（贴纸 / 胶带）
│   ├── stickers/extracted/
│   └── tapes/extracted/
├── assets/                 # 原始拼版图（单张 → 拆分）
│   └── stickers.png
├── split_stickers.py       # 贴纸拆图脚本
├── tools/preview_sheet.py  # 拼版预览图脚本
├── requirements.txt
└── output/                 # ⚠️ 由脚本生成，已 gitignore

📜 License

MIT
