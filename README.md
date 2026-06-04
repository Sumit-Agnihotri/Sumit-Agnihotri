<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Sumit Agnihotri · Data Scientist Portfolio</title>
    <!-- Google Fonts + Smooth Base -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: radial-gradient(circle at 10% 20%, #0B0F1C, #030617);
            font-family: 'Inter', system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            color: #EFF3F8;
            line-height: 1.5;
            padding: 0;
            overflow-x: hidden;
        }

        .main-container {
            max-width: 1280px;
            margin: 0 auto;
            padding: 2rem 1.5rem 4rem;
        }

        /* premium glassmorphic elements */
        .glass-card {
            background: rgba(15, 25, 45, 0.55);
            backdrop-filter: blur(14px);
            border-radius: 2rem;
            border: 1px solid rgba(56, 189, 248, 0.2);
            transition: all 0.25s ease;
        }

        .glass-card:hover {
            border-color: rgba(236, 72, 153, 0.5);
            box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.5);
        }

        /* Gradient texts */
        .gradient-primary {
            background: linear-gradient(130deg, #38BDF8 0%, #A855F7 55%, #EC4899 100%);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            font-weight: 800;
        }

        .gradient-gold {
            background: linear-gradient(135deg, #FDE047, #F97316);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
        }

        h2 {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            border-bottom: 3px solid #38BDF8;
            padding-bottom: 0.4rem;
        }

        .section {
            margin-bottom: 4rem;
        }

        /* tech badges */
        .tech-pill {
            display: inline-flex;
            align-items: center;
            background: rgba(56, 189, 248, 0.1);
            backdrop-filter: blur(4px);
            padding: 0.45rem 1.2rem;
            border-radius: 100px;
            font-weight: 500;
            font-size: 0.85rem;
            letter-spacing: -0.2px;
            border: 1px solid rgba(56, 189, 248, 0.25);
            transition: 0.2s;
            margin: 0.25rem;
        }

        .tech-pill:hover {
            background: rgba(168, 85, 247, 0.2);
            transform: translateY(-2px);
            border-color: #EC4899;
        }

        /* project grid */
        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 1.8rem;
            margin-top: 2rem;
        }

        .project-tile {
            background: rgba(10, 18, 30, 0.7);
            border-radius: 1.5rem;
            padding: 1.6rem;
            backdrop-filter: blur(8px);
            border: 1px solid rgba(59, 130, 246, 0.2);
            transition: all 0.3s cubic-bezier(0.2, 0.9, 0.4, 1.1);
        }

        .project-tile:hover {
            transform: translateY(-8px);
            border-color: #EC4899;
            box-shadow: 0 20px 30px -15px rgba(236, 72, 153, 0.2);
            background: rgba(15, 25, 45, 0.85);
        }

        .project-title {
            font-size: 1.45rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            background: linear-gradient(135deg, #E0F2FE, #C084FC);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
        }

        .project-desc {
            color: #B9C7D9;
            font-size: 0.9rem;
            margin: 0.75rem 0;
            line-height: 1.5;
        }

        .mini-tech {
            display: inline-block;
            background: rgba(236, 72, 153, 0.15);
            border-radius: 20px;
            padding: 0.2rem 0.7rem;
            font-size: 0.7rem;
            font-weight: 500;
            color: #F9A8D4;
            margin-right: 0.5rem;
            margin-bottom: 0.5rem;
        }

        .project-btn {
            display: inline-block;
            margin-top: 1rem;
            background: linear-gradient(95deg, #1E3A8A, #4C1D95);
            padding: 0.5rem 1.2rem;
            border-radius: 40px;
            font-weight: 600;
            font-size: 0.8rem;
            color: white;
            text-decoration: none;
            transition: 0.2s;
            border: 1px solid rgba(56, 189, 248, 0.5);
        }

        .project-btn:hover {
            background: linear-gradient(95deg, #2563EB, #7C3AED);
            transform: scale(1.02);
            box-shadow: 0 4px 12px rgba(0,0,0,0.3);
        }

        /* stats row */
        .stats-row {
            display: flex;
            flex-wrap: wrap;
            gap: 1.8rem;
            justify-content: center;
            margin: 2rem 0;
        }

        .stat-box {
            flex: 1;
            min-width: 250px;
            background: rgba(0, 0, 0, 0.35);
            backdrop-filter: blur(8px);
            border-radius: 1.5rem;
            padding: 1.2rem;
            text-align: center;
            border: 1px solid #2D3A5E;
        }

        /* contribution simulated */
        .contrib-preview {
            background: #0A0F1C;
            border-radius: 1.5rem;
            padding: 1.5rem;
            text-align: center;
        }

        .mini-cal {
            display: grid;
            grid-template-columns: repeat(52, 1fr);
            gap: 3px;
            margin-top: 1rem;
        }

        .day-cell {
            aspect-ratio: 1 / 1;
            background-color: #1A2538;
            border-radius: 3px;
            transition: 0.1s;
        }

        .level-1 { background-color: #0EA5E9; }
        .level-2 { background-color: #3B82F6; }
        .level-3 { background-color: #8B5CF6; }
        .level-4 { background-color: #EC4899; }

        /* socials */
        .social-links {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 1.2rem;
        }

        .social-btn {
            background: rgba(56, 189, 248, 0.1);
            padding: 0.75rem 2rem;
            border-radius: 60px;
            text-decoration: none;
            font-weight: 600;
            color: white;
            border: 1px solid rgba(56, 189, 248, 0.4);
            transition: 0.2s;
            backdrop-filter: blur(8px);
        }

        .social-btn:hover {
            background: linear-gradient(120deg, #2563EB, #C026D3);
            border-color: transparent;
            transform: translateY(-3px);
        }

        .code-snip {
            background: #050C1A;
            border-radius: 1.2rem;
            padding: 1.2rem;
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.8rem;
            border-left: 4px solid #EC4899;
            overflow-x: auto;
        }

        footer {
            text-align: center;
            margin-top: 3rem;
            padding-top: 2rem;
            border-top: 1px solid #1E2A44;
        }

        @media (max-width: 720px) {
            .main-container {
                padding: 1rem;
            }
            h2 {
                font-size: 1.6rem;
            }
            .project-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
<div class="main-container">

    <!-- ========= HERO with wave effect ========= -->
    <div align="center" style="margin-bottom: 1rem;">
        <img src="https://capsule-render.vercel.app/api?type=waving&height=260&color=0:0F172A,25:1E3A8A,50:2563EB,75:7C3AED,100:EC4899&text=SUMIT%20AGNIHOTRI&fontSize=52&fontColor=ffffff&animation=fadeIn&fontAlignY=40&desc=Aspiring%20Data%20Scientist%20•%20Machine%20Learning%20Enthusiast%20•%20AI%20Learner&descAlignY=62&descSize=17" style="max-width: 100%; width: 100%;" alt="wave banner">
        <div style="margin: 20px 0 10px;">
            <div style="font-weight: 700; font-size: 1.7rem; background: linear-gradient(135deg,#38BDF8,#F472B6); background-clip:text; -webkit-background-clip:text; color:transparent;">
                ✦ Transforming Data into Actionable Intelligence ✦
            </div>
            <div style="margin-top: 12px;">
                <img src="https://komarev.com/ghpvc/?username=Sumit-Agnihotri&label=✨+PROFILE+VIEWS&color=0ea5e9&style=for-the-badge" alt="views" style="margin:0 5px;">
                <img src="https://img.shields.io/github/followers/Sumit-Agnihotri?style=for-the-badge&logo=github&color=7C3AED" alt="followers" style="margin:0 5px;">
                <img src="https://img.shields.io/github/stars/Sumit-Agnihotri?style=for-the-badge&color=EC4899" alt="stars" style="margin:0 5px;">
            </div>
        </div>
    </div>

    <!-- ========= ABOUT ME SECTION (refined) ========= -->
    <div class="section">
        <h2>🌌 About Me</h2>
        <div style="display: flex; flex-wrap: wrap; gap: 2rem; align-items: stretch;">
            <div style="flex: 1.2; background: rgba(0,0,0,0.25); border-radius: 1.5rem; padding: 1.5rem;">
                <div class="code-snip" style="background:#0A0F1F;">
                    <pre style="color:#CBD5E1; margin:0; font-family: monospace;">
<span style="color:#38BDF8;">┌──</span> <span style="color:#F97316;">Identity</span>
│ Name        : Sumit Agnihotri
│ Role        : Aspiring Data Scientist
│ 
├── <span style="color:#38BDF8;">Learning Path</span>
│ • Data Science & Machine Learning
│ • Artificial Intelligence
│ • Data Visualization & Analytics
│ • SQL (PostgreSQL)
│
├── <span style="color:#EC4899;">Core Stack</span>
│ • Python (pandas, numpy, scikit-learn)
│ • PostgreSQL
│ • Power BI / Tableau
│
├── <span style="color:#A855F7;">Current Focus</span>
│ → Deep Learning (PyTorch/TensorFlow)
│ → Generative AI & LLMs
│ → End-to-end ML projects
│
└── <span style="color:#FDE047;">Mission</span>   : Become a Data Scientist & AI Engineer 🚀
                    </pre>
                </div>
            </div>
            <div style="flex: 0.8; text-align: center; display: flex; align-items: center; justify-content: center;">
                <img src="https://media.giphy.com/media/L8K62iTDkzGX6/giphy.gif?cid=790b7611mz89s3j7u790jshph2h1x2erwnurcf4dp7gg95jr&ep=v1_gifs_search&rid=giphy.gif&ct=g" width="260" style="border-radius: 28px; border: 2px solid #38BDF8; box-shadow: 0 15px 30px -10px black;" alt="data gif">
            </div>
        </div>
    </div>

    <!-- ========= TECH STACK (improved badges) ========= -->
    <div class="section">
        <h2>⚡ Tech Stack & Tools</h2>
        <div class="glass-card" style="padding: 1.8rem; margin-top: 0.5rem;">
            <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 1rem;">
                <div style="min-width: 200px;"><strong class="gradient-primary">🐍 Languages</strong><br><span class="tech-pill">Python</span> <span class="tech-pill">SQL (PostgreSQL)</span></div>
                <div style="min-width: 240px;"><strong class="gradient-primary">📊 Data Science</strong><br><span class="tech-pill">NumPy</span> <span class="tech-pill">Pandas</span> <span class="tech-pill">Scikit-learn</span> <span class="tech-pill">Matplotlib</span> <span class="tech-pill">Seaborn</span> <span class="tech-pill">Plotly</span></div>
                <div style="min-width: 200px;"><strong class="gradient-primary">🧠 ML/DL</strong><br><span class="tech-pill">TensorFlow</span> <span class="tech-pill">PyTorch</span> <span class="tech-pill">OpenCV</span></div>
                <div style="min-width: 180px;"><strong class="gradient-primary">📉 BI & Viz</strong><br><span class="tech-pill">Power BI</span> <span class="tech-pill">Excel</span> <span class="tech-pill">Jupyter</span></div>
                <div><strong class="gradient-primary">🛠️ DevOps/Tools</strong><br><span class="tech-pill">Git/GitHub</span> <span class="tech-pill">VS Code</span> <span class="tech-pill">Linux</span></div>
            </div>
        </div>
    </div>

    <!-- ========= FEATURED PROJECTS (placeholders ready for links) ========= -->
    <div class="section">
        <h2>🚀 Featured Projects</h2>
        <div class="project-grid">
            <div class="project-tile"><div class="project-title">📊 Customer Churn Predictor</div><div class="project-desc">End-to-end classification model (Random Forest/XGBoost) with 91% recall. Feature engineering + SHAP explainability.</div><div><span class="mini-tech">Python</span><span class="mini-tech">Pandas</span><span class="mini-tech">Scikit-learn</span></div><a href="#" class="project-btn">🔍 Preview →</a></div>
            <div class="project-tile"><div class="project-title">🤖 NLP Sentiment Analysis</div><div class="project-desc">Fine-tuned BERT for movie reviews; deployed with FastAPI + Streamlit dashboard.</div><div><span class="mini-tech">Transformers</span><span class="mini-tech">PyTorch</span><span class="mini-tech">Streamlit</span></div><a href="#" class="project-btn">🔍 Preview →</a></div>
            <div class="project-tile"><div class="project-title">📈 Sales Forecasting Dashboard</div><div class="project-desc">Time series (Prophet/ARIMA) + interactive PowerBI dashboard; SQL data pipeline.</div><div><span class="mini-tech">Prophet</span><span class="mini-tech">PowerBI</span><span class="mini-tech">PostgreSQL</span></div><a href="#" class="project-btn">🔍 Preview →</a></div>
            <div class="project-tile"><div class="project-title">🧠 Brain Tumor Segmentation</div><div class="project-desc">CNN + U-Net architecture (TensorFlow) for MRI segmentation; 87% dice score.</div><div><span class="mini-tech">TensorFlow</span><span class="mini-tech">OpenCV</span><span class="mini-tech">Keras</span></div><a href="#" class="project-btn">🔍 Preview →</a></div>
            <div class="project-tile"><div class="project-title">📉 COVID-19 Exploratory Analysis</div><div class="project-desc">Global dataset analysis using Plotly and pandas; animated choropleth maps.</div><div><span class="mini-tech">Plotly</span><span class="mini-tech">Pandas</span><span class="mini-tech">Jupyter</span></div><a href="#" class="project-btn">🔍 Preview →</a></div>
            <div class="project-tile"><div class="project-title">🎬 Movie Recommender System</div><div class="project-desc">Content-based & collaborative filtering with cosine similarity; Flask deployment.</div><div><span class="mini-tech">Scikit-learn</span><span class="mini-tech">Flask</span><span class="mini-tech">NLP</span></div><a href="#" class="project-btn">🔍 Preview →</a></div>
        </div>
        <p align="center" style="margin-top: 1rem; opacity: 0.7; font-size: 0.9rem;">⭐ <em>Project links coming soon — live demos & repos in progress</em> ⭐</p>
    </div>

    <!-- ========= GITHUB ANALYTICS (dynamic images) ========= -->
    <div class="section">
        <h2>📊 GitHub Analytics</h2>
        <div class="stats-row">
            <div class="stat-box">
                <img src="https://github-readme-stats.vercel.app/api?username=Sumit-Agnihotri&show_icons=true&theme=tokyonight&hide_border=true&title_color=38BDF8&icon_color=EC4899&text_color=E2E8F0&bg_color=0D111A" width="100%" alt="stats">
            </div>
            <div class="stat-box">
                <img src="https://github-readme-streak-stats.herokuapp.com/?user=Sumit-Agnihotri&theme=tokyonight&hide_border=true&ring=EC4899&fire=F97316&currStreakLabel=38BDF8&background=0D111A" width="100%" alt="streak">
            </div>
        </div>
        <div align="center" style="margin-top: 1rem;">
            <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Sumit-Agnihotri&layout=compact&theme=tokyonight&hide_border=true&title_color=38BDF8&text_color=E2E8F0&bg_color=0D111A" width="45%" alt="top langs">
        </div>
    </div>

    <!-- ========= CONTRIBUTION CALENDAR (interactive visual simulation) ========= -->
    <div class="section">
        <h2>🟩 Contribution Calendar</h2>
        <div class="contrib-preview glass-card">
            <div style="font-weight: 500; margin-bottom: 1rem;">🌟 2025 activity heatmap (simulated)</div>
            <div id="heatmapGrid" style="display: flex; flex-wrap: wrap; justify-content: center;"></div>
            <div style="display: flex; justify-content: center; gap: 1rem; margin-top: 1.5rem;">
                <span style="display:inline-flex;align-items:center;gap:4px"><span style="width:12px;height:12px;background:#1A2538;border-radius:2px"></span> Low</span>
                <span style="display:inline-flex;align-items:center;gap:4px"><span style="width:12px;height:12px;background:#0EA5E9;border-radius:2px"></span> </span>
                <span style="display:inline-flex;align-items:center;gap:4px"><span style="width:12px;height:12px;background:#3B82F6;border-radius:2px"></span> </span>
                <span style="display:inline-flex;align-items:center;gap:4px"><span style="width:12px;height:12px;background:#8B5CF6;border-radius:2px"></span> </span>
                <span style="display:inline-flex;align-items:center;gap:4px"><span style="width:12px;height:12px;background:#EC4899;border-radius:2px"></span> High</span>
            </div>
        </div>
    </div>

    <!-- ========= ACTIVITY GRAPH (GitHub like) ========= -->
    <div class="section">
        <h2>📈 Activity Graph</h2>
        <div align="center">
            <img src="https://github-readme-activity-graph.vercel.app/graph?username=Sumit-Agnihotri&bg_color=0F172A&color=38BDF8&line=EC4899&point=F97316&area=true&hide_border=true&area_color=EC489920" width="100%" alt="contribution graph">
        </div>
    </div>

    <!-- ========= ACHIEVEMENTS TROPHY ========= -->
    <div class="section">
        <h2>🏆 GitHub Achievements</h2>
        <div align="center">
            <img src="https://github-profile-trophy.vercel.app/?username=Sumit-Agnihotri&theme=algolia&no-frame=true&column=7&margin-w=8" width="100%" alt="trophies">
        </div>
    </div>

    <!-- ========= LEARNING FOCUS (python code block) ========= -->
    <div class="section">
        <h2>📚 Current Learning Focus</h2>
        <div class="code-snip" style="background:#0A0F1F;">
            <pre style="color:#CBD5E6; font-family: monospace;">
<span style="color:#7C3AED;">class</span> <span style="color:#38BDF8;">SumitAgnihotri</span>:
    
    <span style="color:#F97316;">def __init__</span>(self):
        self.learning = [
            "Advanced Machine Learning",
            "Deep Learning (CNNs, RNNs)",
            "Generative AI & LLMs",
            "MLOps basics (Docker, FastAPI)",
            "Big Data (Spark fundamentals)"
        ]
    
    <span style="color:#EC4899;">@property</span>
    <span style="color:#F97316;">def daily_motto</span>(self):
        return "Build -> Analyze -> Iterate -> Impact 🚀"

<span style="color:#10B981;">me = SumitAgnihotri()</span>
<span style="color:#FDE047;">print(me.daily_motto)</span>
            </pre>
        </div>
    </div>

    <!-- ========= CONNECT & QUOTE ========= -->
    <div class="section">
        <h2>🌐 Connect With Me</h2>
        <div class="social-links">
            <a href="mailto:sagnihotri9710@gmail.com" class="social-btn">📧 Gmail</a>
            <a href="https://www.linkedin.com/in/sumit-agnihotri/" class="social-btn" target="_blank">🔗 LinkedIn</a>
            <a href="https://github.com/Sumit-Agnihotri" class="social-btn" target="_blank">🐙 GitHub</a>
        </div>
    </div>

    <div align="center" style="margin: 3rem 0 1rem;">
        <div class="glass-card" style="padding: 1.5rem; max-width: 700px; margin: 0 auto;">
            <p style="font-size: 1.2rem; font-style: italic;">✨ “Without data, you're just another person with an opinion.”</p>
            <p style="margin-top: 0.3rem; font-weight: 300;">— W. Edwards Deming</p>
        </div>
    </div>

    <footer>
        <img src="https://capsule-render.vercel.app/api?type=waving&height=130&color=0:0F172A,25:1E3A8A,50:2563EB,75:7C3AED,100:EC4899&section=footer" style="width:100%; margin-bottom: 1rem;" alt="footer wave">
        <div class="gradient-primary" style="font-weight: 800; font-size: 1.4rem;">⭐ Thank You for Visiting ⭐</div>
        <div style="margin-top: 0.5rem;">Learn • Build • Analyze • Grow 🚀</div>
        <div style="margin-top: 1rem; font-size: 0.75rem; opacity: 0.6;">Sumit Agnihotri – Data Science & AI Enthusiast</div>
    </footer>
</div>

<script>
    // dynamic contribution grid simulator (visual fix)
    function generateContributionMap() {
        const container = document.getElementById("heatmapGrid");
        if (!container) return;
        container.innerHTML = "";
        // create a 52x7 matrix style ( weeks x days )
        const weeks = 48;
        const days = 7;
        const gridWrapper = document.createElement("div");
        gridWrapper.style.display = "grid";
        gridWrapper.style.gridTemplateColumns = `repeat(${weeks}, 1fr)`;
        gridWrapper.style.gap = "3px";
        gridWrapper.style.width = "100%";
        
        for (let w = 0; w < weeks; w++) {
            const colDiv = document.createElement("div");
            colDiv.style.display = "flex";
            colDiv.style.flexDirection = "column";
            colDiv.style.gap = "3px";
            for (let d = 0; d < days; d++) {
                const cell = document.createElement("div");
                cell.style.aspectRatio = "1/1";
                cell.style.backgroundColor = "#1A2538";
                cell.style.borderRadius = "3px";
                // pseudo random but consistent based on week + day
                let val = (w * 7 + d) % 13;
                if (w > 5 && w < 20) val = (val + d) % 9;
                if (w > 25 && w < 38) val = (val + 7) % 12;
                let level = 0;
                if (val > 9) level = 4;
                else if (val > 6) level = 3;
                else if (val > 3) level = 2;
                else if (val > 1) level = 1;
                if (level === 1) cell.classList.add("level-1");
                else if (level === 2) cell.classList.add("level-2");
                else if (level === 3) cell.classList.add("level-3");
                else if (level === 4) cell.classList.add("level-4");
                if (level > 0) {
                    cell.style.backgroundColor = getComputedStyle(cell).backgroundColor;
                }
                colDiv.appendChild(cell);
            }
            gridWrapper.appendChild(colDiv);
        }
        container.appendChild(gridWrapper);
    }
    generateContributionMap();
</script>
</body>
</html>
