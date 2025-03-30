# Reddit Scraper and Sentiment Analysis

## Overview
This project extracts data from Reddit using the PRAW API, cleans the extracted text, performs sentiment analysis, and visualizes high-risk posts using a heatmap.

## Features
- **Scrape Reddit posts** from a specific subreddit based on mental health keywords.
- **Clean text data** by removing URLs, special characters, and stopwords.
- **Perform sentiment analysis** using Textblob to classify posts as Positive, Neutral, or Negative and Sentimental Score.
- **Classify risk levels** based on predefined crisis-related keywords.
- **Visualize data** through bar plots and a geolocation-based heatmap.

## Installation
To install the required dependencies, run:
```sh
pip install praw nltk pandas textblob geopy folium matplotlib scikit-learn
```

## Usage
### Step 1: Configure Reddit API Credentials
Replace the placeholders in the script with your Reddit API credentials:
```python
reddit = praw.Reddit(
    client_id="YOUR_CLIENT_ID",
    client_secret="YOUR_CLIENT_SECRET",
    user_agent="YOUR_USER_AGENT"
)
```

### Step 2: Run the Script
```sh
python GSOC_Reddit.py
```

### Step 3: Analyze Data
The script will:
- Extract and clean Reddit posts.
- Perform sentiment and risk analysis.
- Save the processed data to `cleaned_reddit_data.csv`.
- Generate a heatmap and save it as `crisis_heatmap.html`.

## Libraries Used
- **praw**: Reddit API Wrapper
- **nltk**: Natural Language Toolkit for stopword removal and sentiment analysis
- **textblob**: Text preprocessing
- **geopy**: Location extraction
- **folium**: Geolocation visualization
- **matplotlib**: Data visualization
- **pandas**: Data manipulation
- **scikit-learn**: Feature extraction

## Risk Level Classification
The script categorizes posts into different risk levels based on predefined keywords.

### High Risk Keywords
- depressed, end, struggle, anxiety, depression, suicide, hopeless, worthless, no way out, can't go on, giving up, ending it, goodbye, life is meaningless, self-harm, hurting myself

### Moderate Risk Keywords
- lost, overwhelmed, struggling, help, feeling lost, not okay, empty, tired, burned out, drained, can't focus, frustrated, confused

### Low Risk Keywords
- stressed, nervous, uncertain, down, sad, not feeling great, need advice, feeling off

## Output
### Sentiment and Risk Classification
Example output:
```
Cleaned Content | Sentiment | Risk Level
----------------------------------------
I feel so lost and alone... | Negative | High Risk
Trying my best but still struggling... | Neutral | Moderate Concern
Life is tough but I'll manage | Positive | Low Concern
```

### Visualizations

- **Bar plots** for sentiment and risk distribution.
- **Heatmap** showing crisis posts' locations.



## Author
Developed by **Shreya S. Nalawade**

## License
MIT License

