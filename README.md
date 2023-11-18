# Calculating-Free-to-Paid-Conversion-Rate-with-SQL-and-Python
to estimate the fraction of students who purchase a subscription after starting a lecture, i.e., the free-to-paid conversion rate among students who’ve engaged with video content on the 365 platform. You will also be tasked with calculating several other key metrics and analyzing the results.

The data you’ll be working with includes three tables storing information about students’ registration dates, engagement dates, and subscription purchase dates.
The task is to find out 
. What is the free-to-paid conversion rate of students who have watched a lecture on the 365 platform?
. What is the average duration between the registration date and when a student has watched a lecture for the first time (date of first-time engagement)?
. What is the average duration between the date of first-time engagement and when a student purchases a subscription for the first time (date of first-time purchase)?
. How can we interpret these results, and what are their implications?

The result found are-

**Conversion Rate**
Let’s first discuss the result we obtained for the free-to-paid conversion rate metric. The fraction of students who purchase monthly, quarterly, or annual subscriptions from those who watch a lecture is about 11%—i.e., for every 100 students who come to the 365 platform, roughly 11 of them purchase a subscription. At first glance, this number seems relatively low, but let’s dig a bit deeper.

A significant number of students register on the platform out of curiosity. Nevertheless, we can outline why most students aren’t prompted to benefit from the program entirely. One factor contributing to this could be that we’re targeting a broader audience rather than focusing specifically on data science enthusiasts eager to begin their journey in the field.

Second, since our platform targets a beginner audience, students may need clarification about what to start with. Should they first invest weeks in mastering an object-oriented programming language such as Python, a query language such as SQL, or maybe a data visualization software like Tableau? What prerequisites are necessary for each of these tools? In August 2023, the team at 365 put effort into making its audience’s journey much easier by introducing an onboarding sequence that creates a customized learning path for each of its students. This way, users will know exactly where to start and how to continue.

Still, some users might need more time to embark on a data science journey. They might be college students whose exam periods have just started or working people who can’t dedicate the desired time.

Finally, we must consider that some users might not fancy the platform and would instead take the first steps toward data science elsewhere. Still, whatever the reason, reaching out to customers is essential, pinpointing any flaws and striving towards a better product.

**Average Duration Between Registration and First-Time Engagement**
The results from the second metric indicate that, on average, it takes students between three and four days to start watching a lecture after registering on the platform. Ideally, it would be great if a new student started watching a lecture on their first day. Every other element the platform offers (exams, projects, career tracks) requires more attention, while the lessons are easy to check out. It’s worth diving a bit deeper into this analysis.

The dataset’s average is a metric that shouldn’t be studied in a vacuum because outliers heavily affect it. It’s, therefore, essential to study the other two metrics that typically come hand-in-hand with the average: median and mode. The median tells us which number sits in the middle of a dataset—assuming it’s ordered—while the mode is the number that occurs most often in a dataset. Calculating these is not as straightforward in SQL—so you can use another tool. I’ve chosen Python. The results are as follows:

Mode: 0
Median: 0
Mean: 3.42
The number that repeats the most in the data is 0. Additionally, the number that sits in the middle of the dataset is also 0. Such metric values indicate the right-skewness of the data—i.e., we can find outliers to the right, towards higher values, of the data distribution. This implies that some students in the dataset have registered on the 365 platform but started watching a lecture much later. To convince ourselves, let’s also study visually the distribution of the numbers.
Almost all students watch a lecture immediately after registering. Very few return to the platform to start a course several days or even a year after registration. One reason for returning could be because of a marketing campaign, a free-day campaign, etc.

**Average Duration Between First-Time Engagement and First-Time Purchase**
Let’s study analogously the average duration between the first-time engagement and purchase. The results we retrieved from our SQL analysis show that, on average, it takes students roughly 24 days to purchase a subscription after getting acquainted with the product. Once again, we should take this result with a grain of salt and study the other relevant metrics: median and mode. Using, for example, Python, we can calculate the three metrics, which turn out to be as follows:

Mode: 0
Median: 1
Mean: 26
We see that the mean is significantly higher than the other two metrics. This points towards the presence of even more extreme outliers in this dataset. Let’s discuss the metrics one by one. The most occurring value is again 0. Therefore, students who purchase a subscription are prone to do it on the same day. The value in the middle of the dataset—assuming it’s ordered—is 1, which means that the people who buy on the same day are less than half of all users making a purchase. To be more specific, about 49% of the people purchase on the day they’ve watched a lecture for the first time. The mean value, however, assumes that the transition from free-plan to paying students happens for almost a month. Let’s again estimate this discrepancy visually.
We can again see that the data is skewed to the right, which we could’ve inferred from the fact that the mode is smaller than the median, which, in turn, is smaller than the mean. As we can see, most users purchase within a day or two after they’ve watched a lecture. Some people, however, purchase several months later. One reason could be that they liked the content on the platform but have been waiting for the product to be offered at an exclusive price.

