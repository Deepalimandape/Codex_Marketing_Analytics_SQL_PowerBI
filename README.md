# a. Who prefers energy drink more? (male/female/non-binary?)
```sql
Select Gender, count(respondent_ID) 
From dim_repondents
Group by Gender
order by count(respondent_ID) desc
```
