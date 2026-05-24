# JD2Resume

根据岗位 JD（Job Description）优化现有简历，支持解析 JD 关键词、分析匹配度、微调简历内容、生成多种格式输出。

## 功能

- **JD 解析**：从纯文本、截图或网页链接中提取岗位关键词
- **匹配度分析**：对比 JD 要求与简历内容，标记已覆盖/偏差/缺失项
- **简历优化**：基于匹配结果调整叙述角度，自然融入关键词
- **多格式输出**：生成 HTML、PDF、长截图三种格式的简历文件

## 使用方式

### 作为 Claude Code Skill

将本项目作为 Claude Code 的 Skill 使用，支持五步交互式流程：

1. 岗位解析：发送 JD，提取关键词
2. 简历输入：提供现有简历内容
3. 匹配与调整：分析匹配度，制定优化方案
4. 用户确认：预览修改计划并确认
5. 最终输出：生成优化后的简历文件

### 脚本工具

```bash
# 生成 HTML 简历
python3 scripts/generate_html_resume.py --input resume_data.json --output resume.html

# HTML 转 PDF
python3 scripts/html_to_pdf.py --input resume.html --output resume.pdf

# HTML 转长截图
python3 scripts/screenshot_resume.py --input resume.html --output resume.png
```

## 项目结构

```
.
├── SKILL.md                    # Skill 定义与交互流程
├── scripts/
│   ├── generate_html_resume.py # 生成 HTML 简历
│   ├── html_to_pdf.py          # HTML 转 PDF
│   └── screenshot_resume.py    # HTML 转长截图
├── assets/
│   └── resume-template.html    # 简历 HTML 模板
└── references/
    └── workflow.md             # 详细流程文档
```

## 核心原则

- **不编造**：保留事实，只调整叙述角度
- **自然嵌入**：关键词融入上下文，不硬塞
- **一页纸约束**：控制信息密度，按岗位相关性排序
- **量化但不硬编**：有数据就放，没数据不写假数字

## License

MIT
