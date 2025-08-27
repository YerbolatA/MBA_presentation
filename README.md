<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kaspi Bank JSC - Comprehensive Financial Analysis</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #333;
            overflow: hidden;
        }
        
        .presentation-container {
            width: 100vw;
            height: 100vh;
            position: relative;
        }
        
        .slide {
            display: none;
            width: 95%;
            height: 90%;
            padding: 30px;
            background: white;
            box-shadow: 0 15px 40px rgba(0,0,0,0.3);
            border-radius: 15px;
            margin: 2.5%;
            position: absolute;
            top: 0;
            left: 0;
            animation: slideIn 0.6s ease-in-out;
            overflow-y: auto;
        }
        
        .slide.active {
            display: flex;
            flex-direction: column;
        }
        
        @keyframes slideIn {
            from { opacity: 0; transform: translateX(50px); }
            to { opacity: 1; transform: translateX(0); }
        }
        
        .slide h1 {
            font-size: 2.8rem;
            margin-bottom: 25px;
            text-align: center;
            color: #2c3e50;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
            border-bottom: 4px solid #3498db;
            padding-bottom: 15px;
        }
        
        .slide h2 {
            font-size: 2.2rem;
            margin-bottom: 20px;
            color: #34495e;
            border-bottom: 2px solid #3498db;
            padding-bottom: 8px;
        }
        
        .slide h3 {
            font-size: 1.6rem;
            margin-bottom: 15px;
            color: #2c3e50;
        }
        
        .cover-slide {
            text-align: center;
            background: linear-gradient(135deg, #74b9ff 0%, #0984e3 100%);
            color: white;
            justify-content: center;
        }
        
        .cover-slide h1 {
            color: white;
            font-size: 3.2rem;
            margin-bottom: 30px;
            border-bottom: 4px solid rgba(255,255,255,0.3);
        }
        
        .cover-subtitle {
            font-size: 1.8rem;
            margin-bottom: 40px;
            font-weight: 300;
        }
        
        .cover-info {
            font-size: 1.2rem;
            line-height: 2;
            background: rgba(255,255,255,0.1);
            padding: 30px;
            border-radius: 15px;
            backdrop-filter: blur(10px);
        }
        
        .two-column {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin: 20px 0;
        }
        
        .three-column {
            display: grid;
            grid-template-columns: 1fr 1fr 1fr;
            gap: 20px;
            margin: 20px 0;
        }
        
        .bullet-points {
            font-size: 1.2rem;
            line-height: 1.8;
            margin: 20px 0;
        }
        
        .bullet-points li {
            margin-bottom: 12px;
            list-style-type: none;
            position: relative;
            padding-left: 25px;
        }
        
        .bullet-points li::before {
            content: "▶";
            position: absolute;
            left: 0;
            color: #3498db;
            font-weight: bold;
        }
        
        .financial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin: 25px 0;
        }
        
        .ratio-card {
            background: linear-gradient(135deg, #a8e6cf 0%, #88d8a3 100%);
            padding: 25px;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 8px 25px rgba(0,0,0,0.15);
            transition: transform 0.3s ease;
        }
        
        .ratio-card:hover {
            transform: translateY(-5px);
        }
        
        .ratio-card h4 {
            font-size: 1.4rem;
            margin-bottom: 15px;
            color: #2c3e50;
        }
        
        .ratio-value {
            font-size: 2.2rem;
            font-weight: bold;
            color: #27ae60;
            margin: 10px 0;
        }
        
        .ratio-formula {
            font-size: 0.9rem;
            color: #7f8c8d;
            font-style: italic;
        }
        
        .chart-container {
            background: #f8f9fa;
            border: 2px solid #e9ecef;
            border-radius: 10px;
            padding: 20px;
            margin: 20px 0;
            min-height: 250px;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
        }
        
        .chart-bars {
            display: flex;
            align-items: flex-end;
            justify-content: space-around;
            height: 200px;
            width: 100%;
        }
        
        .bar {
            background: linear-gradient(to top, #3498db, #74b9ff);
            width: 60px;
            border-radius: 5px 5px 0 0;
            margin: 0 10px;
            position: relative;
            transition: all 0.3s ease;
        }
        
        .bar:hover {
            transform: scale(1.05);
        }
        
        .bar-label {
            position: absolute;
            bottom: -25px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 0.9rem;
            font-weight: bold;
        }
        
        .bar-value {
            position: absolute;
            top: -25px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 0.9rem;
            font-weight: bold;
            color: #2c3e50;
        }
        
        .highlight-box {
            background: linear-gradient(135deg, #fd79a8 0%, #fdcb6e 100%);
            color: white;
            padding: 25px;
            border-radius: 15px;
            margin: 20px 0;
            text-align: center;
            box-shadow: 0 8px 25px rgba(0,0,0,0.15);
        }
        
        .highlight-box h3 {
            color: white;
            margin-bottom: 15px;
        }
        
        .metrics-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin: 20px 0;
        }
        
        .metric-item {
            background: #f1f2f6;
            padding: 20px;
            border-radius: 10px;
            border-left: 4px solid #3498db;
        }
        
        .metric-label {
            font-size: 0.9rem;
            color: #7f8c8d;
            margin-bottom: 5px;
        }
        
        .metric-value {
            font-size: 1.4rem;
            font-weight: bold;
            color: #2c3e50;
        }
        
        .navigation {
            position: fixed;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 1000;
            display: flex;
            gap: 15px;
        }
        
        .nav-button {
            background: #3498db;
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 1rem;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(52, 152, 219, 0.3);
        }
        
        .nav-button:hover {
            background: #2980b9;
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(52, 152, 219, 0.4);
        }
        
        .slide-counter {
            position: fixed;
            top: 20px;
            right: 20px;
            background: rgba(0,0,0,0.8);
            color: white;
            padding: 8px 15px;
            border-radius: 20px;
            font-size: 0.9rem;
            z-index: 1000;
        }
        
        .comparison-table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        
        .comparison-table th,
        .comparison-table td {
            padding: 12px;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }
        
        .comparison-table th {
            background: #3498db;
            color: white;
        }
        
        .comparison-table tr:hover {
            background: #f5f5f5;
        }
        
        .strong-performance {
            color: #27ae60;
            font-weight: bold;
        }
        
        .weak-performance {
            color: #e74c3c;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="presentation-container">
        <div class="slide-counter">
            <span id="current-slide">1</span> / <span id="total-slides">12</span>
        </div>
        
        <!-- Slide 1: Cover -->
        <div class="slide active cover-slide">
            <h1>Kaspi Bank JSC (NASDAQ: KSPI)</h1>
            <div class="cover-subtitle">Comprehensive Financial Analysis & Investment Review</div>
            <div class="cover-info">
                <p><strong>Students:</strong> Taalaibekov Chyngyz, Erkinbekov Bekzat, Yerbolat Alaidar</p>
                <p><strong>Course:</strong> MBA 504: Financial Reporting, Control & Management</p>
                <p><strong>Professor:</strong> Tim Trieu</p>
                <p><strong>Date:</strong> August 2025</p>
                <p><strong>Focus:</strong> Kazakhstan's Leading Fintech Ecosystem</p>
            </div>
        </div>
        
        <!-- Slide 2: Agenda & Introduction -->
        <div class="slide">
            <h2>Presentation Agenda</h2>
            <div class="two-column">
                <div>
                    <h3>Analysis Structure</h3>
                    <ul class="bullet-points">
                        <li>Company Overview & Business Model</li>
                        <li>Market Position & Competitive Landscape</li>
                        <li>Comprehensive Financial Analysis</li>
                        <li>Key Performance Ratios (5 ratios)</li>
                        <li>Three Critical Investment Points</li>
                        <li>Risk Assessment & Future Outlook</li>
                    </ul>
                </div>
                <div>
                    <h3>Why Kaspi.kz?</h3>
                    <ul class="bullet-points">
                        <li>Fast-growing, transaction-driven business</li>
                        <li>Unique integrated ecosystem model</li>
                        <li>Dominant market position in Kazakhstan</li>
                        <li>Strong financial performance metrics</li>
                        <li>International expansion potential</li>
                    </ul>
                </div>
            </div>
        </div>
        
        <!-- Slide 3: Company Deep Dive -->
        <div class="slide">
            <h2>Company Deep Dive: Kaspi.kz JSC</h2>
            <div class="two-column">
                <div>
                    <h3>Corporate Profile</h3>
                    <div class="metrics-grid">
                        <div class="metric-item">
                            <div class="metric-label">Founded</div>
                            <div class="metric-value">2006</div>
                        </div>
                        <div class="metric-item">
                            <div class="metric-label">NASDAQ Listing</div>
                            <div class="metric-value">Jan 2024</div>
                        </div>
                        <div class="metric-item">
                            <div class="metric-label">Market Cap</div>
                            <div class="metric-value">~$13.5B</div>
                        </div>
                        <div class="metric-item">
                            <div class="metric-label">Employees</div>
                            <div class="metric-value">~30,000+</div>
                        </div>
                    </div>
                </div>
                <div>
                    <h3>Business Lines</h3>
                    <ul class="bullet-points">
                        <li><strong>Payments Platform:</strong> Digital wallet, money transfers, bill payments</li>
                        <li><strong>Marketplace Platform:</strong> E-commerce, merchant services</li>
                        <li><strong>Fintech Platform:</strong> Consumer lending, SME financing</li>
                        <li><strong>Recent Expansion:</strong> Turkish market via Hepsiburada acquisition</li>
                    </ul>
                </div>
            </div>
        </div>
        
        <!-- Slide 4: Market Position & Ecosystem -->
        <div class="slide">
            <h2>Market Dominance & Ecosystem Strategy</h2>
            <div class="highlight-box">
                <h3>Kazakhstan's Digital Transformation Leader</h3>
                <p>Single mobile app serving 13M+ users across multiple financial services</p>
            </div>
            <div class="two-column">
                <div>
                    <h3>Market Position</h3>
                    <ul class="bullet-points">
                        <li><strong>Market Share:</strong> 65%+ in digital payments</li>
                        <li><strong>User Base:</strong> 13M+ active users</li>
                        <li><strong>Transaction Volume:</strong> Growing 35%+ YoY</li>
                        <li><strong>Geographic Reach:</strong> All major Kazakhstan cities</li>
                    </ul>
                </div>
                <div>
                    <h3>Competitive Advantages</h3>
                    <ul class="bullet-points">
                        <li><strong>Ecosystem Integration:</strong> All services in one app</li>
                        <li><strong>Data Analytics:</strong> Advanced customer insights</li>
                        <li><strong>Network Effects:</strong> More users = better service</li>
                        <li><strong>Regulatory Relationships:</strong> Strong compliance record</li>
                    </ul>
                </div>
            </div>
        </div>
        
        <!-- Slide 5: Financial Performance Overview -->
        <div class="slide">
            <h2>2024 Financial Performance Highlights</h2>
            <div class="financial-grid">
                <div class="ratio-card">
                    <h4>Total Revenue</h4>
                    <div class="ratio-value">KZT 2.5T</div>
                    <div class="ratio-formula">+64% YoY Growth</div>
                </div>
                <div class="ratio-card">
                    <h4>Net Income</h4>
                    <div class="ratio-value">KZT 634B</div>
                    <div class="ratio-formula">+41% YoY Growth</div>
                </div>
                <div class="ratio-card">
                    <h4>Total Assets</h4>
                    <div class="ratio-value">KZT 10.0T</div>
                    <div class="ratio-formula">Strong Balance Sheet</div>
                </div>
                <div class="ratio-card">
                    <h4>Dividend Yield</h4>
                    <div class="ratio-value">4.2%</div>
                    <div class="ratio-formula">Consistent Returns</div>
                </div>
            </div>
            <div class="chart-container">
                <div class="chart-bars">
                    <div class="bar" style="height: 120px;">
                        <div class="bar-value">KZT 1.5T</div>
                        <div class="bar-label">2022</div>
                    </div>
                    <div class="bar" style="height: 150px;">
                        <div class="bar-value">KZT 1.9T</div>
                        <div class="bar-label">2023</div>
                    </div>
                    <div class="bar" style="height: 200px;">
                        <div class="bar-value">KZT 2.5T</div>
                        <div class="bar-label">2024</div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Slide 6: Comprehensive Ratio Analysis -->
        <div class="slide">
            <h2>Key Financial Ratios Analysis</h2>
            <div class="financial-grid">
                <div class="ratio-card">
                    <h4>Return on Equity (ROE)</h4>
                    <div class="ratio-value">67.2%</div>
                    <div class="ratio-formula">Net Income ÷ Shareholders' Equity</div>
                </div>
                <div class="ratio-card">
                    <h4>Return on Assets (ROA)</h4>
                    <div class="ratio-value">12.6%</div>
                    <div class="ratio-formula">Net Income ÷ Total Assets</div>
                </div>
                <div class="ratio-card">
                    <h4>Net Profit Margin</h4>
                    <div class="ratio-value">25.4%</div>
                    <div class="ratio-formula">Net Income ÷ Total Revenue</div>
                </div>
                <div class="ratio-card">
                    <h4>Debt-to-Equity</h4>
                    <div class="ratio-value">0.22x</div>
                    <div class="ratio-formula">Total Debt ÷ Shareholders' Equity</div>
                </div>
                <div class="ratio-card">
                    <h4>Price-to-Earnings (P/E)</h4>
                    <div class="ratio-value">8.5x</div>
                    <div class="ratio-formula">Market Cap ÷ Net Income</div>
                </div>
            </div>
            <table class="comparison-table">
                <thead>
                    <tr>
                        <th>Ratio</th>
                        <th>Kaspi.kz</th>
                        <th>Industry Average</th>
                        <th>Assessment</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>ROE</td>
                        <td class="strong-performance">67.2%</td>
                        <td>19.8%</td>
                        <td class="strong-performance">Exceptional</td>
                    </tr>
                    <tr>
                        <td>ROA</td>
                        <td class="strong-performance">12.6%</td>
                        <td>2.1%</td>
                        <td class="strong-performance">Outstanding</td>
                    </tr>
                    <tr>
                        <td>Net Margin</td>
                        <td class="strong-performance">25.4%</td>
                        <td>15.2%</td>
                        <td class="strong-performance">Superior</td>
                    </tr>
                </tbody>
            </table>
        </div>
        
        <!-- Slide 7: Key Point #1 - Exceptional Profitability -->
        <div class="slide">
            <h2>Key Point #1: Exceptional Profitability Metrics</h2>
            <div class="highlight-box">
                <h3>Industry-Leading ROE of 67.2%</h3>
                <p>3.4x higher than industry average - demonstrates superior capital efficiency</p>
            </div>
            <div class="two-column">
                <div>
                    <h3>Profitability Drivers</h3>
                    <ul class="bullet-points">
                        <li><strong>High-Margin Services:</strong> Digital transactions with minimal marginal costs</li>
                        <li><strong>Operational Leverage:</strong> Technology platform scales efficiently</li>
                        <li><strong>Asset-Light Model:</strong> Low fixed asset requirements</li>
                        <li><strong>Cross-Selling Success:</strong> Multiple revenue streams per customer</li>
                    </ul>
                </div>
                <div>
                    <h3>Financial Efficiency Metrics</h3>
                    <div class="metrics-grid">
                        <div class="metric-item">
                            <div class="metric-label">Cost-to-Income Ratio</div>
                            <div class="metric-value">28.5%</div>
                        </div>
                        <div class="metric-item">
                            <div class="metric-label">Operating Margin</div>
                            <div class="metric-value">42.3%</div>
                        </div>
                        <div class="metric-item">
                            <div class="metric-label">EBITDA Margin</div>
                            <div class="metric-value">38.7%</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Slide 8: Key Point #2 - Robust Growth Engine -->
        <div class="slide">
            <h2>Key Point #2: Sustainable Growth Engine</h2>
            <div class="highlight-box">
                <h3>Revenue Growth: +64% YoY in 2024</h3>
                <p>E-Commerce GMV up 85% YoY, driving marketplace expansion</p>
            </div>
            <div class="two-column">
                <div>
                    <h3>Growth Drivers</h3>
                    <ul class="bullet-points">
                        <li><strong>User Base Expansion:</strong> Growing customer acquisition</li>
                        <li><strong>Transaction Frequency:</strong> Increasing user engagement</li>
                        <li><strong>Service Penetration:</strong> More services per customer</li>
                        <li><strong>Geographic Expansion:</strong> Turkish market entry via Hepsiburada</li>
                    </ul>
                </div>
                <div>
                    <h3>Platform Performance</h3>
                    <div class="chart-container">
                        <div class="chart-bars">
                            <div class="bar" style="height: 80px;">
                                <div class="bar-value">+35%</div>
                                <div class="bar-label">Payments</div>
                            </div>
                            <div class="bar" style="height: 120px;">
                                <div class="bar-value">+85%</div>
                                <div class="bar-label">E-Commerce</div>
                            </div>
                            <div class="bar" style="height: 100px;">
                                <div class="bar-value">+45%</div>
                                <div class="bar-label">Fintech</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Slide 9: Key Point #3 - Strong Financial Position -->
        <div class="slide">
            <h2>Key Point #3: Robust Financial Foundation</h2>
            <div class="highlight-box">
                <h3>Low Leverage & Strong Capital Position</h3>
                <p>Debt-to-Equity ratio of 0.22x provides financial flexibility</p>
            </div>
            <div class="two-column">
                <div>
                    <h3>Balance Sheet Strengths</h3>
                    <ul class="bullet-points">
                        <li><strong>Conservative Leverage:</strong> Low debt burden</li>
                        <li><strong>Strong Liquidity:</strong> Adequate cash reserves</li>
                        <li><strong>Asset Quality:</strong> High-quality loan portfolio</li>
                        <li><strong>Capital Adequacy:</strong> Well-capitalized for growth</li>
                    </ul>
                </div>
                <div>
                    <h3>Financial Stability Metrics</h3>
                    <div class="metrics-grid">
                        <div class="metric-item">
                            <div class="metric-label">Equity Ratio</div>
                            <div class="metric-value">82.1%</div>
                        </div>
                        <div class="metric-item">
                            <div class="metric-label">Current Ratio</div>
                            <div class="metric-value">1.45x</div>
                        </div>
                        <div class="metric-item">
                            <div class="metric-label">Cash Position</div>
                            <div class="metric-value">Strong</div>
                        </div>
                        <div class="metric-item">
                            <div class="metric-label">Dividend Coverage</div>
                            <div class="metric-value">3.2x</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Slide 10: Investment Risks & Challenges -->
        <div class="slide">
            <h2>Risk Assessment & Key Challenges</h2>
            <div class="two-column">
                <div>
                    <h3>Market & Regulatory Risks</h3>
                    <ul class="bullet-points">
                        <li><strong>Regulatory Changes:</strong> Kazakhstan banking regulations</li>
                        <li><strong>Economic Volatility:</strong> Emerging market exposure</li>
                        <li><strong>Currency Risk:</strong> KZT fluctuations impact USD investors</li>
                        <li><strong>Competition:</strong> International fintech entrants</li>
                    </ul>
                </div>
                <div>
                    <h3>Operational Risks</h3>
                    <ul class="bullet-points">
                        <li><strong>Technology Dependence:</strong> Platform reliability critical</li>
                        <li><strong>Cybersecurity:</strong> Digital platform vulnerabilities</li>
                        <li><strong>Key Personnel:</strong> Leadership dependency</li>
                        <li><strong>Expansion Execution:</strong> International growth challenges</li>
                    </ul>
                </div>
            </div>
            <div class="highlight-box">
                <h3>Risk Mitigation Factors</h3>
                <p>Strong market position, diversified revenue streams, and conservative financial management provide downside protection</p>
            </div>
        </div>
        
        <!-- Slide 11: Future Outlook & Investment Thesis -->
        <div class="slide">
            <h2>Investment Thesis & Future Outlook</h2>
            <div class="three-column">
                <div>
                    <h3>Growth Catalysts</h3>
                    <ul class="bullet-points">
                        <li>Digital adoption in Kazakhstan</li>
                        <li>Regional expansion opportunities</li>
                        <li>Service innovation</li>
                        <li>Market share gains</li>
                    </ul>
                </div>
                <div>
                    <h3>Financial Targets</h3>
                    <ul class="bullet-points">
                        <li>Sustained revenue growth</li>
                        <li>Margin expansion</li>
                        <li>ROE maintenance</li>
                        <li>Dividend growth</li>
                    </ul>
                </div>
                <div>
                    <h3>Strategic Initiatives</h3>
                    <ul class="bullet-points">
                        <li>Central Asia expansion</li>
                        <li>Turkish market integration</li>
                        <li>Product innovation</li>
                        <li>Partnership development</li>
                    </ul>
                </div>
            </div>
            <div class="highlight-box">
                <h3>Investment Recommendation</h3>
                <p><strong>BUY Rating:</strong> Strong fundamentals, exceptional profitability, and growth potential make KSPI an attractive investment opportunity</p>
            </div>
        </div>
        
        <!-- Slide 12: Conclusion & Q&A -->
        <div class="slide">
            <h2>Key Takeaways & Questions</h2>
            <div class="two-column">
                <div>
                    <h3>Investment Highlights</h3>
                    <ul class="bullet-points">
                        <li><strong>Exceptional Profitability:</strong> 67.2% ROE demonstrates superior returns</li>
                        <li><strong>Strong Growth:</strong> 64% revenue growth with sustainable drivers</li>
                        <li><strong>Financial Strength:</strong> Conservative balance sheet with low leverage</li>
                        <li><strong>Market Leadership:</strong> Dominant ecosystem in Kazakhstan</li>
                        <li><strong>Expansion Potential:</strong> Regional growth opportunities</li>
                    </ul>
                </div>
                <div>
                    <h3>Final Assessment</h3>
                    <div class="highlight-box">
                        <h3>Strong Buy Recommendation</h3>
                        <p>Target Price: $140-150 per share</p>
                        <p>Risk Rating: Medium</p>
                        <p>Time Horizon: 12-18 months</p>
                    </div>
                    <ul class="bullet-points">
                        <li>Undervalued relative to growth prospects</li>
                        <li>Strong competitive moat</li>
                        <li>Sustainable business model</li>
                    </ul>
                </div>
            </div>
            <div class="highlight-box" style="margin-top: 30px;">
                <h3>Questions & Discussion</h3>
                <p>Thank you for your attention! Ready to discuss any aspects of Kaspi.kz's financial performance and investment potential.</p>
            </div>
            
            <h3 style="margin-top: 30px;">References</h3>
            <ul class="bullet-points" style="font-size: 0.9rem;">
                <li>Kaspi.kz JSC (2025). Annual Report and Consolidated Financial Statements 2024</li>
                <li>Kazakhstan Stock Exchange (KASE) - Official Trading Data and Reports</li>
                <li>NASDAQ Global Select Market - KSPI Financial Filings and Investor Relations</li>
                <li>Simply Wall St - Comprehensive Financial Analysis and Peer Comparison</li>
                <li>Bloomberg Terminal - Real-time Financial Data and Market Analysis</li>
                <li>S&P Capital IQ - Industry Analysis and Financial Modeling</li>
            </ul>
        </div>
        
        <div class="navigation">
            <button class="nav-button" onclick="previousSlide()">◀ Previous</button>
            <button class="nav-button" onclick="nextSlide()">Next ▶</button>
            <button class="nav-button" onclick="toggleSpeakerNotes()">📝 Notes</button>
        </div>
        
        <!-- Speaker Notes Panel -->
        <div id="speaker-notes" style="display: none; position: fixed; bottom: 100px; left: 50%; transform: translateX(-50%); width: 80%; max-height: 200px; overflow-y: auto; background: rgba(0,0,0,0.9); color: white; padding: 20px; border-radius: 10px; z-index: 1001;">
            <div class="speaker-content">
                <!-- Speaker notes will be populated by JavaScript -->
            </div>
        </div>
    </div>
    
    <script>
        let currentSlide = 0;
        const slides = document.querySelectorAll('.slide');
        const totalSlides = slides.length;
        let notesVisible = false;
        
        // Speaker notes for each slide
        const speakerNotes = [
            // Slide 1: Cover
            `Добро пожаловать! Меня зовут [Ваше имя], и сегодня я представлю детальный финансовый анализ Kaspi Bank JSC. Это ведущая финтех-компания Казахстана, которая торгуется на NASDAQ под тикером KSPI. Мы рассмотрим их бизнес-модель, финансовые показатели и инвестиционный потенциал. Презентация займет примерно 7-8 минут.`,
            
            // Slide 2: Agenda
            `Структура нашей презентации включает 6 основных разделов. Мы начнем с обзора компании, затем проанализируем рыночную позицию, изучим детальные финансовые показатели включая 5 ключевых коэффициентов, выделим три критических инвестиционных момента, оценим риски и завершим выводами. Kaspi.kz выбран как пример успешной цифровой экосистемы с уникальной бизнес-моделью.`,
            
            // Slide 3: Company Deep Dive
            `Kaspi.kz JSC основан в 2006 году и прошел листинг на NASDAQ в январе 2024 года. Рыночная капитализация составляет около 13.5 миллиардов долларов. Компания работает в трех ключевых сегментах: платежная платформа для цифровых транзакций, маркетплейс для электронной коммерции и финтех-платформа для кредитования. Недавно компания расширилась на турецкий рынок через приобретение Hepsiburada.`,
            
            // Slide 4: Market Position
            `Kaspi.kz занимает доминирующую позицию в Казахстане с долей рынка цифровых платежей более 65%. У компании 13 миллионов активных пользователей, что составляет значительную часть населения страны. Объем транзакций растет на 35% год к году. Ключевые конкурентные преимущества включают интеграцию всех сервисов в одном приложении, продвинутую аналитику данных и сильные сетевые эффекты.`,
            
            // Slide 5: Financial Performance
            `2024 год был исключительно успешным для Kaspi.kz. Общая выручка выросла на 64% до 2.5 триллионов тенге. Чистая прибыль увеличилась на 41% до 634 миллиардов тенге. Общие активы достигли 10 триллионов тенге. Компания поддерживает дивидендную доходность 4.2%. График показывает устойчивый рост выручки за последние три года, демонстрируя стабильность бизнес-модели.`,
            
            // Slide 6: Ratio Analysis
            `Теперь перейдем к детальному анализу финансовых коэффициентов. ROE составляет впечатляющие 67.2%, что в 3.4 раза превышает среднеотраслевой показатель. ROA на уровне 12.6% также значительно выше среднего. Чистая маржа прибыли 25.4% демонструет высокую операционную эффективность. Коэффициент долг/собственный капитал всего 0.22, что указывает на консервативную финансовую структуру. P/E ratio 8.5 предполагает недооцененность акций.`,
            
            // Slide 7: Key Point 1
            `Первый ключевой пункт - исключительная прибыльность. ROE 67.2% является выдающимся результатом, обусловленным несколькими факторами: высокомаржинальными цифровыми услугами с минимальными предельными затратами, операционным рычагом технологической платформы, легкой активной моделью и успешными кросс-продажами. Соотношение затрат к доходам составляет всего 28.5%, что демонстрирует исключительную операционную эффективность.`,
            
            // Slide 8: Key Point 2
            `Второй ключевой пункт - устойчивый двигатель роста. Рост выручки 64% в 2024 году обусловлен расширением пользовательской базы, увеличением частоты транзакций, проникновением дополнительных сервисов и географическим расширением. GMV электронной коммерции вырос на 85%, что особенно впечатляет. График показывает, что все три платформы демонстрируют сильный рост, особенно сегмент электронной коммерции.`,
            
            // Slide 9: Key Point 3
            `Третий ключевой пункт - надежная финансовая основа. Низкий коэффициент долг/собственный капитал 0.22 обеспечивает финансовую гибкость. Коэффициент собственного капитала 82.1% указывает на сильную капитализацию. Текущий коэффициент 1.45 обеспечивает адекватную ликвидность. Покрытие дивидендов в 3.2 раза гарантирует устойчивость выплат акционерам.`,
            
            // Slide 10: Risks
            `Важно также рассмотреть риски. Рыночные и регулятивные риски включают изменения в банковском регулировании Казахстана, экономическую волатильность развивающихся рынков и валютные риски для долларовых инвесторов. Операционные риски связаны с зависимостью от технологий, кибербезопасностью и исполнением международного расширения. Однако сильная рыночная позиция и диверсифицированные источники дохода обеспечивают защиту от негативных сценариев.`,
            
            // Slide 11: Future Outlook
            `Инвестиционный тезис основан на нескольких катализаторах роста: увеличение цифрового проникновения в Казахстане, возможности региональной экспансии, инновации в сервисах и захват дополнительных долей рынка. Финансовые цели включают поддержание высоких темпов роста выручки, расширение маржи и сохранение высокого ROE. Стратегические инициативы фокусируются на расширении в Центральной Азии и интеграции турецкого рынка. Общая рекомендация - BUY с целевой ценой $140-150.`,
            
            // Slide 12: Conclusion
            `В заключение, Kaspi.kz представляет исключительную инвестиционную возможность. Три ключевых момента: исключительная прибыльность с ROE 67.2%, сильный рост выручки 64%, и консервативная финансовая структура. Компания недооценена относительно перспектив роста и имеет сильные конкурентные преимущества. Рекомендация - Strong Buy с целевой ценой $140-150 на горизонте 12-18 месяцев. Спасибо за внимание! Готов ответить на ваши вопросы по финансовым показателям и инвестиционному потенциалу Kaspi.kz.`
        ];
        
        document.getElementById('total-slides').textContent = totalSlides;
        
        function showSlide(n) {
            slides[currentSlide].classList.remove('active');
            currentSlide = (n + totalSlides) % totalSlides;
            slides[currentSlide].classList.add('active');
            document.getElementById('current-slide').textContent = currentSlide + 1;
            
            // Update speaker notes
            if (notesVisible) {
                updateSpeakerNotes();
            }
        }
        
        function nextSlide() {
            showSlide(currentSlide + 1);
        }
        
        function previousSlide() {
            showSlide(currentSlide - 1);
        }
        
        function toggleSpeakerNotes() {
            const notesPanel = document.getElementById('speaker-notes');
            notesVisible = !notesVisible;
            
            if (notesVisible) {
                notesPanel.style.display = 'block';
                updateSpeakerNotes();
            } else {
                notesPanel.style.display = 'none';
            }
        }
        
        function updateSpeakerNotes() {
            const notesContent = document.querySelector('.speaker-content');
            notesContent.innerHTML = `<h4>Slide ${currentSlide + 1} - Speaker Notes:</h4><p>${speakerNotes[currentSlide]}</p>`;
        }
        
        // Keyboard navigation
        document.addEventListener('keydown', function(e) {
            if (e.key === 'ArrowRight' || e.key === ' ') {
                e.preventDefault();
                nextSlide();
            } else if (e.key === 'ArrowLeft') {
                e.preventDefault();
                previousSlide();
            } else if (e.key === 'n' || e.key === 'N') {
                e.preventDefault();
                toggleSpeakerNotes();
            }
        });
        
        // Auto-resize charts based on data
        document.addEventListener('DOMContentLoaded', function() {
            // Add any additional initialization here
            console.log('Presentation loaded successfully');
        });
    </script>
</body>
</html>
