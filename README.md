# Problem A
Download the Code which is in .ipny file from the github and do the following settings:
## MySQL Setup

Before running this project, make sure you have MySQL installed and set up. Create a database named `your_database_name` and update the database configuration in the code accordingly.

```bash
def get_mysql_connection():
    return mysql.connector.connect(
        host="your_mysql_host",
        user="your_mysql_user",
        password="your_mysql_password",
        database="your_mysql_database"
    )

```

## Database Schema

### Movie Schema
![Movie Schema](https://lh3.googleusercontent.com/d/1wohjKvjkMVTHvXo43jtUnzxEmRt2CON4)

### Reviews Schema
![Reviews Schema](https://lh3.googleusercontent.com/d/1Z8Rfr9WthHxfFyF0iiFTxyAw5KIVsMGJ)

## Libraries to be Imported

Make sure to install the following libraries using `pip install`:

- BeautifulSoup
- selenium
- mysql-connector

```bash
pip install beautifulsoup4
pip install selenium
pip install mysql-connector-python
```

# Chrome Driver

This project uses Selenium with Chrome. Ensure that you have the ChromeDriver installed, and its version matches your Chrome browser version.

## Chrome Driver Version

Download the ChromeDriver version corresponding to your Chrome browser version. You can check your Chrome version by navigating to `chrome://settings/help` in your browser.

## Chrome Driver Download

Download ChromeDriver from [https://sites.google.com/chromium.org/driver/downloads](https://sites.google.com/chromium.org/driver/downloads).

## Note

Ensure that the ChromeDriver executable is in your system's PATH or provide the path to the executable in your code.


```
chrome_path = '/path/to/chromedriver'
driver = webdriver.Chrome(executable_path=chrome_path)
```
Note: Replace /path/to/chromedriver with the actual path where you have downloaded the ChromeDriver executable.

Now you are ready to run the project!

# Project Overview

This project utilizes Selenium and BeautifulSoup to extract dynamic data from a website. Selenium is used for simulating user interactions, such as clicking events, while BeautifulSoup is employed for efficient data extraction.

## Data Extraction Process

1. **Fetching Genres:**
   - The initial step involves scraping all available genres from the [IMDb Genres page](https://www.imdb.com/feature/genre/). 
   - The fetched genres are stored in an array for subsequent data retrieval.

2. **Fetching Movie Data:**
   - The script then iterates through each genre, navigating to the respective genre's webpage.
   - For each genre, the top 20 movies are extracted and stored in a MySQL database.
   - The dynamic nature of the data necessitates the use of Selenium to perform click events and efficiently retrieve details from the site.

3. **Fetching Reviews:**
   - Reviews are linked to movies via the movie ID, which is extracted from the query parameter present in the URL.
   - Using this movie ID, the script fetches and stores 10 reviews data for each movie in the reviews table of the MySQL database.

# Assumptions

During the assessment and development of this project, the following assumptions were made:

1. **Number of Cast Members:**
   - The website displays three names of cast members for each movie. This assumption is hardcoded in the script, and the extraction process is designed to accommodate this specific structure. If the website changes its format or the number of cast members per movie varies, the script may need adjustments.

2. **Top Rated Movies:**
   - The script fetches top-rated movies according to the default filter on the website. If the website changes its default filter or the definition of "top-rated" evolves, the script may need to be adapted to reflect these changes.

# Challenges Faced

While developing this project, the following challenges were encountered:

1. **Lack of HTML Element IDs:**
   - The HTML structure of the website did not consistently provide unique IDs for elements. As a result, the script relies on class names to extract data. While class names are commonly used for most of the elements.



