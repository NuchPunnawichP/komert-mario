<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>NuchPunnawichP's GitHub Stats</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    }
    
    body {
      background-color: #0d1117;
      color: #c9d1d9;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      padding: 2rem;
    }
    
    .container {
      max-width: 1000px;
      width: 100%;
    }
    
    .profile-header {
      display: flex;
      align-items: center;
      gap: 1.5rem;
      margin-bottom: 2rem;
    }
    
    .profile-avatar {
      width: 80px;
      height: 80px;
      border-radius: 50%;
      background-color: #30363d;
    }
    
    .profile-info h1 {
      font-size: 1.8rem;
      margin-bottom: 0.5rem;
      color: #f0f6fc;
    }
    
    .profile-info p {
      color: #8b949e;
    }
    
    .stats-container {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.5rem;
      margin-bottom: 2rem;
    }
    
    @media (max-width: 768px) {
      .stats-container {
        grid-template-columns: 1fr;
      }
    }
    
    .stats-card, .languages-card, .contributions-card, .repositories-card {
      background-color: #161b22;
      border-radius: 6px;
      padding: 1.5rem;
      border: 1px solid #30363d;
    }
    
    .card-title {
      font-size: 1.2rem;
      color: #58a6ff;
      margin-bottom: 1.5rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }
    
    .stat-item {
      display: flex;
      align-items: center;
      margin-bottom: 1rem;
      gap: 1rem;
    }
    
    .stat-icon {
      width: 24px;
      height: 24px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #8b949e;
    }
    
    .stat-label {
      flex: 1;
      color: #8b949e;
    }
    
    .stat-value {
      font-weight: bold;
      color: #f0f6fc;
    }
    
    .languages-card {
      grid-column: span 2;
    }
    
    @media (max-width: 768px) {
      .languages-card {
        grid-column: span 1;
      }
    }
    
    .languages-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.5rem;
    }
    
    @media (max-width: 768px) {
      .languages-grid {
        grid-template-columns: 1fr;
      }
    }
    
    .language-stats {
      flex: 1;
    }
    
    .language-item {
      display: flex;
      align-items: center;
      margin-bottom: 0.75rem;
      gap: 0.5rem;
    }
    
    .language-color {
      width: 12px;
      height: 12px;
      border-radius: 50%;
    }
    
    .language-name {
      flex: 1;
      color: #c9d1d9;
    }
    
    .language-percentage {
      color: #8b949e;
    }
    
    .language-bar {
      height: 8px;
      background-color: #30363d;
      border-radius: 4px;
      margin-top: 0.25rem;
      overflow: hidden;
    }
    
    .language-progress {
      height: 100%;
      border-radius: 4px;
    }
    
    .chart-container {
      position: relative;
      width: 240px;
      height: 240px;
    }
    
    .donut-chart {
      width: 100%;
      height: 100%;
    }
    
    .chart-center {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      text-align: center;
    }
    
    .chart-grade {
      font-size: 3rem;
      font-weight: bold;
      color: #f0f6fc;
    }
    
    .chart-label {
      color: #8b949e;
      font-size: 0.9rem;
    }
    
    .contributions-card {
      grid-column: span 2;
    }
    
    @media (max-width: 768px) {
      .contributions-card {
        grid-column: span 1;
      }
    }
    
    .contribution-graph {
      display: flex;
      gap: 3px;
      overflow-x: auto;
      padding-bottom: 1rem;
    }
    
    .contribution-week {
      display: flex;
      flex-direction: column;
      gap: 3px;
    }
    
    .contribution-day {
      width: 10px;
      height: 10px;
      border-radius: 2px;
      background-color: #161b22;
      border: 1px solid #30363d;
    }
    
    .contribution-day.level-0 {
      background-color: #161b22;
    }
    
    .contribution-day.level-1 {
      background-color: #0e4429;
    }
    
    .contribution-day.level-2 {
      background-color: #006d32;
    }
    
    .contribution-day.level-3 {
      background-color: #26a641;
    }
    
    .contribution-day.level-4 {
      background-color: #39d353;
    }
    
    .repositories-list {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1rem;
    }
    
    @media (max-width: 768px) {
      .repositories-list {
        grid-template-columns: 1fr;
      }
    }
    
    .repository-item {
      border: 1px solid #30363d;
      border-radius: 6px;
      padding: 1rem;
      background-color: #0d1117;
    }
    
    .repository-name {
      color: #58a6ff;
      font-weight: bold;
      margin-bottom: 0.5rem;
    }
    
    .repository-description {
      color: #8b949e;
      font-size: 0.9rem;
      margin-bottom: 1rem;
      display: -webkit-box;
      -webkit-box-orient: vertical;
      -webkit-line-clamp: 2;
      overflow: hidden;
    }
    
    .repository-meta {
      display: flex;
      align-items: center;
      gap: 1rem;
      font-size: 0.8rem;
      color: #8b949e;
    }
    
    .repository-meta-item {
      display: flex;
      align-items: center;
      gap: 0.25rem;
    }
    
    .summary-footer {
      margin-top: 2rem;
      text-align: center;
      color: #8b949e;
      font-size: 0.9rem;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="profile-header">
      <div class="profile-avatar"></div>
      <div class="profile-info">
        <h1>NuchPunnawichP</h1>
        <p>Developer & Student</p>
      </div>
    </div>
    
    <div class="stats-container">
      <div class="stats-card">
        <h2 class="card-title">
          <svg viewBox="0 0 16 16" width="16" height="16" fill="currentColor">
            <path d="M8 .25a.75.75 0 0 1 .673.418l1.882 3.815 4.21.612a.75.75 0 0 1 .416 1.279l-3.046 2.97.719 4.192a.751.751 0 0 1-1.088.791L8 12.347l-3.766 1.98a.75.75 0 0 1-1.088-.79l.72-4.194L.818 6.374a.75.75 0 0 1 .416-1.28l4.21-.611L7.327.668A.75.75 0 0 1 8 .25Z"></path>
          </svg>
          GitHub Stats
        </h2>
        <div class="stat-item">
          <div class="stat-icon">
            <svg viewBox="0 0 16 16" width="16" height="16" fill="currentColor">
              <path d="M8 .25a.75.75 0 0 1 .673.418l1.882 3.815 4.21.612a.75.75 0 0 1 .416 1.279l-3.046 2.97.719 4.192a.751.751 0 0 1-1.088.791L8 12.347l-3.766 1.98a.75.75 0 0 1-1.088-.79l.72-4.194L.818 6.374a.75.75 0 0 1 .416-1.28l4.21-.611L7.327.668A.75.75 0 0 1 8 .25Z"></path>
            </svg>
          </div>
          <div class="stat-label">Total Stars Earned</div>
          <div class="stat-value">28</div>
        </div>
        <div class="stat-item">
          <div class="stat-icon">
            <svg viewBox="0 0 16 16" width="16" height="16" fill="currentColor">
              <path d="M1.643 3.143 .427 1.927A.25.25 0 0 0 0 2.104V5.75c0 .138.112.25.25.25h3.646a.25.25 0 0 0 .177-.427L2.715 4.215a6.5 6.5 0 1 1-1.18 4.458.75.75 0 1 0-1.493.154 8.001 8.001 0 1 0 1.6-5.684ZM7.75 4a.75.75 0 0 1 .75.75v2.992l2.028.812a.75.75 0 0 1-.557 1.392l-2.5-1A.751.751 0 0 1 7 8.25v-3.5A.75.75 0 0 1 7.75 4Z"></path>
            </svg>
          </div>
          <div class="stat-label">Total Commits</div>
          <div class="stat-value">462</div>
        </div>
        <div class="stat-item">
          <div class="stat-icon">
            <svg viewBox="0 0 16 16" width="16" height="16" fill="currentColor">
              <path d="M7.177 3.073 9.573.677A.25.25 0 0 1 10 .854v4.792a.25.25 0 0 1-.427.177L7.177 3.427a.25.25 0 0 1 0-.354ZM3.75 2.5a.75.75 0 1 0 0 1.5.75.75 0 0 0 0-1.5Zm0 5.5a.75.75 0 1 0 0 1.5.75.75 0 0 0 0-1.5Zm0 5.5a.75.75 0 1 0 0 1.5.75.75 0 0 0 0-1.5Z"></path>
            </svg>
          </div>
          <div class="stat-label">Total PRs</div>
          <div class="stat-value">14</div>
        </div>
        <div class="stat-item">
          <div class="stat-icon">
            <svg viewBox="0 0 16 16" width="16" height="16" fill="currentColor">
              <path d="M8 9.5a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Z"></path><path d="M8 0a8 8 0 1 1 0 16A8 8 0 0 1 8 0ZM1.5 8a6.5 6.5 0 1 0 13 0 6.5 6.5 0 0 0-13 0Z"></path>
            </svg>
          </div>
          <div class="stat-label">Total Issues</div>
          <div class="stat-value">8</div>
        </div>
        <div class="stat-item">
          <div class="stat-icon">
            <svg viewBox="0 0 16 16" width="16" height="16" fill="currentColor">
              <path d="M2 2.5A2.5 2.5 0 0 1 4.5 0h8.75a.75.75 0 0 1 .75.75v12.5a.75.75 0 0 1-.75.75h-2.5a.75.75 0 0 1 0-1.5h1.75v-2h-8a1 1 0 0 0-.714 1.7.75.75 0 1 1-1.072 1.05A2.495 2.495 0 0 1 2 11.5Zm10.5-1h-8a1 1 0 0 0-1 1v6.708A2.486 2.486 0 0 1 4.5 9h8ZM5 12.25a.25.25 0 0 1 .25-.25h3.5a.25.25 0 0 1 .25.25v3.25a.25.25 0 0 1-.4.2l-1.45-1.087a.249.249 0 0 0-.3 0L5.4 15.7a.25.25 0 0 1-.4-.2Z"></path>
            </svg>
          </div>
          <div class="stat-label">Contributed to (last year)</div>
          <div class="stat-value">10</div>
        </div>
      </div>
      
      <div class="stats-card">
        <h2 class="card-title">
          <svg viewBox="0 0 16 16" width="16" height="16" fill="currentColor">
            <path d="M12.17 9.53c2.307-2.592 3.278-4.684 3.641-6.218.21-.887.214-1.58.16-2.065a3.578 3.578 0 0 0-.281-.95 3.377 3.377 0 0 0-.772-.984c-.277-.215-.624-.394-1.104-.517-.478-.123-1.059-.182-1.79-.182-1.775 0-5.784.923-13.544 7.396 1.01-.262 1.94-.429 2.83-.429 1.284 0 2.527.175 3.29.48.236.094.437.213.558.343.115.124.24.347.302.604.057.243.071.487.024.788-.234 1.454.785 3.39 1.86 4.593"></path>
          </svg>
          Performance Grade
        </h2>
        <div style="display: flex; justify-content: center; margin-top: 1rem;">
          <div class="chart-container">
            <svg class="donut-chart" viewBox="0 0 40 40">
              <circle cx="20" cy="20" r="15.915" fill="none" stroke="#30363d" stroke-width="3"></circle>
              <circle cx="20" cy="20" r="15.915" fill="none" stroke="#58a6ff" stroke-width="3" stroke-dasharray="85, 100" stroke-dashoffset="25" transform="rotate(-90 20 20)"></circle>
            </svg>
            <div class="chart-center">
              <div class="chart-grade">B+</div>
              <div class="chart-label">85%</div>
            </div>
          </div>
        </div>
      </div>
      
      <div class="languages-card">
        <h2 class="card-title">
          <svg viewBox="0 0 16 16" width="16" height="16" fill="currentColor">
            <path d="m11.28 3.22 4.25 4.25a.75.75 0 0 1 0 1.06l-4.25 4.25a.749.749 0 0 1-1.275-.326.749.749 0 0 1 .215-.734L13.94 8l-3.72-3.72a.749.749 0 0 1 .326-1.275.749.749 0 0 1 .734.215Zm-6.56 0a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042L2.06 8l3.72 3.72a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L.47 8.53a.75.75 0 0 1 0-1.06Z"></path>
          </svg>
          Most Used Languages
        </h2>
        <div class="languages-grid">
          <div class="language-stats">
            <div class="language-item">
              <div class="language-color" style="background-color: #DA5B0B;"></div>
              <div class="language-name">JavaScript</div>
              <div class="language-percentage">45.2%</div>
            </div>
            <div class="language-bar">
              <div class="language-progress" style="width: 45.2%; background-color: #DA5B0B;"></div>
            </div>
            
            <div class="language-item">
              <div class="language-color" style="background-color: #563d7c;"></div>
              <div class="language-name">CSS</div>
              <div class="language-percentage">22.8%</div>
            </div>
            <div class="language-bar">
              <div class="language-progress" style="width: 22.8%; background-color: #563d7c;"></div>
            </div>
            
            <div class="language-item">
              <div class="language-color" style="background-color: #3572A5;"></div>
              <div class="language-name">Python</div>
              <div class="language-percentage">18.7%</div>
            </div>
            <div class="language-bar">
              <div class="language-progress" style="width: 18.7%; background-color: #3572A5;"></div>
            </div>
          </div>
          
          <div class="chart-container">
            <svg class="donut-chart" viewBox="0 0 40 40">
              <circle cx="20" cy="20" r="15.915" fill="none" stroke="#30363d" stroke-width="3"></circle>
              <!-- JavaScript - 45.2% -->
              <circle cx="20" cy="20" r="15.915" fill="none" stroke="#DA5B0B" stroke-width="3" stroke-dasharray="45.2, 100" stroke-dashoffset="25" transform="rotate(-90 20 20)"></circle>
              <!-- CSS - 22.8% -->
              <circle cx="20" cy="20" r="15.915" fill="none" stroke="#563d7c" stroke-width="3" stroke-dasharray="22.8, 100" stroke-dashoffset="79.2" transform="rotate(-90 20 20)"></circle>
              <!-- Python - 18.7% -->
              <circle cx="20" cy="20" r="15.915" fill="none" stroke="#3572A5" stroke-width="3" stroke-dasharray="18.7, 100" stroke-dashoffset="102" transform="rotate(-90 20 20)"></circle>
              <!-- HTML - 8.3% -->
              <circle cx="20" cy="20" r="15.915" fill="none" stroke="#e34c26" stroke-width="3" stroke-dasharray="8.3, 100" stroke-dashoffset="120.7" transform="rotate(-90 20 20)"></circle>
              <!-- Java - 5% -->
              <circle cx="20" cy="20" r="15.915" fill="none" stroke="#b07219" stroke-width="3" stroke-dasharray="5, 100" stroke-dashoffset="129" transform="rotate(-90 20 20)"></circle>
            </svg>
            <div class="language-item">
              <div class="language-color" style="background-color: #e34c26;"></div>
              <div class="language-name">HTML</div>
              <div class="language-percentage">8.3%</div>
            </div>
            <div class="language-bar">
              <div class="language-progress" style="width: 8.3%; background-color: #e34c26;"></div>
            </div>
            
            <div class="language-item">
              <div class="language-color" style="background-color: #b07219;"></div>
              <div class="language-name">Java</div>
              <div class="language-percentage">5.0%</div>
            </div>
            <div class="language-bar">
              <div class="language-progress" style="width: 5.0%; background-color: #b07219;"></div>
            </div>
          </div>
        </div>
      </div>
      
      <div class="contributions-card">
        <h2 class="card-title">
          <svg viewBox="0 0 16 16" width="16" height="16" fill="currentColor">
            <path d="M10.5 2a2.5 2.5 0 1 1-5 0 2.5 2.5 0 0 1 5 0Zm1.5 5a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z"></path><path d="M0 13a2 2 0 0 1 2-2h12a2 2 0 0 1 2 2v3H0v-3Zm3-1h1v2H3v-2Zm9 0h1v2h-1v-2Z"></path>
          </svg>
          Contribution Activity
        </h2>
        <div class="contribution-graph">
          <!-- Each column represents a week (7 days) -->
          <!-- We'll show 20 weeks of data -->
          <!-- Each square's fill color represents activity level -->
          <div class="contribution-week">
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-1"></div>
            <div class="contribution-day level-3"></div>
            <div class="contribution-day level-1"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-2"></div>
            <div class="contribution-day level-0"></div>
          </div>
          <div class="contribution-week">
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-3"></div>
            <div class="contribution-day level-2"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-1"></div>
            <div class="contribution-day level-4"></div>
            <div class="contribution-day level-0"></div>
          </div>
          <div class="contribution-week">
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-2"></div>
            <div class="contribution-day level-3"></div>
            <div class="contribution-day level-1"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-2"></div>
            <div class="contribution-day level-0"></div>
          </div>
          <div class="contribution-week">
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-1"></div>
            <div class="contribution-day level-2"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-0"></div>
          </div>
          <div class="contribution-week">
            <div class="contribution-day level-1"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-3"></div>
            <div class="contribution-day level-4"></div>
            <div class="contribution-day level-2"></div>
            <div class="contribution-day level-1"></div>
          </div>
          <div class="contribution-week">
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-1"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-3"></div>
            <div class="contribution-day level-2"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-0"></div>
          </div>
          <div class="contribution-week">
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-2"></div>
            <div class="contribution-day level-3"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-1"></div>
          </div>
          <div class="contribution-week">
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-1"></div>
            <div class="contribution-day level-2"></div>
            <div class="contribution-day level-4"></div>
            <div class="contribution-day level-2"></div>
            <div class="contribution-day level-0"></div>
          </div>
          <div class="contribution-week">
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-1"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-2"></div>
            <div class="contribution-day level-3"></div>
          </div>
          <div class="contribution-week">
            <div class="contribution-day level-1"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-2"></div>
            <div class="contribution-day level-3"></div>
            <div class="contribution-day level-4"></div>
          </div>
          <div class="contribution-week">
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-1"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-3"></div>
            <div class="contribution-day level-2"></div>
            <div class="contribution-day level-0"></div>
          </div>
          <div class="contribution-week">
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-1"></div>
            <div class="contribution-day level-2"></div>
            <div class="contribution-day level-3"></div>
            <div class="contribution-day level-4"></div>
            <div class="contribution-day level-0"></div>
            <div class="contribution-day level-1"></div>
          </div>
        </div>
      </div>
      
      <div class="repositories-card">
        <h2 class="card-title">
          <svg viewBox="0 0 16 16" width="16" height="16" fill="currentColor">
            <path d="M2 2.5A2.5 2.5 0 0 1 4.5 0h8.75a.75.75 0 0 1 .75.75v12.5a.75.75 0 0 1-.75.75h-2.5a.75.75 0 0 1 0-1.5h1.75v-2h-8a1 1 0 0 0-.714 1.7.75.75 0 1 1-1.072 1.05A2.495 2.495 0 0 1 2 11.5Zm10.5-1h-8a1 1 0 0 0-1 1v6.708A2