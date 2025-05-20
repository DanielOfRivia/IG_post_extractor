# 📸 Instagram Post Extractor & Processor

This project extracts and processes content from **Instagram post folders** (like "Japan") — including **captions, image/video content, and voice overlay** — to produce structured, queryable data.

Once processed, this data can be used with tools like **[NotebookLM](https://notebooklm.google)** or **ChatGPT (Advanced Data Analysis)** to:
- Ask questions about your posts
- Summarize or group them by theme
- Search your trip or content history in a smart way

---

## 🔁 Workflow Overview

1. **Extract post links** from an Instagram folder (e.g., "Japan")
2. **Download posts** (images/videos)
3. **Process posts** to extract:
   - Text from voice overlay (if present)
   - Text from images or video frames
4. Use structured output with tools like NotebookLM or ChatGPT

---

## 📁 Project Structure

```
notebooks/
│
├── get_posts.ipynb         # Extracts post links and saves to insta_links.txt
├── download_posts.ipynb    # Downloads posts using links and saves them to /data
├── process_posts.ipynb     # Extracts voice + image text and adds to each post folder
│
├── requirements.txt        # For get_posts & download_posts notebooks
├── requirements2.txt       # For process_posts notebook
│
├── session1.txt            # Add sessionid & folder link from MAIN IG account
├── session2.txt            # Add sessionid & username for SECOND IG account
├── insta_links.txt         # Output: links to posts
│
└── data/                   # Downloaded and processed Instagram posts
```

---

## 🚀 How to Run

### 1. Get `sessionid` and Folder Link

- Log into the **main Instagram account** (the one that owns the folder).
- Open Developer Tools in your browser:
  - Press `F12` or right-click → **Inspect**
  - Go to the **Application** tab → **Cookies** → `https://www.instagram.com`
  - Find and copy the value of `sessionid`

### 2. Edit `session1.txt`

Create or edit the file with:

```
sessionid=<YOUR_SESSIONID>
link_to_folder=<URL_TO_FOLDER>
```

### 3. Run `get_posts.ipynb`

This will extract links to all saved posts and save them to `insta_links.txt`.

---

### 4. Get a Second Instagram Account

Use a second account to **download posts** (this helps reduce the risk of getting your main account banned).

- Log in to that account and extract the `sessionid` using the same browser steps as above.

### 5. Edit `session2.txt`

```
sessionid=<SECOND_SESSIONID>
username=<SECOND_USERNAME>
```

### 6. Run `download_posts.ipynb`

This downloads all Instagram posts referenced in `insta_links.txt` and saves them in the `/data` directory.

---

### 7. Process Posts to Extract Text

#### Option A — Run in **Google Colab**
- Upload `process_posts.ipynb`
- Uncomment the first cell to mount Google Drive (if needed)
- Run all cells

#### Option B — Run **Locally**
- Simply run `process_posts.ipynb` in Jupyter or VSCode

This notebook will:
- Extract **voice-over text** from videos
- Extract **on-screen text** from images and video frames

All extracted data is saved in each post's subfolder inside `/data`.

---

## 🧠 Example Use Case: Query with NotebookLM

Once the text is extracted, the post data becomes structured and searchable. You can:

- Upload the results to [NotebookLM](https://notebooklm.google)
- Ask smart questions like:
  - “Which places did I visit in Tokyo?”
  - “Summarize all posts mentioning shrines or temples”
  - “What are the themes across my captions?”

> This transforms your Instagram archive into a powerful, personal search engine.

---

## ⚙️ Installation

### Install dependencies for `get_posts.ipynb` and `download_posts.ipynb`:

```bash
pip install -r requirements.txt
```

### Install dependencies for `process_posts.ipynb`:

```bash
pip install -r requirements2.txt
```

---


## 📌 Notes

- This project is intended for **personal and educational use only**
- Respect Instagram’s [Terms of Service](https://help.instagram.com/581066165581870)
- Use secondary accounts for scraping to reduce the risk of bans
- The repository aims to demonstrate **data extraction, text processing**, and **practical ML/AI integration**

---

## 📬 Contact

If you’d like to discuss this project, collaborate, or learn more, feel free to reach out via [GitHub](https://github.com/DanielOfRivia/) or [LinkedIn](https://www.linkedin.com/in/danylo-ustymenko-5b5459223/).
