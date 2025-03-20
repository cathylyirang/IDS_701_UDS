# Solving Problems by Answering Questions - reading

## Syllabus
1. Syllabus
    - Course description
        - Use real world data to answer questions
            - Experiments and A/B testing
            - Causal inference
        - Key to pass
            - Reading + exercise
        - Big ideas
            - Use data to answer - questions not just max AUC score
            - Choose to use proper tool
            - Reasoning rigorously about uncertainty and error
        - Prerequisite 
            - Inferential stat and stat modeling
            - Python and R


        - Assignment and grading
            - Participation 20%
            - Midterm 20%
            - Exercise 20% - drop lowest 
            - Reading reflection and quiz 20% - drop lowest 
            - Team project 20%
        Question: lecture video?
        - Solving problems
        Data science is about solving problems
        did you make your stakeholder’s life better by solving a problem they faced?
        Data scientists solve problems by answering questions, and the question you are asking determines what tool is appropriate.
        what question, if answered, would make it easier to solve this problem?
        Reasoning rigorously about uncertainty and errors is what differentiates good data scientists from great data scientists








## Chapter 1 Solving problems
1. Idea 1: Solving Problems
2. Idea 2: Solving Problems by Answering Questions
    - Exploratory Questions: Questions about patterns and structure in the world.
        - Help us to understand the problem space better and prioritizing subsequent efforts.
        - examples if the company wants to improve recruitment of high quality employees
            - How many job applications are you receiving when you post a job?
            - What share of your current job applicants are of high quality?
            - What share of employees you try to hire accept your offer?
            - What share of employees you do hire turn out to be successful employees?
    - Passive Prediction Questions: Questions about likely outcomes for individual observations or entities.
        - Useful for targeting individuals for additional attention or automating certain tasks.
    - Causal Questions: Questions about the consequences of actions or interventions being considered.
        - Useful for deciding on appropriate courses of action.

3. Idea 3: Being Thoughtful About Being Wrong


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

### 11.1 Fairness and Passive Prediction
- mistaks qty = qlt
- Risk Assessment models in the US criminal justice system
    - racial bias

- Do you think data scientist are in a privileged position to answer this type of question (decide what types of errors to minimize)?
    - stakeholder decides the situation
    - data scientist designs and adjusts the model
    
- questions
    - data imbalance
        - equal - not representing the true population composition
        - uneuqal - result leaning towards the majority
    - if we don't think race should be considered to make decisions
        - remove race to make prediction
        - add race for inference or research only
        
## Chapter 12 Passive Prediction Questions and External Validity
- overview
    - internal validity [已知模型的inference] measures how well a model captures meaningful variation in the data we already have
    - external validity [未知数据的prediction] measures how well our model is likely to perform when faced with new data.
        - only performs well in similar environment
- Extrapolation and Training Parameter Ranges
    - extrapolation -> prediction on untrained data
    - tested data Constitutes Extrapolation 
    - Extrapolation with Non-Tabular Data
    - Train-Test-Splits and External Validity

## Chapter 13 Interpretability and Passive Prediction
- “Stop Using Black Boxes” by Cynthia Rudin.
    - The author argues that high-stakes decisions (e.g., criminal justice, healthcare) require models that are directly interpretable rather than “black boxes” with posthoc explanations 1811.10154v3.
    - She notes that posthoc explanations can be misleading or incomplete, because they approximate a black box rather than reflect its true workings 1811.10154v3.
    - Many black box models, especially when trained on structured data, do not consistently outperform simpler, interpretable models; thus, the trade-off between interpretability and accuracy can be illusive 1811.10154v3.
    - The paper emphasizes that interpretable models can help identify data issues, expose bias, and are much easier to troubleshoot or audit, which is critical in settings where decisions can profoundly affect people’s lives 1811.10154v3.
    - Finally, the author highlights legal, ethical, and policy implications, suggesting that mandating interpretable methods for high-stakes scenarios could improve transparency and accountability in the deployment of machine learning systems 1811.10154v3.
- Who is Cynthia Rudin? A truly amazing scholar.
    - Pioneering “interpretable AI”: Cynthia Rudin has spent 15 years creating machine learning models that reveal how they work, especially for critical domains like criminal justice, healthcare, and energy reliability.
    - $1 million Squirrel AI Award: She became the second winner of this new AAAI prize, likened to a “Nobel Prize” for AI benefiting humanity, for her leadership in transparent, responsible AI.
    - Real-world impact:
        - Helped Con Edison predict which electrical manholes might explode.
        - Designed simple, point-based models for hospitals to predict post-stroke seizures.
        - Created algorithms (adopted by Cambridge Police and later NYPD) that spot whether a crime is part of a criminal pattern.
    - Rejecting black boxes: Rudin shows that interpretable models can match or exceed the accuracy of opaque “black box” algorithms, negating the argument that transparency comes at the expense of predictive power.
    - High-stakes examples:
        - She scrutinized COMPAS, a proprietary model used in bail/parole decisions, arguing that simpler, open models perform equally well without hiding their logic.
        - She advocates strongly against black box approaches in socially sensitive areas.
    - Academic perseverance: At first, her research struggled to find standard publication outlets—there were no established categories for her work. Now, interpretable ML has become a recognized and growing subfield.
    - Broad recognition:
        - Praised by the Cambridge Police Department for advancing crime analysis.
        - Mentors and colleagues (Ingrid Daubechies, Robert Schapire) credit Rudin’s independence, community-building, and focus on real-world problems.
        - She holds multiple appointments at Duke and is a Fellow of the American Statistical Association and the Institute of Mathematical Statistics.
    - Vision for AI: Rudin’s work and influence underscore that for high-stakes decisions, AI can—and should—be both accurate and transparent, ensuring trust and accountability.
- Using Black Boxes requires trusting the data too.
    - Increasing role of automation: Many aspects of the criminal justice system now use software—risk assessments, forensic analysis, parole decisions—raising fairness concerns when lives are on the line.
    - Proprietary “black box” software: Companies keep algorithms and source code secret to protect trade secrets, preventing defendants from scrutinizing how results are generated.
    - Real-life effects: Examples include Glenn Rodríguez’s parole being impacted by a COMPAS score he couldn’t fully contest, and Billy Ray Johnson’s life sentence hinging partly on DNA software (TrueAllele) whose source code was withheld.
    - Trade secrets vs. due process: Courts often uphold companies’ intellectual property interests over defendants’ right to examine evidence. This erodes defendants’ ability to challenge or understand the technology used against them.
    - Call for transparency: The article argues that protective orders can safeguard proprietary information while still allowing defense teams to scrutinize potentially flawed software, preserving fairness and constitutional rights.
    - Legal context: The Supreme Court’s potential hearing of Wisconsin v. Loomis could clarify whether sentencing based on secret risk-assessment algorithms violates due process, and legislatures may need to act if the Court does not.

## Chapter 14 
- Why Causal Questions Matter
    - They aim to predict the consequences of an action or intervention (e.g., giving a new drug, changing an app feature), rather than merely describing or predicting existing patterns.
    - Stakeholders often pose Causal Questions out of risk aversion: they want to know likely outcomes before rolling out an intervention at full scale.
- Relation to Exploratory & Predictive Work
    - Often arise after noticing a pattern from Exploratory or Passive Prediction work (e.g., “High blood pressure is linked to complications—what if we treat it?”).
    - These questions focus on active manipulation, whereas Exploratory or Passive Predictive Questions help identify “what is” without necessarily changing anything.
- Internal vs. External Validity
    - Internal validity: confidence that a study accurately measures the causal effect in the specific setting of the study (e.g., randomization done well, no hidden biases).
    - External validity: how well the study’s findings generalize to a different or broader context (e.g., real-world hospital population vs. a narrow trial population).
- Workflow to Answer Causal Questions
    1. Check existing evidence: look at previous research or similar experiments that might already answer your question.
    2. Evaluate study relevance: assess whether existing studies are both done well (internal validity) and apply to your stakeholder’s setting (external validity).
    3. Plan new study if needed, choosing between:
        - Experimental (RCTs, A/B tests): often stronger internal validity, but might be in artificial settings or small user groups.
        - Observational: uses real-world data where treatments aren’t assigned by the researcher, possibly stronger external validity but can be harder to ensure internal validity.
- Key Takeaway
    - Causal inference is challenging: partly conceptual (we can’t observe both “treatment” and “no treatment” simultaneously) and partly practical (decision-makers want answers before committing).
    - Both experiments and observational data can yield valid causal insights if assumptions are checked.

### 14.1 Answering causal Qs
- Causality via Counterfactuals
    - The course adopts the Neyman-Rubin Counterfactual Model, which says that “X causes Y” if Y would happen when X occurs and would not happen if X did not occur.
    - Practically, this means comparing two imaginary worlds—one where the treatment/action happens (X=1) and one where it does not (X=0)—but we can only ever observe one of these worlds at a time.
- Fundamental Problem of Causal Inference
    - We can never fully measure both the treatment and no-treatment outcomes for the same individual at the same time.
    - All causal inference methods revolve around approximating this unobservable “counterfactual” scenario in some way (e.g., randomized experiments, comparing pre/post treatment data, or observational data with careful assumptions).
- Distinction from Passive Prediction
    - Passive prediction cares about correlations that often persist over time (e.g., a “Check Engine” light correlates with future breakdown).
    - Causal questions ask what would happen if we changed something about the world (e.g., does removing a “Check Engine” light prevent breakdowns?).
    - Merely identifying a correlation is insufficient for determining outcomes under a new action or policy.
- Randomized Experiments
    - A common tool for approximating the counterfactual by randomly assigning who receives treatment vs. control.
    - Despite their advantages, they still rely on assumptions (true randomness, large sample sizes, representativeness) and may have limited external validity.
- Why Correlation ≠ Causation
    - The “Check Engine” example shows how correlated indicators (lights on/off) don’t necessarily cause the underlying problem; cutting the light wire won’t fix the engine.
    - Confounders (hidden differences between treated and untreated groups) can make raw comparisons misleading unless carefully addressed.
- Imperfect but Essential
    - Like detectives, data scientists gather evidence and make inferences about what probably happens under treatment.
    - we can never observe both potential outcomes for the same individual simultaneously but can apply systematic methods (randomized trials, matching methods, etc.) to approximate the missing scenario and reason about how valid our assumptions might be.

## Causal Questions: Potential Outcomes
### Potential Outcomes Framework
- Potential Outcomes Framework
    - Each individual has two potential outcomes: one if they receive the treatment (T=1) and one if they do not (T=0). You can only ever observe one of these outcomes in the real world, which is why causal effects can’t be measured directly on a single person.
- Average Treatment Effect (ATE)
    - The ATE is the mean difference between the potential outcomes for an entire population – effectively, “if everyone got the treatment vs. if no one got it.”
- Correlation vs. Causation
    - The observed difference in outcomes between those who actually receive treatment and those who do not is not automatically the ATE. When certain assumptions hold, the observed difference can estimate a causal effect, but these assumptions (like “no baseline differences” and “no differential response by subgroups”) are often hard to confirm.
- Baseline Differences and ATT
    - If treated and untreated groups differ in ways unrelated to the treatment (e.g., healthier people choose treatment), we have “baseline differences.” Then the observed difference captures both the treatment effect and whatever underlying differences exist between the groups.
    - Even if there are no baseline differences, the observed difference only directly measures the “Average Treatment Effect on the Treated” (ATT), not necessarily the population’s full ATE.
- Why It’s Hard
    - Key assumptions (no baseline differences, no differential responses) typically aren’t directly testable because they involve comparing hypothetical outcomes we don’t observe. Hence, domain knowledge and careful study design are essential for claiming true causality.

## 2 Running and Analyzing Experiments - an end-to-end example

Step-by-Step Explanation and Answer:
- The chapter provides an end-to-end example of designing, running, and analyzing a controlled experiment (A/B test) to evaluate the impact of adding a coupon code field on an e-commerce site’s revenue. Here’s a structured breakdown of the key concepts and steps:

1. Hypothesis Formation
    - Problem: Adding a coupon code field might distract users, reducing revenue.
    - Hypothesis: “Adding a coupon code field to the checkout page will degrade revenue-per-user for users who start the purchase process.”
    - Approach: Use a “painted door” (fake feature) to test two UI implementations (Treatment 1 and 2) against the Control (no coupon field).
2. Metric Selection
    - Primary Metric: Revenue-per-user normalized by users who started checkout (to reduce noise from unaffected users).
    - Why? Focusing on affected users increases sensitivity. Revenue-per-user (not total revenue) accounts for traffic allocation variability.
3. Statistical Foundations
    - Null Hypothesis (H₀): No difference in revenue between Control and Treatments.
    - Significance Threshold: p-value < 0.05 (95% confidence).
    - Practical Significance: A 1% revenue change is meaningful for business decisions.
    - Power Analysis: Aim for 80–90% power to detect the 1% change, requiring sufficient sample size.
4. Experiment Design
    - Randomization Unit: Users (common choice; alternatives in Chapter 14).
    - Target Population: All users starting checkout.
    - Sample Size & Duration:
        - Calculated via power analysis to detect 1% change.
        - Run for 1 week to capture day-of-week effects and avoid primacy/novelty biases.
        - Traffic split: 34% Control, 33% each Treatment.
5. Running the Experiment
    - Infrastructure: Ensure proper logging and variant assignment (Chapter 4 details).
    - Guardrail Metrics (Invariants):
        - Trust-related: Equal traffic splits, cache-hit rates.
        - Organizational: Latency (shouldn’t change due to UI tweak).
6. Data Analysis
    - Sanity Checks: Verify invariants to confirm experiment validity.
    - Results (Table 2.1):
        - Treatment 1: Revenue-per-user dropped 2.8% (p = 0.0003).
        - Treatment 2: Dropped 7.8% (p = 1.5e-23).
        - Both statistically and practically significant (confidence intervals exclude zero and exceed 1% threshold).
7. Decision-Making
    - Conclusion: Adding a coupon field reduces revenue. Decision: Do not launch.
    - Broader Context:
        - Costs: Implementing a full coupon system is expensive, and the experiment shows it would harm revenue.
        - Trade-offs: No conflicting metrics (e.g., engagement vs. revenue).
        - Risk: High downside (revenue loss) outweighs potential benefits.
8. General Decision Framework
    - Use Figure 2.4 to interpret results:
        1. Not Significant + Not Practical: Abandon/iterate.
        2. Significant + Practical: Launch.
        3. Significant but Not Practical: Avoid (costs > gains).
        4. Inconclusive (Wide CI): Re-run with more power.
        5. Practical but Not Significant: Re-test for confidence.
        6. Borderline Practical: Context-dependent (e.g., low cost → launch).
Key Takeaways
- Metric Precision: Focus on affected users (checkout starters) to reduce noise.
- Statistical vs. Practical Significance: Use p-values for confidence, but align thresholds with business impact.
- Guardrails: Ensure experiment integrity via invariants.
- Context Matters: Costs, risks, and trade-offs influence decisions beyond pure statistics.

## 3 Twyman’s Law and Experimentation Trustworthiness
1. Twyman’s Law:
    - Principle: Unusual or "interesting" data is often due to errors (e.g., logging issues, computational mistakes).
    - Application: Extreme results (positive/negative) should prompt skepticism and validation checks (e.g., sample ratio mismatch tests).
2. Common Statistical Misinterpretations:
    - p-value Misuse:
        - Myth: p-value = probability the Null hypothesis is true.
        - Reality: p-value = probability of observing data assuming the Null hypothesis is true.
    - Peeking at Results: Continuously checking p-values inflates false positives. Solutions: predefine experiment duration or use sequential testing.
    - Multiple Hypothesis Testing: Testing many metrics/segments increases false discoveries. Use False Discovery Rate (FDR) corrections.
    - Confidence Intervals (CI): Overlapping CIs ≠ no effect. Non-overlapping CIs imply significance.
3. Threats to Internal Validity:
    - SUTVA Violations: Units interfere (e.g., social networks, shared resources like CPU).
    - Survivorship Bias: Analyzing only "survivors" skews results (e.g., WWII bomber armor analysis).
    - Sample Ratio Mismatch (SRM):
        - Cause: Imbalanced variant allocation (e.g., redirects, bot filtering).
        - Example: MSN’s bot filter removed engaged Treatment users, reversing results.
    - Intention-to-Treat (ITT): Analyze users by initial assignment, not compliance (avoids selection bias).

4. Threats to External Validity:
    - Primacy Effects: Users adapt slowly to changes (e.g., initial dislike of website redesign).
    - Novelty Effects: Short-term engagement spikes (e.g., fake "busy operator" messaging).
    - Segment Differences:
        - Heterogeneous Treatment Effects: Treatment impacts vary by segments (e.g., browser compatibility issues).
        - Example: MSN’s iOS vs. Android click-tracking discrepancies.
    - Simpson’s Paradox: Aggregated data shows opposite trends of segmented data (e.g., conversion rates across days/markets).

5. Key Solutions & Practices:
    - Pre-experiment Checks: A/A tests, randomization integrity (e.g., cryptographic hashing).
    - Avoid Redirects: Use server-side logic to prevent SRM.
    - Segment Analysis: Check pre-experiment segments (e.g., countries, browsers) to avoid post-hoc bias.
    - Monitor Over Time: Plot metric trends to detect novelty/primacy decay.

- Quiz Focus: Understand Twyman’s Law, differentiate internal/external validity threats, interpret p-values/CIs correctly, recognize Simpson’s paradox, and apply real-world examples (e.g., MSN bot filtering, WWII survivorship bias).



### 3.1 threads of internal validity

General Definition
- Internal Validity: The extent to which an experiment accurately measures the causal relationship between treatment and outcome, without external confounding factors.
Threats to Internal Validity
1. Violations of SUTVA (Stable Unit Treatment Value Assumption)
    - Units (e.g., users) should not interfere with one another. (independence)
    - Common violations:
        - Social networks (spillover effects).
        - Communication tools (e.g., Skype calls).
        - Shared resources (e.g., memory leaks affecting both groups).
        - Two-sided marketplaces (e.g., pricing effects in auctions).
2. Survivorship Bias 幸存者偏差
    - Analyzing only those who remain in the study can lead to biased conclusions.
    - Example: WWII bomber armor—planes that didn’t return were ignored.
3. Intention-to-Treat (ITT) vs. Selection Bias
    - ITT accounts for all participants as assigned, regardless of actual participation. 首对齐
    - Selection bias occurs when only those who complete treatment are analyzed. 尾对齐
4. Sample Ratio Mismatch (SRM)
    - Occurs when the actual ratio of Control to Treatment deviates from the intended design.
    - Common causes:
        - Browser redirects causing user loss.
        - Bots handling redirects differently.
        - Asymmetric user behavior (e.g., bookmarking Treatment pages).
5. Residual or Carryover Effects of prior experiments or bugs can persist and affect new results.
    - Examples:
        - LinkedIn’s "People You May Know" feature carried over effects.
        - Cookies storing experiment-related information from previous runs.
6. Bad Hash Function for Randomization
    - Weak hashing can lead to imbalanced randomization.
    - Fix: Use cryptographic hash functions like MD5 or SpookyHash.
7. Triggering Impacted by Treatment
    - If treatment influences attributes used for segmentation, biases can occur.
    - Example: E-mail campaigns targeting "inactive users" may change user activity status.
8. Time-of-Day Effects
    - If one variant is sent at a different time than another, results can be biased.
    - Example: Control emails sent during work hours, Treatment emails after work.
9. Data Pipeline Issues
    - Changes in user behavior due to Treatment can affect how data is recorded.
    - Example: Higher engagement led to bot filtering, reversing observed effects.
- Key Takeaways for Experimentation
    - Always check for SRM before trusting results.
    - Use Intention-to-Treat (ITT) to avoid selection bias.
    - Ensure randomization integrity with strong hash functions.
    - Consider carryover effects from previous experiments.
    - Monitor for data pipeline issues that could skew results.



## 7 Metrics for Experimentation and the OEC
1. Metrics for Experimentation and the Overall Evaluation Criterion (OEC)
    - Measurement is critical: "Tell me how you measure me, and I will tell you how I will behave."
    - A good metric should measure output, not just activity. Example: Sales should be measured by orders, not calls.
2. Characteristics of Good Experimentation Metrics
    - Measurable: Some things (e.g., post-purchase satisfaction) are hard to measure.
    - Attributable: You need to link metric values to experiment variants (e.g., app crashes must be attributed to a specific version).
    - Sensitive and timely: Metrics should be able to detect meaningful changes in a reasonable timeframe.
3. Business Metrics vs. Experimentation Metrics
    - Business metrics (e.g., stock price) are often not suitable for experiments.
    - Experimentation metrics should be carefully chosen based on sensitivity, attribution, and measurability.
4. Combining Metrics into an Overall Evaluation Criterion (OEC)
    - Organizations often have multiple key metrics and need a way to balance tradeoffs.
    - Single-metric approaches (e.g., "One Metric That Matters") are often too simplistic.
    - Example: A pilot cannot rely on a single gauge; multiple factors must be monitored.
    - The OEC can be a weighted sum of normalized metrics.
5. Case Studies on OEC
    - Amazon Email System: Initial revenue-based OEC led to excessive emails → Annoyed users unsubscribed → Long-term revenue loss.
        - New OEC included "unsubscribe lifetime loss," drastically changing optimization strategies.
    - Bing’s Search Engine: A bug increased short-term revenue but degraded user experience.
        - Short-term gains (higher queries per user and ad clicks) conflicted with long-term business goals.
- Quiz Preparation Strategy
    - Focus on why good metrics matter and how they should be chosen.
    - Understand the trade-offs in designing an OEC.
    - Be able to explain real-world examples like Amazon and Bing.
    - Know the three key characteristics of a good experimentation metric (Measurable, Attributable, Sensitive).





## 19 A/A Test
- doing the same test as A/B test but the two arms are the same to validate the baseline
- Step-by-Step Explanation and Answer:
    - A/A tests are a critical tool for validating the integrity of an experimentation platform. Here's a structured breakdown of their purpose, execution, and implications:

1. Purpose of A/A Tests
    - Validation of Statistical Assumptions: Ensure that Type I error rates (false positives) are controlled (e.g., 5% of tests show significance by chance when there’s no effect).
    - Infrastructure Integrity: Detect biases in traffic allocation, logging, or infrastructure (e.g., caching, redirects, hardware).
    - Metric Reliability: Verify that metric calculations (e.g., variance, distributions) align with expectations under the null hypothesis.

2. How to Conduct A/A Tests
    - Split Traffic: Randomly assign users to two identical variants (e.g., 50% Control, 50% Treatment).
    - Run Multiple Iterations: Simulate hundreds or thousands of A/A tests (historical data replay can expedite this).
    - Analyze p-value Distribution:
        - Expected: Under the null hypothesis, p-values should follow a uniform distribution (e.g., 5% of p-values < 0.05).
        - Actual: Use histograms and statistical tests (e.g., Kolmogorov-Smirnov) to check uniformity.
    - Identify Anomalies:
        - Skewed Distributions: Indicate incorrect variance calculations (Example 1) or outliers (Example 2).
        - Spikes at Specific p-values: Suggest implementation biases (Example 3) or infrastructure issues (Example 5).

3. Key Examples and Lessons
    1. Mismatched Analysis vs. Randomization Units
        - Issue: Analyzing CTR by page views (unit) when randomizing by users violates independence.
        - Solution: Use the delta method or bootstrapping for correct variance estimation.
        - Takeaway: Ensure analysis units match randomization units to avoid inflated Type I errors.
    2. Early Stopping and Peeking
        - Issue: Repeated significance testing (peeking) inflates false positives.
        - Solution: Use sequential testing methods or adjust p-values for multiple comparisons.
        - Takeaway: Implement strict stopping rules to maintain statistical validity.

    3. Redirects and Technical Biases
        - Issue: Redirects introduce latency, bot anomalies, and bookmark contamination.
        - Solution: Avoid redirects or apply them symmetrically to both variants.
        - Takeaway: Technical implementation details (e.g., redirects, caching) must not differentially affect variants.

    4. Unequal Traffic Splits
        - Issue: Skewed splits (e.g., 10%/90%) bias shared resources (caches) or violate normality assumptions.
        - Solution: Test with balanced splits or account for unequal variance in analysis.
        - Takeaway: Validate traffic allocation strategies with A/A tests.

    5. Hardware/Environmental Differences
        - Issue: Subtle hardware differences (e.g., server performance) create detectable biases.
        - Solution: Ensure identical environments for Control and Treatment.
        - Takeaway: Control extraneous variables to isolate treatment effects.

4. When A/A Tests Fail: Troubleshooting
    - Non-Uniform p-values:
        - Skewed Distributions: Check for unit mismatches (Example 1) or outliers (Example 2). Apply robust variance estimation (delta method) or data capping.
        - Spikes at p ≈ 0.32: Indicates outliers dominating metrics. Investigate outlier sources or cap extreme values.
        - Discrete p-values: Caused by sparse data (e.g., rare events). Consider larger sample sizes or alternative metrics.
    - Continuous Monitoring: Run A/A tests alongside live experiments to catch regressions (e.g., new metrics, infrastructure changes).

5. Best Practices
    - Pre-Launch Validation: Run A/A tests before trusting the platform.
    - Regular Checks: Continuously monitor A/A tests to detect infrastructure/metric drift.
    - Data Storage: Retain raw data to replay historical tests and validate new methodologies.
    - Contextual Adjustments: For skewed metrics, use non-parametric tests or transformations (e.g., log, rank).

Conclusion
- A/A tests are the cornerstone of trustworthy experimentation. They expose flaws in statistical methods, infrastructure, and metric design, ensuring that subsequent A/B tests yield valid results. By rigorously applying A/A tests, organizations can avoid costly false discoveries and build confidence in their data-driven decisions.

## 22 Leakage and Interference between Variants
1. Key Concept:
    - SUTVA Violation: The Stable Unit Treatment Value Assumption (SUTVA) is violated when a unit’s behavior is influenced by other units’ variant assignments, leading to interference (spillover/leakage).
2. Types of Interference:
    - Direct Connections:
        - Social networks (e.g., Facebook messages, LinkedIn posts).
        - Communication tools (e.g., Skype calls between users in different variants).
    - Indirect Connections:
        - Shared resources (e.g., Airbnb inventory, Uber driver availability, ad campaign budgets).
        - Latent variables (e.g., CPU usage, sub-user units like pageviews affecting user behavior).
3. Consequences:
    - Biased experiment results (e.g., underestimated/overestimated Treatment effects).
    - Example: A Treatment improving ad clicks might drain a shared budget, inflating its perceived success.
4. Solutions to Address Interference:
    - Isolation Techniques:
        - Resource Splitting: Separate budgets/training data by variant.
        - Geo/Time-Based Randomization: Assign variants by region or time (e.g., daily flips).
        - Network-Cluster/Ego-Centric Randomization: Group users into clusters or focus on "ego-alter" relationships in social networks.
    - Edge-Level Analysis: Compare interactions (e.g., messages) between Treatment-Treatment vs. Treatment-Control users.
        - Rule-of-Thumb: Estimate ecosystem impact (e.g., downstream metrics like message replies).
5. Detection & Monitoring:
    - Use ramp phases (Chapter 15) to catch severe interference early.
    - Monitor metrics for anomalies (e.g., budget exhaustion, unexpected engagement drops).
- Quiz Focus: Understand SUTVA violations, real-world examples of direct/indirect interference, isolation strategies, and detection methods.

## Summary of Causal Questions, Experiments, and External Validity
1. Key Concepts:
    - Internal Validity: Experiments (e.g., RCTs, A/B tests) excel at isolating causal effects by controlling variables.
    - External Validity: Challenges arise in generalizing results beyond the experiment’s context due to time effects and scaling effects.
2. Time Effects:
    - Novelty Effects: Short-term engagement spikes because users interact with new features/products out of curiosity. Example: A website redesign initially boosts clicks, but interest fades.
    - Primacy Effects: Users resist changes initially but adapt over time. Example: Users dislike a new app layout temporarily, then adjust.
    - Risk: Short experiments may misrepresent long-term outcomes (overestimating novelty benefits or underestimating primacy adoption).
3. Scaling Effects:
    - General Equilibrium Effects: Small-scale experiments miss ecosystem-wide behavioral changes. Example:
        - Amazon sellers don’t adjust listings in a small test but would globally, altering market dynamics.
        - TikTok algorithm changes for 1% of users won’t influence creators, but a full rollout would shift content strategies.
    - Example: A healthcare experiment in India improved nurse attendance initially, but nurses later organized against fines, nullifying gains.

4. Key Takeaways:
    - Experiments prioritize internal validity but often sacrifice external validity.
    - Temporal and scaling biases can distort real-world outcomes.
    - Critical to consider long-term monitoring and broader ecosystem impacts when interpreting results.

- Quiz Focus: Understand the trade-offs between internal/external validity, define novelty/primacy effects, explain general equilibrium effects, and apply examples (e.g., Amazon, healthcare study).



## 2025//2/6 Lecture
- data science is about solving problems
- solve problems by answering questions
- errors and uncertainty
    - understand errors
    - understand differences among models
 

## 2025/02/27 Lecture
- Notation
    - $i \in \{1, 2, ... N\}$ ~ **individual**
    - $T \in \{0,1\}$ ~ yes or no
    - $Y$ ~ **estimated outcome** what the future customers' answer are yes or no
        - $Y_{i}^{T}$
            - $Y_{i}^{0}$ = **outcome where not treated**
            - $Y_{i}^{1}$ = **outcome where treated**
    - $D_i \in \{0,1\}$ = **actual treatment condition**

- Individual treatment effect
    - $\delta_{Mona} = Y_{Mona}^1 - Y_{Mona}^0$  **Fundamental problem of causal inference**

- ATE = Average treatment effect of population = $\frac{1}{N}\Sigma\delta_i$ = $\frac{1}{N}\Sigma(Y_i^1-Y_i^0)$ = $E(Y_i^1-Y_i^0)$

- well defined
    - $E(Y^1|D=1)$   <- and observable
    - $E(Y^0|D=1)$   <- but not observable
- ATE = $E(Y_i^1-Y_i^0)$ <- not abservable
- $\widehat{ATE}$ = $E(Y_i^1|D=1)-E(Y_i^0|D=0)$
- $\widehat{ATE}$ = $E(Y_i^1|D=1)-E(Y_i^0|D=0) + E(Y_i^0|D=1)-E(Y_i^0|D=1)$
- $\widehat{ATE}$ = $E(Y_i^1|D=1)-E(Y_i^0|D=1) + E(Y_i^0|D=1)-E(Y_i^0|D=0)$
- $\widehat{ATE}$ = $[E(Y_i^1|D=1)-E(Y_i^0|D=0)] + [E(Y_i^0|D=1)-E(Y_i^0|D=1)]$
- $\widehat{ATE}$ = $[ATT] + E(Y_i^0|D=1)-E(Y_i^0|D=1)$
- ATT = Average Treatment 
1. No baseline differences --> don't like gym so don't go
    - $E(Y_i^0|D=1)-E(Y_i^0|D=0) = 0$
    - if (1) exists, $\widehat{ATE}$ = ATT$ = treatment effect for D=1
    - if (1) exists, $\widehat{ATE}$ = $[E(Y_i^1|D=1)-E(Y_i^0|D=0)]$
    - $ATE = \lambda[E(Y_i^1|D=1)-E(Y_i^0|D=1)] +(1-\lambda)[E(Y_i^1|D=0)-E(Y_i^0|D=0)]$
2. No difference tretment effects: like gym so don't need to go
    - $E=(Y_i^1|D=1)-E(Y_i^0|D=1)=E(Y_i^1|D=0)-E(Y_i^0|D=1)$

|  | T=0 | T=1 |
|--|-----|-----|
| D=0 | (1) 30 |  (2)  |
| D=1 | (3) |  (4) 25 |

- observable if D = T --> (1)(4)
- non-observable if D != T --> (2)(3)

- No baseline differences = Same T regardless of D
- No difference tretment effects = 
- $\widehat{ATE} = -5 = 25-30 $ 
- $ATT = (4)-(3) = 5$

## 2025/03/04 Lecture
- Randomized controlled trial (RCT) == A/B test

- Given

|        | Tylenol | Pain | D |
|--------|---------|------|---|
|Fan     |   yes   |   5  | 0 |
| Cindy  | yes     |   5  | 0 |
| Nzarama| no      |   7  | 1 |
| Eric   | no      |   9  | 1 |



- Find numeric value of
    - $E(Y^1|D=1)$ = 
    - $E(Y^0|D=0)$
    - $E(Y^1|D=0)$
    - $E(Y^0|D=1)$
    - in box math, what would no baseline difference mean : for T=1 (D=1)-(D=0)=0
    - tell me a story for why we might see baseline differences?

- Notation
    -   T = treatment
        T = 0 = no action
        T = 1 = action
    -   D = observation
        D = 0 = not observed
        D = 1 = observed
    -   Y = Expected result
        - $E(Y^1|D=1)$ = treated with observed outcome
        - $E(Y^0|D=0)$ = not treated with no outcome
        - $E(Y^1|D=0)$ = n
        - $E(Y^0|D=1)$
    - No baseline difference
        - result varies with no action
    - No differential treatment effects
        - result is the same with or without action

|      | T=0 | T=1 | D |
|------|-----|-----|---|
| D=0  |     |   5 | 0 |
| D=1  |     |     |   |


## 2025/03/18 Lecture
- OEC: Overall Evaluation Criterion
    - Alignment with Business Goals
    - Sensitivity
    - Robustness
    - Interpretability

- multiple test

# Midterm topics
- explanatory questions
- causal questions
- another question
- internal validity
- external validity
- confusion matrix and related
- differential treatment effects
- baseline differences
- Fundamental problem of causal inference
- big three questions
    - Use data to answer - questions not just max AUC score
    - Choose to use proper tool
    - Reasoning rigorously about uncertainty and error
- AUC