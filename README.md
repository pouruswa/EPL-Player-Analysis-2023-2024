
# English Premiere League - Player Data Analysis 2023-2024 ⚽⚽

This project is an experimental analysis to understand the player performance visually for all the players in the English Premiere League during the 2023-2024 season. Through python's webscraping ability I scraped data via fbref.com and performed data cleaning and data visualization. Some findings were interesting!


## 🛠 Skills
Webscraping in Selenium, Matplotlib, Seaborn, Pandas


# Hi, I'm Pourus! 👋 
Passionate about all things formula 1, eletric vehicles & soccer. An avid Chelsea supporter (#KTBFFH) and worship the greats - CR7, Ronaldinho, Zinedine Zidane, Kevin DeBruyne and Sunil Chhetri. I'm originally from India and been playing as a CAM (Central Attacking Midfielder or Left Wing) since I got fired up watching "Goal" where John Abraham is a MVP of a humble club, Southhall United in England. (Indian movie reference) I was aiming to be a goalie, since I grew up oversize and could never move as quick, but voila!


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


## Lessons Learned & Challenges
#### Code Insights
a) Webscraping via Selenium was easier compared to using BeautifulSoup : BeautifulSoup was not able to pick the correct table using the same ID that I used in Selenium to pick the Player Statistics table

b) Multi-indexed columns in the table were saved as tuples in the dataframe, this made it difficult to work with the columns

c) Every 26th row the table is picking up column headers as that's how they are listed in the table on the url. I am unable to skip those rows for all their occurences - hence I saved the dataframe in a csv and manually deleted the rows. I noticed this error when the dataframe I initially ingested showed all data types as 'objects', including the columns I know must be numeric

d) matplotlib has a subplot function that displays two plots side-by-side in a single call. This was cool!

e) Column normalization/Feature scaling was performed on 3 columns that need to be used to calculate an overall average for that player's playmaking ability. Since the column had same minimums (0) but different ranges, I brought them within 0-100 range using [(value-min)/range)

f) Developed a new column called 'playmaking_ability'. This column was a weighted average of progressive passes, progressive carries and progressive passes received as playmakers like Kevin De Bruyne are those that make critical passes hold and take control of the game i.e. carry the ball forward and receive passes to make the game

#### Analysis Insights
a) Correlation Matrix (heatmap) helped me explore relationships with different columns - such as age having moderate correlation with yellow cards & progressive passes

b) While plotting top assisting positions - after forwards, defenders made it to the second position of the maximum assists provided in a game - this was a revelation but was in line with actuality as players like Kyle Walker, Kieran Trippier, Reguilon playing the left back and right back positions come upfield during attacking plays and cross the ball directly into the box for Forwards to finish

c) The url - fbref.com provided a glossary on what the columns meant that helped me with the analysis

