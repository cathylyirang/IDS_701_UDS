## Chapter 9 Using Passive Prediction Questions
- Exploratory Questions vs. Passive Prediction Questions
    - Exploratory Questions help understand problems and prioritize efforts but don’t solve stakeholder problems alone.
    - Passive Prediction Questions predict future or unknown outcomes for individual entities.
- Purpose of Passive Prediction Questions
    - Identify entities of interest (e.g., high-risk patients, high-value clients, machinery needing maintenance).
    - Automate classification or labeling tasks (e.g., mammogram reading, spam detection).
- How Passive Prediction Questions Work
    - Data scientists develop models that provide entity-specific predictions.
    - Answers are statistical outputs, not general insights.
    - Supervised machine learning and statistical prediction are commonly used.
- Types of Passive Prediction Questions 
    - Predicting future outcomes for individuals (e.g., will Patient A experience complications?).
    - Predicting what would happen under different circumstances (e.g., would a radiologist classify this mammogram as cancerous?).
- Exploratory vs. Passive Prediction Questions
    - Exploratory Questions: Understand patterns, focus on variable relationships, don’t require high predictive accuracy.
    - Passive Prediction Questions: Prioritize prediction accuracy over understanding causal factors, often use black-box models.
- The “Passive” in Passive Prediction
    - Distinction from Causal Questions: Passive Prediction identifies correlations for prediction, while Causal Questions investigate cause-effect relationships.
- Correlations are useful for prediction but don’t imply causation (e.g., high blood pressure correlates with surgical complications but might not cause them).

## Chapter 10 Passive Prediction, Internal Validity, and Alignment
- Internal Validity in Passive Prediction
    - Evaluating model validity goes beyond standard quantitative metrics.
    - Requires reflection on model alignment and biases before and after fitting.
- Alignment in Machine Learning Models
    - Models answer the question they were trained on, not necessarily the question we want them to answer.
    - Example: A mammogram-reading AI predicts what a radiologist would say, not whether cancer is present.
    - The gap between desired vs. actual model behavior is called the alignment problem.
- Large Language Models (LLMs) and Alignment
- LLMs predict the most likely next word based on internet text patterns.
    - They reinforce existing biases found in their training data.
    - Example: A coding assistant suggests code similar to what it has seen before, reinforcing existing practices rather than improving them.
- Bias in Machine Learning
    - Models trained on historical human decisions inherit societal biases.
    - Bias is not an implementation flaw; it results from faithfully replicating training data.
    - Example: Amazon’s hiring algorithm reinforced gender bias because it was trained on past hiring decisions.
    - Bias in ML is not an error but a systemic reflection of past human behavior.

## Chapter 11 The Right Way To Be Wrong
- Real-World Model Evaluation
    - Success in real-world data science is not just about maximizing standard metrics like AUC, Accuracy, or F1-score.
    - Understanding the types of mistakes a model makes is as important as minimizing them.
    - The balance between true positives, true negatives, false positives, and false negatives is problem-specific.
- Consequences of Model Errors
    - Some mistakes have far worse consequences than others (e.g., false negatives in cancer detection vs. false positives).
    - Choosing the right trade-off depends on the business or real-world impact.
- Pitfalls of Using Accuracy as a Metric
    - Accuracy is relative to alternative models; a 95% accuracy score is meaningless without context.
    - Imbalanced data can lead to misleading accuracy (e.g., always predicting the dominant class results in high accuracy but useless predictions).
    - Accuracy does not differentiate between false positives and false negatives.
- Limitations of AUC as a Metric
    - AUC provides a broad performance measure but doesn’t always reflect real-world needs.
    - Most models operate at a specific threshold, making AUC’s global averaging less relevant in practice.
    - AUC focuses on positive predictions but may ignore false negative and false positive trade-offs.
- Choosing the Right Metric for Model Evaluation
    - Identify the real-world impact of different types of errors.
    - Work with stakeholders to determine the relative costs of mistakes.
    - Optimize the model to minimize problem-specific costs, not just generic performance metrics.
- Handling Errors Beyond Classification Models
    - Regression models also embed assumptions about how errors are weighted.
    - Weighted linear regression allows for prioritizing more valuable observations.
    - Robust modeling techniques adjust error minimization to fit real-world needs.
- Key Takeaways
    - No metric alone defines model quality—context matters.
    - A model’s value is determined by its improvement over the best available alternative.
    - Balancing errors appropriately is essential for effective real-world deployment.

### 9.1 Fairness and Passive Prediction