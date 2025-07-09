# Ai-automation-checklist
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI Marketing Automation Learning Tracker</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }

        h1 {
            text-align: center;
            color: #2c3e50;
            margin-bottom: 30px;
            font-size: 2.5em;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .progress-overview {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .progress-card {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .progress-card h3 {
            color: #2c3e50;
            margin-bottom: 10px;
        }

        .progress-bar {
            width: 100%;
            height: 10px;
            background: #e0e0e0;
            border-radius: 5px;
            overflow: hidden;
            margin: 10px 0;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
            transition: width 0.3s ease;
        }

        .phase {
            background: white;
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 30px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            border-left: 5px solid #667eea;
        }

        .phase-header {
            display: flex;
            justify-content: between;
            align-items: center;
            margin-bottom: 20px;
        }

        .phase-title {
            color: #2c3e50;
            font-size: 1.5em;
            margin-bottom: 5px;
        }

        .phase-duration {
            color: #7f8c8d;
            font-size: 0.9em;
        }

        .task-list {
            list-style: none;
        }

        .task-item {
            background: #f8f9fa;
            margin: 10px 0;
            padding: 15px;
            border-radius: 10px;
            border-left: 4px solid #e0e0e0;
            transition: all 0.3s ease;
        }

        .task-item.completed {
            background: #d4edda;
            border-left-color: #28a745;
        }

        .task-item.in-progress {
            background: #fff3cd;
            border-left-color: #ffc107;
        }

        .task-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }

        .task-title {
            font-weight: bold;
            color: #2c3e50;
        }

        .task-controls {
            display: flex;
            gap: 10px;
        }

        .btn {
            padding: 5px 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 0.8em;
            transition: all 0.3s ease;
        }

        .btn-complete {
            background: #28a745;
            color: white;
        }

        .btn-in-progress {
            background: #ffc107;
            color: #212529;
        }

        .btn-reset {
            background: #6c757d;
            color: white;
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        }

        .notes-section {
            margin-top: 15px;
        }

        .notes-input {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 0.9em;
            min-height: 60px;
            resize: vertical;
        }

        .date-completed {
            font-size: 0.8em;
            color: #6c757d;
            font-style: italic;
        }

        .export-btn {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 12px 24px;
            border: none;
            border-radius: 10px;
            font-size: 1em;
            cursor: pointer;
            margin: 10px 5px;
            transition: all 0.3s ease;
        }

        .export-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 16px rgba(0,0,0,0.2);
        }

        .export-section {
            text-align: center;
            margin-top: 30px;
            padding: 20px;
            background: #f8f9fa;
            border-radius: 15px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>AI Marketing Automation Learning Tracker</h1>
        
        <div class="progress-overview">
            <div class="progress-card">
                <h3>Overall Progress</h3>
                <div class="progress-bar">
                    <div class="progress-fill" id="overall-progress"></div>
                </div>
                <p id="overall-percentage">0%</p>
            </div>
            <div class="progress-card">
                <h3>Tasks Completed</h3>
                <p id="completed-tasks">0 / 0</p>
            </div>
            <div class="progress-card">
                <h3>Current Phase</h3>
                <p id="current-phase">Pre-Launch</p>
            </div>
            <div class="progress-card">
                <h3>Days Active</h3>
                <p id="days-active">0</p>
            </div>
        </div>

        <div class="phase">
            <div class="phase-header">
                <div>
                    <h2 class="phase-title">Phase 0: Pre-Launch</h2>
                    <p class="phase-duration">Week 0 - Setup your automation command center</p>
                </div>
            </div>
            <ul class="task-list">
                <li class="task-item" data-phase="0">
                    <div class="task-header">
                        <span class="task-title">Set up Trello for project tracking</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
                <li class="task-item" data-phase="0">
                    <div class="task-header">
                        <span class="task-title">Create Notion portfolio page (free tier)</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
                <li class="task-item" data-phase="0">
                    <div class="task-header">
                        <span class="task-title">Set up GitHub account for automation scripts</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
                <li class="task-item" data-phase="0">
                    <div class="task-header">
                        <span class="task-title">Create "Learn in Public" social account (LinkedIn/X)</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
            </ul>
        </div>

        <div class="phase">
            <div class="phase-header">
                <div>
                    <h2 class="phase-title">Phase 1: Foundations</h2>
                    <p class="phase-duration">Weeks 1-4 - Master no-code basics + AI-powered marketing fundamentals</p>
                </div>
            </div>
            <ul class="task-list">
                <li class="task-item" data-phase="1">
                    <div class="task-header">
                        <span class="task-title">Complete Zapier's 2025 "AI Automation for Marketers" course</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
                <li class="task-item" data-phase="1">
                    <div class="task-header">
                        <span class="task-title">Project: Build lead-to-email automation (Zapier + ChatGPT)</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
                <li class="task-item" data-phase="1">
                    <div class="task-header">
                        <span class="task-title">Learn Make (Integromat) multi-step workflows</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></content>
                    </div>
                </li>
                <li class="task-item" data-phase="1">
                    <div class="task-header">
                        <span class="task-title">Project: Automate content calendar sync (Google Calendar + Buffer)</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
                <li class="task-item" data-phase="1">
                    <div class="task-header">
                        <span class="task-title">Complete Google's "Generative AI for Marketers" course</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
            </ul>
        </div>

        <div class="phase">
            <div class="phase-header">
                <div>
                    <h2 class="phase-title">Phase 2: AI Automation Deep Dive</h2>
                    <p class="phase-duration">Weeks 5-12 - Build complex workflows with AI integrations</p>
                </div>
            </div>
            <ul class="task-list">
                <li class="task-item" data-phase="2">
                    <div class="task-header">
                        <span class="task-title">Set up AI agent with Lindy.ai for competitor pricing alerts</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
                <li class="task-item" data-phase="2">
                    <div class="task-header">
                        <span class="task-title">Build customer sentiment analyzer with n8n + LangChain</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
                <li class="task-item" data-phase="2">
                    <div class="task-header">
                        <span class="task-title">Automate LinkedIn lead scraping with Bardeen.ai</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
                <li class="task-item" data-phase="2">
                    <div class="task-header">
                        <span class="task-title">Portfolio Project: Create Dynamic Pricing Engine</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
            </ul>
        </div>

        <div class="phase">
            <div class="phase-header">
                <div>
                    <h2 class="phase-title">Phase 3: Data & Predictive Marketing</h2>
                    <p class="phase-duration">Weeks 13-20 - Leverage AI for data-driven decisions</p>
                </div>
            </div>
            <ul class="task-list">
                <li class="task-item" data-phase="3">
                    <div class="task-header">
                        <span class="task-title">Complete Google's "Advanced GA4 for Marketers" course</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></content>
                    </div>
                </li>
                <li class="task-item" data-phase="3">
                    <div class="task-header">
                        <span class="task-title">Project: Automate weekly performance report with Looker Studio</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
                <li class="task-item" data-phase="3">
                    <div class="task-header">
                        <span class="task-title">Set up Mixpanel for user behavior tracking</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
                <li class="task-item" data-phase="3">
                    <div class="task-header">
                        <span class="task-title">Use Clay.com for AI-powered lead enrichment</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
            </ul>
        </div>

        <div class="phase">
            <div class="phase-header">
                <div>
                    <h2 class="phase-title">Phase 4: Portfolio & Job Launch</h2>
                    <p class="phase-duration">Weeks 21-28 - Build standout portfolio and land interviews</p>
                </div>
            </div>
            <ul class="task-list">
                <li class="task-item" data-phase="4">
                    <div class="task-header">
                        <span class="task-title">Build AI-Powered Newsletter System (n8n + OpenAI + Substack)</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
                <li class="task-item" data-phase="4">
                    <div class="task-header">
                        <span class="task-title">Create Voice-Based Customer Feedback Analyzer</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
                <li class="task-item" data-phase="4">
                    <div class="task-header">
                        <span class="task-title">Build Autonomous LinkedIn Growth Agent</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
                <li class="task-item" data-phase="4">
                    <div class="task-header">
                        <span class="task-title">Create resume with Kickresume's AI builder</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
                <li class="task-item" data-phase="4">
                    <div class="task-header">
                        <span class="task-title">Post 1 automation tutorial/week on LinkedIn</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
                <li class="task-item" data-phase="4">
                    <div class="task-header">
                        <span class="task-title">Get HubSpot's 2025 Marketing Automation Certification</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
                <li class="task-item" data-phase="4">
                    <div class="task-header">
                        <span class="task-title">Create final Notion portfolio with "Hire Me" page</span>
                        <div class="task-controls">
                            <button class="btn btn-complete" onclick="updateTask(this, 'completed')">Complete</button>
                            <button class="btn btn-in-progress" onclick="updateTask(this, 'in-progress')">In Progress</button>
                            <button class="btn btn-reset" onclick="updateTask(this, 'not-started')">Reset</button>
                        </div>
                    </div>
                    <div class="notes-section">
                        <textarea class="notes-input" placeholder="Add your notes, insights, or progress details here..."></textarea>
                    </div>
                </li>
            </ul>
        </div>

        <div class="export-section">
            <h3>Export Your Progress</h3>
            <p>Save your progress and notes for your records:</p>
            <button class="export-btn" onclick="exportToPDF()">Export to PDF</button>
            <button class="export-btn" onclick="exportToCSV()">Export to CSV</button>
            <button class="export-btn" onclick="exportProgress()">Export Progress Report</button>
        </div>
    </div>

    <script>
        // Initialize the app
        let startDate = new Date().toISOString().split('T')[0];
        let taskData = {};

        // Load saved data
        function loadSavedData() {
            const saved = localStorage.getItem('aiMarketingProgress');
            if (saved) {
                const data = JSON.parse(saved);
                taskData = data.taskData || {};
                startDate = data.startDate || startDate;
                
                // Restore task states
                document.querySelectorAll('.task-item').forEach((item, index) => {
                    const taskId = `task-${index}`;
                    if (taskData[taskId]) {
                        const task = taskData[taskId];
                        item.className = `task-item ${task.status}`;
                        const textarea = item.querySelector('.notes-input');
                        if (textarea) textarea.value = task.notes || '';
                        
                        if (task.status ===
