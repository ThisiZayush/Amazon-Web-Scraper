[Readme.txt](https://github.com/user-attachments/files/30152865/Readme.txt)
# Amazon Price Tracker Bot 🕷️💰

A Python-based web scraper that automatically tracks the price of a specific product on Amazon at regular intervals and appends the data (Product Name, Price, Date, and Time) into a local CSV file for historical tracking and analysis.

## 🚀 Features
* **Automated Web Scraping:** Uses `BeautifulSoup` and `requests` to parse the Amazon HTML page and target specific product elements.
* **Data Cleaning:** Automatically trims whitespace and strips currency symbols for clean data storage.
* **Timestamping:** Generates real-time date and time for every price check.
* **Automated Data Logging:** Uses Python's built-in `csv` module to append the tracked data into a structured CSV file.
* **Continuous Monitoring:** Implements an infinite loop with a customizable time interval (`time.sleep`) to continuously monitor price fluctuations.

## 🛠️ Tech Stack & Libraries Used
* **Language:** Python 3
* **Libraries:**
  * `requests`: To send HTTP requests to the Amazon server.
  * `BeautifulSoup` (from `bs4`): To parse the HTML content of the page.
  * `csv`: To write and append data into the dataset.
  * `pandas`: To read and display the saved dataset in a tabular format.
  * `datetime` & `time`: To handle timestamps and loop intervals.

## ⚙️ Prerequisites & Setup

### 1. Installation

Ensure you have Python installed. You can install the required external libraries using `pip`:

pip install beautifulsoup4 requests pandas

### 2. Update File Paths
In the script, make sure to update the absolute path to match your local system directory where you want the CSV to be read/saved:

df = pd.read_csv(r"C:\Users\YourUsername\Documents\Python\AmazonWebScraperDataset.csv")

### 3. User-Agent

Amazon heavily blocks automated scripts. The code includes a custom User-Agent in the headers to mimic a real browser visit. If the request fails or returns a NoneType error, you might need to update the User-Agent string with your own browser's header (search "my user agent" on Google to find yours).

### How to Run the Script

python amazon_scraper.py

### Note: The script runs on an infinite while(True) loop set to check every 5 seconds by default. You can change time.sleep(5) to time.sleep(86400) if you want to check the price once every day.
