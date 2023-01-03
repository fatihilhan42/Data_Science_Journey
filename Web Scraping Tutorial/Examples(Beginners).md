## Example 1: Extracting text from a single webpage

In this example, we will use the Requests library to send a GET request to a webpage, and use Beautiful Soup to parse the HTML content of the page and extract the text of the first paragraph.

```Python
import requests
from bs4 import BeautifulSoup

# Send a GET request to the webpage
response = requests.get('http://example.com')

# Parse the HTML content of the page
soup = BeautifulSoup(response.text, 'html.parser')

# Extract the text of the first paragraph
paragraph = soup.p
print(paragraph.text)
```


##Example 2: Extracting data from a table

In this example, we will use Beautiful Soup to extract data from a table on a webpage. We will send a GET request to the webpage, parse the HTML content of the page, and then use Beautiful Soup's find_all method to locate the table and the table rows. We will then iterate over the rows and extract the data from each cell.

```Python
import requests
from bs4 import BeautifulSoup

# Send a GET request to the webpage
response = requests.get('http://example.com')

# Parse the HTML content of the page
soup = BeautifulSoup(response.text, 'html.parser')

# Find the table and the rows
table = soup.find('table')
rows = table.find_all('tr')

# Iterate over the rows and extract the data from each cell
for row in rows:
    cells = row.find_all('td')
    if cells:
        cell_1 = cells[0].text
        cell_2 = cells[1].text
        print(f'{cell_1}: {cell_2}')
```

## Example 3: Extracting data from multiple pages

```Python
import requests
from bs4 import BeautifulSoup

# Set the base URL and the URL of the first page
base_url = 'http://example.com'
url = base_url + '/page1'

# Set a flag to indicate whether we are done scraping
done = False

while not done:
    # Send a GET request to the current page
    response = requests.get(url)

    # Parse the HTML content of the page
    soup = BeautifulSoup(response.text, 'html.parser')

    # Find the table and the rows
    table = soup.find('table')
    rows = table.find_all('tr')

    # Iterate over the rows and extract the data from each cell
    for row in rows:
        cells = row.find_all('td')
        if cells:
            cell_1 = cells[0].text
            cell_2 = cells[1].text
            print(f'{cell_1}: {cell_2}')

    # Check if there is a next page
    next_link = soup.find('a', {'class': 'next'})
    if next_link:
        # Update the URL and scrape the next page
        url = base_url + next_link['href']
    else:
        # There are no more pages, so we are done
        done = True
```