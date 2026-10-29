1. HTML Code (index.html)
HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Admin Dashboard | Grid & Flexbox</title>
    <link rel="stylesheet" href="style.css">
    <!-- FontAwesome for Dashboard Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body>

    <!-- Outer Grid Dashboard Container -->
    <div class="dashboard-grid">

        <!-- 1. Header Section -->
        <header class="dashboard-header">
            <div class="logo-area">
                <i class="fa-solid fa-chart-line"></i>
                <span>MetricsPro</span>
            </div>
            <div class="user-profile">
                <i class="fa-regular fa-bell notification-icon"></i>
                <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=100&auto=format&fit=crop&q=80" alt="User Profile">
                <span>Sarah Jenkins</span>
            </div>
        </header>

        <!-- 1. Sidebar Section -->
        <aside class="dashboard-sidebar">
            <ul class="sidebar-menu">
                <li><a href="#" class="active"><i class="fa-solid fa-house"></i> Dashboard</a></li>
                <li><a href="#"><i class="fa-solid fa-users"></i> Users</a></li>
                <li><a href="#"><i class="fa-solid fa-wallet"></i> Finances</a></li>
                <li><a href="#"><i class="fa-solid fa-chart-pie">Analytics</i></a></li>
                <li><a href="#"><i class="fa-solid fa-gear"></i> Settings</a></li>
            </ul>
        </aside>

        <!-- 1. Main Content Area -->
        <main class="dashboard-main">
            <div class="welcome-banner">
                <h1>Welcome back, Sarah!</h1>
                <p>Here is what's happening with your store today.</p>
            </div>

            <!-- 3. Statistic Cards Section (Inner Grid/Flex Container) -->
            <section class="stats-grid">
                <!-- Card 1 -->
                <div class="stat-card">
                    <div class="card-icon revenue"><i class="fa-solid fa-dollar-sign"></i></div>
                    <div class="card-info">
                        <span class="card-title">Total Revenue</span>
                        <h2 class="card-value">$48,250</h2>
                        <span class="card-trend positive"><i class="fa-solid fa-arrow-up"></i> +12% this month</span>
                    </div>
                </div>

                <!-- Card 2 -->
                <div class="stat-card">
                    <div class="card-icon users"><i class="fa-solid fa-user-plus"></i></div>
                    <div class="card-info">
                        <span class="card-title">New Users</span>
                        <h2 class="card-value">1,245</h2>
                        <span class="card-trend positive"><i class="fa-solid fa-arrow-up"></i> +4.5% vs last week</span>
                    </div>
                </div>

                <!-- Card 3 -->
                <div class="stat-card">
                    <div class="card-icon orders"><i class="fa-solid fa-bag-shopping"></i></div>
                    <div class="card-info">
                        <span class="card-title">Active Orders</span>
                        <h2 class="card-value">328</h2>
                        <span class="card-trend negative"><i class="fa-solid fa-arrow-down"></i> -2% today</span>
                    </div>
                </div>

                <!-- Card 4 -->
                <div class="stat-card">
                    <div class="card-icon growth"><i class="fa-solid fa-chart-line"></i></div>
                    <div class="card-info">
                        <span class="card-title">Conversion Rate</span>
                        <h2 class="card-value">3.6%</h2>
                        <span class="card-trend positive"><i class="fa-solid fa-arrow-up"></i> +0.8%</span>
                    </div>
                </div>
            </section>

            <!-- 5. Recent Activity / Table Section -->
            <section class="activity-section">
                <div class="section-header">
                    <h3>Recent Transactions</h3>
                    <a href="#" class="view-all">View All</a>
                </div>
                <div class="table-container">
                    <table>
                        <thead>
                            <tr>
                                <th>Customer</th>
                                <th>Item</th>
                                <th>Amount</th>
                                <th>Status</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>
                                    <div class="customer-info">
                                        <div class="avatar-sm">JD</div>
                                        <span>John Doe</span>
                                    </div>
                                </td>
                                <td>UI/UX Design Kit</td>
                                <td>$120.00</td>
                                <td><span class="badge completed">Completed</span></td>
                            </tr>
                            <tr>
                                <td>
                                    <div class="customer-info">
                                        <div class="avatar-sm" style="background-color: #3b82f6;">AS</div>
                                        <span>Alice Smith</span>
                                    </div>
                                </td>
                                <td>Hosting Plan (1 Year)</td>
                                <td>$240.00</td>
                                <td><span class="badge completed">Completed</span></td>
                            </tr>
                            <tr>
                                <td>
                                    <div class="customer-info">
                                        <div class="avatar-sm" style="background-color: #f59e0b;">MR</div>
                                        <span>Mark Ross</span>
                                    </div>
                                </td>
                                <td>Consulting Session</td>
                                <td>$150.00</td>
                                <td><span class="badge pending">Pending</span></td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </section>

        </main>
    </div>

</body>
</html>
2. CSS Code (style.css)
CSS
/* --- Global Reset & Variables --- */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

:root {
    --bg-color: #f8fafc;
    --card-bg: #ffffff;
    --text-primary: #1e293b;
    --text-secondary: #64748b;
    --border-color: #e2e8f0;
    --primary-color: #4f46e5;
    --sidebar-width: 260px;
}

body {
    font-family: 'Inter', system-ui, -apple-system, sans-serif;
    background-color: var(--bg-color);
    color: var(--text-primary);
    line-height: 1.5;
}

/* --- 2. CSS Grid for Outer Page Layout --- */
.dashboard-grid {
    display: grid;
    min-height: 100vh;
    grid-template-areas:
        "header header"
        "sidebar main";
    grid-template-columns: var(--sidebar-width) 1fr;
    grid-template-rows: 70px 1fr;
}

/* --- Header Styling (Flexbox inside Grid) --- */
.dashboard-header {
    grid-area: header;
    background-color: var(--card-bg);
    border-bottom: 1px solid var(--border-color);
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 30px;
    position: sticky;
    top: 0;
    z-index: 100;
}

.logo-area {
    display: flex;
    align-items: center;
    gap: 12px;
    font-size: 1.25rem;
    font-weight: 700;
    color: var(--primary-color);
}

.user-profile {
    display: flex;
    align-items: center;
    gap: 15px;
}

.notification-icon {
    font-size: 1.2rem;
    color: var(--text-secondary);
    cursor: pointer;
}

.user-profile img {
    width: 38px;
    height: 38px;
    border-radius: 50%;
    object-fit: cover;
}

.user-profile span {
    font-weight: 600;
    font-size: 0.9rem;
}

/* --- Sidebar Styling --- */
.dashboard-sidebar {
    grid-area: sidebar;
    background-color: var(--card-bg);
    border-right: 1px solid var(--border-color);
    padding: 30px 20px;
}

.sidebar-menu {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 8px;
}

.sidebar-menu a {
    display: flex;
    align-items: center;
    gap: 12px;
    text-decoration: none;
    color: var(--text-secondary);
    padding: 12px 16px;
    border-radius: 8px;
    font-weight: 500;
    font-size: 0.95rem;
    transition: all 0.2s ease;
}

.sidebar-menu a:hover,
.sidebar-menu a.active {
    background-color: #eef2ff;
    color: var(--primary-color);
}

/* --- Main Content Area --- */
.dashboard-main {
    grid-area: main;
    padding: 30px;
    overflow-y: auto;
}

.welcome-banner {
    margin-bottom: 25px;
}

.welcome-banner h1 {
    font-size: 1.6rem;
    font-weight: 700;
}

.welcome-banner p {
    color: var(--text-secondary);
    font-size: 0.95rem;
}

/* --- 3. Statistic Cards Grid Container --- */
.stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;
    margin-bottom: 30px;
}

/* --- 4. Stat Card Component (Flexbox Layout) --- */
.stat-card {
    background-color: var(--card-bg);
    border: 1px solid var(--border-color);
    border-radius: 12px;
    padding: 20px;
    display: flex; /* Flexbox applied here */
    align-items: center;
    gap: 20px;
    box-shadow: 0 1px 3px rgba(0,0,0,0.02);
}

.card-icon {
    width: 50px;
    height: 50px;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.25rem;
}

/* Card icon theme colors */
.card-icon.revenue { background-color: #d1fae5; color: #059669; }
.card-icon.users { background-color: #e0e7ff; color: var(--primary-color); }
.card-icon.orders { background-color: #fef3c7; color: #d97706; }
.card-icon.growth { background-color: #f3e8ff; color: #7c3aed; }

.card-info {
    display: flex;
    flex-direction: column; /* Stacking titles, numbers, and trends vertically using Flexbox */
}

.card-title {
    font-size: 0.85rem;
    color: var(--text-secondary);
    font-weight: 500;
}

.card-value {
    font-size: 1.5rem;
    font-weight: 700;
    margin: 2px 0;
}

.card-trend {
    font-size: 0.75rem;
    font-weight: 600;
}

.card-trend.positive { color: #059669; }
.card-trend.negative { color: #dc2626; }

/* --- 5. Recent Activity Table Section --- */
.activity-section {
    background-color: var(--card-bg);
    border: 1px solid var(--border-color);
    border-radius: 12px;
    padding: 25px;
}

.section-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}

.section-header h3 {
    font-size: 1.1rem;
    font-weight: 600;
}

.view-all {
    text-decoration: none;
    color: var(--primary-color);
    font-size: 0.85rem;
    font-weight: 600;
}

.table-container {
    overflow-x: auto;
}

table {
    width: 100%;
    border-collapse: collapse;
    text-align: left;
    font-size: 0.9rem;
}

th {
    color: var(--text-secondary);
    font-weight: 600;
    padding: 12px 16px;
    border-bottom: 1px solid var(--border-color);
}

td {
    padding: 14px 16px;
    border-bottom: 1px solid var(--border-color);
    color: var(--text-primary);
}

.customer-info {
    display: flex;
    align-items: center;
    gap: 10px;
}

.avatar-sm {
    width: 32px;
    height: 32px;
    background-color: #10b981;
    color: #fff;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.75rem;
    font-weight: bold;
}

.badge {
    padding: 4px 10px;
    border-radius: 20px;
    font-size: 0.75rem;
    font-weight: 600;
}

.badge.completed {
    background-color: #d1fae5;
    color: #065f46;
}

.badge.pending {
    background-color: #fef3c7;
    color: #92400e;
}

/* --- Responsive Design --- */
@media (max-width: 768px) {
    .dashboard-grid {
        grid-template-areas:
            "header"
            "main";
        grid-template-columns: 1fr;
    }
    
    .dashboard-sidebar {
        display: none; /* Hide sidebar on small mobile screens */
    }
}
Assignment Checklist Verification:
Header, Sidebar, and Main Content: Implemented with semantic tags (<header>, <aside>, <main>).

CSS Grid for Outer Page: Controlled through .dashboard-grid using grid-template-areas and fractional tracking.

4 Statistic Cards in Main Area: Generated inside the .stats-grid block.

Flexbox Inside Cards: Icons, values, and titles are neatly aligned and stacked via display: flex; align-items: center; and column flex layouts.

Recent Activity Table Section: Fully styled modern transactions data table with status badges and profile avatars.

DevTools Grid Inspector ready: Cleanly defined track structures ideal for browser debugging.