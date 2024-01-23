-- What Platform have the most games?

SELECT platform, count(Platform) as number_of_games


FROM video_games.games_data


group by Platform


order by count(platform) desc;


--What type of game genre have the most highest critic score?

SELECT genre, avg(Critic_Score) as genre_avg_critic_score


FROM video_games.games_data


group by Genre


order by genre_avg_critic_score desc;


--what company have the highest total global sales?

SELECT publisher, sum(Global_Sales)


FROM video_games.games_data


group by Publisher


order by sum(Global_Sales) desc;


--Top 5 games on North america

select name, platform, Year_of_Release, genre, publisher, NA_Sales


from video_games.games_data


order by NA_Sales desc


limit 5;


--Does rating affect the total sales?

select sum(Global_Sales) as Total_sales, rating


from video_games.games_data


where rating is not null


group by rating;


--what publisher have the most user

select publisher , sum(user_count) total_user


from video_games.games_data


group by publisher 


order by total_user desc;



--highest sales of publisher

select publisher, max(Global_Sales) highest_game_sale

from video_games.games_data

group by Publisher

order by highest_game_sale desc

