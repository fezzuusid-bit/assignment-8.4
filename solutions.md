TML
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard with Grid & Flexbox</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="dashboard-layout">
        <!-- 1. Header Section -->
        <header class="dash-header">
            <div class="logo">DevPortal</div>
            <div class="user-profile">
                <span>Atim Akhtar</span>
                <div class="avatar">AA</div>
            </div>
        </header>

        <!-- 1. Sidebar Section -->
        <aside class="dash-sidebar">
            <nav class="sidebar-nav">
                <ul>
                    <li><a href="#" class="active">Dashboard</a></li>
                    <li><a href="#">Projects</a></li>
                    <li><a href="#">Analytics</a></li>
                    <li><a href="#">Settings</a></li>
                </ul>
            </nav>
        </aside>

        <!-- 1. Main Content Area -->
        <main class="dash-main">
            <div class="welcome-section">
                <h2>Dashboard Overview</h2>
                <p>Welcome back! Here is your system performance and activity summary.</p>
            </div>

            <!-- 3 & 4. Four Statistic Cards (Outer Grid / Inner Flexbox) -->
            <div class="stats-container">
                <!-- Card 1 -->
                <div class="stat-card">
                    <div class="card-icon bg-blue">📁</div>
                    <div class="card-content">
                        <h3>Total Projects</h3>
                        <p class="stat-value">12</p>
                        <span class="trend positive">+2 this month</span>
                    </div>
                </div>

                <!-- Card 2 -->
                <div class="stat-card">
                    <div class="card-icon bg-green">👥</div>
                    <div class="card-content">
                        <h3>Active Users</h3>
                        <p class="stat-value">1,429</p>
                        <span class="trend positive">+12% from last week</span>
                    </div>
                </div>

                <!-- Card 3 -->
                <div class="stat-card">
                    <div class="card-icon bg-purple">⭐</div>
                    <div class="card-content">
                        <h3>Repository Stars</h3>
                        <p class="stat-value">348</p>
                        <span class="trend positive">+24 today</span>
                    </div>
                </div>

                <!-- Card 4 -->
                <div class="stat-card">
                    <div class="card-icon bg-orange">⚠️</div>
                    <div class="card-content">
                        <h3>Pending Issues</h3>
                        <p class="stat-value">3</p>
                        <span class="trend negative">Requires attention</span>
                    </div>
                </div>
            </div>

            <!-- 5. Recent Activity / Table Section -->
            <section class="activity-section">
                <div class="section-header">
                    <h3>Recent Submissions</h3>
                    <a href="#" class="view-all">View All</a>
                </div>
                <div class="table-responsive">
                    <table class="activity-table">
                        <thead>
                            <tr>
                                <th>Assignment / Project</th>
                                <th>Category</th>
                                <th>Status</th>
                                <th>Date</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>Assignment 8.4 — Dashboard Grid & Flexbox</td>
                                <td>CSS Grid</td>
                                <td><span class="status-badge success">Completed</span></td>
                                <td>Nov 7, 2026</td>
                            </tr>
                            <tr>
                                <td>Assignment 8.3 — Magazine Layout</td>
                                <td>Grid Areas</td>
                                <td><span class="status-badge success">Completed</span></td>
                                <td>Nov 6, 2026</td>
                            </tr>
                            <tr>
                                <td>Assignment 8.2 — Responsive Gallery</td>
                                <td>Auto-Fit</td>
                                <td><span class="status-badge success">Completed</span></td>
                                <td>Nov 5, 2026</td>
                            </tr>
                            <tr>
                                <td>Assignment 8.1 — Dashboard Grid</td>
                                <td>CSS Grid</td>
                                <td><span class="status-badge success">Completed</span></td>
                                <td>Nov 4, 2026</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </section>
        </main>
    </div>
</body>
</html>
CSS
/* style.css */
:root {
    --primary-color: #0284c7;
    --secondary-color: #0f172a;
    --sidebar-bg: #1e293b;
    --bg-color: #f8fafc;
    --surface-color: #ffffff;
    --text-color: #334155;
    --text-muted: #64748b;
    --border-color: #e2e8f0;
    
    --space-sm: 8px;
    --space-md: 16px;
    --space-lg: 24px;
    --space-xl: 32px;
    
    --radius-md: 8px;
    --radius-lg: 12px;
    --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.05);
    --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
}

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: Arial, sans-serif;
    background-color: var(--bg-color);
    color: var(--text-color);
    line-height: 1.6;
}

/* 2. Outer Page Layout using CSS Grid */
.dashboard-layout {
    display: grid;
    grid-template-columns: 260px 1fr;
    grid-template-rows: 70px 1fr;
    min-height: 100vh;
    grid-template-areas:
        "header header"
        "sidebar main";
}

/* Header Styling */
.dash-header {
    grid-area: header;
    background-color: var(--surface-color);
    border-bottom: 1px solid var(--border-color);
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 var(--space-xl);
    z-index: 100;
}

.logo {
    font-size: 1.25rem;
    font-weight: bold;
    color: var(--secondary-color);
}

.user-profile {
    display: flex;
    align-items: center;
    gap: var(--space-md);
    font-weight: 600;
    font-size: 0.95rem;
}

.avatar {
    width: 38px;
    height: 38px;
    background-color: var(--primary-color);
    color: var(--surface-color);
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 0.85rem;
}

/* Sidebar Styling */
.dash-sidebar {
    grid-area: sidebar;
    background-color: var(--sidebar-bg);
    color: var(--surface-color);
    padding: var(--space-xl) var(--space-md);
}

.sidebar-nav ul {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: var(--space-sm);
}

.sidebar-nav a {
    display: block;
    color: #94a3b8;
    text-decoration: none;
    font-weight: 500;
    padding: var(--space-sm) var(--space-md);
    border-radius: var(--radius-md);
    transition: background-color 0.2s ease, color 0.2s ease;
}

.sidebar-nav a:hover,
.sidebar-nav a.active {
    background-color: var(--primary-color);
    color: var(--surface-color);
}

/* Main Content Area */
.dash-main {
    grid-area: main;
    padding: var(--space-xl);
    display: flex;
    flex-direction: column;
    gap: var(--space-xl);
    overflow-y: auto;
}

.welcome-section h2 {
    font-size: 1.75rem;
    color: var(--secondary-color);
    margin-bottom: 4px;
}

.welcome-section p {
    color: var(--text-muted);
}

/* Stats Cards Grid */
.stats-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: var(--space-lg);
}

/* 4. Align icons, titles, and numbers inside cards using Flexbox */
.stat-card {
    background-color: var(--surface-color);
    border: 1px solid var(--border-color);
    border-radius: var(--radius-lg);
    padding: var(--space-lg);
    box-shadow: var(--shadow-sm);
    display: flex;
    align-items: center;
    gap: var(--space-md);
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.stat-card:hover {
    transform: translateY(-3px);
    box-shadow: var(--shadow-md);
}

.card-icon {
    width: 50px;
    height: 50px;
    border-radius: var(--radius-md);
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 1.25rem;
    flex-shrink: 0;
}

.bg-blue { background-color: #e0f2fe; color: #0284c7; }
.bg-green { background-color: #dcfce7; color: #15803d; }
.bg-purple { background-color: #f3e8ff; color: #7e22ce; }
.bg-orange { background-color: #ffedd5; color: #c2410c; }

.card-content {
    display: flex;
    flex-direction: column;
}

.card-content h3 {
    font-size: 0.85rem;
    color: var(--text-muted);
    font-weight: 500;
}

.stat-value {
    font-size: 1.5rem;
    font-weight: bold;
    color: var(--secondary-color);
    margin: 2px 0;
}

.trend {
    font-size: 0.75rem;
    font-weight: bold;
}

.trend.positive { color: #16a34a; }
.trend.negative { color: #dc2626; }

/* 5. Recent Activity Table Section */
.activity-section {
    background-color: var(--surface-color);
    border: 1px solid var(--border-color);
    border-radius: var(--radius-lg);
    padding: var(--space-lg);
    box-shadow: var(--shadow-sm);
}

.section-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: var(--space-md);
    border-bottom: 1px solid var(--border-color);
    padding-bottom: var(--space-sm);
}

.section-header h3 {
    font-size: 1.15rem;
    color: var(--secondary-color);
}

.view-all {
    font-size: 0.875rem;
    color: var(--primary-color);
    text-decoration: none;
    font-weight: bold;
}

.view-all:hover {
    text-decoration: underline;
}

.table-responsive {
    overflow-x: auto;
}

.activity-table {
    width: 100%;
    border-collapse: collapse;
    text-align: left;
    font-size: 0.95rem;
}

.activity-table th,
.activity-table td {
    padding: 12px 16px;
    border-bottom: 1px solid var(--border-color);
}

.activity-table th {
    font-weight: 600;
    color: var(--text-muted);
    background-color: #f8fafc;
}

.activity-table tr:hover {
    background-color: #f8fafc;
}

.status-badge {
    font-size: 0.75rem;
    font-weight: bold;
    padding: 4px 8px;
    border-radius: 4px;
    display: inline-block;
}

.status-badge.success {
    background-color: #dcfce7;
    color: #15803d;
}

/* Responsive adjustment for small screens */
@media (max-width: 768px) {
    .dashboard-layout {
        grid-template-columns: 1fr;
        grid-template-areas:
            "header"
            "main";
    }
    .dash-sidebar {
        display: none;
    }
}