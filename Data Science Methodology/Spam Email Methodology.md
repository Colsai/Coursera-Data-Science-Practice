# Part I: Problem Overview  
For this project, the topic that I chose was email. A major, and obvious problem of email is the problem of spam email, or bulk-sent email. 
According to Statista.com’s tracking of global spam email, a range of between 48.16% to as high as 71.1% of all global email was spam between the months of January 2014 to September 2019. (See: https://www.statista.com/statistics/420391/spam-email-traffic-share/)
For companies and businesses, spam email can be an obtrusive, and occasionally dangerous problem. Spywear, Phising, and Ransomware attacks can tie up businesses. The industry itself is a multibillion dollar one, so until proper solutions are created, we will continue to fight the change of spam email.  

# PART II: Problem
## 1. Describe the problem, related to the topic you selected. 
Recently, employees at company ‘XYZ’ have unknowingly been receiving spam emails. While most of the company employees do not click on the spam messages they receive, a small percentage of the company have, and it has been causing problems.
Company ‘XYZ’ fears that it is only a matter of time before employees accidentally click on Emails with viruses, spywear, or ransomware that could compromise data and would be very costly to fix.
Thus, company ‘XYZ’ asks the question of how to additionally filter for spam by using patterns of data from previous spam emails. At the same time, they do not want to create a filter in which important external stakeholders are considered as ‘spam’ email.
The problem is balancing how to better filter out email so that email providers can eliminate them before reaching the sender while at the same time not going so far as to filtering out any potential emails that are not spam. 

## 2. Phrase the problem as a question to be answered using data. 
“Can we automatically determine if an email is spam or not based on the contents of the email (sender, title, header, content ie keywords, etc.)?”  

# PART III: Approach
## 1. Analytic Approach
The first step would be to create a decision tree to decide an algorithm for how to decide what might be a spam email, and what might not be a spam email (which would require tuning, etc.).

In a broad outline, I would attempt to classify different emails in a decision tree as spam or spam based on: external or internal sender (internal = not spam), if external, check content keywords. If Content keywords related to business XYZ, then I would consider as “not spam”, and if they were NOT related to our business, “spam”.

## 2. Data Requirements
First, with the business problem that company ‘XYZ’ gave me, they suggested that there had been an upswing in recent spam emails, so I would look to set a time frame for email collection within the past half-year.

The data requirements that I would be looking for would be:
Address of Sender
Content (keywords) of Message

## 3. Data Collection
Having collected the list of emails and using sender address and content, I would move to the data collection stage. From company XYZ, I would receive all the data addresses and content of the emails sent, after going through a text parser to remove unimportant words and phrases (“the”, “and, “but”, etc.), collecting all of the content words as data for each email.

Then, using R or Python, I would play around with the data to look through what I saw from content keywords, etc. in order to:
understand its content,
assess its quality,
discover any interesting preliminary insights, and,
determine whether additional data is necessary to fill any gaps in the data.
(DS0103EN-2-2-10)

As a note, just thinking about my tree diagram, I think that I would probably find a fair number of emails that did not fall under the category of ‘spam’, yet did not contain any of the parameters that I had set.

Additionally, there may be issues with the company providing sensitive emails and information, which we could make a decision about inclusion or exclusion.

## 4. Data Understanding and Preparation
In the first step, data understanding, I would create a list of the most common content words from the emails, and see how they matched up with a list of XYZ-related business words.

In the next step, data preparation, I would prepare my data. I would first check column names, and then check and change my list of text-cleaned keywords from the emails, by setting all words to lower-case so they would be interpreted correctly.

I would also look to check for common misspellings of some of the most frequent keywords, and correct them in order to prepare the data for the model.

## 5. Modeling and Evaluation
For the modeling step, I would use the decision tree diagram I had that separated spam email from real email. This would be done using a predictive model, as it is intended to identify and classify future spam email. I would also tweak my model to balance relative cost (ie how much worse is a Type 1 error (False Positive- IS considered SPAM when it ISN’T) vs a Type 2 error (ISN’T considered SPAM when it IS)

For evaluation, I would randomly create a set of 100 emails as a testing set, and create a confusion matrix to see how many mistakenly classified emails did not fit my model. Thus, I would be able to evaluate how well successful my model was.
