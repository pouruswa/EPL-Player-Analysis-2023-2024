
# English Premiere League - Player Data Analysis 2023-2024

This project is an experimental analysis to understand the player performance visually for all the players in the English Premiere League during the 2023-2024 season. Through python's webscraping ability I scraped data via fbref.com and performed data cleaning and data visualization. Some findings were interesting!


## 🛠 Skills
Webscraping in Selenium, Matplotlib, Seaborn, Pandas


# Hi, I'm Pourus! 👋 
Passionate about all things formula 1, eletric vehicles & FOOTBALL. An avid Chelsea supporter (#KTBFFH) and worship the greats - CR7, Ronaldinho, Zinedine Zidane, Kevin DeBruyne and Sunil Chhetri. Also YES, I call it football since I'm originally from India and been playing as a CAM (Central Attacking Midfielder or Left Wing) since I got fired up watching "Goal" where John Abraham is a MVP of a humble club, Southhall United in England. (Indian movie reference) I was aiming to be a goalie, since I grew up oversize and could never move as quick, but voila!


## FAQ

#### How do I run this script in my local machine?

Step 1 : Download the EPL_PlayerStat_scraping file

Step 2 : Download the ChromeDriver from this webpage - https://developer.chrome.com/docs/chromedriver

Step 3 : Replace 'driver_path' with the chromedriver.exe filepath in your local machine

Step 4 : Insert the url for the webpage in 'url'

Step 5 : Find the appropriate table by ID ; for player data on the webpage use "stats_standard" as the ID

Step 6 : table.getattribute('outerHTML) retrieves the full HTML of the table making it useful for parsing data to a dataframe like Pandas

#### Does the complete table data arrive without any issues?

- After every 25(n) row, the table header is repeated
- I exported the dataframe to csv and cleaned the rows manually in excel


## Lessons Learned

a) Webscraping via Selenium was easier compared to using BeautifulSoup : BeautifulSoup was not able to pick the correct table using the same ID that I used in Selenium to pick the Player Statistics table

b) Multi-indexed columns in the table were saved as tuples in the dataframe 

