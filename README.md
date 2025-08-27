Deepsearch Labs – FT.com Scraping Task


This repository contains the work I did for the **Deepsearch Labs Task**.  
The project is split into **two notebooks**: 

- **Notebook 1 → Scraping Articles**  
- **Notebook 2 → Data Analysis & Automated Presentation**

The goal is to **scrape articles from FT.com**, save them in a database, and then use the data to build an **automated presentation with summaries and insights**.  

## Notebook 1: Scraping Articles from FT.com  

### What it does:
- Uses **Selenium + Stealth** to scrape FT.com (JavaScript site).  
- Bypasses **Cloudflare** and **paywall** with Brave browser + extension.  
- Saves all scraped articles into **MongoDB**.  
- Runs in **parallel** to scrape multiple sections (world, tech, companies, markets, climate).  
- Supports two modes:  
  - **Full scrape** → 20 pages per section (first time).  
  - **Daily scrape** → 2 pages per section (scheduled at 10:00).
 
### Data saved:
- Title  
- Link  
- Article text 
- Authors  
- Topic / Tag  
- Published datetime  
- Section

## Notebook 2: Data Analysis & Automated Presentation  


### What it does:
- Loads the scraped data from **MongoDB** into Pandas.  
- Cleans the dataset (removes missing values).  
- Creates visualizations:  
  - Articles per section (pie + bar chart).  
  - Top authors.  
  - Top topics.  
  - Word cloud of most common words.  
- Uses **Gemini API (LLM)** to generate a **LaTeX Beamer presentation**:  
  - Each section → 3 slides (2 summaries + 1 main ideas).  
  - Clean, professional design.  
- Converts LaTeX into **PDF presentation** automatically with Selenium.

The file **`presentation.pdf`** is included in this repository as an example output.  
It was generated automatically by **Notebook 2** using


All required libraries are already listed in **`requirements.txt`**.  
You can install them with one command:  

```bash
pip install -r requirements.txt




