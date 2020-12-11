# Pycityschools

## Overview 
It's come to the attention of the school board that there is evidence of academic dishonesty commited by the treasonous students of Thomas High School! My task in this analysis was to build on an initial analysis of reading, math, and overall scores to determine if this lecherous behavior had a substantive impact on the board's data. 7 metrics were constructed in parallel; first with the ostensibly corrupt data and then secondly with the potentially innaccurate data converted to null values. 

The 9th grade scores from Thomas High School were removed from the second data set with the simple lines of code: 
``` 
student_data_df.loc[(student_data_df["grade"] == "9th") & (student_data_df["school_name"] == "Thomas High School") & (student_data_df["reading_score"] >= 0), "reading_score"]=np.nan

student_data_df.loc[(student_data_df["grade"] == "9th") & (student_data_df["school_name"] == "Thomas High School") & (student_data_df["math_score"] >= 0), "math_score"]=np.nan
```


## How the Omission Affected Metrics
* District Summary
  * Overall passing rate fell by an entire percentage point. 
* School Summary
  * Removing the Thomas High Data has little affect on the school summary data frame. 
* How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?
  * Removing the erroneous data moves Thomas high out of the top 5 schools in the set. 
* Math and Reading by Grade
  * The biggest change here is that Thomas High ceases to have an average for either reading or math for the 9th grade. Nothing else is affected. 
* Scores by School Spending
  * Removing the scores from Thomas High significantly lowers the percentage passing math, reading, and passing overall scores for the second to highest per student spending range, from 73.484209	84.391793	62.85765 to 66.893995	77.480478	56.389766. 
* Scores by School Size 
  * Removing the scores significantly lowers the percentage passing math, reading, and passing overall scores for the medium size schools from 93.599695	96.790680	90.621535 to 88.327523	91.261628	85.447223
* Scores by School Type
  *  Removing the scores significantly lowers the percentage passing math, reading, and passing overall scores for the charter schools from 93.620830	96.586489	90.432244 to 90.325723	93.130832	87.198299
  
  
## Summary 
1. We have less data for charter schools. 
2. We have less data for schools in the mid-size tier. 
3. We have less data on 9th graders, distorting the actual percentages for passing math, reading, overall. 
4. We have students who are counted in the total number of students who have no scores (at every level). 

