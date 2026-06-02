# Literature Review

The intersection of causal inference and agricultural yield prediction represents an emerging paradigm shift from traditional predictive modeling. Prior approaches can be categorized into three generations:
1) Traditional Statistical Methods: For many years, yield forecasting was dominated by multivariate regression models, time-series analysis, and linear regression (Agiwal, P., & Gupta, R. (2024). Although these methods can be understood, they have trouble with the intricate, non-linear linkages seen in agricultural systems.
2) Predictive Machine Learning: Confounding bias prevents random forests, support vector machines, neural networks, and gradient boosting (XGBoost, LightGBM) from recovering causal linkages despite their superior yield prediction abilities ((Agiwal, P., & Gupta, R. (2024). Instead of identifying causation, these models find correlations.
3) Causal Machine Learning (Emerging): Causal Forests, Double/Debiased Machine Learning (DML), and similar techniques that combine the flexibility of ML with the capacity of causal inference to predict treatment effects while controlling for confounders (Sitokonstantinou et al., 2024).

The main drawback noted in the research is that traditional machine learning techniques used on observational farm data mainly concentrate on yield prediction and frequently fall short of recovering causal treatment responses because of confounding brought on by non-random adoption of agricultural methods. The following paragraphs are going to discuss summaries of some projects relevant to our study.
     
**Summary of Each Work**:

- **Source 1**: [Causal Machine Learning for Sustainable Agroecosystems]

  - **[(https://ar5iv.labs.arxiv.org/html/2408.13155)]()**
    
  - **Objective**: To propose a comprehensive framework for applying causal ML to agricultural systems, addressing the limitations of predictive ML in explaining causal mechanisms and evaluating intervention impacts.
    
  - **Methods**: The paper presents a structured workflow for causal ML in agriculture:
1) Defining causal questions (qualitative via causal discovery; quantitative via effect estimation)
2) Data collection from remote sensing, farm management systems, and observational studies
3) Making structural assumptions (causal sufficiency, graph specification)
4) Selecting appropriate methods (Double ML, Causal Forests, DR-Learner)
5) Estimating ATE (Average Treatment Effect) and CATE (Conditional Average Treatment Effect)

The authors distinguish between "ML for causality" (using ML to answer causal questions) and "causality for ML" (using causal knowledge to improve ML robustness).

  - **Outcomes**:  The framework enables:
    
1) Quantifying intervention impacts for evidence-based decision-making
2) Enhancing predictive model robustness through causal feature selection
3) Identifying heterogeneous treatment effects across different subpopulations
4) Moving from descriptive to prescriptive agricultural analytics
 
  - **Relation to the Project**: 
The theoretical framework for my project is provided by this paper, which validates the selection of Double/Debiased ML and Causal Forests as suitable techniques for estimating irrigation effects. The workflow closely resembles the structure of my project, defining treatment (drip irrigation), outcome (yield), confounders (soil, region, management), and effect modifiers (NDVI, weather variables). The paper's focus on CATE estimation for targeted policy recommendations is exactly in line with my project's objective of determining which farms gain the most from drip irrigation.

- **Source 2**: [Comparing XGBoost and Double Machine Learning for Predicting the Nitrogen Requirement of Rice]

  - **[[Link](https://doaj.org/article/da0104cf754849bc9ebc60ca57cb9700)]()**
  - **Objective**: To develop and evaluate a Causal Machine Learning framework for estimating heterogeneous nitrogen treatment effects under real commercial rice-farming conditions, comparing DML against conventional XGBoost.
  - **Methods**: Double Machine Learning (DML), Doubly Robust (DR) learner, Causal Forest model
  - **Outcomes**:
1) DML outperformed XGBoost in identifying field plots responsive to additional nitrogen
2) The causal framework successfully distinguished responsive from non-responsive zones
3) Integration with plant-status information (LNC) improved treatment effect estimation
4) The decision support system enables targeted nitrogen increases while avoiding overfertilization in non-responsive areas
   
  - **Relation to the Project**:
It is also relevant to my project as we have the same goal as Heterogeneous effect estimation for targeted recommendations. Also we have same validation approach Comparing causal ML against predictive ML.

- **Source 3**: [Effects of Sustainable Soil Fertility Management Practices on Maize Income in Rural Zambia]

  - **[Link](https://doi.org/10.1080/03031853.2025.2600300)**
  - **Objective**:
  To use double machine learning to calculate the effects of sustainable soil fertility management (SFM) techniques, such as animal manure, minimum tillage, and better fallows, on maize income per hectare in rural Zambia.
  - **Methods**:
Debiased/Double Machine Learning (DML) for ATE and ATT.
DML-causal mediation analysis to understand mechanisms (with maize yield as mediator)

  - **Outcomes**:
1) Improved fallows could raise maize income by 37% if adopted universally (ATE)
2) Minimum tillage: 21% higher income (ATE), 15% higher for actual adopters (ATT)
3) Animal manure: 20% higher potential (ATE) with lower realized benefits
4) Adopting at least one SFM practice: 30% average income increase

  - **Relation to the Project**:
It is relevant to my study as it uses Validation of DML in agricultural contexts with observational data. 

In nutshell, In order to evaluate the heterogeneous causal effects of drip irrigation on agricultural productivity utilizing IoT sensor data with NDVI as the principal effect modifier, no study has used Double/Debiased Machine Learning. Therefore, my project will fill this gap by methodologically replicating the DML + Causal forest approach validated in agriculture context. 

References:

1) Agiwal, P., & Gupta, R. (2024, November). Modern agriculture: a review of emerging crop yield prediction models using machine learning. In 2024 2nd International Conference on Advancements and Key Challenges in Green Energy and Computing (AKGEC) (pp. 1-6). IEEE.

2) Sitokonstantinou, V., Porras, E. D. S., Bautista, J. C., Piles, M., Athanasiadis, I., Kerner, H., ... & Camps-Valls, G. (2024). Causal machine learning for sustainable agroecosystems. arXiv preprint arXiv:2408.13155.
   
3) Iatrou, M., Mourelatos, S., & Karydas, C. (2026). Comparing XGBoost and Double Machine Learning for Predicting the Nitrogen Requirement of Rice. Remote Sensing, 18(3), 420. https://doi.org/10.3390/rs18030420

4) Ng'ombe, J., Chikopela, L., Kalinda, T. H., & Kuntashula, E. (2026). Effects of sustainable soil fertility management practices on maize income in rural Zambia: a double machine learning approach. Agrekon, 65(1), 137-156. https://doi.org/10.1080/03031853.2025.2600300
