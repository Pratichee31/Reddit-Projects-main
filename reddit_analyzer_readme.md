# Reddit Engagement Intelligence Platform (REIP)

A sophisticated AI-powered pipeline that automatically discovers, analyzes, and prioritizes high-value Reddit engagement opportunities for strategic community participation.

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

### AI-Powered Analysis
- **GPT-4 integration** with structured JSON schema enforcement
- **Philosophy-based filtering** against 6 core coaching principles
- **Batch processing** with rate limiting for cost efficiency
- **Strategic direction mapping** for each opportunity

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

The system uses 6 core coaching philosophies to evaluate content:

1. **Inner Freedom Before External Skill** - Mastery starts from within
2. **Connection Over Performance** - Authenticity over perfection  
3. **Emotional Honesty + Social Grace** - Express feelings skillfully
4. **Grounded, Not Aggressive Masculinity** - Strength is calm and present
5. **Courtship is a Dance, Not a Chase** - Attraction is co-created
6. **Redefining Modern Masculinity** - Evolve toward openness and depth

Each opportunity is classified as "Suitable" or "Unsuitable" with strategic direction mapping.

## 📈 Output Examples

### Generated Reports Include:
- **Opportunity Score** (velocity-based ranking)
- **Context** (full post/comment thread)
- **Strategic Theme** (AI-identified conversation focus)
- **Core Philosophy** (relevant coaching principle)  
- **Strategic Direction** (recommended response approach)
- **Clickable Reddit Links** (direct access to content)

## 🔒 Cost Management

- **Confirmation prompts** before OpenAI API calls
- **Batch processing** to minimize API requests
- **Deduplication** prevents reprocessing content
- **Empty data detection** skips unnecessary API calls

## 🤝 Contributing

This pipeline is designed for strategic community engagement in dating/relationship coaching contexts. The scoring algorithms and AI prompts can be adapted for other domains.

## 📄 License

Private project for strategic Reddit engagement analysis.