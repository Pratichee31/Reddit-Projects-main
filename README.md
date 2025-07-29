# Reddit Intelligence Analysis Platform (RIAP)

A sophisticated AI-powered pipeline that automatically discovers, analyzes, and prioritizes high-value Reddit content for strategic business intelligence. Configurable for multiple domains through customizable AI analysis frameworks.

## 🎯 Project Overview

REIP transforms Reddit into actionable business intelligence by:
- **Discovering** relevant conversations across targeted subreddits
- **Scoring** opportunities using velocity-based algorithms
- **Analyzing** content with AI for strategic fit
- **Generating** professional reports with actionable insights

## 🏗️ Architecture

```
Reddit API → Data Collection → AI Analysis → Strategic Reports
     ↓              ↓              ↓              ↓
  Raw Posts    Scored Data    AI Insights    Word Docs
```

## 🚀 Key Features

### Intelligent Data Collection
- **Multi-keyword search** across targeted subreddits
- **Deduplication engine** prevents processing the same content twice
- **Opportunity scoring** using velocity-based algorithms (posts gaining traction fast)
- **Master data store** maintains historical context

### AI-Powered Domain Analysis
- **Configurable analysis frameworks** through system prompt customization
- **GPT-4 integration** with structured JSON schema enforcement
- **Domain-specific filtering** against customizable core principles
- **Batch processing** with rate limiting for cost efficiency
- **Strategic intelligence mapping** tailored to business objectives

### Professional Reporting
- **Automated Word document generation** with clickable Reddit links
- **Separate reports** for post vs. comment opportunities
- **Duplicate prevention** across report generations
- **Executive-ready formatting** with opportunity scores and context

## 📊 Opportunity Scoring Algorithm

Posts and comments are scored using a velocity-based formula that prioritizes:
- **Score velocity**: How fast content is gaining upvotes
- **Comment velocity**: Rate of new discussion
- **Engagement depth**: Reply chains and interaction quality
- **Temporal relevance**: Newer content gets higher priority

```python
# Post Opportunity Score
OS_post = (W1 * score * upvote_ratio / age_hours) + (W2 * num_comments / age_hours)

# Comment Reply Score  
OS_reply = OS_post + (W3 * comment_score + W4 * num_replies) * depth_factor
```

## 🛠️ Installation & Setup

### Prerequisites
```bash
pip install praw python-dotenv openai python-docx numpy
```

### Environment Variables
Create a `.env` file:
```env
REDDIT_CLIENT_ID=your_reddit_client_id
REDDIT_CLIENT_SECRET=your_reddit_client_secret  
REDDIT_USER_AGENT=your_app_name/1.0
OPENAI_API_KEY=your_openai_api_key
```

### Configuration
Edit `data/config.json` to customize:
- Target subreddits and keywords
- Scoring parameters
- Export settings
- API rate limits

## 🎮 Usage

### Interactive Pipeline
```bash
python Main_controller.py
```

**Menu Options:**
1. **Full Run** - Fetch new Reddit data and complete pipeline
2. **AI Analysis Only** - Process existing data with fresh AI insights  
3. **Report Generation** - Create Word docs from existing analysis
4. **Custom Start Point** - Resume from any step

### Manual Execution
```bash
python src/1_fetch_reddit_data.py      # Data collection
python src/2_prepare_ai_input.py       # Filter high-value content
python src/3_get_ai_analysis.py        # AI strategic analysis
python src/4_generate_reports.py       # Professional reports
```

## 📁 Project Structure

```
reddit-intelligence/
├── src/
│   ├── 1_fetch_reddit_data.py      # Reddit API scraping with scoring
│   ├── 2_prepare_ai_input.py       # Data preprocessing & filtering
│   ├── 3_get_ai_analysis.py        # OpenAI integration with schema
│   └── 4_generate_reports.py       # Word document generation
├── data/
│   ├── config.json                 # Search & scoring configuration
│   ├── system_prompt_final.txt     # AI analysis instructions
│   ├── master_reddit_data.json     # Historical data store
│   └── processed_ids.log          # Deduplication tracking
├── reports/
│   ├── Report_Posts.docx          # Post engagement opportunities
│   └── Report_Comments.docx       # Comment engagement opportunities
└── Main_controller.py             # Interactive pipeline controller
```

## 🧠 AI Analysis Framework

The system uses configurable domain-specific frameworks to evaluate content. The current skincare marketing configuration uses 6 root cause categories:

### Skincare Marketing Intelligence Framework:

1. **Internal Harmony (Gut & Hormones)** - Systemic imbalances affecting skin health
2. **Environmental Aggressors** - External factors impacting skin barrier function  
3. **Lifestyle & Habits** - Daily routines influencing skin condition
4. **Ingredient Efficacy & Product Suitability** - Formulation effectiveness and compatibility
5. **Genetics & Individual Biology** - Inherited predispositions and unique physiology
6. **Psycho-Dermatology** - Mind-skin connection and emotional impact

Each piece of content is classified as "Suitable" or "Unsuitable" with root cause mapping and marketing communication angles.

### Framework Customization
To adapt the platform for different domains:
1. **Update system prompt** (`data/system_prompt_final.txt`) with new analysis framework
2. **Modify target subreddits** in `data/config.json` for relevant communities
3. **Adjust keywords** for domain-specific content discovery
4. **Customize JSON schema** in analysis script for new output fields

## 📈 Output Examples

### Generated Reports Include:
- **Opportunity Score** (velocity-based ranking)
- **Context** (full post/comment thread)
- **Skin Concern Identified** (AI-detected customer pain point)
- **Root Cause Category** (mapped to analysis framework)  
- **Marketing Communication Angle** (strategic messaging direction)
- **Clickable Reddit Links** (direct access to content)

## 🔒 Cost Management

- **Confirmation prompts** before OpenAI API calls
- **Batch processing** to minimize API requests
- **Deduplication** prevents reprocessing content
- **Empty data detection** skips unnecessary API calls

## 🤝 Contributing

This pipeline is designed for strategic market intelligence across multiple domains. The scoring algorithms and AI analysis frameworks can be easily adapted for different industries by modifying the system prompt and configuration files.

## 📄 License

Private project for strategic market intelligence and business analysis.
