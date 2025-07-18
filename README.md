# 🎮 Steam Game Analysis 🚀

This project performs an exploratory data analysis (EDA) on Steam game data to uncover insights related to game performance, user preferences, and the impact of various game attributes.

## 📚 Libraries Used:
- Pandas
- Numpy
- Seaborn
- Matplotlib.pyplot
- Warnings

## 💾 Data Loading and Initial Inspection:
The analysis begins by loading a CSV file named 'bestSelling_games.csv' into a pandas DataFrame.
Initial data inspection includes:
- Displaying the first few rows of the DataFrame (`df.head()`).
- Checking data types and non-null counts for each column (`df.info()`).
- Identifying missing values (`df.isnull().sum()`).
- Checking for duplicate rows (`df.duplicated().sum()`).
- Viewing descriptive statistics of numerical columns (`df.describe()`).

## Data Preprocessing:
- The 'release_date' column was converted to datetime objects for easier time-based analysis.
- No missing values or duplicates were found, indicating a clean dataset for processing.

## Explanatory Data Analysis (EDA):

1.  Correlation between Numerical Variables:
    A correlation heatmap was generated to visualize relationships between numerical variables such as `reviews_like_rate`, `all_reviews_number`, `price`, `age_restriction`, `rating`, `difficulty`, `length`, and `estimated_downloads`.
    Key correlations observed:
    - `all_reviews_number` with `estimated_downloads` = 0.9 (strong positive correlation).
    - `rating` with `reviews_like_rate` = 0.5 (moderate positive correlation).
    - `price` with `length` = 0.3 (weak positive correlation).
    - `rating` with `length` = 0.3 (weak positive correlation).
    - `length` with `estimated_downloads` = 0.3 (weak positive correlation).
    - `length` with `difficulty` = 0.3 (weak positive correlation).

2.  Outlier Analysis:

    Box plots were used to identify outliers in numerical variables. 'Price', 'estimated downloads', and 'reviews' columns contained the most outliers. Upon cross-referencing with specific game names, these outliers were found to be legitimate for known expensive or popular titles.

3.  Top Games Analysis:
    -  **Top 10 Games by All Reviews, Estimated Downloads, and Price:** Bar plots were generated to show the top 10 games in terms of total reviews, estimated downloads, and price. This visualization helped understand why certain values appeared as outliers, confirming that high-priced and highly downloaded games are typically well-known titles.
    -   **Top 10 Most Downloaded Games (Rating >= 3.0) and Their Genres:** The analysis focused on games with a rating of 3.0 or higher.
        Action is the most prevalent genre among top-rated, highly downloaded games, closely followed by FPS, Survival, and Tactical. This is consistent with popular titles like Counter-Strike 2, Dota 2, PUBG: BATTLEGROUNDS, Team Fortress 2, and Apex Legends, all featuring "Action" or "FPS" as core genres.
    -   **Top 10 Fewest Downloaded Games (Rating <= 3.0) and Their Genres:** The analysis also explored games with lower ratings (rating <= 3.0) and the fewest estimated downloads. The results indicate that even games with the "Action" genre do not always have high ratings or estimated downloads, suggesting that user preferences and game quality (gameplay, story, graphics, sound, music, replay value, etc.) are crucial factors.

4.  Impact of Difficulty on Game Performance (Rating, Downloads):
    A line plot of average rating and estimated downloads by difficulty level revealed interesting trends:
    -   Both downloads and ratings generally follow a similar path as difficulty increases.
    -   There's a slight dip in both metrics at difficulty level 2.0, suggesting that games that are too easy or slightly harder than "super easy" might not be as appealing.
    -   Downloads and ratings significantly increase around difficulty level 3.0 and peak at 4.0. This indicates that gamers appreciate a challenging experience.
    -   Beyond difficulty level 4.0 (at 5.0), both metrics start to decline, suggesting that overly frustrating games can deter players.
    -   Conclusion: The sweet spot for game difficulty appears to be around level 4.0, balancing engagement without becoming too frustrating.

Most Used OS and Popular Games within It:
The analysis identified the most used operating systems (OS) for downloading games. "Windows" is the predominant OS, followed by "Linux" and "mac".
Within the "Windows" OS, the most popular games by estimated downloads (with a rating >= 3.0) are:
- Counter-Strike 2 (Rating: 3.20, Genre: FPS, Action, Tactical)
- Dota 2 (Rating: 3.28, Genre: MOBA, Free to Play, Action)
- PUBG: BATTLEGROUNDS (Rating: 3.10, Genre: Survival, Shooter, Action)
- Team Fortress 2 (Rating: 3.00, Genre: Free to Play, Multiplayer, FPS)
- Apex Legends (Rating: 3.00, Genre: Free to Play, Battle Royale, Multiplayer)
- Grand Theft Auto V (Rating: 4.16, Genre: Open World, Action, Multiplayer)
- Unturned (Rating: 3.00, Genre: Free to Play, Survival, Zombie)
- Garry's Mod (Rating: 4.05, Genre: Sandbox, Multiplayer, Physics)
- Tom Clancy's Rainbow Six Siege (Rating: 3.63, Genre: FPS, Tactical, Multiplayer)
- Rust (Rating: 3.86, Genre: Survival, Multiplayer, Open World)


## 🌟 Conclusion:
The analysis shows a strong preference for Action and its sub-genres (FPS, Tactical, Survival, Combat, Shooter) among highly downloaded and well-rated games on Steam, with difficulty level 4.0 being the optimal balance. Windows is the most used OS. Developers aiming for broad market reach should focus on high-quality, action-oriented titles with well-calibrated difficulty 🎮💡
