# 行测5000+ 在线刷题网站（静态部署版）

## 当前交付内容
- `index.html`：可直接运行的单页刷题网站，无需安装、无需注册、无需后端。
- `sample_questions.json`：12道原创演示题，可用于测试导入功能。
- 练习、随机抽题、模块/年份/地区/难度筛选、每日一练、错题本、收藏、计时模拟考试、学习统计、学习记录导出。
- 浏览器本地保存答题记录（localStorage）；不同设备/浏览器之间不会自动同步。
- 导入 JSON 时按 ID 与“题干+选项”指纹去重。

## 本地运行
直接双击 `index.html` 即可使用；也可用 VS Code Live Server 打开。

## 导入题库格式
文件顶层是 JSON 数组，每条记录格式如下：

```json
{
  "id": "唯一ID",
  "module": "言语理解",
  "type": "国考真题",
  "year": "2024",
  "province": "国家",
  "difficulty": "中",
  "stem": "题干",
  "options": ["A. 选项一", "B. 选项二", "C. 选项三", "D. 选项四"],
  "answer": "B",
  "explanation": "答案解析"
}
```

## 发布到公网（GitHub Pages）
1. 登录 GitHub，创建一个 Public 仓库，例如 `xingce-practice`。
2. 将解压后的 `index.html`、`sample_questions.json`、`README.md` 上传到仓库根目录。
3. 打开仓库 `Settings` → `Pages`。
4. 在 `Build and deployment` 中选择 `Deploy from a branch`。
5. Branch 选择 `main`，目录选择 `/ (root)`，点击 `Save`。
6. 等待部署完成，网址通常为 `https://你的GitHub用户名.github.io/xingce-practice/`。
7. 进入 Pages 页面点击 `Visit site`，取得实际公网网址。

也可使用 Cloudflare Pages：选择连接 Git 仓库，框架预设选 `None`，构建命令留空，输出目录填 `/` 或仓库根目录。

## 重要：5000道真实题库的接入与版权
本交付包内只有12道原创演示题，**并未声称已经包含5000道真题**。
可研究的公开数据来源：
- https://github.com/ERRRC/xingcezhenti
  仓库 README 声称包含 58,890 条题目记录（2016–2026，515套卷）。但同一仓库的蒸馏参考说明指出跨省联考会重复收录，言语理解模块 16,000 条按题干+选项去重后为 6,292 条。记录数不等于唯一题数。
- https://github.com/jangviktor-web/GongkaoNaoku
  可参考其题库处理与刷题功能实现；其说明亦提醒题库原题版权归原作者。

在公开上线、分享或商业使用前，请核对上游仓库的 LICENSE、题目来源及相关版权/授权。若没有明确授权，建议只导入自有授权题目或原创模拟题。当前导入器会自动跳过相同 ID 或相同题干+选项指纹的重复记录，但图片型题目、材料题、改写题可能需要人工复核。

## 当前版本限制
- 学习数据只存在当前浏览器；清理浏览器数据可能导致记录丢失，请定期导出备份。
- 当前版本不含账号体系、云端同步、管理员后台。
- 当前题库样例为原创演示题，不是官方真题；完整 5000 道经去重、授权核验的题库需要单独整理后导入。
