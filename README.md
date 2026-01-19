# AI Usage Statistics Dashboard - Europe

Interactive dashboard visualizing Claude AI adoption across European countries based on Anthropic's Economic Index dataset.

## 🎯 Overview

This project provides an interactive visualization of AI usage statistics across Europe, featuring:
- **Interactive SVG Map** - Click on countries to view detailed statistics
- **Usage Rankings** - Sortable country grid showing conversation volumes
- **Category Breakdown** - Professional occupation categories using AI
- **Task Analysis** - Top AI-assisted tasks by country
- **Collaboration Metrics** - Augmentation vs Automation split

## 🚀 Live Demo

**Production:** [View Live Dashboard](https://thinkingahead.com/data-statistics)

## 📊 Data Source

Dataset from **Anthropic Economic Index** (Jan 15, 2026)
- Source: HuggingFace - Anthropic Economic Index
- 20 European countries included
- Detailed breakdowns available for: UK, Germany, France

## 🛠️ Tech Stack

- **HTML5** - Semantic structure
- **CSS3** - Custom styling with responsive design
- **JavaScript (Vanilla)** - No frameworks, pure JS
- **Chart.js** - Data visualization library
- **SVG** - Interactive country map

## 📁 Project Structure

```
ai-usage-stats-europe/
│
├── index.html           # Main application file (standalone)
├── README.md           # Project documentation
├── LICENSE             # MIT License
└── .gitignore          # Git ignore rules
```

## 🎨 Design System

### Color Palette
- **Primary (Metrics):** `#c15f3c` - Coral red
- **Success (Green):** `#bee5d8` - Turquoise
- **Info (Blue):** `#b8c5ff` - Periwinkle
- **Dark (CTA):** `#242322` - Near black
- **Background:** `#fafaf8` - Off-white

### Typography
- **Font Family:** Inter, -apple-system, BlinkMacSystemFont, sans-serif
- **Headings:** 700 weight
- **Body:** 400 weight

## 🚀 Quick Start

### Option 1: Direct Deployment
1. Download `index.html`
2. Upload to your hosting provider
3. Done! No build process required

### Option 2: Local Development
```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/ai-usage-stats-europe.git

# Navigate to directory
cd ai-usage-stats-europe

# Serve locally (Python 3)
python -m http.server 8000

# Or with Node.js
npx serve .

# Open browser
open http://localhost:8000
```

## 📦 Deployment

### GitHub Pages
1. Push to GitHub
2. Go to Settings → Pages
3. Select branch: `main`, folder: `/ (root)`
4. Access via: `https://USERNAME.github.io/REPO_NAME`

### Umso CMS (Current Production)
1. Open Umso editor
2. Add "Custom Code" block
3. Paste `index.html` content
4. Embed via iframe or direct integration

### Other Platforms
Works with any static hosting:
- Netlify (drag & drop)
- Vercel (zero config)
- AWS S3 + CloudFront
- Firebase Hosting

## 🔧 Configuration

### Updating Data
Data is embedded in the HTML file (lines ~183-370). To update:

```javascript
const allData = {
    "last_updated": "Jan 15, 2026",  // Update date
    "countries": {
        "GBR": {
            "name": "United Kingdom",
            "usage_count": 30700,        // Update count
            "soc_categories": [...],     // Update categories
            "top_tasks": [...],          // Update tasks
            "collaboration": [...]       // Update metrics
        },
        // Add more countries...
    }
};
```

### Customizing Colors
Update CSS variables (lines ~9-120):
```css
.country-usage { color: #c15f3c !important; }  /* Metrics color */
.stat-value { color: #c15f3c !important; }     /* Stats color */
/* Charts use: #b8c5ff (blue) and #bee5d8 (green) */
```

## 🎯 Features

### Interactive Map
- Hover tooltips with country names and usage
- Click to view detailed statistics
- Color intensity based on usage volume
- Responsive SVG implementation

### Country Details
- Total conversation volume
- European ranking
- SOC category breakdown (bar charts)
- Top 5 AI-assisted tasks
- Augmentation vs Automation split (doughnut chart)

### Responsive Design
- Mobile-first approach
- Flexible grid layouts
- Touch-friendly interactions
- Optimized for iframe embedding

## 🔒 Data Privacy

- No external API calls (data embedded)
- No user tracking or analytics
- No cookies or local storage
- GDPR compliant
- Client-side only processing

## 📈 Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

## 🐛 Known Issues & Limitations

1. **Detailed Data** - Only UK, Germany, France have full breakdowns
2. **Static Data** - Manually updated, not real-time
3. **Map Simplification** - Countries represented as rectangles for reliability

## 🤝 Contributing

Contributions welcome! To contribute:

1. Fork the repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open Pull Request

## 📝 Changelog

### v1.0.0 (Jan 19, 2026)
- ✅ Initial production release
- ✅ Interactive SVG map
- ✅ Country detail views
- ✅ Chart.js visualizations
- ✅ Embedded data structure
- ✅ Fixed back button functionality
- ✅ Removed CTA section

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Florian Negre**
- Website: [thinkingahead.com](https://thinkingahead.com)
- LinkedIn: [Florian Negre](https://linkedin.com/in/florian-negre)
- Project: Thinking Ahead Business Intelligence Suite

## 🙏 Acknowledgments

- **Anthropic** - Economic Index dataset
- **Chart.js** - Visualization library
- **HuggingFace** - Dataset hosting

## 📧 Support

For issues or questions:
- Open an issue on GitHub
- Contact via [thinkingahead.com](https://thinkingahead.com)

---

**Note:** This is part of the "Thinking Ahead" business intelligence suite, providing data-driven insights for B2B SaaS and FinTech companies.
