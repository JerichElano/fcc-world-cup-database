# 🏆 World Cup Database

Hi! This is one of my database projects for the **freeCodeCamp Relational Database Certification**. 

In this project, I created a PostgreSQL database from scratch called `worldcup`. It stores and organizes information about match results, winners, and participants from the 2014 and 2018 World Cup tournaments.


## ⚽ About the Project

The core goal was to build a normalized relational schema, automate data ingestion from a CSV file using a Bash script, and answer complex analytical questions using advanced SQL queries.

* **`games.csv`** - The raw dataset containing match results (`year,round,winner,opponent,winner_goals,opponent_goals`).
* **`insert_data.sh`** - A custom Bash script that reads `games.csv`, parses unique teams into the `teams` table, and maps foreign keys (`winner_id`, `opponent_id`) to insert games into the `games` table.
* **`queries.sh`** - A script containing SQL queries to aggregate, filter, and extract specific match statistics required by the project specifications.
* **`worldcup.sql`** - A complete PostgreSQL database dump generated using `pg_dump`.

## 🛠️ What I Learned & Key Takeaways

While building this project, I practiced and strengthened several core database and scripting skills:

* **Relational Schema Design:** Created primary keys (`SERIAL`), established `FOREIGN KEY` constraints linking `games` to `teams`, and enforced data integrity using `UNIQUE` and `NOT NULL`.
* **Automated Data Ingestion:** Built shell logic using `cat`, `while IFS=","`, `read`, and `if` conditions to skip CSV headers and prevent duplicate database entries.
* **Complex SQL Aggregations:** Used functions like `SUM()`, `AVG()`, `ROUND()`, `MAX()`, and `GREATEST()` to calculate overall statistics across multi-column data.

## ⚡ Challenges & Debugging Highlights

Working through this project involved solving several practical development challenges:

* **Extracting Unique Entities Across Two Columns:** Since every game has both a `winner` and an `opponent`, I had to ensure my ingestion script extracted and inserted unique team names from both columns so no participating team was left out.
* **Avoiding Duplicate Inserts in Shell Scripts:** Designed conditional checks in Bash to query whether a team name already existed in the database before attempting an `INSERT`.
