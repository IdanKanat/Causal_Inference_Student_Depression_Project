# Applied Introduction to Causal Inference - Project - Estimation of Causal Effects of High Academic Pressure on Depression among Students
This project applies causal inference methods to estimate the effect of high academic pressure on student depression. It was part of a *Causal Inference* course at Tel Aviv University (2025), during the 3rd year of our Data Science studies. As a team of 3, we combined DAG-based confounder selection, multiple causal estimators, and heterogeneity analysis to evaluate treatment effects.

The dataset is **synthetic** (27,901 students) and was provided as part of the coursework. While it may not reflect all real-world complexities, it allows us to demonstrate causal methodology in practice.

---

### Methodology

We structured our analysis around core causal inference assumptions (exchangeability, positivity, consistency), guided by a Directed Acyclic Graph (DAG). The analysis included:

- **Confounder selection via DAG** (minimal backdoor sets).  
- **Positivity checks** (empirical overlap, strata violations).  
- **Propensity Score estimation**: multiple logistic regression models (age & CGPA continuous vs. quartiles).  
- **ATE Estimation**:  
  - *Naïve comparison*  
  - *Standardization* (logistic regression outcome models, bootstrapped SEs & CIs)  
  - *IPTW with stabilized weights*  
- **CATE Estimation**:  
  - Meta-learners (S- and T-learners)  
  - Base learners: Logistic Regression & Random Forest (500 trees via Ranger)  
  - Effect modifiers: age, CGPA, study field, financial stress  

---

### Key Results

- **ATE:** All causal estimators consistently estimated an increase in depression risk of ~0.35–0.40 under high academic pressure. Naïve estimates were upward-biased (~0.39).  
- **Statistical Significance:** All 95% confidence intervals excluded 0, indicating robust evidence of a causal effect.  
- **Heterogeneity (CATE):** Most modifiers showed homogeneous effects (~0.32), with stronger heterogeneity by **age quartile** (older students more affected), **study field**, and **financial stress**.  

---

### Deliverables

- **Code:** End-to-end R scripts implementing the causal pipeline.  
- **Figures:** Positivity checks, PS distributions, ATE & CATE visualizations.  
- **Final Report (PDF):** [Link here once uploaded].  

---

### Notes

- Dataset is **synthetic** and used for demonstration purposes only.  
- Methodology is directly generalizable to real-world educational or psychological data.  

The full implementation details can be found in the [Final Report (PDF)](https://github.com/IdanKanat/Causal_Inference_Student_Depression_Project/blob/14b17fa9613ad7ab15d49402e3853a60157d9aa6/Intro%20to%20Causal%20Inference%20%E2%80%93%20Project%20Report%20%E2%80%93%20%20Student%20Depression%20Dataset%20-%20Idan%2C%20Yonatan%20%26%20Tomer%20-%204.9.2025.pdf)
![_](https://github.com/IdanKanat/Causal_Inference_Student_Depression_Project/blob/67fb3fdd3475c7a460a87c98b0711f5939104078/IntroCausalInferenceProject_ThemePic_StudentDepression.png)
