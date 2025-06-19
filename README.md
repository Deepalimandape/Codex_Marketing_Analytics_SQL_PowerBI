# 1. Who prefers energy drink more? (male/female/non-binary?)
```sql
Select Gender, count(respondent_ID) 
From dim_repondents
Group by Gender
order by count(respondent_ID) desc
```

# 2. Which age group prefers energy drinks more?
```sql
Select Age, count(respondent_ID) 
From dim_repondents
Group by Age
order by count(respondent_ID) desc
```

# 3. Which type of marketing reaches the most Youth (15-30)?
```sql
Select Marketing_channels, count(*)
From fact_survey_responses
join dim_repondents ON fact_survey_responses.Respondent_ID=dim_repondents.Respondent_ID
where Age IN ("15-18", "19-30")
Group by Marketing_channels
Order by count(*) Desc
```
# 3. What are the preferred ingredients of energy drinks among respondents?
```sql
SELECT Ingredients_expected, count(*)
FROM fact_survey_responses
Group by Ingredients_expected
order by count(*) DESC
```
# 4. What packaging preferences do respondents have for energy drinks?
```sql
SELECT Packaging_preference, count(*)
FROM fact_survey_responses
Group by Packaging_preference
order by count(*) DESC
```
# 5. Who are the current market leaders?
```sql
SELECT Current_brands, count(*)
FROM fact_survey_responses
Group by Current_brands
order by count(*) DESC
```
# 6. What are the primary reasons consumers prefer those brands over ours?
```sql
SELECT Reasons_for_choosing_brands, count(*)
FROM fact_survey_responses
Group by Reasons_for_choosing_brands
order by count(*) DESC;
```
