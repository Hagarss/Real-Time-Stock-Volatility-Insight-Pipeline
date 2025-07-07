

# Real-Time Stock Volatility Insight Pipeline

This is a team-based data engineering project to build a real-time data pipeline that ingests stock trade data, enriches it with contextual information (e.g., weather), and stores it for analysis and anomaly detection.

---

## Project Overview

This project simulates a **real-world fintech data pipeline**. It processes live or simulated stock trade data, adds weather data per exchange location, stores the enriched stream in a lakehouse, and provides dashboards and anomaly alerts.

**Main Features:**
- Real-time stock data ingestion using Kafka
- Stream processing using PySpark
- Weather enrichment via OpenWeatherMap API
- Storage using Delta Lake or Parquet
- Pipeline orchestration using Apache Airflow
- Dashboarding with Superset / Grafana (or Tableau / Power BI)
- Anomaly detection using Prophet or rule-based logic

---

## Tech Stack

| Component             | Tool / Technology          |
|----------------------|----------------------------|
| Data Ingestion        | Kafka                      |
| Stream Processing     | PySpark Structured Streaming |
| Enrichment API        | OpenWeatherMap             |
| Storage               | Delta Lake or Parquet      |
| Orchestration         | Apache Airflow             |
| Dashboarding          | Superset / Grafana / Power BI |
| Anomaly Detection     | Prophet, Python rules      |

---

##  Project Structure

```

stock-volatility-project/
│
├── docker-compose.yml          # Runs Kafka + Zookeeper
├── producer.py                 # Sends simulated stock trade data to Kafka
├── README.md                   # Project overview
├── requirements.txt            # Python dependencies
└── (coming soon)
├── consumer\_spark.py       # Reads from Kafka and enriches with weather
├── airflow/                # DAGs for orchestration
├── dashboard/              # Dashboard setup & configs
└── anomaly\_detection.py    # Anomaly detection logic

````

---

## How to Run Locally

### 1. Clone the Repo
```bash
git clone https://github.com/your-username/stock-volatility-project.git
cd stock-volatility-project
````

### 2. Start Kafka using Docker

```bash
docker-compose up -d
```

### 3. Create Kafka Topic

```bash
docker exec -it stock-volatility-project-kafka-1 kafka-topics \
--create --topic stock_prices --bootstrap-server localhost:9092 \
--partitions 1 --replication-factor 1
```

### 4. Run the Python Producer

```bash
pip install -r requirements.txt
python producer.py
```

This will begin sending random stock trade events to the `stock_prices` topic every second.

---

## Sample Kafka Message

```json
{
  "timestamp": "2025-07-07T01:23:45Z",
  "symbol": "AAPL",
  "price": 191.24,
  "volume": 250
}
```

---


---

## Team Members

* Hager Sayed Soliman
* Alaa Osama Sayed
* Omar El Hawary
* Ahmed Magdy Abdelsatar

---

## Notes

* The project is designed to simulate real-time fintech applications with streaming + batch workflows.

---

