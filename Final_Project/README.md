# Predicting Soccer Player Valuations
***

For my final project, I tried building a model capable of predicting the transfer market value of soccer players. I'm a huge soccer fan, so I wanted to see if I could apply data science and analytical tools to find the fair price of any given player given historical playing stats, salaries, contract lengths, injury history, and more.

## Data Acquisition

I scraped 3 websites to obtain the data for this project - [transfermarkt](https://www.transfermarkt.com/) for price and injury history, [whoscored](https://www.whoscored.com/) for historical game statistics, and [fifaindex](https://www.fifaindex.com/) for wage and contract data. I used BeautifulSoup to scrape transfermarkt and fifaindex, and Selenium for whoscored. Unfortunately, I was only able to get prices for ~1500 players from transfermarkt, so the data isn't as exhaustive as I would've liked. Every notebook other than 'Final_Modelling' was used to scrape, clean, or join the data. 

## Feature Engineering

The majority of my time on this project was dedicated to engineering features related to playing position and relevant playing stats. I mostly used my domain knowledge as a soccer fan to select which features to ....

- **Position**: Check to see if a player's position has any impact on their price; my intuition suggested yes, as players who take on goalscoring roles (such as Strikers or Wingers) are generally more sought-after than defensive players
- **Positional Interactions**: I also created interaction terms for the key statistics that I thought would be most relevant to each position. For example, a Striker's main role is to score goals (you wouldn't care how good Cristiano Ronaldo is at defending), so I made interaction terms for all goalscoring stats with the Striker dummy variables, and likewise for all other positions (Winger, Central Midfielder, Attacking Midfielder, Defensive Midfielder, Center-Back, Wing-Back). 
- **Club Bargaining Power**: I created rankings of the bargaining power of every team in the dataset. I suspect that larger, wealthier teams would have more power in controlling their player's selling price, so I found rankings made by [Forbes](https://www.forbes.com/sites/forbespr/2018/06/12/forbes-releases-15th-annual-list-of-the-worlds-most-valuable-soccer-teams/) and created a feature that captured the hierarchy in club value as a possible way to capture the club's bargaining power. 
- **Lagging Historical Features**: 