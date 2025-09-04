# Applied Introduction to Causal Inference - Project - Estimation of Causal Effects of High Academic Pressure on Depression among Students
This project applies causal inference methods to estimate the effect of high academic pressure on student depression. It has been a major part of a course we took - "Applied Introduction to Causal Inference" at Tel Aviv University department of Statistics (2025), during the 3rd year of our studies. As a team of 3, we designed a full causal analysis pipeline: specifying a DAG to identify confounders, estimating the Average Treatment Effect (ATE) with multiple estimation and modeling approaches, and examining heterogeneity of effects (CATE) across subgroups using various methods.

More specifically, we structured our analysis around core causal inference assumptions (conditional exchangeability, positivity, SUTVA), guided by a Directed Acyclic Graph (DAG). The analysis included:

- **Confounder selection via DAG** (minimal backdoor sets).  
- **Positivity checks** (empirical overlap, strata violations, etc.).  
- **Propensity Score estimation**: multiple logistic regression models. 
- **ATE Estimation**:  
  - *Naïve comparison*  
  - *Standardization* (logistic regression outcome models + bootstrapped SEs & CIs. Models are adjusted for confounding).  
  - *Inverse Probability of Treatment Weighting (IPTW) with Stabilized Weights (SW).* 
- **CATE Estimation**:  
  - Meta-learners *(S & T-learners)*.
  - Base learners for each meta-learner: Logistic Regression & Random Forest, each under different effect modifier specifications. 

Experimental results show that all causal estimators consistently estimated an increase in depression risk of ~0.35–0.4 under high academic pressure. Naïve estimate was upward-biased (~0.39). All 95% confidence intervals excluded 0, indicating robust evidence of a causal effect. Marked heterogeneity by age, where mean CATE grew by age quartiles across all model specifications.

The full implementation details can be found in the [Final Report (PDF)](https://github.com/IdanKanat/Causal_Inference_Student_Depression_Project/blob/14b17fa9613ad7ab15d49402e3853a60157d9aa6/Intro%20to%20Causal%20Inference%20%E2%80%93%20Project%20Report%20%E2%80%93%20%20Student%20Depression%20Dataset%20-%20Idan%2C%20Yonatan%20%26%20Tomer%20-%204.9.2025.pdf)


![_](https://github.com/IdanKanat/Causal_Inference_Student_Depression_Project/blob/67fb3fdd3475c7a460a87c98b0711f5939104078/IntroCausalInferenceProject_ThemePic_StudentDepression.png)
