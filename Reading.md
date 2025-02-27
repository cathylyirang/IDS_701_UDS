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



## 2025//2/6 Lecture
- data science is about solving problems
- solve problems by answeringh questions
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

