<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Sumit Agnihotri - Data Scientist Portfolio</title>
    <!-- Google Fonts for better typography -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&family=Fira+Code:wght@400;500;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #0B1120 0%, #0F172A 100%);
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            color: #E2E8F0;
            line-height: 1.5;
            padding: 2rem 1rem;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
        }

        /* Glass morphism cards */
        .glass-card {
            background: rgba(15, 23, 42, 0.6);
            backdrop-filter: blur(12px);
            border-radius: 2rem;
            border: 1px solid rgba(56, 189, 248, 0.15);
            transition: all 0.3s ease;
        }

        .glass-card:hover {
            border-color: rgba(56, 189, 248, 0.4);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
        }

        /* Headers */
        h1, h2, h3 {
            font-weight: 700;
            background: linear-gradient(135deg, #38BDF8, #A855F7, #EC4899);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            letter-spacing: -0.02em;
        }

        h2 {
            font-size: 2rem;
            margin-bottom: 1.5rem;
            display: inline-block;
            border-bottom: 3px solid #38BDF8;
            padding-bottom: 0.5rem;
        }

        .section {
            margin-bottom: 4rem;
        }

        /* Badges and tech stack */
        .tech-badge {
            display: inline-flex;
            align-items: center;
            background: rgba(56, 189, 248, 0.1);
            padding: 0.5rem 1.2rem;
            border-radius: 100px;
            font-weight: 500;
            font-size: 0.9rem;
            backdrop-filter: blur(4px);
            border: 1px solid rgba(56, 189, 248, 0.2);
            transition: transform 0.2s, background 0.2s;
            margin: 0.3rem;
        }

        .tech-badge:hover {
            transform: translateY(-2px);
            background: rgba(56, 189, 248, 0.2);
            border-color: #38BDF8;
        }

        /* Project grid */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 1.8rem;
            margin-top: 2rem;
        }

        .project-card {
            background: rgba(15, 23, 42, 0.7);
            border-radius: 1.5rem;
            padding: 1.8rem;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            border: 1px solid rgba(56, 189, 248, 0.1);
            backdrop-filter: blur(8px);
        }

        .project-card:hover {
            transform: translateY(-8px);
            border-color: #EC4899;
            box-shadow: 0 20px 40px -12px rgba(236, 72, 153, 0.2);
        }

        .project-title {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 0.75rem;
            background: linear-gradient(135deg, #E2E8F0, #94A3B8);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
        }

        .project-desc {
            color: #94A3B8;
            margin-bottom: 1rem;
            line-height: 1.6;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin: 1rem 0;
        }

        .mini-badge {
            background: rgba(168, 85, 247, 0.2);
            padding: 0.25rem 0.75rem;
            border-radius: 100px;
            font-size: 0.75rem;
            font-weight: 500;
            color: #C084FC;
        }

        /* Stats layout */
        .stats-wrapper {
            display: flex;
            flex-wrap: wrap;
            gap: 1.5rem;
            justify-content: center;
            margin-bottom: 2rem;
        }

        .stats-card {
            flex: 1;
            min-width: 280px;
            background: rgba(15, 23, 42, 0.6);
            border-radius: 1.5rem;
            padding: 1.5rem;
            text-align: center;
            border: 1px solid rgba(56, 189, 248, 0.2);
        }

        /* Contribution calendar simulation (improved visual) */
        .calendar-container {
            background: rgba(15, 23, 42, 0.8);
            border-radius: 1.5rem;
            padding: 2rem;
            text-align: center;
        }

        .calendar-grid {
            display: grid;
            grid-template-columns: repeat(52, 1fr);
            gap: 3px;
            margin-top: 1rem;
        }

        .calendar-week {
            display: flex;
            gap: 3px;
            justify-content: center;
        }

        .contribution-day {
            aspect-ratio: 1;
            background: #1E293B;
            border-radius: 3px;
            transition: all 0.2s;
        }

        /* For demo - showing activity simulation visually */
        .contribution-level-0 { background: #1E293B; }
        .contribution-level-1 { background: #0EA5E9; }
        .contribution-level-2 { background: #3B82F6; }
        .contribution-level-3 { background: #8B5CF6; }
        .contribution-level-4 { background: #EC4899; }

        /* Code block styling */
        .code-block {
            background: #0F172A;
            border-radius: 1rem;
            padding: 1.5rem;
            font-family: 'Fira Code', monospace;
            font-size: 0.85rem;
            overflow-x: auto;
            border: 1px solid #334155;
            text-align: left;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .projects-grid {
                grid-template-columns: 1fr;
            }
            .stats-wrapper {
                flex-direction: column;
            }
            h2 {
                font-size: 1.75rem;
            }
        }

        /* Social links */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.2rem;
            flex-wrap: wrap;
        }
        .social-btn {
            background: linear-gradient(135deg, rgba(56, 189, 248, 0.1), rgba(236, 72, 153, 0.1));
            padding: 0.8rem 1.8rem;
            border-radius: 60px;
            text-decoration: none;
            color: white;
            font-weight: 600;
            transition: all 0.3s;
            backdrop-filter: blur(4px);
            border: 1px solid rgba(56, 189, 248, 0.3);
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
        }

        .social-btn:hover {
            transform: scale(1.05);
            background: linear-gradient(135deg, #38BDF8, #EC4899);
            border-color: transparent;
            box-shadow: 0 6px 20px rgba(56, 189, 248, 0.4);
        }

        .quote-text {
            font-size: 1.3rem;
            font-style: italic;
            background: linear-gradient(135deg, #CBD5E1, #94A3B8);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
        }

        footer {
            text-align: center;
            margin-top: 3rem;
            padding-top: 2rem;
            border-top: 1px solid rgba(56, 189, 248, 0.2);
        }

        .gradient-text {
            background: linear-gradient(135deg, #38BDF8, #EC4899);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
        }
        
        .wave-header {
            width: 100%;
            height: auto;
        }

        .typing-demo {
            font-size: 1.2rem;
            font-weight: 500;
            text-align: center;
        }
        
        .profile-badge {
            display: inline-block;
            margin: 0.5rem;
        }
        
        .btn-link {
            text-decoration: none;
        }
    </style>
</head>
<body>
<div class="container">

    <!-- Hero Wave + Header -->
    <div align="center">
        <img src="https://capsule-render.vercel.app/api?type=waving&height=270&color=0:0F172A,25:1E3A8A,50:2563EB,75:7C3AED,100:EC4899&text=SUMIT%20AGNIHOTRI&fontSize=55&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Aspiring%20Data%20Scientist%20•%20Machine%20Learning%20Enthusiast%20•%20AI%20Learner&descAlignY=58&descSize=18" style="max-width: 100%; height: auto;" alt="header"/>
        
        <br>
        <!-- Enhanced Typing SVG alternative (static but styled) -->
        <div class="typing-demo" style="margin: 20px 0;">
            <span class="gradient-text" style="font-size: 1.6rem; font-weight: 700;">✨ Transforming Data into Insights &nbsp;|&nbsp; 📊 Python & ML &nbsp;|&nbsp; 🤖 AI Explorer</span>
        </div>
        
        <div style="margin: 1rem 0;">
            <img src="https://komarev.com/ghpvc/?username=Sumit-Agnihotri&label=PROFILE+VIEWS&color=0ea5e9&style=for-the-badge" alt="views"/>
            <img src="https://img.shields.io/github/followers/Sumit-Agnihotri?style=for-the-badge&logo=github&color=7C3AED" alt="followers"/>
            <img src="https://img.shields.io/github/stars/Sumit-Agnihotri?style=for-the-badge&color=EC4899" alt="stars"/>
        </div>
    </div>

    <!-- About Me Section (improved layout) -->
    <div class="section">
        <h2>🌌 About Me</h2>
        <div style="display: flex; flex-wrap: wrap; gap: 2rem; align-items: flex-start; margin-top: 1.5rem;">
            <div style="flex: 1.2; min-width: 240px;">
                <div class="code-block" style="background: #0A0F1F;">
                    <pre style="color: #E2E8F0; margin: 0; font-size: 0.85rem;">
<span style="color:#38BDF8;">Name:</span> Sumit Agnihotri
<span style="color:#EC4899;">Role:</span> Aspiring Data Scientist

<span style="color:#A855F7;">Learning Journey:</span>
  ▸ Data Science
  ▸ Machine Learning
  ▸ Artificial Intelligence
  ▸ Data Visualization
  ▸ SQL & Analytics

<span style="color:#38BDF8;">Languages:</span> Python, PostgreSQL

<span style="color:#F97316;">Current Focus:</span>
  ✦ Building Real-World Projects
  ✦ Learning Deep Learning
  ✦ Exploring Generative AI
  ✦ Improving Analytical Skills

<span style="color:#EC4899;">Goal:</span> Become a Data Scientist & AI Engineer 🚀
                    </pre>
                </div>
            </div>
            <div style="flex: 0.8; text-align: center;">
                <img width="280" src="https://media.giphy.com/media/f3iwJFOVOwuy7K6FFw/giphy.gif" style="border-radius: 20px; border: 2px solid #38BDF8;" alt="coding"/>
            </div>
        </div>
    </div>

    <!-- Tech Stack -->
    <div class="section">
        <h2>⚡ Tech Stack</h2>
        <div align="center" style="background: rgba(15, 23, 42, 0.4); border-radius: 2rem; padding: 1.8rem; margin-top: 1rem;">
            <div style="margin-bottom: 2rem;">
                <h3 style="font-size: 1.4rem;">💻 Programming Languages</h3>
                <div style="margin-top: 0.8rem;">
                    <span class="tech-badge">🐍 Python</span>
                    <span class="tech-badge">🐘 PostgreSQL</span>
                </div>
            </div>
            <div style="margin-bottom: 2rem;">
                <h3 style="font-size: 1.4rem;">📚 Data Science & ML</h3>
                <div>
                    <span class="tech-badge">NumPy</span> <span class="tech-badge">Pandas</span> <span class="tech-badge">Scikit-learn</span>
                    <span class="tech-badge">Matplotlib</span> <span class="tech-badge">Seaborn</span> <span class="tech-badge">Plotly</span>
                    <span class="tech-badge">OpenCV</span> <span class="tech-badge">TensorFlow</span> <span class="tech-badge">PyTorch</span>
                </div>
            </div>
            <div style="margin-bottom: 2rem;">
                <h3 style="font-size: 1.4rem;">📊 Visualization & BI</h3>
                <div>
                    <span class="tech-badge">Power BI</span> <span class="tech-badge">Google Sheets</span>
                    <span class="tech-badge">Jupyter</span> <span class="tech-badge">MS Excel</span>
                </div>
            </div>
            <div>
                <h3 style="font-size: 1.4rem;">🛠️ Tools & Platforms</h3>
                <div>
                    <span class="tech-badge">Git</span> <span class="tech-badge">GitHub</span>
                    <span class="tech-badge">VS Code</span> <span class="tech-badge">Linux</span>
                </div>
            </div>
        </div>
    </div>

    <!-- Featured Projects - Improved Design, ready for links -->
    <div class="section">
        <h2>🚀 Featured Projects</h2>
        <div class="projects-grid">
            <!-- Project 1 -->
            <div class="project-card">
                <div class="project-title">📊 Customer Churn Analysis</div>
                <div class="project-desc">Built an end-to-end ML pipeline to predict customer churn with 92% accuracy. Performed EDA and feature engineering.</div>
                <div class="project-tech">
                    <span class="mini-badge">Python</span>
                    <span class="mini-badge">Pandas</span>
                    <span class="mini-badge">Scikit-learn</span>
                </div>
                <a href="#" style="text-decoration: none;"><span class="tech-badge" style="background:#2563EB;">🔗 View Project →</span></a>
            </div>
            <!-- Project 2 -->
            <div class="project-card">
                <div class="project-title">🤖 NLP Sentiment Analyzer</div>
                <div class="project-desc">Analyzed movie reviews using NLTK & Transformers. Achieved 88% F1-score with deployment using Streamlit.</div>
                <div class="project-tech">
                    <span class="mini-badge">Transformers</span>
                    <span class="mini-badge">TensorFlow</span>
                    <span class="mini-badge">Streamlit</span>
                </div>
                <a href="#" style="text-decoration: none;"><span class="tech-badge" style="background:#7C3AED;">🔗 View Project →</span></a>
            </div>
            <!-- Project 3 -->
            <div class="project-card">
                <div class="project-title">📈 Sales Forecasting Dashboard</div>
                <div class="project-desc">Time-series forecasting using ARIMA & Prophet. Interactive Power BI dashboard for business insights.</div>
                <div class="project-tech">
                    <span class="mini-badge">Power BI</span>
                    <span class="mini-badge">Prophet</span>
                    <span class="mini-badge">SQL</span>
                </div>
                <a href="#" style="text-decoration: none;"><span class="tech-badge" style="background:#EC4899;">🔗 View Project →</span></a>
            </div>
            <!-- Project 4 -->
            <div class="project-card">
                <div class="project-title">🧠 Image Classification CNN</div>
                <div class="project-desc">Deep learning model to classify CIFAR-10 with 85% test accuracy using PyTorch and data augmentation.</div>
                <div class="project-tech">
                    <span class="mini-badge">PyTorch</span>
                    <span class="mini-badge">OpenCV</span>
                    <span class="mini-badge">Matplotlib</span>
                </div>
                <a href="#" style="text-decoration: none;"><span class="tech-badge" style="background:#0EA5E9;">🔗 View Project →</span></a>
            </div>
            <!-- Project 5 -->
            <div class="project-card">
                <div class="project-title">📉 COVID-19 Data Analysis</div>
                <div class="project-desc">Exploratory data analysis and real-time dashboard using Plotly Dash. Data sourced from WHO APIs.</div>
                <div class="project-tech">
                    <span class="mini-badge">Plotly</span>
                    <span class="mini-badge">Dash</span>
                    <span class="mini-badge">Pandas</span>
                </div>
                <a href="#" style="text-decoration: none;"><span class="tech-badge" style="background:#22C55E;">🔗 View Project →</span></a>
            </div>
            <!-- Project 6 -->
            <div class="project-card">
                <div class="project-title">🚀 Movie Recommender System</div>
                <div class="project-desc">Content-based filtering using cosine similarity, built with Flask and deployed on HuggingFace Spaces.</div>
                <div class="project-tech">
                    <span class="mini-badge">Scikit-learn</span>
                    <span class="mini-badge">Flask</span>
                    <span class="mini-badge">NLP</span>
                </div>
                <a href="#" style="text-decoration: none;"><span class="tech-badge" style="background:#F97316;">🔗 View Project →</span></a>
            </div>
        </div>
        <p align="center" style="margin-top: 1rem; color: #94A3B8;">✨ <i>Project links will be added soon — stay tuned!</i></p>
    </div>

    <!-- GitHub Analytics (Improved) -->
    <div class="section">
        <h2>📊 GitHub Analytics</h2>
        <div class="stats-wrapper">
            <div class="stats-card">
                <img src="https://github-readme-stats.vercel.app/api?username=Sumit-Agnihotri&show_icons=true&theme=tokyonight&hide_border=true&title_color=38BDF8&icon_color=EC4899&text_color=E2E8F0&bg_color=0D111A" width="100%" alt="GitHub Stats"/>
            </div>
            <div class="stats-card">
                <img src="https://github-readme-streak-stats.herokuapp.com/?user=Sumit-Agnihotri&theme=tokyonight&hide_border=true&ring=EC4899&fire=F97316&currStreakLabel=38BDF8&background=0D111A" width="100%" alt="Streak"/>
            </div>
        </div>
        <div align="center" style="margin-top: 1rem;">
            <img width="45%" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Sumit-Agnihotri&layout=compact&theme=tokyonight&hide_border=true&title_color=38BDF8&text_color=E2E8F0&bg_color=0D111A" alt="Top Languages"/>
        </div>
    </div>

    <!-- Contribution Calendar (improved representation) -->
    <div class="section">
        <h2>🟩 Contribution Calendar</h2>
        <div class="calendar-container">
            <div style="font-size: 0.85rem; margin-bottom: 1rem;">🔥 Simulated activity grid (2024-2025)</div>
            <div class="calendar-grid" id="contribGrid">
                <!-- JS generated grid for better visual: 52 weeks x 7 days = 364 days approximate, simplified -->
            </div>
            <div style="display: flex; justify-content: center; gap: 8px; margin-top: 16px;">
                <span style="background:#1E293B; width:14px;height:14px;display:inline-block;border-radius:2px;"></span> Less
                <span style="background:#0EA5E9; width:14px;height:14px;display:inline-block;border-radius:2px;"></span>
                <span style="background:#3B82F6; width:14px;height:14px;display:inline-block;border-radius:2px;"></span>
                <span style="background:#8B5CF6; width:14px;height:14px;display:inline-block;border-radius:2px;"></span>
                <span style="background:#EC4899; width:14px;height:14px;display:inline-block;border-radius:2px;"></span> More
            </div>
        </div>
    </div>

    <!-- Activity Graph -->
    <div class="section">
        <h2>📈 Activity Graph</h2>
        <div align="center">
            <img width="100%" src="https://github-readme-activity-graph.vercel.app/graph?username=Sumit-Agnihotri&bg_color=0F172A&color=38BDF8&line=EC4899&point=F97316&area=true&hide_border=true" alt="activity graph"/>
        </div>
    </div>

    <!-- GitHub Achievements -->
    <div class="section">
        <h2>🏆 GitHub Achievements</h2>
        <div align="center">
            <img src="https://github-profile-trophy.vercel.app/?username=Sumit-Agnihotri&theme=algolia&no-frame=true&column=7&margin-w=10&margin-h=10" width="100%" alt="trophies"/>
        </div>
    </div>

    <!-- Learning Focus Section (interactive style) -->
    <div class="section">
        <h2>📚 Current Learning Focus</h2>
        <div class="code-block" style="background:#0A0F1F;">
            <pre style="margin:0; color:#E2E8F0;">
<span style="color:#38BDF8;">class</span> <span style="color:#EC4899;">SumitAgnihotri</span>:
    
    <span style="color:#A855F7;">def</span> <span style="color:#F97316;">__init__</span>(self):
        self.learning = [
            <span style="color:#10B981;">"Python"</span>, <span style="color:#10B981;">"PostgreSQL"</span>, <span style="color:#10B981;">"Machine Learning"</span>,
            <span style="color:#10B981;">"Deep Learning"</span>, <span style="color:#10B981;">"Generative AI"</span>, <span style="color:#10B981;">"Data Visualization"</span>
        ]
    
    <span style="color:#A855F7;">def</span> <span style="color:#F97316;">goal</span>(self):
        <span style="color:#A855F7;">return</span> <span style="color:#10B981;">"Become a Data Scientist & AI Engineer 🚀"</span>

<span style="color:#FCD34D;">profile</span> = <span style="color:#EC4899;">SumitAgnihotri</span>()
<span style="color:#FCD34D;">print</span>(profile.goal())
            </pre>
        </div>
    </div>

    <!-- Connect with Me -->
    <div class="section">
        <h2>🌐 Connect With Me</h2>
        <div class="social-links">
            <a href="mailto:sagnihotri9710@gmail.com" class="social-btn">📧 Gmail</a>
            <a href="https://www.linkedin.com/in/sumit-agnihotri/" class="social-btn">🔗 LinkedIn</a>
            <a href="https://github.com/Sumit-Agnihotri" class="social-btn">🐙 GitHub</a>
        </div>
    </div>

    <!-- Quote -->
    <div class="section" align="center">
        <div class="glass-card" style="padding: 2rem; margin-top: 1rem;">
            <div class="quote-text">✨ “Without data, you're just another person with an opinion.”</div>
            <div style="margin-top: 0.5rem; color: #94A3B8;">— W. Edwards Deming</div>
        </div>
    </div>

    <footer>
        <img src="https://capsule-render.vercel.app/api?type=waving&height=120&color=0:0F172A,25:1E3A8A,50:2563EB,75:7C3AED,100:EC4899&section=footer" style="width:100%" alt="footer"/>
        <div style="margin-top: 1.8rem;">
            <h3 class="gradient-text">⭐ Thank You for Visiting ⭐</h3>
            <p style="margin-top: 0.5rem; font-weight: 500;">Learn • Build • Analyze • Grow 🚀</p>
        </div>
    </footer>
</div>

<script>
    // Generate a nice contribution grid simulation (visual improvement)
    function generateContributionGrid() {
        const gridContainer = document.getElementById('contribGrid');
        if (!gridContainer) return;
        gridContainer.innerHTML = '';
        const weeks = 52;
        const maxHeight = 7; // 7 days a week
        
        for (let w = 0; w < weeks; w++) {
            const weekDiv = document.createElement('div');
            weekDiv.style.display = 'flex';
            weekDiv.style.gap = '3px';
            weekDiv.style.marginBottom = '3px';
            for (let d = 0; d < 7; d++) {
                const day = document.createElement('div');
                day.style.aspectRatio = '1';
                day.style.width = '100%';
                day.style.maxWidth = '12px';
                day.style.borderRadius = '3px';
                // random but deterministic simulated activity based on week index
                let level = 0;
                if (w > 8 && w < 20) level = Math.floor(Math.random() * 3) + 1;
                else if (w > 25 && w < 40) level = Math.floor(Math.random() * 4) + 1;
                else if (w > 42) level = Math.floor(Math.random() * 5);
                else level = Math.floor(Math.random() * 3);
                
                if (level === 0) day.classList.add('contribution-level-0');
                else if (level === 1) day.classList.add('contribution-level-1');
                else if (level === 2) day.classList.add('contribution-level-2');
                else if (level === 3) day.classList.add('contribution-level-3');
                else day.classList.add('contribution-level-4');
                
                day.style.backgroundColor = getComputedStyle(day).backgroundColor;
                weekDiv.appendChild(day);
            }
            gridContainer.appendChild(weekDiv);
        }
    }
    generateContributionGrid();
</script>
</body>
</html>
