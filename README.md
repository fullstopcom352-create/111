<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>YouTube Studio Dashboard - Pro Max Clone</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        /* CSS Styles - Pro Max Modern Design */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: 'Roboto', sans-serif;
            background-color: #0f0f0f; /* Dark theme default */
            color: #fff;
            transition: background-color 0.3s, color 0.3s;
        }
        body.light {
            background-color: #f9f9f9;
            color: #333;
        }
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 16px 24px;
            background-color: #212121;
            border-bottom: 1px solid #333;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        body.light .header {
            background-color: #fff;
            border-bottom: 1px solid #ddd;
            color: #333;
        }
        .logo {
            font-size: 24px;
            font-weight: 700;
            color: #ff0000;
        }
        .header-actions {
            display: flex;
            align-items: center;
            gap: 16px;
        }
        .theme-toggle {
            background: none;
            border: none;
            color: inherit;
            font-size: 20px;
            cursor: pointer;
            padding: 8px;
        }
        .main-content {
            display: flex;
            min-height: calc(100vh - 64px);
        }
        .sidebar {
            width: 240px;
            background-color: #212121;
            padding: 24px 0;
            overflow-y: auto;
        }
        body.light .sidebar {
            background-color: #f5f5f5;
        }
        .sidebar-item {
            display: flex;
            align-items: center;
            padding: 12px 24px;
            color: #ccc;
            text-decoration: none;
            cursor: pointer;
            transition: background-color 0.2s;
        }
        .sidebar-item:hover, .sidebar-item.active {
            background-color: #ff0000;
            color: #fff;
        }
        .sidebar-item i {
            margin-right: 12px;
            width: 20px;
        }
        .dashboard {
            flex: 1;
            padding: 24px;
            overflow-y: auto;
        }
        .welcome-card {
            background: linear-gradient(135deg, #ff0000, #cc0000);
            padding: 24px;
            border-radius: 12px;
            margin-bottom: 24px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        body.light .welcome-card {
            background: linear-gradient(135deg, #ff6b6b, #ee5a52);
        }
        .welcome-text h1 {
            font-size: 28px;
            margin-bottom: 4px;
        }
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 32px;
        }
        .stat-card {
            background-color: #212121;
            padding: 20px;
            border-radius: 12px;
            text-align: center;
            transition: transform 0.2s;
        }
        body.light .stat-card {
            background-color: #fff;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }
        .stat-card:hover {
            transform: translateY(-4px);
        }
        .stat-value {
            font-size: 36px;
            font-weight: 700;
            color: #ff0000;
            margin-bottom: 8px;
        }
        .stat-label {
            color: #ccc;
            font-size: 14px;
        }
        body.light .stat-label {
            color: #666;
        }
        .recent-videos {
            background-color: #212121;
            border-radius: 12px;
            padding: 20px;
        }
        body.light .recent-videos {
            background-color: #fff;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }
        .section-title {
            font-size: 20px;
            margin-bottom: 16px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .video-item {
            display: flex;
            align-items: center;
            padding: 12px 0;
            border-bottom: 1px solid #333;
            transition: background-color 0.2s;
        }
        .video-item:hover {
            background-color: #333;
        }
        body.light .video-item:hover {
            background-color: #f0f0f0;
        }
        body.light .video-item {
            border-bottom: 1px solid #ddd;
        }
        .video-thumbnail {
            width: 80px;
            height: 60px;
            background-color: #333;
            border-radius: 8px;
            margin-right: 16px;
            position: relative;
            overflow: hidden;
        }
        .video-thumbnail img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        .video-info h4 {
            margin-bottom: 4px;
            font-size: 16px;
        }
        .video-meta {
            color: #ccc;
            font-size: 12px;
        }
        body.light .video-meta {
            color: #666;
        }
        @media (max-width: 768px) {
            .main-content {
                flex-direction: column;
            }
            .sidebar {
                width: 100%;
                order: 2;
            }
            .stats-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header">
        <div class="logo">YouTube Studio</div>
        <div class="header-actions">
            <button class="theme-toggle" onclick="toggleTheme()">
                <i class="fas fa-moon"></i>
            </button>
            <i class="fas fa-bell"></i>
            <i class="fas fa-user-circle"></i>
        </div>
    </header>

    <!-- Main Content -->
    <div class="main-content">
        <!-- Sidebar -->
        <nav class="sidebar">
            <a href="#" class="sidebar-item active">
                <i class="fas fa-home"></i>
                Dashboard
            </a>
            <a href="#" class="sidebar-item">
                <i class="fas fa-video"></i>
                Content
            </a>
            <a href="#" class="sidebar-item">
                <i class="fas fa-chart-bar"></i>
                Analytics
            </a>
            <a href="#" class="sidebar-item">
                <i class="fas fa-dollar-sign"></i>
                Revenue
            </a>
            <a href="#" class="sidebar-item">
                <i class="fas fa-comments"></i>
                Comments
            </a>
            <a href="#" class="sidebar-item">
                <i class="fas fa-cog"></i>
                Studio Settings
            </a>
        </nav>

        <!-- Dashboard Content -->
        <main class="dashboard">
            <!-- Welcome Card -->
            <div class="welcome-card">
                <div class="welcome-text">
                    <h1>Welcome back, Creator!</h1>
                    <p>Here's what's happening with your channel today.</p>
                </div>
                <i class="fas fa-rocket" style="font-size: 48px; opacity: 0.8;"></i>
            </div>

            <!-- Stats Cards -->
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-value">1.2M</div>
                    <div class="stat-label">Views this week</div>
                </div>
                <div class="stat-card">
                    <div class="stat-value">+5K</div>
                    <div class="stat-label">New Subscribers</div>
                </div>
                <div class="stat-card">
                    <div class="stat-value">$1,250</div>
                    <div class="stat-label">Estimated Revenue</div>
                </div>
                <div class="stat-card">
                    <div class="stat-value">89%</div>
                    <div class="stat-label">Watch Time Retention</div>
                </div>
            </div>

            <!-- Recent Videos Section -->
            <div class="recent-videos">
                <h3 class="section-title">
                    Recent Videos
                    <a href="#" style="color: #ff0000; text-decoration: none; font-size: 14px;">View all</a>
                </h3>
                <div class="video-item">
                    <div class="video-thumbnail">
                        <img src="https://img.youtube.com/vi/dQw4w9WgXcQ/maxresdefault.jpg" alt="Video Thumbnail">
                    </div>
                    <div class="video-info">
                        <h4>Rick Roll Tutorial</h4>
                        <div class="video-meta">2 days ago • 500K views</div>
                    </div>
                </div>
                <div class="video-item">
                    <div class="video-thumbnail">
                        <img src="https://img.youtube.com/vi/9bZkp7q19f0/maxresdefault.jpg" alt="Video Thumbnail">
                    </div>
                    <div class="video-info">
                        <h4>Pro Max Tips</h4>
                        <div class="video-meta">1 week ago • 1.1M views</div>
                    </div>
                </div>
                <div class="video-item">
                    <div class="video-thumbnail">
                        <img src="https://img.youtube.com/vi/kJQP7kiw5Fk/maxresdefault.jpg" alt="Video Thumbnail">
                    </div>
                    <div class="video-info">
                        <h4>Dashboard Hacks</h4>
                        <div class="video-meta">3 days ago • 300K views</div>
                    </div>
                </div>
            </div>
        </main>
    </div>

    <script>
        // JavaScript for Interactivity - Pro Max Features
        function toggleTheme() {
            document.body.classList.toggle('light');
            const icon = document.querySelector('.theme-toggle i');
            icon.classList.toggle('fa-moon');
            icon.classList.toggle('fa-sun');
        }

        // Simple sidebar active toggle (for demo)
        document.querySelectorAll('.sidebar-item').forEach(item => {
            item.addEventListener('click', () => {
                document.querySelector('.sidebar-item.active').classList.remove('active');
                item.classList.add('active');
            });
        });

        // Animate stats on load (pro touch)
        window.addEventListener('load', () => {
            const stats = document.querySelectorAll('.stat-value');
            stats.forEach(stat => {
                stat.style.opacity = '0';
                stat.style.transform = 'translateY(20px)';
                setTimeout(() => {
                    stat.style.transition = 'all 0.6s ease';
                    stat.style.opacity = '1';
                    stat.style.transform = 'translateY(0)';
                }, 200);
            });
        });
    </script>
</body>
</html>
