# PyCity School Analysis
Utilizing pandas district wide standardized test resutls will be analized to identify trends in school preformances. The data specifies students math scores, reading scores, and the schools they attended. The analysis will specify 

1. District summary
2. School summary
3. Highest vs. lowest preforming schools based on passing score 
4. Math and reading scores by school grade
5. Test scores based on spending per student
6. Test scores based on school size
7. Test scores based on school types


## Results

<p>The distrct summary shows that there are a total of 15 schools that sum close to 40k students and slightly under $25 mill in total budget for all schools. These details were foudn by searching and counting for the unique school names throghout the data as well as adding the number of student ID's and budget detailed throughout the data.</p>

```
# Calculate the total number of unique schools
school_count = school_data_complete['school_name'].unique()
school_count = len(school_count)
school_count
15

# Calculate the total number of students
student_count = school_data_complete['Student ID'].count()
student_count = int(student_count)

student_count
39170

# Calculate the total budget
total_budget = school_data['budget'].sum()
total_budget = int(total_budget)
total_budget
24649428
````

<p>Additionally, we can see that overall over half of the schools are preforming with passing grades in both reading and math scores.</p>

```
# Use the following to calculate the percentage of students who passed math (math scores greather than or equal to 70)
passing_math_count = school_data_complete[(school_data_complete["math_score"] >= 70)].count()["student_name"]
passing_math_percentage = float(passing_math_count / float(student_count) * 100)
passing_math_percentage
74.9808526933878

# Calculate the percentage of students who passed reading (hint: look at how the math percentage was calculated)
passing_reading_count = school_data_complete[school_data_complete['reading_score']>= 70].count()['student_name']
passing_reading_percentage = float(passing_reading_count / float(student_count) *100)
passing_reading_percentage
85.80546336482001 
````

<p> We can see from our distinction of charter and distric school, that charter schools generally have a smaller population of students compared to district schools. Additionally we can see charter schools like Cabrera High School and Griffin High School had higher math and reading scores comapared to district schools like Bailey High School Figueroa High School respectively. From this we can conclude that there is not a direct correlation between per student budget and avergae score preformance for reading and math scrores. Furhter more we may conclude that the type of school (i.e. District and charter school) is directly associated with a students score preformance. Looking at the highest preforming school by % overall passing, our conclusion that success rate is directly correlated with charter schools is proven since the top 5 schools in this analysis are charter schools. </p>
<img width="801" alt="image" src="https://github.com/user-attachments/assets/d073eea9-68d6-4672-8111-952ce1a392e4" </p>


## Data Source 
1. Resources/schools_complete.csv
2. Resources/students_complete.csv
   
