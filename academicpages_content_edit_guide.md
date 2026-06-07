# academicpages 个人主页内容修改指南

适用仓库：`zhangshanwei-mm/zhangshanwei-mm.github.io`

网站地址：`https://zhangshanwei-mm.github.io/`

这份指南按“你想修改网站上的什么内容 -> 去哪个文件改 -> 怎么改”的方式整理。大多数日常维护只需要改 `_config.yml`、`_pages/about.md`、`_data/navigation.yml`、`_publications/`、`_talks/`、`_teaching/`、`files/` 和 `images/`。

## 1. 修改前先记住

1. GitHub Pages 默认从 `master` 分支构建。
2. 每次修改并提交后，进入仓库的 `Actions` 页面，等待最新一次构建变成绿色对勾。
3. 构建成功后访问 `https://zhangshanwei-mm.github.io/`，如果刚提交后没有立刻更新，等 1 到 5 分钟再刷新。
4. Markdown 文件开头的 `---` 到 `---` 之间叫 front matter，控制标题、链接、日期、布局等。正文写在第二个 `---` 后面。
5. 文件名、图片名、PDF 名建议只用英文、数字、短横线和下划线，少用空格。

## 2. 网站基本信息

修改文件：`_config.yml`

主要改这些字段：

```yml
title                    : "Shanwei Zhang"
name                     : &name "Shanwei Zhang"
description              : &description "Academic portfolio of Shanwei Zhang"
url                      : https://zhangshanwei-mm.github.io
baseurl                  : ""
repository               : "zhangshanwei-mm/zhangshanwei-mm.github.io"
```

这些字段分别控制：

| 网站内容 | 修改位置 |
|---|---|
| 浏览器标签页标题、站点标题 | `_config.yml` 里的 `title` |
| 你的姓名 | `_config.yml` 里的 `name` |
| 网站简介、搜索引擎描述 | `_config.yml` 里的 `description` |
| 网站网址 | `_config.yml` 里的 `url` |
| 个人主页根路径 | `_config.yml` 里的 `baseurl`，这里保持 `""` |
| GitHub 仓库名 | `_config.yml` 里的 `repository` |
| 主题配色 | `_config.yml` 里的 `site_theme` |

你的仓库目前 `url`、`baseurl`、`repository` 已经应该保持成：

```yml
url                      : https://zhangshanwei-mm.github.io
baseurl                  : ""
repository               : "zhangshanwei-mm/zhangshanwei-mm.github.io"
```

## 3. 左侧个人信息栏

修改文件：`_config.yml`

找到 `author:` 这一段。

常用字段：

```yml
author:
  avatar           : "profile.png"
  name             : "Shanwei Zhang"
  bio              : "Your short research bio"
  location         : "City, Country"
  employer         : "Your institution"
  uri              : "https://zhangshanwei-mm.github.io"
  email            : "your_email@example.com"

  googlescholar    : "https://scholar.google.com/citations?user=你的ID"
  orcid            : "https://orcid.org/你的ORCID"
  pubmed           :
  researchgate     :
  github           : "zhangshanwei-mm"
  linkedin         :
  twitter          :
  zhihu            :
```

对应关系：

| 网站内容 | 修改位置 |
|---|---|
| 左侧头像 | `images/profile.png`，同时 `_config.yml` 里 `author.avatar: "profile.png"` |
| 左侧姓名 | `_config.yml` -> `author.name` |
| 左侧一句话简介 | `_config.yml` -> `author.bio` |
| 地点 | `_config.yml` -> `author.location` |
| 单位 | `_config.yml` -> `author.employer` |
| 邮箱 | `_config.yml` -> `author.email` |
| Google Scholar | `_config.yml` -> `author.googlescholar` |
| ORCID | `_config.yml` -> `author.orcid` |
| GitHub 链接 | `_config.yml` -> `author.github`，建议填 `zhangshanwei-mm` |
| LinkedIn、知乎、微博等 | `_config.yml` -> `author.linkedin`、`author.zhihu`、`author.weibo` 等 |

如果某个链接不想显示，冒号后面留空即可。

## 4. 首页 / About 页面正文

修改文件：`_pages/about.md`

这个文件通常就是网站首页。它的开头大概像这样：

```md
---
permalink: /
title: "About me"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---
```

修改方式：

| 网站内容 | 修改位置 |
|---|---|
| 首页标题 | `_pages/about.md` 里的 `title` |
| 首页正文介绍 | `_pages/about.md` 第二个 `---` 下面的正文 |
| 是否显示左侧个人栏 | `_pages/about.md` 里的 `author_profile: true` |
| 首页链接 | `_pages/about.md` 里的 `permalink: /`，不要随便改 |

建议把模板自带的介绍文字全部替换成你的真实简介，例如：

```md
I am Shanwei Zhang. My research focuses on ...

## Research Interests

- Biomedical signal processing
- ECG and clinical AI
- Machine learning for health data

## News

- 2026-06: I launched this academic website.
```

## 5. 顶部导航栏

修改文件：`_data/navigation.yml`

这个文件控制顶部菜单显示哪些入口、顺序是什么、链接到哪里。

常见结构：

```yml
main:
  - title: "Publications"
    url: /publications/

  - title: "Talks"
    url: /talks/

  - title: "Teaching"
    url: /teaching/

  - title: "CV"
    url: /cv/
```

对应关系：

| 网站内容 | 修改位置 |
|---|---|
| 顶部菜单文字 | `_data/navigation.yml` 里的 `title` |
| 顶部菜单链接 | `_data/navigation.yml` 里的 `url` |
| 菜单顺序 | `_data/navigation.yml` 中条目的上下顺序 |
| 隐藏某个菜单 | 删除或注释掉对应的 `- title:` 条目 |
| 增加新菜单 | 在 `main:` 下新增一组 `title` 和 `url` |

如果暂时没有 `Talks` 或 `Teaching` 内容，可以先从导航栏删除，等以后需要再加回来。

## 6. Publications 论文页面

列表页文件：`_pages/publications.html`

论文条目目录：`_publications/`

你的仓库目前 `_publications/` 里还有模板示例，例如：

```text
_publications/2009-10-01-paper-title-number-1.md
_publications/2010-10-01-paper-title-number-2.md
_publications/2015-10-01-paper-title-number-3.md
_publications/2024-02-17-paper-title-number-4.md
_publications/2025-06-08-paper-title-number-5.md
```

这些示例可以删除，或者改成你自己的论文。

新增一篇论文时，在 `_publications/` 里新建一个 Markdown 文件，建议命名：

```text
_publications/2026-06-01-paper-short-title.md
```

示例：

```md
---
title: "Paper title"
collection: publications
category: manuscripts
permalink: /publication/2026-06-01-paper-short-title
excerpt: "One sentence summary of this paper."
date: 2026-06-01
venue: "Journal or Conference Name"
paperurl: "https://doi.org/..."
citation: "Zhang S, et al. Paper title. Journal, 2026."
---

Short description, abstract, highlights, code link, or notes.
```

常用字段：

| 论文内容 | 修改位置 |
|---|---|
| 论文标题 | 单篇论文 `.md` 的 `title` |
| 论文日期 | 单篇论文 `.md` 的 `date` |
| 期刊/会议 | 单篇论文 `.md` 的 `venue` |
| DOI 或论文链接 | 单篇论文 `.md` 的 `paperurl` |
| 引用格式 | 单篇论文 `.md` 的 `citation` |
| 论文分类 | 单篇论文 `.md` 的 `category` |
| 页面链接 | 单篇论文 `.md` 的 `permalink` |
| 论文详情页正文 | 单篇论文 `.md` 第二个 `---` 后面的正文 |

论文分类标题在 `_config.yml` 里改：

```yml
publication_category:
  books:
    title: 'Books'
  manuscripts:
    title: 'Journal Articles'
  conferences:
    title: 'Conference Papers'
```

如果你想改成中文或更符合医学方向的分类，可以改成：

```yml
publication_category:
  manuscripts:
    title: 'Journal Articles'
  conferences:
    title: 'Conference Papers'
  preprints:
    title: 'Preprints'
```

注意：如果新增 `preprints`，论文文件里的 `category: preprints` 才会对应上。

## 7. Talks 演讲 / 报告页面

列表页文件：`_pages/talks.html`

报告条目目录：`_talks/`

新增报告时，在 `_talks/` 里新建文件：

```text
_talks/2026-06-01-talk-title.md
```

示例：

```md
---
title: "Talk title"
collection: talks
type: "Conference presentation"
permalink: /talks/2026-06-01-talk-title
venue: "Conference or Institution"
date: 2026-06-01
location: "City, Country"
---

Short description of the talk.
```

对应关系：

| 报告内容 | 修改位置 |
|---|---|
| 报告标题 | `_talks/*.md` 的 `title` |
| 报告类型 | `_talks/*.md` 的 `type` |
| 会议或机构 | `_talks/*.md` 的 `venue` |
| 日期 | `_talks/*.md` 的 `date` |
| 地点 | `_talks/*.md` 的 `location` |
| 详情 | `_talks/*.md` 正文 |

如果不需要地图页面，可以在 `_config.yml` 里保持：

```yml
talkmap_link             : false
```

## 8. Teaching 教学页面

列表页文件：`_pages/teaching.html`

教学条目目录：`_teaching/`

新增课程时，在 `_teaching/` 里新建文件：

```text
_teaching/2026-spring-course-name.md
```

示例：

```md
---
title: "Course title"
collection: teaching
type: "Undergraduate course"
permalink: /teaching/2026-spring-course-name
venue: "Institution"
date: 2026-02-01
location: "City, Country"
---

Course description, responsibilities, syllabus, or teaching materials.
```

如果你暂时没有教学内容，可以删除 `_data/navigation.yml` 里的 Teaching 菜单项。

## 9. Portfolio 项目页面

列表页文件：`_pages/portfolio.html`

项目条目目录：`_portfolio/`

适合放：

- 研究项目
- 软件工具
- 数据集
- Demo
- 开源代码

新增项目示例：

```md
---
title: "Project title"
collection: portfolio
permalink: /portfolio/project-title
excerpt: "One sentence project summary."
---

Project description, figures, links, and outcomes.
```

如果不需要项目页，可以删除 `_data/navigation.yml` 里的 Portfolio 菜单项。

## 10. CV 页面

手写 CV 页面：`_pages/cv.md`

JSON CV 数据：`_data/cv.json`

JSON CV 页面：`_pages/cv-json.md`

推荐新手先改 `_pages/cv.md`，因为它就是普通 Markdown，最直观。

你可以在 `_pages/cv.md` 里写：

```md
---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
---

## Education

- Ph.D., ...

## Experience

- ...

## Publications

- ...
```

如果你有 PDF 简历，把文件放到 `files/` 目录，例如：

```text
files/Shanwei_Zhang_CV.pdf
```

然后在 `_pages/cv.md` 里链接：

```md
[Download PDF CV](/files/Shanwei_Zhang_CV.pdf)
```

## 11. Blog / News 文章

文章目录：`_posts/`

文件名必须用这种格式：

```text
_posts/YYYY-MM-DD-title.md
```

示例：

```text
_posts/2026-06-07-website-launched.md
```

内容示例：

```md
---
title: "Website launched"
date: 2026-06-07
permalink: /posts/2026/06/website-launched/
tags:
  - news
---

I launched my academic website today.
```

对应关系：

| 内容 | 修改位置 |
|---|---|
| 文章标题 | `_posts/*.md` 的 `title` |
| 发布日期 | 文件名日期和 `date` |
| 文章链接 | `permalink` |
| 标签 | `tags` |
| 正文 | 第二个 `---` 后面 |

如果只想在首页放 News，不想单独开 Blog 页面，可以直接在 `_pages/about.md` 里写 News 列表。

## 12. 图片

图片目录：`images/`

常见用法：

| 图片用途 | 放在哪里 | 怎么引用 |
|---|---|---|
| 左侧头像 | `images/profile.png` | `_config.yml` -> `author.avatar: "profile.png"` |
| 首页图片 | `images/your-image.png` | `![caption](/images/your-image.png)` |
| 论文或项目配图 | `images/project-figure.png` | `![caption](/images/project-figure.png)` |
| 社交分享图 | `images/og-image.png` | `_config.yml` -> `og_image: /images/og-image.png` |

Markdown 中插入图片：

```md
![ECG figure](/images/ecg-figure.png)
```

头像建议用正方形图片，例如 `400x400` 或 `800x800`。

## 13. PDF、Word、附件

附件目录：`files/`

适合放：

- CV PDF
- 论文 PDF
- Supplementary materials
- Slides
- Dataset description

引用方式：

```md
[Download CV](/files/Shanwei_Zhang_CV.pdf)
[Download slides](/files/talk-slides.pdf)
```

如果在论文条目里放 PDF，也可以这样写：

```yml
paperurl: "/files/my-paper.pdf"
```

## 14. 页面标题和链接

大多数页面都在 `_pages/` 里。

常见页面：

| 网站页面 | 修改文件 |
|---|---|
| 首页 / About | `_pages/about.md` |
| Publications 列表页 | `_pages/publications.html` |
| Talks 列表页 | `_pages/talks.html` |
| Teaching 列表页 | `_pages/teaching.html` |
| Portfolio 列表页 | `_pages/portfolio.html` |
| CV | `_pages/cv.md` |
| 404 页面 | `_pages/404.md` |
| Terms | `_pages/terms.md` |
| Sitemap | `_pages/sitemap.md` |

页面开头常见字段：

```md
---
title: "Page title"
permalink: /page-url/
author_profile: true
---
```

对应关系：

| 页面属性 | 修改位置 |
|---|---|
| 页面显示标题 | `title` |
| 页面 URL | `permalink` |
| 是否显示左侧个人栏 | `author_profile` |
| 页面正文 | 第二个 `---` 后面 |

## 15. 网站颜色和主题

最简单：改 `_config.yml` 的 `site_theme`。

可选值通常包括：

```yml
site_theme               : "default"
```

可尝试：

```yml
site_theme               : "air"
site_theme               : "sunrise"
site_theme               : "mint"
site_theme               : "dirt"
site_theme               : "contrast"
```

高级自定义样式在：

```text
_sass/
assets/css/
```

不熟悉 CSS 时，不建议先改 `_sass/`。

## 16. 页脚、作者栏、布局

这些属于高级修改：

| 想改的内容 | 文件位置 |
|---|---|
| 左侧作者栏 HTML 结构 | `_includes/author-profile.html` |
| 页脚 | `_includes/footer.html` 或相关 include 文件 |
| 顶部 masthead | `_includes/masthead.html` |
| 页面布局模板 | `_layouts/` |
| 列表项显示方式 | `_includes/archive-single.html` 或相关 include 文件 |

一般只改内容时，不需要动 `_includes/` 和 `_layouts/`。

## 17. SEO、统计和社交分享

修改文件：`_config.yml`

常见字段：

```yml
google_site_verification :
bing_site_verification   :

analytics:
  provider               : "false"
  google:
    tracking_id          :

og_image                 :
og_description           :
```

对应关系：

| 内容 | 修改位置 |
|---|---|
| Google Search Console 验证 | `_config.yml` -> `google_site_verification` |
| Bing 验证 | `_config.yml` -> `bing_site_verification` |
| Google Analytics | `_config.yml` -> `analytics` |
| 分享预览图 | `_config.yml` -> `og_image` |
| 分享描述 | `_config.yml` -> `og_description` |

## 18. 不建议随便改的文件

这些文件主要和构建、依赖、模板逻辑有关：

```text
Gemfile
Dockerfile
docker-compose.yaml
package.json
.github/workflows/
_layouts/
_includes/
_sass/
assets/js/
```

除非你明确知道要改构建流程、布局或样式，否则先不要动。

## 19. 推荐的第一次清理顺序

1. 改 `_config.yml`：站点标题、姓名、简介、作者信息、社交链接。
2. 替换 `images/profile.png`：放你的头像。
3. 改 `_pages/about.md`：写真实首页介绍。
4. 改 `_data/navigation.yml`：只保留需要的菜单。
5. 清理 `_publications/`：删除模板论文，添加你的论文。
6. 清理 `_talks/`、`_teaching/`、`_portfolio/`：暂时不用就删除菜单或留空。
7. 改 `_pages/cv.md`：写简历，或上传 PDF 到 `files/`。
8. 提交修改，去 `Actions` 等绿色对勾。
9. 打开 `https://zhangshanwei-mm.github.io/` 检查效果。

## 20. GitHub 网页端修改流程

1. 打开仓库：`https://github.com/zhangshanwei-mm/zhangshanwei-mm.github.io`
2. 点击要修改的文件。
3. 点击右上角铅笔图标。
4. 修改内容。
5. 点击 `Commit changes`。
6. 进入 `Actions`。
7. 等最新构建变成绿色对勾。
8. 访问 `https://zhangshanwei-mm.github.io/` 查看效果。

## 21. 常见错误

| 问题 | 常见原因 | 修复方式 |
|---|---|---|
| 网站 404 | Actions 还没跑完，或仓库名/Pages 设置错误 | 等 Actions 完成；确认仓库名是 `zhangshanwei-mm.github.io` |
| 修改后网站没变化 | GitHub Pages 缓存或 Actions 失败 | 等几分钟；检查 Actions 报错 |
| 图片不显示 | 图片路径写错 | 图片放 `images/`，引用 `/images/file.png` |
| PDF 不显示 | 文件路径写错 | 文件放 `files/`，引用 `/files/file.pdf` |
| 页面链接打不开 | `permalink` 写错或导航链接不匹配 | 检查 `_pages/*.md` 和 `_data/navigation.yml` |
| 论文不显示 | front matter 缺少 `collection: publications` 或分类不匹配 | 检查 `_publications/*.md` |
| 左侧 GitHub 还是 academicpages | `_config.yml` 里 `author.github` 没改 | 改成 `github: "zhangshanwei-mm"` |
| 首页还是模板文字 | `_pages/about.md` 没替换正文 | 删除模板文字，写自己的简介 |

## 22. 最小可用修改清单

如果你只想先让网站像一个真实个人主页，先完成这些：

- `_config.yml`：改 `title`、`name`、`description`
- `_config.yml`：改 `author.name`、`author.bio`、`author.location`、`author.employer`、`author.email`
- `_config.yml`：把 `author.github` 改成 `zhangshanwei-mm`
- `images/profile.png`：换成你的头像
- `_pages/about.md`：改首页正文
- `_data/navigation.yml`：删掉暂时不用的菜单
- `_publications/`：删除模板论文，添加真实论文
- `_pages/cv.md`：写简历或放 PDF 链接

完成这些后，网站就可以先公开使用，再慢慢补充细节。
