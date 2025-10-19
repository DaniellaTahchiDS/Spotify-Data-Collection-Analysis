# Spotify Music Data Collection & Analysis

**Author:** Daniella Tahchi  
**Date:** October 19, 2025

## Overview

This project demonstrates how to collect and analyze music data from the Spotify API. It focuses on extracting detailed track information from playlists and performing exploratory data analysis to uncover insights and visualize trends.

## Project Components

### 1. Data Collection: Obtaining an Access Token

To interact with the Spotify API, authentication is required through an access token. The process includes:

- Creating a Spotify Developer account and application to obtain `CLIENT_ID` and `CLIENT_SECRET`
- Encoding credentials using Base64 format
- Making a POST request to `https://accounts.spotify.com/api/token` with `grant_type=client_credentials`
- Extracting the access token from the successful response

### 2. Data Extraction: Gathering Track Information

The `get_trending_playlist_data` function extracts comprehensive track information from a specified playlist:

**Parameters:**
- `playlist_id`: Unique identifier of the target playlist
- `access_token`: Authentication token for API requests

**Data Extracted:**
- Track Name
- Artists (comma-separated)
- Album Name and ID
- Track ID
- Popularity Score (0-100)
- Release Date
- Explicit Content Flag
- External URLs

The function uses the `spotipy` library to retrieve data and returns a pandas DataFrame containing all extracted information.

### 3. Exploratory Data Analysis (EDA)

The analysis includes several visualization techniques to understand the dataset:

#### Initial Data Inspection
- Used `df.info()` to examine data structure
- Dataset contains 34 tracks with no missing values
- All data types are appropriate for their respective columns

#### Key Visualizations

**Number of Tracks per Album**
- Bar plot showing track distribution across albums
- 'The Life of a Showgirl' has the highest number of tracks
- 'reputation' and '1989' follow as the next most represented albums

**Album Representation**
- Pie chart displaying the proportion of tracks from each album
- Visually reinforces the dominance of 'The Life of a Showgirl'

**Average Track Popularity by Artist**
- Bar plot of average popularity scores per artist
- Taylor Swift & Sabrina Carpenter collaboration shows highest average popularity
- Followed by Taylor Swift solo tracks and collaborations with Ed Sheeran and Future

**Word Cloud of Track Names**
- Visual representation of most frequent words in track titles
- Highlights recurring themes and popular terms

## Key Insights

- 'The Life of a Showgirl' album dominates the playlist in terms of track count and representation
- Collaborative tracks, particularly Taylor Swift with Sabrina Carpenter, show higher average popularity
- All tracks in the dataset have complete information with no missing values
- High-popularity tracks (>90) are easily identifiable through styling

## Technologies Used

- **Python Libraries:** pandas, spotipy, matplotlib/seaborn (for visualizations), wordcloud
- **API:** Spotify Web API
- **Authentication:** OAuth 2.0 Client Credentials flow

## Requirements

- Spotify Developer Account
- Python 3.x
- Required libraries: `spotipy`, `pandas`, `matplotlib`, `wordcloud`

---

*This project serves as a comprehensive guide for anyone looking to work with the Spotify API for music data analysis and visualization.*
