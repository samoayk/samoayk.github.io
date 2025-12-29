<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>游戏资料库</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "Microsoft YaHei", "Segoe UI", sans-serif;
        }
        
        body {
            display: flex;
            min-height: 100vh;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            color: #e0e0e0;
        }
        
        /* 左侧导航栏 */
        .sidebar {
            width: 280px;
            background: rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(10px);
            padding: 20px 0;
            border-right: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 5px 0 15px rgba(0, 0, 0, 0.3);
            overflow-y: auto;
            position: sticky;
            top: 0;
            height: 100vh;
        }
        
        .sidebar-header {
            padding: 0 20px 20px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            margin-bottom: 20px;
        }
        
        .sidebar-header h1 {
            color: #ffd700;
            font-size: 24px;
            text-align: center;
            text-shadow: 0 0 10px rgba(255, 215, 0, 0.3);
        }
        
        .game-section {
            margin-bottom: 25px;
        }
        
        .game-title {
            padding: 10px 20px;
            font-size: 18px;
            font-weight: bold;
            color: #4fc3f7;
            border-left: 4px solid #4fc3f7;
            margin-bottom: 10px;
            background: rgba(79, 195, 247, 0.1);
        }
        
        .nav-links {
            list-style: none;
        }
        
        .nav-links li {
            margin-bottom: 2px;
        }
        
        .nav-links a {
            display: block;
            padding: 12px 20px;
            color: #b0bec5;
            text-decoration: none;
            transition: all 0.3s;
            border-left: 3px solid transparent;
            font-size: 14px;
        }
        
        .nav-links a:hover {
            background: rgba(255, 255, 255, 0.05);
            color: #ffffff;
            border-left: 3px solid #ffd700;
            padding-left: 25px;
        }
        
        .nav-links a.active {
            background: rgba(255, 215, 0, 0.1);
            color: #ffd700;
            border-left: 3px solid #ffd700;
            font-weight: bold;
        }
        
        /* 主内容区 */
        .main-content {
            flex: 1;
            padding: 40px;
            overflow-y: auto;
        }
        
        .main-header {
            margin-bottom: 40px;
            text-align: center;
        }
        
        .main-header h1 {
            font-size: 36px;
            color: #ffd700;
            margin-bottom: 10px;
            text-shadow: 0 0 15px rgba(255, 215, 0, 0.4);
        }
        
        .main-header p {
            color: #90a4ae;
            font-size: 18px;
            max-width: 800px;
            margin: 0 auto;
            line-height: 1.6;
        }
        
        .content-card {
            background: rgba(30, 30, 46, 0.8);
            border-radius: 10px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        
        .content-card h2 {
            color: #4fc3f7;
            font-size: 26px;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid rgba(79, 195, 247, 0.3);
        }
        
        .content-card p {
            line-height: 1.8;
            margin-bottom: 20px;
            color: #cfd8dc;
        }
        
        .game-highlights {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            margin-top: 20px;
        }
        
        .highlight-card {
            flex: 1;
            min-width: 250px;
            background: rgba(0, 0, 0, 0.3);
            border-radius: 8px;
            padding: 20px;
            border: 1px solid rgba(255, 215, 0, 0.1);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .highlight-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.4);
            border-color: rgba(255, 215, 0, 0.3);
        }
        
        .highlight-card h3 {
            color: #ffd700;
            font-size: 20px;
            margin-bottom: 10px;
        }
        
        .highlight-card p {
            font-size: 14px;
            color: #b0bec5;
        }
        
        /* 响应式设计 */
        @media (max-width: 768px) {
            body {
                flex-direction: column;
            }
            
            .sidebar {
                width: 100%;
                height: auto;
                position: relative;
                padding: 15px;
            }
            
            .main-content {
                padding: 25px;
            }
            
            .main-header h1 {
                font-size: 28px;
            }
        }
        
        /* 滚动条样式 */
        ::-webkit-scrollbar {
            width: 8px;
        }
        
        ::-webkit-scrollbar-track {
            background: rgba(0, 0, 0, 0.2);
        }
        
        ::-webkit-scrollbar-thumb {
            background: rgba(255, 215, 0, 0.5);
            border-radius: 4px;
        }
        
        ::-webkit-scrollbar-thumb:hover {
            background: rgba(255, 215, 0, 0.7);
        }
    </style>
</head>
<body>
    <!-- 左侧导航栏 -->
    <div class="sidebar">
        <div class="sidebar-header">
            <h1>游戏资料库</h1>
        </div>
        
        <div class="game-section">
            <div class="game-title">魔兽世界资料库</div>
            <ul class="nav-links">
                <li><a href="#wow-guild" class="active">公会管理制度</a></li>
                <li><a href="#wow-icc">ICC BOSS攻略</a></li>
                <li><a href="#wow-addon">字符串插件</a></li>
                <li><a href="#wow-dk">DK一键输出宏</a></li>
                <li><a href="#wow-druid">德鲁伊三系指南</a></li>
                <li><a href="#wow-hunter">猎人一键输出</a></li>
                <li><a href="#wow-mage">火法指南</a></li>
                <li><a href="#wow-shaman">奶萨指南</a></li>
                <li><a href="#wow-warrior">狂暴战指南</a></li>
            </ul>
        </div>
        
        <div class="game-section">
            <div class="game-title">信长之野望资料库</div>
            <ul class="nav-links">
                <li><a href="#nobunaga-skill">特技及武技</a></li>
                <li><a href="#nobunaga-resource">特产+金银山</a></li>
            </ul>
        </div>
    </div>
    
    <!-- 主内容区 -->
    <div class="main-content">
        <div class="main-header">
            <h1>游戏资料库</h1>
            <p>整理并归档各类游戏资料，包含魔兽世界WLK版本攻略、插件、职业指南，以及信长之野望游戏资料。</p>
        </div>
        
        <div class="content-card">
            <h2>欢迎使用游戏资料库</h2>
            <p>本网站旨在为游戏玩家提供全面、实用的游戏资料和指南。所有内容均经过整理和验证，帮助您更好地享受游戏乐趣。</p>
            
            <div class="game-highlights">
                <div class="highlight-card">
                    <h3>魔兽世界 WLK</h3>
                    <p>包含冰冠堡垒(ICC)全BOSS攻略、各职业输出指南、实用插件字符串等，专为巫妖王之怒版本玩家准备。</p>
                </div>
                <div class="highlight-card">
                    <h3>信长之野望</h3>
                    <p>收录信长之野望12的游戏资料，包括特技武技详解、特产分布和金银山位置等实用信息。</p>
                </div>
            </div>
        </div>
        
        <div class="content-card">
            <h2>魔兽世界资料库</h2>
            <p>巫妖王之怒版本的游戏资料，涵盖副本攻略、职业指南、插件配置等内容，帮助您在诺森德大陆上取得更好的成就。</p>
            <p>公会管理制度为您提供了团队活动的基本规范，确保团队协作顺畅有序。</p>
        </div>
        
        <div class="content-card">
            <h2>信长之野望资料库</h2>
            <p>信长之野望12的游戏资料，包含武将特技、战法技能、资源分布等核心游戏信息，助您统一日本战国时代。</p>
            <p>了解各地特产和金银山位置，可以有效提升您的经济发展和战略布局。</p>
        </div>
    </div>
    
    <script>
        // 导航点击效果
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', function(e) {
                // 移除所有active类
                document.querySelectorAll('.nav-links a').forEach(item => {
                    item.classList.remove('active');
                });
                
                // 为当前点击的链接添加active类
                this.classList.add('active');
                
                // 在实际应用中，这里应该加载对应的内容
                // 由于是示例，我们只模拟导航效果
                e.preventDefault();
            });
        });
        
        // 页面滚动时更新导航状态（模拟）
        window.addEventListener('scroll', function() {
            // 在实际应用中，这里可以根据滚动位置更新导航状态
            // 本示例中简化处理
        });
        
        // 页面加载时默认选中第一个链接
        document.addEventListener('DOMContentLoaded', function() {
            const firstLink = document.querySelector('.nav-links a');
            if (firstLink) {
                firstLink.classList.add('active');
            }
        });
    </script>
</body>
</html>
