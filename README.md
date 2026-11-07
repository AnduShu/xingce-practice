# 行测在线刷题网站（GitHub Pages 静态部署版）

## 文件
- `index.html`：刷题网站。启动时自动请求同目录 `question_bank.json`。
- `question_bank.json`：首批 1000 道原创模拟练习题，按六个模块分类。
- `README.md`：部署与维护说明。

## 首批题库说明
首批 1000 道均标记为“原创模拟”，并非国考/省考历年真题。包含言语理解、判断推理、数量关系、资料分析、常识判断、政治理论。题库为机器辅助生成的初版，正式用于备考前应继续逐题校验答案、解析、事实时效性与题型质量；常识和政治理论题尤其需要按现行法规及最新政策复核。不要把它宣传为“1000道官方真题”。

## 网站如何长期读取公共题库
网站每次打开都会读取 `./question_bank.json`。要让所有访客看到更新：
1. 在本地编辑/生成 `question_bank.json`。
2. 打开 GitHub 仓库 `AnduShu/xingce-practice`。
3. 进入根目录，选择 `Add file` → `Upload files`，上传并覆盖 `question_bank.json`。
4. Commit changes，等待 GitHub Pages 自动重新部署。

注意：在网站“导入题库”页选择文件只会临时改变当前浏览器内存中的题库，不会自动写回 GitHub。公共题库必须通过提交文件更新。

## 学习记录
答题记录、错题本、收藏和模拟考试记录保存在访问者自己的浏览器 `localStorage`。无需注册，但不同设备/浏览器之间不会自动同步。

## 发布
仓库根目录至少应有 `index.html` 与 `question_bank.json`。GitHub Pages 设置：`Settings → Pages → Deploy from a branch → main → /(root)`。

## 真题来源与版权提示
可研究的真题整理项目：
- https://github.com/ERRRC/xingcezhenti：项目 README 自述包含 2016–2026 年 58,890 条题目记录；记录行数不等于去重后的唯一题数，且公开仓库本身不等于授予题目内容再发布许可。
- https://github.com/jangviktor-web/GongkaoNaoku：其代码仓库标示 Apache-2.0，但 README 明确说明原题版权归原作者/原题库平台，并提示仅供个人学习、小范围交流，不应公开传播真题内容。代码许可证不自动覆盖题目文本、材料和图片。

因此，本网站首批公开题库使用原创模拟题，不从上述仓库复制真题文本或图片。若以后加入真题，先取得明确的内容再发布授权，或只做本地个人使用。
