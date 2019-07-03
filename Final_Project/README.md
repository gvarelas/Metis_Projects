# Predicting Soccer Player Valuations
***

For my final project, I tried building a model capable of predicting the transfer market value of soccer players. I'm a huge soccer fan, so I wanted to see if I could apply data science and analytical tools to find the fair price of any given player given historical playing stats, salaries, contract lengths, injury history, and more.

## Data Acquisition

I scraped 3 websites to obtain the data for this project - [transfermarkt](https://www.transfermarkt.com/) for price and injury history, [whoscored](https://www.whoscored.com/) for historical game statistics, and [fifaindex](https://www.fifaindex.com/) for wage and contract data. I used BeautifulSoup to scrape transfermarkt and fifaindex, and Selenium for whoscored. Unfortunately, I was only able to get prices for ~1500 players from transfermarkt, so the data isn't as exhaustive as I would've liked. Every notebook other than 'Final_Modelling' was used to scrape, clean, or join the data. 

## Feature Engineering

