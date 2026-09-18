<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>🧠 Мой LifeHub</title>
<link href="https://cdn.jsdelivr.net/npm/@fontsource/inter@5.0.0/index.min.css" rel="stylesheet">
<style>
* { margin: 0; padding: 0; box-sizing: border-box; }

:root {
    --indigo: #6366f1;
    --purple: #a855f7;
    --cyan: #06b6d4;
    --glass-bg: rgba(255, 255, 255, 0.08);
    --glass-border: rgba(255, 255, 255, 0.15);
    --text-primary: #f1f5f9;
    --text-secondary: rgba(241, 245, 249, 0.6);
}

body {
    font-family: 'Inter', -apple-system, sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
    background: #0f0f23;
    color: var(--text-primary);
}

/* Animated Mesh Gradient Background */
.mesh-gradient {
    position: fixed;
    top: 0; left: 0;
    width: 400%; height: 400%;
    background: 
        radial-gradient(ellipse at 20% 50%, rgba(99, 102, 241, 0.3) 0%, transparent 50%),
        radial-gradient(ellipse at 80% 20%, rgba(168, 85, 247, 0.25) 0%, transparent 50%),
        radial-gradient(ellipse at 50% 80%, rgba(6, 182, 212, 0.2) 0%, transparent 50%),
        radial-gradient(ellipse at 70% 60%, rgba(99, 102, 241, 0.15) 0%, transparent 40%),
        linear-gradient(135deg, #0f0f23 0%, #1a1a3e 50%, #0f0f23 100%);
    animation: meshMove 20s ease-in-out infinite;
    z-index: 0;
}

@keyframes meshMove {
    0%, 100% { transform: translate(0%, 0%); }
    25% { transform: translate(-5%, -3%); }
    50% { transform: translate(-3%, -5%); }
    75% { transform: translate(-7%, -2%); }
}

/* Floating Orbs */
.orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(80px);
    opacity: 0.6;
    z-index: 1;
    pointer-events: none;
}

.orb-1 {
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(99, 102, 241, 0.5) 0%, transparent 70%);
    top: -100px; left: -100px;
    animation: orbFloat1 15s ease-in-out infinite;
}

.orb-2 {
    width: 350px; height: 350px;
    background: radial-gradient(circle, rgba(6, 182, 212, 0.4) 0%, transparent 70%);
    top: 40%; right: -80px;
    animation: orbFloat2 18s ease-in-out infinite;
}

.orb-3 {
    width: 300px; height: 300px;
    background: radial-gradient(circle, rgba(168, 85, 247, 0.45) 0%, transparent 70%);
    bottom: -50px; left: 30%;
    animation: orbFloat3 22s ease-in-out infinite;
}

@keyframes orbFloat1 {
    0%, 100% { transform: translate(0, 0) scale(1); }
    33% { transform: translate(80px, 60px) scale(1.1); }
    66% { transform: translate(40px, 100px) scale(0.9); }
}

@keyframes orbFloat2 {
    0%, 100% { transform: translate(0, 0) scale(1); }
    33% { transform: translate(-60px, -80px) scale(1.15); }
    66% { transform: translate(-100px, 40px) scale(0.95); }
}

@keyframes orbFloat3 {
    0%, 100% { transform: translate(0, 0) scale(1); }
    33% { transform: translate(70px, -50px) scale(1.05); }
    66% { transform: translate(-50px, -80px) scale(1.1); }
}

.container {
    position: relative;
    z-index: 10;
    max-width: 1200px;
    margin: 0 auto;
    padding: 30px 20px 120px;
}

.page-header {
    text-align: center;
    margin-bottom: 40px;
    animation: fadeUp 0.8s ease-out;
}

.page-header h1 {
    font-size: 2.8rem;
    font-weight: 700;
    letter-spacing: -0.5px;
    background: linear-gradient(135deg, #f1f5f9 0%, rgba(241, 245, 249, 0.7) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 8px;
}

.page-header p {
    font-weight: 300;
    color: var(--text-secondary);
    font-size: 1rem;
}

.glass-card {
    position: relative;
    background: linear-gradient(135deg, rgba(255, 255, 255, 0.1) 0%, rgba(255, 255, 255, 0.03) 100%);
    backdrop-filter: blur(40px) saturate(1.8);
    -webkit-backdrop-filter: blur(40px) saturate(1.8);
    border: 1px solid var(--glass-border);
    border-radius: 20px;
    padding: 28px;
    margin-bottom: 24px;
    box-shadow: 
        inset 0 1px 0 rgba(255, 255, 255, 0.15),
        0 20px 60px rgba(0, 0, 0, 0.3);
    overflow: hidden;
    animation: fadeUp 0.8s ease-out both;
}

.glass-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 50%;
    background: linear-gradient(180deg, rgba(255, 255, 255, 0.06) 0%, transparent 100%);
    pointer-events: none;
    border-radius: 20px 20px 0 0;
}

.card-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 20px;
    position: relative;
    z-index: 2;
}

.card-header h2 {
    font-size: 1.4rem;
    font-weight: 600;
    letter-spacing: -0.5px;
}

.badge {
    font-size: 0.75rem;
    font-weight: 500;
    padding: 4px 12px;
    border-radius: 20px;
    background: rgba(99, 102, 241, 0.2);
    border: 1px solid rgba(99, 102, 241, 0.3);
    color: #a5b4fc;
}

.db-table {
    width: 100%;
    border-collapse: collapse;
    position: relative;
    z-index: 2;
}

.db-table thead th {
    text-align: left;
    padding: 10px 14px;
    font-size: 0.72rem;
    font-weight: 500;
    color: var(--text-secondary);
    text-transform: uppercase;
    letter-spacing: 0.5px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.08);
}

.db-table tbody tr {
    transition: background 0.2s ease;
}

.db-table tbody tr:hover {
    background: rgba(255, 255, 255, 0.04);
}

.db-table tbody td {
    padding: 12px 14px;
    font-size: 0.875rem;
    font-weight: 400;
    border-bottom: 1px solid rgba(255, 255, 255, 0.04);
    color: var(--text-primary);
}

.text-secondary {
    color: var(--text-secondary);
    font-weight: 300;
}

.tag {
    display: inline-block;
    padding: 3px 10px;
    border-radius: 6px;
    font-size: 0.75rem;
    font-weight: 500;
}

.tag-income { background: rgba(34, 197, 94, 0.15); color: #4ade80; border: 1px solid rgba(34, 197, 94, 0.2); }
.tag-expense { background: rgba(239, 68, 68, 0.15); color: #f87171; border: 1px solid rgba(239, 68, 68, 0.2); }
.tag-category { background: rgba(99, 102, 241, 0.12); color: #a5b4fc; border: 1px solid rgba(99, 102, 241, 0.2); }
.tag-type { background: rgba(6, 182, 212, 0.12); color: #67e8f9; border: 1px solid rgba(6, 182, 212, 0.2); }
.tag-status { background: rgba(251, 191, 36, 0.12); color: #fbbf24; border: 1px solid rgba(251, 191, 36, 0.2); }
.tag-done { background: rgba(34, 197, 94, 0.12); color: #4ade80; border: 1px solid rgba(34, 197, 94, 0.2); }

.tag-multi {
    display: inline-block;
    padding: 2px 8px;
    border-radius: 4px;
    font-size: 0.7rem;
    font-weight: 500;
    margin: 2px;
}

.tag-work { background: rgba(99, 102, 241, 0.15); color: #a5b4fc; }
.tag-personal { background: rgba(236, 72, 153, 0.15); color: #f9a8d4; }
.tag-ideas { background: rgba(251, 191, 36, 0.15); color: #fde68a; }
.tag-finance { background: rgba(34, 197, 94, 0.15); color: #4ade80; }

.btn-add {
    position: relative;
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 10px 20px;
    border: none;
    border-radius: 12px;
    background: linear-gradient(135deg, var(--indigo), var(--purple));
    color: white;
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.3s ease;
    box-shadow: 
        inset 0 1px 0 rgba(255, 255, 255, 0.2),
        0 4px 20px rgba(99, 102, 241, 0.3);
    animation: pulseShadow 3s ease-in-out infinite;
    margin-top: 16px;
    z-index: 2;
}

.btn-add:hover {
    transform: translateY(-2px);
    box-shadow: 
        inset 0 1px 0 rgba(255, 255, 255, 0.2),
        0 8px 30px rgba(99, 102, 241, 0.5);
}

@keyframes pulseShadow {
    0%, 100% { box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2), 0 4px 20px rgba(99, 102, 241, 0.3); }
    50% { box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2), 0 4px 30px rgba(168, 85, 247, 0.5); }
}

.nav-bar {
    position: fixed;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    gap: 4px;
    padding: 8px 12px;
    background: rgba(15, 15, 35, 0.7);
    backdrop-filter: blur(50px) saturate(2);
    -webkit-backdrop-filter: blur(50px) saturate(2);
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 20px;
    z-index: 100;
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5);
    animation: fadeUp 1s ease-out 0.6s both;
}

.nav-tab {
    position: relative;
    display: flex;
    align-items: center;
    gap: 6px;
    padding: 10px 18px;
    border: none;
    border-radius: 14px;
    background: transparent;
    color: var(--text-secondary);
    font-family: 'Inter', sans-serif;
    font-size: 0.8rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.3s ease;
}

.nav-tab:hover {
    color: var(--text-primary);
    background: rgba(255, 255, 255, 0.05);
}

.nav-tab.active {
    color: var(--text-primary);
    background: rgba(255, 255, 255, 0.1);
    box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1);
}

.nav-tab.active::before {
    content: '';
    position: absolute;
    top: -1px;
    left: 20%; right: 20%;
    height: 2px;
    background: linear-gradient(90deg, var(--indigo), var(--purple));
    border-radius: 2px;
}

.nav-tab span.emoji { font-size: 1.1rem; }

.db-section { display: none; }
.db-section.active { display: block; animation: fadeUp 0.5s ease-out; }

.stats-row {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 12px;
    margin-bottom: 20px;
    position: relative;
    z-index: 2;
}

.stat-card {
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 12px;
    padding: 14px;
    text-align: center;
}

.stat-value {
    font-size: 1.3rem;
    font-weight: 700;
    letter-spacing: -0.5px;
    margin-bottom: 4px;
}

.stat-value.income { color: #4ade80; }
.stat-value.expense { color: #f87171; }
.stat-value.balance { color: #67e8f9; }

.stat-label {
    font-size: 0.7rem;
    color: var(--text-secondary);
    font-weight: 400;
    text-transform: uppercase;
    letter-spacing: 0.5px;
}

.formula-value { font-weight: 600; color: #4ade80; }
.formula-negative { color: #f87171; }

/* Calendar */
.calendar-nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 16px;
    position: relative;
    z-index: 2;
}

.calendar-nav h3 {
    font-size: 1.1rem;
    font-weight: 600;
}

.cal-btn {
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.1);
    color: var(--text-primary);
    width: 32px; height: 32px;
    border-radius: 8px;
    cursor: pointer;
    font-size: 1rem;
    transition: all 0.2s;
}

.cal-btn:hover { background: rgba(255, 255, 255, 0.1); }

.calendar-grid {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    gap: 4px;
    position: relative;
    z-index: 2;
}

.calendar-header-cell {
    text-align: center;
    padding: 8px;
    font-size: 0.7rem;
    font-weight: 500;
    color: var(--text-secondary);
    text-transform: uppercase;
}

.calendar-cell {
    aspect-ratio: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    border-radius: 10px;
    font-size: 0.8rem;
    font-weight: 400;
    transition: all 0.2s ease;
    cursor: pointer;
    position: relative;
}

.calendar-cell:hover { background: rgba(255, 255, 255, 0.06); }

.calendar-cell.today {
    background: rgba(99, 102, 241, 0.2);
    border: 1px solid rgba(99, 102, 241, 0.4);
    font-weight: 600;
}

.calendar-cell.has-event::after {
    content: '';
    width: 5px; height: 5px;
    border-radius: 50%;
    background: var(--cyan);
    position: absolute;
    bottom: 6px;
}

.calendar-cell.other-month { color: rgba(255, 255, 255, 0.2); }

/* Board View */
.board-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 16px;
    margin-top: 16px;
    position: relative;
    z-index: 2;
}

.board-column {
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 14px;
    padding: 14px;
    min-height: 200px;
}

.board-column-title {
    font-size: 0.8rem;
    font-weight: 600;
    margin-bottom: 12px;
    color: var(--text-secondary);
    text-transform: uppercase;
    letter-spacing: 0.5px;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.board-count {
    background: rgba(255, 255, 255, 0.1);
    padding: 2px 8px;
    border-radius: 10px;
    font-size: 0.7rem;
}

.board-item {
    background: rgba(255, 255, 255, 0.06);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 10px;
    padding: 12px;
    margin-bottom: 8px;
    transition: all 0.2s ease;
    cursor: pointer;
}

.board-item:hover {
    background: rgba(255, 255, 255, 0.1);
    transform: translateY(-2px);
}

.board-item-title {
    font-size: 0.85rem;
    font-weight: 500;
    margin-bottom: 6px;
}

.board-item-meta {
    font-size: 0.7rem;
    color: var(--text-secondary);
    font-weight: 300;
}

.relation-link {
    display: inline-flex;
    align-items: center;
    gap: 4px;
    padding: 2px 8px;
    border-radius: 6px;
    background: rgba(168, 85, 247, 0.12);
    border: 1px solid rgba(168, 85, 247, 0.2);
    color: #c4b5fd;
    font-size: 0.72rem;
    font-weight: 500;
}

@keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
}

/* Modal */
.modal-overlay {
    position: fixed;
    inset: 0;
    background: rgba(0, 0, 0, 0.6);
    backdrop-filter: blur(10px);
    z-index: 200;
    display: none;
    align-items: center;
    justify-content: center;
    padding: 20px;
    animation: fadeIn 0.3s ease;
}

.modal-overlay.active { display: flex; }

@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}

.modal {
    background: linear-gradient(135deg, rgba(30, 30, 60, 0.95) 0%, rgba(20, 20, 45, 0.95) 100%);
    backdrop-filter: blur(40px) saturate(1.8);
    border: 1px solid var(--glass-border);
    border-radius: 20px;
    padding: 28px;
    max-width: 500px;
    width: 100%;
    max-height: 85vh;
    overflow-y: auto;
    box-shadow: 0 30px 80px rgba(0, 0, 0, 0.5);
    animation: modalUp 0.4s ease-out;
}

@keyframes modalUp {
    from { opacity: 0; transform: translateY(30px) scale(0.95); }
    to { opacity: 1; transform: translateY(0) scale(1); }
}

.modal h3 {
    font-size: 1.3rem;
    font-weight: 600;
    letter-spacing: -0.5px;
    margin-bottom: 20px;
}

.form-group { margin-bottom: 14px; }

.form-group label {
    display: block;
    font-size: 0.75rem;
    font-weight: 500;
    color: var(--text-secondary);
    margin-bottom: 6px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
}

.input-field, .select-field, .textarea-field {
    width: 100%;
    padding: 12px 16px;
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 12px;
    color: var(--text-primary);
    font-family: 'Inter', sans-serif;
    font-size: 0.875rem;
    transition: all 0.3s ease;
    outline: none;
}

.input-field:focus, .select-field:focus, .textarea-field:focus {
    background: rgba(255, 255, 255, 0.08);
    border-color: rgba(99, 102, 241, 0.5);
    box-shadow: 0 0 20px rgba(99, 102, 241, 0.15);
}

.select-field {
    appearance: none;
    background-image: url("data:image/svg+xml;charset=UTF-8,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='none' stroke='%23a5b4fc' stroke-width='2'%3e%3cpolyline points='6 9 12 15 18 9'%3e%3c/polyline%3e%3c/svg%3e");
    background-repeat: no-repeat;
    background-position: right 12px center;
    background-size: 16px;
    padding-right: 40px;
}

.select-field option {
    background: #1a1a3e;
    color: var(--text-primary);
}

.textarea-field {
    resize: vertical;
    min-height: 80px;
    font-family: inherit;
}

.modal-actions {
    display: flex;
    gap: 10px;
    margin-top: 20px;
}

.btn {
    flex: 1;
    padding: 12px 20px;
    border: none;
    border-radius: 12px;
    font-family: 'Inter', sans-serif;
    font-size: 0.85rem;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.3s ease;
}

.btn-primary {
    background: linear-gradient(135deg, var(--indigo), var(--purple));
    color: white;
    box-shadow: 
        inset 0 1px 0 rgba(255, 255, 255, 0.2),
        0 4px 20px rgba(99, 102, 241, 0.3);
}

.btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 30px rgba(99, 102, 241, 0.5);
}

.btn-secondary {
    background: rgba(255, 255, 255, 0.05);
    color: var(--text-primary);
    border: 1px solid rgba(255, 255, 255, 0.1);
}

.btn-secondary:hover {
    background: rgba(255, 255, 255, 0.1);
}

.empty-state {
    text-align: center;
    padding: 40px 20px;
    color: var(--text-secondary);
    font-weight: 300;
}

.empty-state-icon {
    font-size: 3rem;
    margin-bottom: 12px;
    opacity: 0.5;
}

::-webkit-scrollbar { width: 6px; }
::-webkit-scrollbar-track { background: transparent; }
::-webkit-scrollbar-thumb { background: rgba(255, 255, 255, 0.1); border-radius: 3px; }
::-webkit-scrollbar-thumb:hover { background: rgba(255, 255, 255, 0.2); }

@media (max-width: 768px) {
    .page-header h1 { font-size: 2rem; }
    .glass-card { padding: 20px 16px; }
    .nav-tab { padding: 8px 12px; font-size: 0.72rem; }
    .nav-tab span.tab-text { display: none; }
    .board-container { grid-template-columns: 1fr; }
}
</style>
</head>
<body>
<div class="mesh-gradient"></div>
<div class="orb orb-1"></div>
<div class="orb orb-2"></div>
<div class="orb orb-3"></div>

<div class="container">
    <div class="page-header">
        <h1>🧠 Мой LifeHub</h1>
        <p>Центр управления жизнью — финансы, события, идеи</p>
    </div>

    <!-- 💰 Финансы -->
    <div class="db-section active" id="section-finance">
        <div class="glass-card">
            <div class="card-header">
                <h2>💰 Финансы</h2>
                <span class="badge">Table View</span>
            </div>
            <div class="stats-row" id="finance-stats"></div>
            <div style="overflow-x: auto;">
                <table class="db-table">
                    <thead>
                        <tr>
                            <th>Дата</th>
                            <th>Тип</th>
                            <th>Категория</th>
                            <th>Сумма USDT</th>
                            <th>Курс</th>
                            <th>Комиссии (₽)</th>
                            <th>Итого (₽)</th>
                            <th>Комментарий</th>
                        </tr>
                    </thead>
                    <tbody id="finance-tbody"></tbody>
                </table>
            </div>
            <button class="btn-add" onclick="openModal('finance')">
                <span>＋</span> Добавить запись
            </button>
        </div>
    </div>

    <!-- 📅 Календарь -->
    <div class="db-section" id="section-calendar">
        <div class="glass-card">
            <div class="card-header">
                <h2>📅 Календарь и События</h2>
                <span class="badge">Calendar View</span>
            </div>
            <div class="calendar-nav">
                <button class="cal-btn" onclick="changeMonth(-1)">‹</button>
                <h3 id="calendar-title"></h3>
                <button class="cal-btn" onclick="changeMonth(1)">›</button>
            </div>
            <div class="calendar-grid" id="calendar"></div>
            <div style="margin-top: 24px; overflow-x: auto;">
                <table class="db-table">
                    <thead>
                        <tr>
                            <th>Название</th>
                            <th>Дата и время</th>
                            <th>Тип</th>
                            <th>Статус</th>
                            <th>Связано с финансами</th>
                        </tr>
                    </thead>
                    <tbody id="calendar-tbody"></tbody>
                </table>
            </div>
            <button class="btn-add" onclick="openModal('calendar')">
                <span>＋</span> Добавить событие
            </button>
        </div>
    </div>

    <!-- 📝 Заметки -->
    <div class="db-section" id="section-notes">
        <div class="glass-card">
            <div class="card-header">
                <h2>📝 Заметки и Идеи</h2>
                <span class="badge">Board View</span>
            </div>
            <div class="board-container" id="board-container"></div>
            <button class="btn-add" onclick="openModal('notes')">
                <span>＋</span> Добавить заметку
            </button>
        </div>
    </div>
</div>

<nav class="nav-bar">
    <button class="nav-tab active" onclick="switchTab('finance', this)">
        <span class="emoji">💰</span>
        <span class="tab-text">Финансы</span>
    </button>
    <button class="nav-tab" onclick="switchTab('calendar', this)">
        <span class="emoji">📅</span>
        <span class="tab-text">Календарь</span>
    </button>
    <button class="nav-tab" onclick="switchTab('notes', this)">
        <span class="emoji">📝</span>
        <span class="tab-text">Заметки</span>
    </button>
</nav>

<!-- Modal -->
<div class="modal-overlay" id="modal-overlay" onclick="if(event.target===this)closeModal()">
    <div class="modal" id="modal-content"></div>
</div>

<script>
// ============ STATE ============
const STORAGE_KEY = 'lifehub_data_v2';

let state = {
    finance: [],
    calendar: [],
    notes: []
};

let calendarDate = new Date();

const CATEGORIES = ['ЗП USDT', 'Роялти', 'Еда', 'Транспорт', 'Комиссии', 'Быт', 'Развлечения'];
const EVENT_TYPES = ['Встреча', 'Командировка', 'Дедлайн', 'Личное'];
const TAGS = ['работа', 'личное', 'идеи', 'финансы'];

// ============ PERSISTENCE ============
function saveState() {
    localStorage.setItem(STORAGE_KEY, JSON.stringify(state));
}

function loadState() {
    const saved = localStorage.getItem(STORAGE_KEY);
    if (saved) {
        try {
            state = JSON.parse(saved);
        } catch(e) {
            seedData();
        }
    } else {
        seedData();
    }
}

function seedData() {
    state.finance = [
        { id: 'f1', date: '2026-09-15', type: 'Доход', category: 'ЗП USDT', amount: 2000, rate: 95.5, fees: 150, comment: 'Зарплата за сентябрь' },
        { id: 'f2', date: '2026-09-18', type: 'Доход', category: 'Роялти', amount: 500, rate: 95.8, fees: 50, comment: 'Роялти за курс' },
        { id: 'f3', date: '2026-09-10', type: 'Расход', category: 'Еда', amount: 120, rate: 95.5, fees: 0, comment: 'Продукты' },
        { id: 'f4', date: '2026-09-12', type: 'Расход', category: 'Транспорт', amount: 45, rate: 95.5, fees: 0, comment: 'Такси' }
    ];
    state.calendar = [
        { id: 'c1', title: 'Созвон с командой', datetime: '2026-09-22T10:00', type: 'Встреча', status: 'Запланировано', relationId: 'f2' },
        { id: 'c2', title: 'Дедлайн: Курс по Web3', datetime: '2026-09-30T23:59', type: 'Дедлайн', status: 'Запланировано', relationId: 'f1' },
        { id: 'c3', title: 'Йога', datetime: '2026-09-20T07:30', type: 'Личное', status: 'Сделано', relationId: null }
    ];
    state.notes = [
        { id: 'n1', title: 'Новый модуль для курса', tags: ['работа', 'идеи'], content: 'Добавить раздел про DeFi', createdAt: Date.now() - 86400000 * 3 },
        { id: 'n2', title: 'План путешествия в Грузию', tags: ['личное', 'идеи'], content: 'Тбилиси → Батуми', createdAt: Date.now() - 86400000 * 2 },
        { id: 'n3', title: 'Стратегия стейкинга USDT', tags: ['финансы', 'идеи'], content: 'Изучить Bybit Earn', createdAt: Date.now() - 86400000 }
    ];
    saveState();
}

// ============ TAB NAVIGATION ============
function switchTab(section, btn) {
    document.querySelectorAll('.db-section').forEach(s => s.classList.remove('active'));
    document.getElementById('section-' + section).classList.add('active');
    document.querySelectorAll('.nav-tab').forEach(t => t.classList.remove('active'));
    btn.classList.add('active');
    if (section === 'calendar') renderCalendar();
}

// ============ FINANCE RENDER ============
function calcFiat(item) {
    return (item.amount * item.rate) - item.fees;
}

function renderFinance() {
    const tbody = document.getElementById('finance-tbody');
    const stats = document.getElementById('finance-stats');
    
    let totalIncome = 0, totalExpense = 0, totalFiat = 0;
    
    if (state.finance.length === 0) {
        tbody.innerHTML = '<tr><td colspan="8" class="empty-state"><div class="empty-state-icon">💰</div>Нет записей. Добавьте первую!</td></tr>';
    } else {
        tbody.innerHTML = state.finance.map(item => {
            const fiat = calcFiat(item);
            if (item.type === 'Доход') totalIncome += item.amount;
            else totalExpense += item.amount;
            totalFiat += fiat;
            const isIncome = item.type === 'Доход';
            return `
                <tr>
                    <td class="text-secondary">${item.date}</td>
                    <td><span class="tag ${isIncome ? 'tag-income' : 'tag-expense'}">${item.type}</span></td>
                    <td><span class="tag tag-category">${item.category}</span></td>
                    <td>${item.amount.toLocaleString('ru-RU')}</td>
                    <td>${item.rate}</td>
                    <td>${item.fees}</td>
                    <td><span class="${fiat >= 0 ? 'formula-value' : 'formula-value formula-negative'}">${Math.round(fiat).toLocaleString('ru-RU')} ₽</span></td>
                    <td class="text-secondary">${item.comment || '—'}</td>
                </tr>
            `;
        }).join('');
    }
    
    stats.innerHTML = `
        <div class="stat-card">
            <div class="stat-value income">+${totalIncome.toLocaleString('ru-RU')}</div>
            <div class="stat-label">Доходы USDT</div>
        </div>
        <div class="stat-card">
            <div class="stat-value expense">-${totalExpense.toLocaleString('ru-RU')}</div>
            <div class="stat-label">Расходы USDT</div>
        </div>
        <div class="stat-card">
            <div class="stat-value balance">${Math.round(totalFiat).toLocaleString('ru-RU')} ₽</div>
            <div class="stat-label">Итого в фиате</div>
        </div>
    `;
}

// ============ CALENDAR RENDER ============
const MONTHS = ['Январь', 'Февраль', 'Март', 'Апрель', 'Май', 'Июнь', 'Июль', 'Август', 'Сентябрь', 'Октябрь', 'Ноябрь', 'Декабрь'];

function changeMonth(delta) {
    calendarDate.setMonth(calendarDate.getMonth() + delta);
    renderCalendar();
}

function renderCalendar() {
    const cal = document.getElementById('calendar');
    const title = document.getElementById('calendar-title');
    const tbody = document.getElementById('calendar-tbody');
    
    const year = calendarDate.getFullYear();
    const month = calendarDate.getMonth();
    title.textContent = `${MONTHS[month]} ${year}`;
    
    const firstDay = new Date(year, month, 1);
    const lastDay = new Date(year, month + 1, 0);
    const startDay = (firstDay.getDay() + 6) % 7;
    
    const eventDays = new Set();
    state.calendar.forEach(ev => {
        const d = new Date(ev.datetime);
        if (d.getFullYear() === year && d.getMonth() === month) {
            eventDays.add(d.getDate());
        }
    });
    
    let html = ['Пн', 'Вт', 'Ср', 'Чт', 'Пт', 'Сб', 'Вс']
        .map(d => `<div class="calendar-header-cell">${d}</div>`).join('');
    
    const prevLast = new Date(year, month, 0).getDate();
    for (let i = startDay - 1; i >= 0; i--) {
        html += `<div class="calendar-cell other-month">${prevLast - i}</div>`;
    }
    
    const today = new Date();
    for (let d = 1; d <= lastDay.getDate(); d++) {
        const classes = ['calendar-cell'];
        if (d === today.getDate() && month === today.getMonth() && year === today.getFullYear()) {
            classes.push('today');
        }
        if (eventDays.has(d)) classes.push('has-event');
        html += `<div class="${classes.join(' ')}">${d}</div>`;
    }
    
    const totalCells = startDay + lastDay.getDate();
    const remaining = (7 - (totalCells % 7)) % 7;
    for (let i = 1; i <= remaining; i++) {
        html += `<div class="calendar-cell other-month">${i}</div>`;
    }
    
    cal.innerHTML = html;
    
    if (state.calendar.length === 0) {
        tbody.innerHTML = '<tr><td colspan="5" class="empty-state"><div class="empty-state-icon">📅</div>Нет событий</td></tr>';
    } else {
        tbody.innerHTML = state.calendar.map(ev => {
            const related = ev.relationId ? state.finance.find(f => f.id === ev.relationId) : null;
            return `
                <tr>
                    <td>${ev.title}</td>
                    <td class="text-secondary">${ev.datetime.replace('T', ' ')}</td>
                    <td><span class="tag tag-type">${ev.type}</span></td>
                    <td><span class="tag ${ev.status === 'Сделано' ? 'tag-done' : 'tag-status'}">${ev.status}</span></td>
                    <td>${related ? `<span class="relation-link">🔗 ${related.category}</span>` : '—'}</td>
                </tr>
            `;
        }).join('');
    }
}

// ============ NOTES BOARD RENDER ============
function renderNotes() {
    const container = document.getElementById('board-container');
    
    if (state.notes.length === 0) {
        container.innerHTML = '<div class="empty-state" style="grid-column: 1/-1;"><div class="empty-state-icon">📝</div>Нет заметок</div>';
        return;
    }
    
    const grouped = {};
    TAGS.forEach(t => grouped[t] = []);
    grouped['другое'] = [];
    
    state.notes.forEach(n => {
        if (n.tags.length === 0) {
            grouped['другое'].push(n);
        } else {
            n.tags.forEach(t => {
                if (grouped[t]) grouped[t].push(n);
                else grouped['другое'].push(n);
            });
        }
    });
    
    container.innerHTML = TAGS.map(tag => {
        const items = grouped[tag];
        const tagClass = tag === 'работа' ? 'tag-work' : tag === 'личное' ? 'tag-personal' : tag === 'идеи' ? 'tag-ideas' : 'tag-finance';
        return `
            <div class="board-column">
                <div class="board-column-title">
                    <span>#${tag}</span>
                    <span class="board-count">${items.length}</span>
                </div>
                ${items.length === 0 ? '<div style="font-size:0.75rem;color:var(--text-secondary);text-align:center;padding:20px 0;">Пусто</div>' : 
                items.map(n => {
                    const date = new Date(n.createdAt);
                    const dateStr = date.toLocaleDateString('ru-RU', { day: 'numeric', month: 'short' });
                    return `
                        <div class="board-item">
                            <div class="board-item-title">${n.title}</div>
                            <div class="board-item-meta">
                                ${n.tags.map(t => {
                                    const cls = t === 'работа' ? 'tag-work' : t === 'личное' ? 'tag-personal' : t === 'идеи' ? 'tag-ideas' : 'tag-finance';
                                    return `<span class="tag-multi ${cls}">#${t}</span>`;
                                }).join('')}
                            </div>
                            <div class="board-item-meta" style="margin-top: 6px;">Создано: ${dateStr}</div>
                        </div>
                    `;
                }).join('')}
            </div>
        `;
    }).join('');
}

// ============ MODAL ============
function openModal(type) {
    const overlay = document.getElementById('modal-overlay');
    const content = document.getElementById('modal-content');
    
    let html = '';
    
    if (type === 'finance') {
        html = `
            <h3>💰 Новая запись</h3>
            <div class="form-group">
                <label>Дата</label>
                <input type="date" class="input-field" id="f-date" value="${new Date().toISOString().split('T')[0]}">
            </div>
            <div class="form-group">
                <label>Тип</label>
                <select class="select-field" id="f-type">
                    <option value="Доход">Доход</option>
                    <option value="Расход">Расход</option>
                </select>
            </div>
            <div class="form-group">
                <label>Категория</label>
                <select class="select-field" id="f-category">
                    ${CATEGORIES.map(c => `<option value="${c}">${c}</option>`).join('')}
                </select>
            </div>
            <div class="form-group">
                <label>Сумма USDT</label>
                <input type="number" class="input-field" id="f-amount" placeholder="0" step="0.01">
            </div>
            <div class="form-group">
                <label>Курс (₽)</label>
                <input type="number" class="input-field" id="f-rate" placeholder="95.5" step="0.01">
            </div>
            <div class="form-group">
                <label>Комиссии (₽)</label>
                <input type="number" class="input-field" id="f-fees" placeholder="0" step="0.01" value="0">
            </div>
            <div class="form-group">
                <label>Комментарий</label>
                <textarea class="textarea-field" id="f-comment" placeholder="Необязательно"></textarea>
            </div>
            <div class="modal-actions">
                <button class="btn btn-secondary" onclick="closeModal()">Отмена</button>
                <button class="btn btn-primary" onclick="saveFinance()">Сохранить</button>
            </div>
        `;
    } else if (type === 'calendar') {
        html = `
            <h3>📅 Новое событие</h3>
            <div class="form-group">
                <label>Название</label>
                <input type="text" class="input-field" id="c-title" placeholder="Название встречи">
            </div>
            <div class="form-group">
                <label>Дата и время</label>
                <input type="datetime-local" class="input-field" id="c-datetime">
            </div>
            <div class="form-group">
                <label>Тип</label>
                <select class="select-field" id="c-type">
                    ${EVENT_TYPES.map(t => `<option value="${t}">${t}</option>`).join('')}
                </select>
            </div>
            <div class="form-group">
                <label>Статус</label>
                <select class="select-field" id="c-status">
                    <option value="Запланировано">Запланировано</option>
                    <option value="Сделано">Сделано</option>
                </select>
            </div>
            <div class="form-group">
                <label>Связано с финансами (Relation)</label>
                <select class="select-field" id="c-relation">
                    <option value="">— Нет —</option>
                    ${state.finance.map(f => `<option value="${f.id}">${f.date} · ${f.category} · ${f.amount} USDT</option>`).join('')}
                </select>
            </div>
            <div class="modal-actions">
                <button class="btn btn-secondary" onclick="closeModal()">Отмена</button>
                <button class="btn btn-primary" onclick="saveCalendar()">Сохранить</button>
            </div>
        `;
    } else if (type === 'notes') {
        html = `
            <h3>📝 Новая заметка</h3>
            <div class="form-group">
                <label>Тема</label>
                <input type="text" class="input-field" id="n-title" placeholder="Тема заметки">
            </div>
            <div class="form-group">
                <label>Теги (через запятую)</label>
                <input type="text" class="input-field" id="n-tags" placeholder="работа, идеи, финансы">
                <div style="margin-top:6px;font-size:0.7rem;color:var(--text-secondary);">
                    Доступные: ${TAGS.map(t => '#'+t).join(', ')}
                </div>
            </div>
            <div class="form-group">
                <label>Содержание</label>
                <textarea class="textarea-field" id="n-content" placeholder="Пишите здесь..." style="min-height:120px;"></textarea>
            </div>
            <div class="modal-actions">
                <button class="btn btn-secondary" onclick="closeModal()">Отмена</button>
                <button class="btn btn-primary" onclick="saveNote()">Сохранить</button>
            </div>
        `;
    }
    
    content.innerHTML = html;
    overlay.classList.add('active');
}

function closeModal() {
    document.getElementById('modal-overlay').classList.remove('active');
}

function saveFinance() {
    const date = document.getElementById('f-date').value;
    const type = document.getElementById('f-type').value;
    const category = document.getElementById('f-category').value;
    const amount = parseFloat(document.getElementById('f-amount').value) || 0;
    const rate = parseFloat(document.getElementById('f-rate').value) || 0;
    const fees = parseFloat(document.getElementById('f-fees').value) || 0;
    const comment = document.getElementById('f-comment').value;
    
    if (!date || amount === 0) {
        alert('Заполните дату и сумму');
        return;
    }
    
    state.finance.push({
        id: 'f' + Date.now(),
        date, type, category, amount, rate, fees, comment
    });
    
    saveState();
    renderFinance();
    closeModal();
}

function saveCalendar() {
    const title = document.getElementById('c-title').value.trim();
    const datetime = document.getElementById('c-datetime').value;
    const type = document.getElementById('c-type').value;
    const status = document.getElementById('c-status').value;
    const relationId = document.getElementById('c-relation').value || null;
    
    if (!title || !datetime) {
        alert('Заполните название и дату');
        return;
    }
    
    state.calendar.push({
        id: 'c' + Date.now(),
        title, datetime, type, status, relationId
    });
    
    saveState();
    renderCalendar();
    closeModal();
}

function saveNote() {
    const title = document.getElementById('n-title').value.trim();
    const tagsRaw = document.getElementById('n-tags').value;
    const content = document.getElementById('n-content').value;
    
    if (!title) {
        alert('Введите тему');
        return;
    }
    
    const tags = tagsRaw.split(',').map(t => t.trim().replace(/^#/, '').toLowerCase()).filter(t => TAGS.includes(t));
    
    state.notes.push({
        id: 'n' + Date.now(),
        title, tags, content, createdAt: Date.now()
    });
    
    saveState();
    renderNotes();
    closeModal();
}

// ============ INIT ============
loadState();
renderFinance();
renderCalendar();
renderNotes();
</script>
</body>
</html>
