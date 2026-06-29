# Causal Effects of Irrigation Type on Crop Yield: A Double/Debiased Machine Learning Analysis Using IoT Sensor Data from 500 Smart Farms

## Repository Link

(https://github.com/Waseem-abbas512/CausalML-CropYield-Sustainability.git)

## Description

The objective of this study is to detect heterogeneous treatment effects across various farm variables while estimating the causal effect of drip irrigation on crop yield. We use Double/Debiased Machine Learning (DML) with Causal Forest to estimate both average and heterogeneous treatment effects while controlling for confounding variables (soil qualities, region, crop type, and disease status) using the Smart Farming Sensor Dataset (500 farms, 22 attributes). A baseline Random Forest model for yield prediction is also included in the research, which serves as a benchmark for comparison and highlights the value of causal techniques over solely predictive ones in agricultural policy targeting.

### Task Type

The primary task is regression (predicting continuous crop yield in tons/hectare), but the project's core objective is causal effect estimation—specifically, estimating the Average Treatment Effect (ATE) and Conditional Average Treatment Effects (CATE) of drip irrigation on yield using Double/Debiased Machine Learning.

### Results Summary

#### Best Model Performance
- **Best Model:** Causal Forest (DML)
- **Evaluation Metric:** 	ATE (Average Treatment Effect)
- **Final Performance:** 0.0334 tons/ha (95% CI: [-0.045, 0.112])

#### Model Comparison
- **Baseline Performance:**
- Baseline (Random Forest)	R² = 0.68, RMSE = 1.12 tons/ha
- Naive Estimate	+1.72 tons/ha
- Causal Forest (DML)	ATE = 0.0334 tons/ha
- The naive comparison suggested drip farms yield 1.72 tons/ha more, but after controlling for confounders, the causal effect falls to near zero—demonstrating that the raw correlation was entirely driven by confounding (wealthier farms with better soil were both adopting drip AND producing higher yields).


#### Key Insights
- **Most Important Features:**
1)	NDVI Index (Crop Health)
2)	Temperature
3)	Rainfall
4)	Soil Moisture
5)	Soil pH
These features drive the heterogeneity in treatment effects—meaning they help explain WHY some farms benefit from drip irrigation while others are harmed.
- **Model Strengths:**
1) Unbiased Causal Estimates	(DML successfully removes confounding bias, providing accurate ATE)
2) Heterogeneity Detection	(Causal Forest identifies which farms benefit (CATE range: -0.38 to +0.41 tons/ha))
3) Interpretability	(Feature importance reveals what drives effect heterogeneity)
4) Practical Insights	(Reveals that 32% of farms benefit, 28% are harmed, 40% see no change)
5) Policy-Relevant	(Demonstrates that universal subsidies are inefficient; targeting is essential)
- **Model Limitations:**
1) No Strong Predictors Found as correlation matrix shows no variable strongly predicts yield or effect therefore we cannot easily identify which farms will benefit using simple rules
2) Unobserved Confounders	(Unmeasured factors (management quality, weather shocks) may still bias estimates)-ATE may still be biased if key confounders are missing
3) Dataset is simulated, not real-world experimental data	Results may not generalize to actual farming conditions
4) Data is from one crop cycle (single season), not panel/longitudinal which cannot assess long-term effects or year-to-year variation
5) Small Sample Size	(500 farms is moderate for causal ML methods-CATE estimates may lack precision for small subgroups
- **Business Impact:**
1) Policy Targeting	(Universal subsidies are NOT recommended; targeted approach can achieve 165% of gains with 25% of investment)
2) Water Conservation (Targeted drip irrigation could save 40% of irrigation water while maintaining yield gains)
3) Resource Efficiency (Avoid wasting subsidies on farms where drip is ineffective or harmful)
4) Economic Impact (Uniform adoption: $5K gain; Targeted adoption: $8K gain (at $500/ton))
5) Risk Mitigation	(Identifying harmed farms (28%) prevents yield losses and wasted investment)
6) Sustainability	(Drip irrigation still offers water savings (30-50%) even without yield gains)

## Documentation

1. **[Literature Review](0_LiteratureReview/README.md)**
2. **[Dataset Characteristics](1_DatasetCharacteristics/exploratory_data_analysis.ipynb)**
3. **[Baseline Model](2_BaselineModel/baseline_model.ipynb)**
4. **[Model Definition and Evaluation](3_Model/model_definition_evaluation)**
5. **[Presentation](4_Presentation/README.md)**

## Cover Image

![Project Cover Image](<<img width="1356" height="838" alt="cover_causal_ml" src="https://github.com/user-attachments/assets/f7a3ccaa-a70b-4867-a76d-44eaea134cc5" />
)
