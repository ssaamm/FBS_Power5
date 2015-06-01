FBS_Power5
==========

In the world of college football, the big-money schools will pay smaller schools to come play at their stadium.  The smaller school walks away with a paycheck of up to $1 million for agreeing to the game, and the big school gets a win (usually).  

But occaisionally a big name school plays a smaller school on the road [for various reasons](http://espn.go.com/blog/acc/post/_/id/74265/acc-hits-the-road-vs-group-of-5), and I love watching those games.  It's a huge game for the smaller school, and the bigger Power 5 school just wants to escape with a win.  

I wanted to know if and when these games happen each week, so I made a Python script to determine when a college football team from a Power 5 conference (ACC, Big Ten, Big 12, Pac-12, or SEC) plays a non-power 5 school on the road.

Requirements: 

+ Python 2.7 or 3+
+ SQLAlchemy 0.9.4+
+ Beautiful Soup 4.3+

Note: both SQLAlchemy (for database creation) and Beautiful Soup (for web scraping) are available as pre-installed modules in [Anaconda](https://store.continuum.io/cshop/anaconda/).  

To run:

```python
print_results.py
```

This first creates a blank MySQL database. Next, that database is populated with all FBS schools and their conference.  This scrapes the [Wikipedia table](http://en.wikipedia.org/wiki/List_of_NCAA_Division_I_FBS_football_programs) that lists all FBS schools.

Finally, we use that database and a an online college football schedule to determine which Power 5 teams are playing road games vs. a non-Power 5 opponent each week.  I found the weekly schedule on the [CBS Sports website](http://www.cbssports.com/collegefootball/schedules/FBS/week1) was the easiest to scrape.

Output for the 2015 season looks like this:

```
School database created

Air Force is not a Power 5 school, they're in the Mountain West
Akron is not a Power 5 school, they're in the MAC
Alabama is a Power 5 school in the SEC
<etc...>

Week 1:
Duke at Tulane
Baylor at SMU
Washington at Boise State
Mississippi State at Southern Miss
Penn State at Temple
Texas at Notre Dame
Purdue at Marshall
 
Week 2:
Pittsburgh at Akron
Missouri at Arkansas State
Minnesota at Colorado State
Arizona at Nevada
UCLA at UNLV

<etc...>
```

