# students-mental-health-analysis
# Analyzing Students' Mental Health
## Project Overview
This project involves using SQL to explore data from a study on the mental health of international students. The goal is to identify factors that may have the greatest impact on students' mental health.
## Dataset
The dataset used in this project contains information on various factors such as study hours, sleep hours, social activities, and their corresponding mental health scores.

Does going to university in a different country affect your mental health? A Japanese international university surveyed its students in 2018 and published a study the following year that was approved by several ethical and regulatory boards.
The study found that international students have a higher risk of mental health difficulties than the general population, and that social connectedness (belonging to a social group) and acculturative stress (stress associated with joining a new culture) are predictive of depression.
Exploring the students data using PostgreSQL to see results for international students, if the length of stay is a contributing factor.

## SQL Queries

### Exploring the students data using PostgreSQL to see results for international students, analyzing the Impact of Stay Duration in a foreign country on Mental Health 
The following SQL queries were used to analyze the dataset:

```sql
SELECT STAY, COUNT(inter_dom) AS COUNT_INT, ROUND(AVG(todep), 2) AS AVERAGE_PHQ, ROUND(AVG(tosc), 2) AS AVERAGE_SCS, ROUND(AVG(TOAS), 2) AS AVERAGE_AS
FROM public.students
WHERE inter_dom = 'Inter'
GROUP BY stay
ORDER BY stay DESC
LIMIT 9;
