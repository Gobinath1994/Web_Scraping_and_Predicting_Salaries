
In this project, we will practice two major skills: collecting data by scraping a website and then building a binary classifier.
We are going to collect salary information on data science jobs in a variety of markets. Then using the location, title, and summary of the job we will attempt to predict the salary of the job. For job posting sites, this would be extraordinarily useful. While most listings DO NOT come with salary information (as you will see in this exercise), being to able extrapolate or predict the expected salaries from other listings can help guide negotiations.
Normally, we could use regression for this task; however, we will convert this problem into classification and use a random forest classifier, as well as another classifier of your choice; either logistic regression, SVM, or KNN.
Question: Why would we want this to be a classification problem?
Answer: While more precision may be better, there is a fair amount of natural variance in job salaries - predicting a range be may be useful.
Therefore, the first part of the assignment will be focused on scraping Indeed.com. In the second, we'll focus on using listings with salary information to build a model and predict additional salaries.
Scraping job listings from Indeed.com
We will be scraping job listings from Indeed.com using BeautifulSoup. Luckily, Indeed.com is a simple text page where we can easily find relevant entries.
First, look at the source of an Indeed.com page: (http://www.indeed.com/jobs?q=data+scientist+%2420%2C000&l=New+York&start=10")
Notice, each job listing is underneath a div tag with a class name of result. We can use BeautifulSoup to extract those.
Set up a request (using requests) to the URL below. Use BeautifulSoup to parse the page and extract all results (HINT: Look for div tags with class name result)
The URL here has many query parameters
q for the job search
This is followed by "+20,000" to return results with salaries (or expected salaries >$20,000)
l for a location
start for what result number to start on
