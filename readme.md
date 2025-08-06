## Webscraping Project (Python, BeautifulSoup, Pandas)

### Overview
This project demonstartes how to collect data from a website using Python.
I used the `requests` library to retrieve HTML content, `BeautifulSoup` to parse and extract the required elements and `panadas` to organize the data into a clean, reusable format. 

### Objective
Extract relevant information from a web page, in this case, list of companies by revenue from wikipedia and stored into a CSV file for analysis. 

### Tools and Libraries
- Jupyter Notebooks
- Requests to send HTTTP GET requests
- BeautifulSoup (bs4) to parse HTML
- Pandas to store and export structured data

### Steps;
1. Import packages
   ```python
   import from bs4 import BeautifulSoup
   import requests
   import pandas as pd
   
3. Get HTML from website
   ```python
   url = 'https://en.wikipedia.org/wiki/List_of_largest_companies_in_the_United_States_by_revenue'

   page = requests.get(url)
   
5. Parse HTML with BeautifulSoup
   ```python
   soup = BeautifulSoup(page.text, 'html')

   print(soup)
   
7. Inspect and Query HTML
   ```python
   soup.find('table')
   soup.find('table', class_ = 'wikitable sortable')
   table = soup.find_all('table')[0]

   world_titles = table.find_all('th')
   column_data = table.find_all('tr')
   
9. Store data in pandas
    ```python
    world_table_titles = [title.text.strip() for title in world_titles]
    df = pd.DataFrame(columns = world_table_titles)

    for row in column_data[1:]:
    row_data = row.find_all('td')
    individual_row_data = [data.text.strip() for data in row_data]
    
    length = len(df)
    df.loc[length] = individual_row_data


11. Export to CSV
    ```python
    df.to_csv(r'WebScraping.csv', index = False)

### Potential Use Cases
- To aggregate product prices from e-commerce sites.
- Collecting job postings from online job boards
- Extracting article headlines for content analysis


