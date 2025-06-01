<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Why Method - Science-Backed Goal Achievement System</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Cormorant+Garamond:wght@300;400;500;600&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --cream: #FEFDF9;
            --warm-white: #FFFFFF;
            --soft-beige: #F7F5F3;
            --charcoal: #1A1A1A;
            --muted-gray: #6B6B6B;
            --light-gray: #F0F0F0;
            --border-light: #E8E6E3;
            --accent-sage: #9CAF88;
            --light-sage: #E8EDE5;
            --warm-terracotta: #D4A574;
            --soft-pink: #F5EDE8;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: var(--cream);
            color: var(--charcoal);
            line-height: 1.6;
            font-weight: 400;
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .hero {
            padding: 5rem 0 4rem;
            text-align: center;
            background: var(--warm-white);
            border-bottom: 1px solid var(--border-light);
        }

        .hero h1 {
            font-family: 'Cormorant Garamond', serif;
            font-size: clamp(2.8rem, 5vw, 4.2rem);
            font-weight: 400;
            color: var(--charcoal);
            margin-bottom: 1.5rem;
            letter-spacing: -0.02em;
            line-height: 1.1;
        }

        .hero .tagline {
            font-size: 1.3rem;
            color: var(--muted-gray);
            max-width: 650px;
            margin: 0 auto 2.5rem;
            font-weight: 300;
            line-height: 1.5;
        }

        .research-stat {
            background: var(--soft-pink);
            padding: 2rem 2.5rem;
            border-radius: 12px;
            margin: 2.5rem auto;
            max-width: 650px;
            border-left: 4px solid var(--warm-terracotta);
            text-align: left;
        }

        .stat-highlight {
            font-size: 1.4rem;
            font-weight: 600;
            color: var(--charcoal);
            display: block;
            margin-bottom: 0.75rem;
            line-height: 1.3;
        }

        .stat-subtext {
            font-size: 1rem;
            color: var(--muted-gray);
            font-weight: 400;
            line-height: 1.5;
        }

        .main-content {
            padding: 3rem 0;
            background: var(--cream);
        }

        .conversation-card {
            background: var(--warm-white);
            border-radius: 16px;
            padding: 3rem;
            box-shadow: 0 2px 20px rgba(26, 26, 26, 0.06);
            border: 1px solid var(--border-light);
            margin-bottom: 2rem;
        }

        .section-header {
            margin-bottom: 2.5rem;
            text-align: center;
        }

        .section-title {
            font-family: 'Cormorant Garamond', serif;
            font-size: 2rem;
            font-weight: 500;
            color: var(--charcoal);
            margin-bottom: 0.75rem;
        }

        .section-subtitle {
            font-size: 1.1rem;
            color: var(--muted-gray);
            font-weight: 300;
        }

        .progress-container {
            margin-bottom: 2.5rem;
        }

        .progress-steps {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 1.5rem;
        }

        .step {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            font-size: 0.9rem;
            color: var(--muted-gray);
            font-weight: 500;
        }

        .step-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: var(--border-light);
            transition: all 0.3s ease;
        }

        .step-dot.active {
            background: var(--accent-sage);
            transform: scale(1.2);
        }

        .step-dot.completed {
            background: var(--warm-terracotta);
        }

        .progress-bar {
            background: var(--border-light);
            height: 3px;
            border-radius: 10px;
            overflow: hidden;
        }

        .progress-fill {
            background: linear-gradient(90deg, var(--accent-sage), var(--warm-terracotta));
            height: 100%;
            width: 0%;
            transition: width 0.8s cubic-bezier(0.4, 0, 0.2, 1);
            border-radius: 10px;
        }

        .chat-container {
            background: var(--soft-beige);
            border-radius: 12px;
            padding: 2rem;
            margin-bottom: 2rem;
            min-height: 320px;
        }

        .message {
            margin-bottom: 2rem;
            animation: slideUp 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .message:last-child {
            margin-bottom: 0;
        }

        .bot-message {
            background: var(--warm-white);
            padding: 2rem;
            border-radius: 12px;
            margin-right: 1.5rem;
            box-shadow: 0 1px 10px rgba(26, 26, 26, 0.04);
            font-size: 1.05rem;
            line-height: 1.7;
            border-left: 3px solid var(--accent-sage);
        }

        .user-message {
            background: var(--light-sage);
            padding: 1.5rem;
            border-radius: 12px;
            margin-left: 1.5rem;
            text-align: right;
            font-size: 1rem;
            border-right: 3px solid var(--warm-terracotta);
        }

        .input-section {
            display: flex;
            gap: 1rem;
            align-items: flex-end;
        }

        .input-wrapper {
            flex: 1;
            position: relative;
        }

        .input-field {
            width: 100%;
            padding: 1.25rem 1.5rem;
            border: 1px solid var(--border-light);
            border-radius: 12px;
            font-size: 1rem;
            font-family: inherit;
            background: var(--warm-white);
            transition: all 0.3s ease;
            resize: none;
            font-weight: 400;
        }

        .input-field:focus {
            outline: none;
            border-color: var(--accent-sage);
            box-shadow: 0 0 0 3px rgba(156, 175, 136, 0.1);
        }

        .send-btn {
            padding: 1.25rem 2.5rem;
            background: var(--charcoal);
            color: white;
            border: none;
            border-radius: 12px;
            font-size: 1rem;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s ease;
            text-transform: lowercase;
            letter-spacing: 0.3px;
            font-family: inherit;
        }

        .send-btn:hover {
            background: var(--accent-sage);
            transform: translateY(-1px);
        }

        .typing-indicator {
            display: none;
            color: var(--muted-gray);
            font-style: italic;
            padding: 1rem 2rem;
            animation: pulse 2s infinite;
            font-weight: 300;
        }

        .results-section {
            background: var(--warm-white);
            border-radius: 16px;
            padding: 3rem;
            box-shadow: 0 2px 20px rgba(26, 26, 26, 0.06);
            border: 1px solid var(--border-light);
            display: none;
        }

        .results-header {
            text-align: center;
            margin-bottom: 3rem;
            padding-bottom: 2rem;
            border-bottom: 1px solid var(--border-light);
        }

        .results-header h3 {
            font-family: 'Cormorant Garamond', serif;
            font-size: 2.2rem;
            color: var(--charcoal);
            margin-bottom: 1rem;
            font-weight: 500;
        }

        .results-header p {
            color: var(--muted-gray);
            font-weight: 300;
            font-size: 1.1rem;
            max-width: 500px;
            margin: 0 auto;
        }

        .download-options {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .download-card {
            background: var(--soft-beige);
            padding: 2.5rem;
            border-radius: 12px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 1px solid var(--border-light);
            position: relative;
        }

        .download-card:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(26, 26, 26, 0.1);
            border-color: var(--accent-sage);
        }

        .download-icon {
            width: 48px;
            height: 48px;
            margin: 0 auto 1.5rem;
            background: var(--accent-sage);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
        }

        .download-title {
            font-family: 'Cormorant Garamond', serif;
            font-size: 1.4rem;
            font-weight: 500;
            margin-bottom: 0.75rem;
            color: var(--charcoal);
        }

        .download-desc {
            font-size: 0.95rem;
            color: var(--muted-gray);
            line-height: 1.5;
            font-weight: 300;
        }

        .expand-btn {
            background: var(--charcoal);
            color: white;
            border: none;
            padding: 0.75rem 2rem;
            border-radius: 8px;
            font-size: 0.9rem;
            cursor: pointer;
            margin: 1.5rem auto;
            display: block;
            transition: all 0.3s ease;
            font-family: inherit;
            font-weight: 500;
        }

        .expand-btn:hover {
            background: var(--accent-sage);
            transform: translateY(-1px);
        }

        .prompt-list {
            display: none;
            margin-top: 2rem;
            padding-top: 2rem;
            border-top: 1px solid var(--border-light);
        }

        .prompt-list.expanded {
            display: block;
        }

        .prompt-item {
            background: var(--light-gray);
            padding: 2rem;
            border-radius: 12px;
            margin-bottom: 1.5rem;
            border-left: 3px solid var(--warm-terracotta);
            transition: all 0.3s ease;
        }

        .prompt-item:hover {
            background: var(--soft-beige);
            transform: translateX(4px);
        }

        .prompt-day {
            font-weight: 600;
            color: var(--warm-terracotta);
            margin-bottom: 0.75rem;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .restart-btn {
            display: block;
            margin: 0 auto;
            padding: 1rem 2.5rem;
            background: transparent;
            color: var(--charcoal);
            border: 1px solid var(--border-light);
            border-radius: 12px;
            font-size: 1rem;
            font-weight: 400;
            cursor: pointer;
            transition: all 0.3s ease;
            text-transform: lowercase;
            letter-spacing: 0.3px;
            font-family: inherit;
        }

        .restart-btn:hover {
            background: var(--charcoal);
            color: white;
            transform: translateY(-1px);
        }

        .summary-box {
            background: var(--light-sage);
            padding: 2rem;
            border-radius: 12px;
            margin-bottom: 2rem;
            border-left: 3px solid var(--accent-sage);
        }

        .summary-title {
            font-family: 'Cormorant Garamond', serif;
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: var(--charcoal);
        }

        .summary-item {
            margin-bottom: 0.75rem;
            font-size: 0.95rem;
        }

        .summary-label {
            font-weight: 600;
            color: var(--charcoal);
        }

        .feature-list {
            background: var(--soft-pink);
            padding: 1.5rem;
            border-radius: 8px;
            margin: 1.5rem 0;
        }

        .feature-item {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            margin-bottom: 0.75rem;
            font-size: 0.9rem;
            color: var(--charcoal);
        }

        .feature-item:last-child {
            margin-bottom: 0;
        }

        .feature-check {
            width: 16px;
            height: 16px;
            background: var(--accent-sage);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 10px;
            font-weight: bold;
            flex-shrink: 0;
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.7; }
            50% { opacity: 1; }
        }

        @media (max-width: 768px) {
            .container {
                padding: 0 1rem;
            }
            
            .hero {
                padding: 3rem 0 2rem;
            }
            
            .conversation-card,
            .results-section {
                padding: 2rem;
            }
            
            .input-section {
                flex-direction: column;
                gap: 1rem;
            }
            
            .bot-message {
                margin-right: 0;
            }
            
            .user-message {
                margin-left: 0;
                text-align: left;
            }

            .download-options {
                grid-template-columns: 1fr;
            }

            .progress-steps {
                flex-direction: column;
                align-items: center;
                gap: 0.75rem;
            }

            .step {
                flex-direction: row;
                gap: 1rem;
            }
        }
    </style>
</head>
<body>
    <section class="hero">
        <div class="container">
            <h1>the why method</h1>
            <p class="tagline">the research-backed system that transforms surface goals into lasting motivation</p>
            
            <div class="research-stat">
                <span class="stat-highlight">People who understand their deeper "why" are 10x more likely to achieve their goals</span>
                <span class="stat-subtext">Dominican University research shows that clarity of purpose is the strongest predictor of goal success, outperforming willpower, talent, and resources</span>
            </div>
        </div>
    </section>

    <div class="container">
        <div class="main-content">
            <div class="conversation-card">
                <div class="section-header">
                    <h2 class="section-title">discover your deeper why</h2>
                    <p class="section-subtitle">two questions. three minutes. transformative clarity.</p>
                </div>
                
                <div class="progress-container">
                    <div class="progress-steps">
                        <div class="step">
                            <div class="step-dot active" id="dot0"></div>
                            <span>goal</span>
                        </div>
                        <div class="step">
                            <div class="step-dot" id="dot1"></div>
                            <span>surface why</span>
                        </div>
                        <div class="step">
                            <div class="step-dot" id="dot2"></div>
                            <span>deeper why</span>
                        </div>
                    </div>
                    
                    <div class="progress-bar">
                        <div class="progress-fill" id="progressFill"></div>
                    </div>
                </div>
                
                <div class="chat-container" id="chatContainer">
                    <div class="message bot-message">
                        Research from neuroscience and performance psychology shows that people who understand their core motivations achieve goals at dramatically higher rates than those who rely on willpower alone.
                        <br><br>
                        <strong>let's start: what specific goal or change are you working toward right now?</strong> fitness, career, relationships, creativity, finances—whatever feels most important to you.
                    </div>
                </div>
                
                <div class="typing-indicator" id="typingIndicator">
                    analyzing your response...
                </div>
                
                <div class="input-section">
                    <div class="input-wrapper">
                        <textarea 
                            class="input-field" 
                            id="userInput" 
                            placeholder="describe your goal..."
                            rows="2"
                            maxlength="500"
                        ></textarea>
                    </div>
                    <button class="send-btn" onclick="sendMessage()">continue</button>
                </div>
            </div>

            <div class="results-section" id="resultsSection">
                <div class="results-header">
                    <h3>your personalized why system</h3>
                    <p>your custom motivation framework, backed by goal achievement research</p>
                </div>
                
                <div class="download-options">
                    <div class="download-card" onclick="generatePDF()">
                        <div class="download-icon">
                            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                <path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/>
                                <polyline points="14,2 14,8 20,8"/>
                                <line x1="16" y1="13" x2="8" y2="13"/>
                                <line x1="16" y1="17" x2="8" y2="17"/>
                                <polyline points="10,9 9,9 8,9"/>
                            </svg>
                        </div>
                        <div class="download-title">structured reflection system</div>
                        <div class="download-desc">21-day guided journey with your personalized why analysis and daily prompts</div>
                        
                        <div class="feature-list">
                            <div class="feature-item">
                                <div class="feature-check">✓</div>
                                <span>personalized goal breakdown</span>
                            </div>
                            <div class="feature-item">
                                <div class="feature-check">✓</div>
                                <span>weekly progress tracking</span>
                            </div>
                            <div class="feature-item">
                                <div class="feature-check">✓</div>
                                <span>motivation maintenance system</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="download-card" onclick="generateGoogleSheet()">
                        <div class="download-icon">
                            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                <path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2-2V8z"/>
                                <polyline points="14,2 14,8 20,8"/>
                                <path d="M8 13h8"/>
                                <path d="M8 17h8"/>
                                <path d="M8 9h2"/>
                            </svg>
                        </div>
                        <div class="download-title">digital tracking system</div>
                        <div class="download-desc">interactive spreadsheet for ongoing reflection and progress optimization</div>
                        
                        <div class="feature-list">
                            <div class="feature-item">
                                <div class="feature-check">✓</div>
                                <span>progress analytics dashboard</span>
                            </div>
                            <div class="feature-item">
                                <div class="feature-check">✓</div>
                                <span>habit tracking integration</span>
                            </div>
                            <div class="feature-item">
                                <div class="feature-check">✓</div>
                                <span>accountability partner tools</span>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="summary-box" id="summaryBox">
                    <!-- Summary will be generated here -->
                </div>
                
                <div>
                    <h4 style="font-family: 'Cormorant Garamond', serif; font-size: 1.4rem; margin-bottom: 1rem; text-align: center;">sample reflection prompts (<span id="promptCount">21</span> total in your system):</h4>
                    <div id="samplePrompts">
                        <!-- Sample prompts will be generated here -->
                    </div>
                    
                    <button class="expand-btn" onclick="togglePromptView('preview')">
                        view all prompts
                    </button>
                    
                    <div class="prompt-list" id="previewPromptList">
                        <!-- All prompts will be generated here -->
                    </div>
                </div>
                
                <button class="restart-btn" onclick="startOver()">start new analysis</button>
            </div>
        </div>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
    <script>
        let conversationState = {
            stage: 0,
            responses: [],
            goal: '',
            surfaceWhy: '',
            deeperWhy: ''
        };

        const conversationFlow = [
            {
                stage: 'goal',
                followUp: "'{response}' — that's a meaningful pursuit. research shows that goals connected to deeper values have dramatically higher success rates.<br><br><strong>now let's dig into the why: what's driving this goal for you right now?</strong> what will achieving this give you or change about your life?"
            },
            {
                stage: 'surface_why',
                followUp: "i hear you saying '{response}' — that's solid motivation. but neuroscience research reveals there's usually a deeper layer that's even more powerful.<br><br><strong>let's go one level deeper: when you think about {goal} and {surface_why}, what feeling or identity shift are you really seeking?</strong> what would this prove about who you are or who you're becoming?"
            },
            {
                stage: 'deeper_why',
                complete: "powerful. from '{goal}' to discovering that your core driver is '{response}' — this is exactly the kind of self-awareness that separates people who achieve lasting change from those who don't.<br><br>research shows that people who understand their deeper motivations are 10x more likely to achieve their goals. let me create your personalized reflection system to build on this insight."
            }
        ];

        function sendMessage() {
            const input = document.getElementById('userInput');
            const message = input.value.trim();
            
            if (!message) return;

            addMessage(message, 'user');
            
            // Store response based on current stage
            const currentFlow = conversationFlow[conversationState.stage];
            if (currentFlow) {
                switch(currentFlow.stage) {
                    case 'goal':
                        conversationState.goal = message;
                        break;
                    case 'surface_why':
                        conversationState.surfaceWhy = message;
                        break;
                    case 'deeper_why':
                        conversationState.deeperWhy = message;
                        break;
                }
            }
            
            conversationState.responses.push(message);
            input.value = '';
            input.style.height = 'auto';
            
            showTyping();
            
            setTimeout(() => {
                hideTyping();
                processResponse(message);
            }, 2000);
        }

        function addMessage(text, sender) {
            const container = document.getElementById('chatContainer');
            const messageDiv = document.createElement('div');
            messageDiv.className = `message ${sender}-message`;
            messageDiv.innerHTML = text;
            container.appendChild(messageDiv);
            container.scrollTop = container.scrollHeight;
        }

        function showTyping() {
            document.getElementById('typingIndicator').style.display = 'block';
        }

        function hideTyping() {
            document.getElementById('typingIndicator').style.display = 'none';
        }

        function updateProgress() {
            const progress = ((conversationState.stage + 1) / conversationFlow.length) * 100;
            document.getElementById('progressFill').style.width = progress + '%';
            
            // Update step dots
            for (let i = 0; i <= conversationState.stage; i++) {
                const dot = document.getElementById(`dot${i}`);
                if (dot) {
                    dot.classList.add('completed');
                    dot.classList.remove('active');
                }
            }
            
            const nextDot = document.getElementById(`dot${conversationState.stage + 1}`);
            if (nextDot) {
                nextDot.classList.add('active');
            }
        }

        function processResponse(response) {
            updateProgress();
            
            if (conversationState.stage < conversationFlow.length) {
                const currentFlow = conversationFlow[conversationState.stage];
                
                if (currentFlow.complete) {
                    // Final stage - show completion message
                    const message = currentFlow.complete
                        .replace('{goal}', conversationState.goal)
                        .replace('{response}', response);
                    addMessage(message, 'bot');
                    
                    setTimeout(() => {
                        generateResults();
                    }, 2000);
                } else {
                    // Continue conversation
                    const message = currentFlow.followUp
                        .replace('{response}', response)
                        .replace('{goal}', conversationState.goal)
                        .replace('{surface_why}', conversationState.surfaceWhy);
                    addMessage(message, 'bot');
                }
                
                conversationState.stage++;
            }
        }

        function generateResults() {
            createSummary();
            createSamplePrompts();
            createFullPromptList();
            document.getElementById('resultsSection').style.display = 'block';
            document.getElementById('resultsSection').scrollIntoView({ behavior: 'smooth' });
        }

        function createSummary() {
            const summary = document.getElementById('summaryBox');
            summary.innerHTML = `
                <h4 class="summary-title">your why method analysis</h4>
                <div class="summary-item">
                    <span class="summary-label">goal:</span> ${conversationState.goal}
                </div>
                <div class="summary-item">
                    <span class="summary-label">surface why:</span> ${conversationState.surfaceWhy}
                </div>
                <div class="summary-item">
                    <span class="summary-label">deeper why:</span> ${conversationState.deeperWhy}
                </div>
            `;
        }

        function createSamplePrompts() {
            const prompts = generateJournalPrompts();
            const sampleContainer = document.getElementById('samplePrompts');
            
            sampleContainer.innerHTML = prompts.slice(0, 3).map((prompt, i) => `
                <div class="prompt-item">
                    <div class="prompt-day">day ${i + 1}</div>
                    <div>${prompt}</div>
                </div>
            `).join('');

            document.getElementById('promptCount').textContent = prompts.length;
        }

        function createFullPromptList() {
            const prompts = generateJournalPrompts();
            const promptList = document.getElementById('previewPromptList');
            
            promptList.innerHTML = prompts.map((prompt, i) => `
                <div class="prompt-item">
                    <div class="prompt-day">day ${i + 1}</div>
                    <div>${prompt}</div>
                </div>
            `).join('');
        }

        function generateJournalPrompts() {
            const { goal, surfaceWhy, deeperWhy } = conversationState
