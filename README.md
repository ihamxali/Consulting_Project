# HostEase Dynamic Pricing Implementation

An AI-driven dynamic pricing system for short-term rental properties in France, developed as part of the Master 1 BDEEM - Supervised Project in AI 2024-2025.

## About the Project

HostEase is a online platform that connects travelers with short-term rental properties in France. This project implements an advanced AI-powered dynamic pricing strategy that adapts to market fluctuations, competitor pricing, seasonal trends, and external factors to maximize revenue and occupancy rates.


## Project Objectives

- **Revenue Optimization**: Maximize revenue per available night (RevPAN)
- **Dynamic Adaptation**: Real-time price adjustments based on demand
- **Competitive Edge**: Stay competitive with platforms like Airbnb and Booking.com
- **Automation**: Reduce manual pricing intervention
- **Data-Driven Decisions**: Leverage AI and ML for intelligent pricing

## System Architecture

### Core Components

1. **Data Collection Engine**: Multi-source data aggregation
2. **AI Pricing Model**: Machine learning-based price optimization
3. **Real-time Processing**: Apache Kafka for streaming data
4. **API Integration**: RESTful APIs for price updates
5. **Monitoring Dashboard**: Performance tracking and visualization

### Data Sources

- **Internal Data**: Booking history, customer behavior, property details
- **External Market Data**: Competitor pricing, demand trends
- **Third-party APIs**: Weather, events, economic indicators
- **Social Media**: Sentiment analysis from reviews and social platforms
- **Manual/Crowdsourced**: Web scraping and user feedback

## AI/ML Techniques

- **Time Series Forecasting**: LSTM, ARIMA models for demand prediction
- **Reinforcement Learning**: Continuous strategy adaptation
- **Gradient Boosting**: XGBoost, LightGBM for booking probability
- **Clustering**: K-Means, DBSCAN for customer segmentation
- **Regression Models**: Random Forest, Linear Regression for price factors

## Key Performance Indicators

- Occupancy Rate (%)
- Revenue Per Available Night (RevPAN)
- Booking Conversion Rate
- Customer Satisfaction Score
- Price Elasticity Analysis
- Competitive Benchmarking

## Technology Stack

- **Backend**: Python, FastAPI
- **ML/AI**: TensorFlow, Scikit-learn, XGBoost
- **Data Processing**: Pandas, NumPy, Apache Spark
- **Database**: PostgreSQL, Redis
- **Streaming**: Apache Kafka
- **Cloud**: AWS (S3, Redshift, Lambda)
- **Visualization**: Matplotlib, Seaborn, Power BI
- **Web Scraping**: BeautifulSoup, Scrapy, Selenium

## Getting Started

### Prerequisites

```bash
Python 3.8+
PostgreSQL
Redis
Docker (optional)
```

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/hostease-dynamic-pricing.git
cd hostease-dynamic-pricing
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Set up environment variables:
```bash
cp .env.example .env
# Edit .env with your configuration
```

4. Initialize the database:
```bash
python scripts/init_db.py
```

5. Run the application:
```bash
python main.py
```

## 📁 Project Structure

```
hostease-dynamic-pricing/
├── src/
│   ├── data_collection/
│   │   ├── internal_data.py
│   │   ├── external_data.py
│   │   ├── api_integrations.py
│   │   └── web_scraper.py
│   ├── models/
│   │   ├── pricing_model.py
│   │   ├── demand_forecasting.py
│   │   └── customer_segmentation.py
│   ├── api/
│   │   ├── routes.py
│   │   └── middleware.py
│   ├── utils/
│   │   ├── data_preprocessing.py
│   │   └── visualization.py
│   └── config/
│       └── settings.py
├── tests/
├── docs/
├── scripts/
├── requirements.txt
├── main.py
├── README.md
└── .env.example
```

## Configuration

Key configuration parameters in `.env`:

```
DATABASE_URL=postgresql://user:password@localhost/hostease
REDIS_URL=redis://localhost:6379
OPENWEATHER_API_KEY=your_api_key
EVENTBRITE_API_KEY=your_api_key
AWS_ACCESS_KEY_ID=your_access_key
AWS_SECRET_ACCESS_KEY=your_secret_key
```

## Usage Examples

### Basic Price Prediction

```python
from src.models.pricing_model import DynamicPricingModel

model = DynamicPricingModel()
price = model.predict_price(
    property_id="123",
    check_in_date="2025-07-15",
    check_out_date="2025-07-18"
)
print(f"Recommended price: €{price}")
```

### Real-time Price Updates

```python
from src.api.routes import update_prices

# Update all property prices based on current market conditions
update_prices()
```



## Visualization

Generate pricing heatmaps and analytics:

```python
from src.utils.visualization import generate_heatmap

# Generate demand heatmap
generate_heatmap(
    data_type="demand",
    time_period="monthly",
    location="Paris"
)
```



---

*This project was developed as part of the Master 1 BDEEM - Supervised Project in AI 2024-2025*
