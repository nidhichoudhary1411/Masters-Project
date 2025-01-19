# Amazon Product Review Analysis

---

## Author

Trapti Damodar Balgi, Nidhi Choudhary
(Group 14)

---

## Overview

This project provides a complete solution to scrape, analyze, and present insights from Amazon product reviews. It performs sentiment analysis, summarization, and topic extraction, helping users make informed decisions.

---

## Features

- **Scraping**: Extract reviews and ratings from Amazon product pages.
- **Summarization**: Condense customer feedback into concise summaries using advanced models.
- **Sentiment Analysis**: Classify reviews into positive, neutral, and negative categories.
- **Topic Extraction**: Identify key topics discussed in reviews.
- **Data Storage**: Store processed data (reviews, ratings, summaries, sentiments, and topics) in MinIO as CSV files.
- **User Interface**: Submit product URLs and view analysis results through a web-based interface.

---

## Prerequisites

1. Docker Desktop installed and running.
2. Kubernetes CLI (`kubectl`) installed.
3. A web browser for accessing the application.

---

## Deployment Instructions

1. **Start Docker Desktop**: Ensure Docker Desktop is running on your system.

2. **Navigate to the Project Directory**: Open a terminal and navigate to the folder containing the project code.

3. **Run the Deployment Script**: Execute the script to deploy the application:
   ```bash
   ./deploy-local-dev.sh
   ```

4. **Access the Application**: Open your web browser and go to:
   [http://localhost:5000](http://localhost:5000)

5. **Check Running Pods**:
   Verify the running pods with:
   ```bash
   kubectl get pods
   ```

6. **Submit an Amazon Product Link**:
   Enter an Amazon product URL in the UI and submit it for analysis.

7. **Monitor Logs**:
   Check worker logs using:
   ```bash
   kubectl logs <worker-pod>
   ```

8. **View Results**:
   The UI will display:
   - Product Name
   - Average Rating
   - Review Summary
   - Sentiment Analysis

9. **Access Processed Data in MinIO**:
   - Open MinIO in your browser: [http://localhost:9000](http://localhost:9000)
   - Log in and navigate to the appropriate bucket.
   - Find CSV files containing reviews, ratings, summaries, sentiments, and topics.

---

## Technologies Used

- **Docker**: For containerization.
- **Kubernetes**: For deployment and scaling.
- **Redis**: For task queue management.
- **MinIO**: For storage of processed data.
- **Pre-trained Models**:
  - `facebook/bart-large-cnn`: Summarization.
  - `joeddav/distilbert-base-uncased-go-emotions-student`: Sentiment Analysis.
  - Latent Dirichlet Allocation (LDA): Topic Extraction.

---

## YouTube Link

- Watch a demonstration of the project: [Amazon Product Review Analysis Demo](https://youtu.be/7qUju_MCX20?si=rLOvE96LoDIEF2do)

---

## Known Limitations

- **Amazon Rate Limiting**: Large-scale scraping can trigger rate limits.
- **OpenAI API Costs**: Free tier limitations require a paid plan for extended usage.
- **Fake Reviews**: Finding and removing unreliable or fake reviews.
- **Performance Bottlenecks**: Processing large datasets can strain resources.

---

## Future Work

- Implement proxy rotation to bypass rate limits.
- Remove Fake Reviews
- Optimize model performance for faster processing.
- Add features for enhanced visualization of analysis results.

---


