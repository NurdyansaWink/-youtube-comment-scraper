# 📺 YouTube Comment Scraper with Multi-Video and Title Support

This Python script extracts **YouTube video comments** (including replies) using the **YouTube Data API v3**, with support for:

- ✅ Multiple API Keys (automatically rotates when quota is exceeded)
- ✅ URL or ID input (supports both regular videos and Shorts)
- ✅ Automatic video title retrieval via API and fallback scraping
- ✅ Fetches both **top-level comments** and **comment replies**
- ✅ Saves output into a clean, structured **CSV file**

---

## ✨ Features

- **Title Handling**: Attempts to fetch the title using the YouTube API. If that fails, it falls back to scraping the video page.
- **Quota Management**: Uses a list of API keys and rotates them when hitting quota limits (`403`, `429`).
- **Progress Indicator**: Shows real-time progress with `tqdm`.
- **Resilient Scraping**: Handles timeouts, network issues, and missing or private videos.
- **Structured Output**: Stores all extracted data in a well-formatted CSV for further analysis.

---

## 📥 Input

Define your list of videos in either full URL or just video ID:

```python
video_inputs = [
    'https://www.youtube.com/watch?v=OwMiq_4cRfg',
    'https://www.youtube.com/shorts/2RzQeceu7zE',
    ...
]
```

---

## 🧾 Output

After execution, comments are saved to:

```
multi_video_comments_with_title.csv
```

Each row includes:

- `video_id`
- `video_title`
- `comment_id`
- `type` (`main` or `reply`)
- `author`
- `text`
- `like_count`
- `published_at`

---

## 🔧 Requirements

Install the required libraries via pip:

```bash
pip install google-api-python-client pandas requests beautifulsoup4 tqdm
```

---

## 🚀 Run the Script

Simply run:

```bash
python youtube_comment_scraper.py
```

Make sure you’ve set up your API keys correctly in the `API_KEYS` list.

---

## ⚠️ Notes

- Make sure the YouTube Data API v3 is **enabled** in your Google Developer Console.
- Free quota is limited — that’s why **multiple API keys** are supported for rotation.
- If scraping fails to retrieve the video title, `"Unknown Title"` will be used.

---

## 👤 Author
Just someone who's simply curious.

Contact Me 
nurdyansa@gmail.com
---

## 📄 License

MIT License — feel free to use, modify, and share.
