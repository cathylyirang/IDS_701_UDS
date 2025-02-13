## Quiz: Intro Chapter
- **Big ideas**: What are the three Big Ideas of the book?
    - Data science is about solving problems.
    - Reasoning carefully about uncertainty and model errors is the skill that makes someone a great data scientist.
    - Data scientists solve problems by answering questions.
- **Accuracy**: Why isn't it meaningful to report the accuracy of a classification model without context?
    - These are all reasons accuracy is meaningless without context.
- In the view of the author (me) of the chapter you read, what is the main/most common purpose of Exploratory Questions?
    - To help improve your understanding of the problem space and thus better prioritize subsequent efforts.
- What is the difference between a Passive Prediction Question and a Causal Question?
    - A Causal Question is a question about how the world would be different if a certain action took place (usually an action that you or your stakeholder is thinking about undertaking). A Passive Prediction Question is a question about how things are likely to proceed if the status quo prevails.

## Quiz: Descriptive and Prescriptive Questions, Solving Problems
- **Accuracy**: Why isn't it meaningful to report the accuracy of a classification model without context?
    - These are all reasons accuracy is meaningless without context.
- **Big Ideas**: What are the three Big Ideas of the book?
    - Data science is about solving problems.
    - Reasoning carefully about uncertainty and model errors is the skill that makes someone a great data scientist.
    - Data scientists solve problems by answering questions.
- **Domain Expertise**: According to me, which of the following is an accurate statement about domain knowledge and stakeholders?
    - Application is what separates data science from pure math, statistics, and computer science. Stakeholders will almost always have more domain knowledge than the data scientist on a project, but ensuring the final deliverable is well-tailored to the application context is everyone's responsibility.
- **Prescriptive**: Which of the following is a Prescriptive Question about marijuana (also known, in various circles, as weed, pot, cannabis, ganja, Mary Jane, and of course, best of all, the Devil's Lettuce)?
    - Is it a good idea to legalize recreational marijuana?
- **Prescriptive**: Which of the following is true of Prescriptive Questions?
    - All of these are true.

## Quiz: Exploratory and Passive Prediction (2) and fairness
- **Aimovig**: According to the author of the reading (me!), what's wrong with advertisements reporting Aimovig "caused episodic migraine sufferers to experience 3-4 fewer days of migraines a month"?
    - 3-4 days was the average treatment effect, but almost no patient experienced that effect. For most patients, the effect of Aimovig is much less or much greater.
- **Teams**: Early in her career, Amy Edmundson was studying team effectiveness in a hospital Neonatal Intensive Care Unit (NICU). She collected data on both team dynamics and medical errors. She hypothesized that teams that appeared to collaborate more effectively would have lower rates of medical errors. When she looked at her data, however, she found the opposite was true — the data showed her measures of team effectiveness and medical errors were positively correlated (i.e., the more effective teams — by her measure — had more reported medical errors). **What did Edmundson eventually conclude was the reason for this result?**
    - Effective teams weren't actually committing more medical errors; they were just more likely to admit when errors occurred.
- **Passive Prediction**: What are the two most common business uses of models for answering Passive Prediction Questions?
    - Identifying individual entities for additional attention.
    - Automation.
- **Fairness**: In 2016, investigative journalists from ProPublica published a piece on the COMPAS risk assessment model based on data from Florida. They concluded that: "Black defendants were often predicted to be at a higher risk of recidivism than they actually were. Our analysis found that black defendants who did not recidivate [are newly arrested for committing a crime in the future] over a two-year period were nearly twice as likely to be misclassified as higher risk compared to their white counterparts (45 percent vs. 23 percent)." In other words, the false positive rate (the share of people not re-arrested predicted to be re-arrested) for Black defendants was higher than it was for White defendants. **Which following statement best captures the takeaway from the reading about this finding?**
    - While there are many issues with COMPAS, having a differential false positive rate is a defensible property of their model given they wanted their model to have equal Positive Predictive rates across Black and White defendants (the share predicted to be re-arrested that are re-arrested is the same for both Black and White defendants). It's impossible not to have racial differences in (a) Positive Predictive rates, (b) False Positive Rates, or (c) False Negative Rates given differences in arrest rates by race.

## Exploratory and Passive Prediction
- **EDA**: Which of the following is NOT one of the author's concerns about the term EDA?
    - The term's prevalence creates the impression students need to invest in really "getting to know their data" before fitting a model. Students should really just be focused on post-modeling diagnostics (e.g., residual plots) to catch errors.
- **Aimovig**: According to the author of the reading (me!), what's wrong with advertisements reporting Aimovig "caused episodic migraine sufferers to experience 3-4 fewer days of migraines a month"?
    - 3-4 days was the average treatment effect, but almost no patient experienced that effect. For most patients, the effect of Aimovig is much less or much greater.
- **Passive Prediction**: What are the two most common business uses of models for answering Passive Prediction Questions?
    - Automation.
    - Identifying individual entities for additional attention.
- **Accuracy**: Why isn't it meaningful to report the accuracy of a classification model without context?
    - These are all reasons accuracy is meaningless without context.