<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CrescentFlux Digital Hub</title>
    <style>
          /* ===== 隐藏一切非你内容的东西 ===== */
/* 1. 隐藏DOCTYPE可能产生的空白 */
html::before, body::before {
    display: none !important;
    content: none !important;
}

/* 2. 隐藏所有非.hub-container的直接子元素 */
body > *:not(.hub-container) {
    display: none !important;
    height: 0 !important;
    min-height: 0 !important;
    padding: 0 !important;
    margin: 0 !important;
    border: none !important;
}

/* 3. 强制你的容器占据全屏 */
.hub-container {
    position: absolute !important;
    top: 0 !important;
    left: 0 !important;
    width: 100% !important;
    min-height: 100vh !important;
    margin: 0 !important;
    padding: 40px 20px !important;
    z-index: 9999 !important;
    background: rgba(15, 25, 45, 0.95) !important;
}

/* 4. 确保html/body没有边距 */
html, body {
    margin: 0 !important;
    padding: 0 !important;
    position: relative !important;
    min-height: 100vh !important;
    overflow-x: hidden !important;
}
        nav, header, .navigation, .navbar, .site-header { display: none !important; }
        /* 重置 */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        /* 背景 - 你喜欢的星河蓝 */
        body {
            background: #0a192f;
            background-image: 
                radial-gradient(circle at 20% 30%, rgba(100,217,254,0.05) 0%, transparent 20%),
                radial-gradient(circle at 80% 70%, rgba(72,187,255,0.03) 0%, transparent 20%);
            color: #e6f1ff;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            line-height: 1.7;
            padding: 20px;
            min-height: 100vh;
        }
        
        /* 主容器 */
        .hub-container {
            max-width: 1000px;
            margin: 0 auto;
            background: rgba(15, 25, 45, 0.85);
            backdrop-filter: blur(12px);
            border-radius: 20px;
            padding: 40px;
            border: 1px solid rgba(100, 217, 254, 0.2);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
        }
        
        /* 标题 */
        .main-title {
            text-align: center;
            font-size: 2.8rem;
            margin-bottom: 20px;
            background: linear-gradient(90deg, #64d9fe, #48bbff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .subtitle {
            text-align: center;
            margin-bottom: 40px;
            opacity: 0.9;
            font-size: 1.1rem;
        }
        
        /* 章节标题 */
        .section-title {
            border-bottom: 2px solid rgba(100, 217, 254, 0.3);
            padding-bottom: 10px;
            margin: 40px 0 20px;
            font-size: 1.8rem;
        }
        
        /* 表格 - 深色融入 */
        .projects-table {
            width: 100%;
            border-collapse: collapse;
            margin: 30px 0;
            background: rgba(20, 30, 50, 0.9);
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid rgba(100, 217, 254, 0.1);
        }
        
        .projects-table th {
            background: rgba(30, 41, 59, 0.95);
            padding: 18px 15px;
            text-align: left;
            font-weight: 600;
            color: #cbd5e1;
            border-bottom: 2px solid rgba(100, 217, 254, 0.15);
        }
        
        .projects-table td {
            padding: 18px 15px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
            color: #a5b4cb;
            background: rgba(25, 35, 55, 0.8);
        }
        
        .projects-table tr:nth-child(even) td {
            background: rgba(30, 40, 60, 0.8);
        }
        
        /* 项目名称 */
        .project-name {
            font-weight: 600;
            color: #dbeafe;
            font-size: 1.1rem;
            line-height: 1.5;
        }
        
        /* 状态徽章 */
        .status-badge {
            display: inline-block;
            padding: 6px 12px;
            background: rgba(255, 255, 255, 0.08);
            border-radius: 8px;
            border: 1px solid rgba(255, 255, 255, 0.12);
            color: #e2e8f0;
            font-weight: 500;
            font-size: 0.9rem;
        }
        
        /* 按钮 */
        .action-btn {
            display: inline-block;
            padding: 8px 16px;
            background: rgba(255, 255, 255, 0.12);
            border-radius: 8px;
            border: 1px solid rgba(255, 255, 255, 0.18);
            color: #f8fafc;
            font-weight: 500;
            text-decoration: none;
            transition: all 0.3s;
            min-width: 120px;
            text-align: center;
        }
        
        .action-btn:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        /* 分隔线 */
        .divider {
            border: none;
            height: 1px;
            background: linear-gradient(90deg, transparent, rgba(100,217,254,0.3), transparent);
            margin: 40px 0;
        }
        
        /* 链接列表 */
        .links-list {
            background: rgba(255, 255, 255, 0.05);
            padding: 20px;
            border-radius: 10px;
            border-left: 4px solid #64d9fe;
            list-style: none;
        }
        
        .links-list li {
            padding: 8px 0;
            font-size: 1.1rem;
        }
        
        .links-list a {
            color: #64d9fe;
            text-decoration: none;
        }
        
        .links-list a:hover {
            color: #48bbff;
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <div class="hub-container">
        <h1 class="main-title">🌌 My Digital Hub 我的数字空间</h1>
        <p class="subtitle">
            这里是我所有公开项目的入口。每个链接都会带你进入一个独立的知识站点。<br>
            Here is the gateway to all my public projects. Each link leads to an independent knowledge site.
        </p>

        <h2 class="section-title">📝 Core Projects 核心项目</h2>
        <p style="margin-bottom: 25px;">
            以下是我投入最深、持续更新的项目。<br>
            Below are my most invested and continuously updated projects.
        </p>

        <table class="projects-table">
            <thead>
                <tr>
                    <th>项目 / Project</th>
                    <th>简介 / Description</th>
                    <th>状态 / Status</th>
                    <th>直达链接 / Visit</th>
                    <th>源码地址 / Source</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>
                        <div class="project-name">Productivity Engine<br>生产力引擎</div>
                    </td>
                    <td>
                        A systematic knowledge base on efficiency, learning, and first-principles thinking.<br>
                        关于效率、学习与底层思考的系统化知识库。
                    </td>
                    <td><span class="status-badge">🟢 Public / 已公开</span></td>
                    <td><a href="https://www.crescentflux.com" class="action-btn">📈 访问知识库</a></td>
                    <td><a href="https://github.com/CrescentFlux/Productivity-Engine" class="action-btn">GitHub</a></td>
                </tr>
                <tr>
                    <td>
                        <div class="project-name">My Blog<br>我的博客</div>
                    </td>
                    <td>
                        A place for personal in-depth articles and long-form thinking.<br>
                        个人深度文章与长篇思考的发布地。
                    </td>
                    <td><span class="status-badge">🟢 Public / 已公开</span></td>
                    <td><a href="https://blog.crescentflux.com" class="action-btn">✍️ 访问博客</a></td>
                    <td><a href="https://github.com/CrescentFlux/Blog" class="action-btn">GitHub</a></td>
                </tr>
                <tr>
                    <td>
                        <div class="project-name">Story Studio<br>故事创作</div>
                    </td>
                    <td>
                        A creative space for stories and narratives.<br>
                        故事与叙事的创作空间。
                    </td>
                    <td><span class="status-badge">🟢 Public / 已公开</span></td>
                    <td><a href="https://story.crescentflux.com" class="action-btn">📖 访问故事集</a></td>
                    <td><a href="https://github.com/CrescentFlux/STORY" class="action-btn">GitHub</a></td>
                </tr>
            </tbody>
        </table>

        <div class="divider"></div>

        <h2 class="section-title">🔗 All Links / 所有链接</h2>
        <ul class="links-list">
            <li>GitHub 主页：<a href="https://github.com/CrescentFlux">https://github.com/CrescentFlux</a></li>
        </ul>
    </div>
</body>
</html>