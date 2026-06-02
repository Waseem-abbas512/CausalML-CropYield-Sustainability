# Dataset Characteristics

**[Notebook](exploratory_data_analysis.ipynb)**

## Dataset Information

### Dataset Source
- **Dataset Link:** https://www.kaggle.com/datasets/atharvasoundankar/smart-farming-sensor-data-for-yield-prediction/data
- 
### Dataset Characteristics
- **Number of Observations:** This dataset simulates real-world smart farming operations powered by IoT sensors and satellite data. It captures environmental and operational variables that affect crop yield across 500 farms located in regions like India, the USA, and Africa.
- **Number of Features:** The dataset contains 22 original features organized into logical groups for causal analysis.

### Target Variable/Label
- **Label Name:** [yield_tons_per_hecter. My outcome (Y) is a continuous yield variable - I will estimate average treatment effects (ATE) in tons/hectare]
- **Label Type:** [REGRESSION (Continuous numerical prediction)]
- **Label Description:** [Crop yield, which is measured in metric tons per hectare, is the quantity of agricultural produce harvested per unit of land area. This is the outcome variable (Y) that I wish to comprehend the causal impact of drip irrigation on in this project.
- Prediction Task: My causal machine learning project assesses the causal influence of treatment (drip irrigation) on yield while accounting for confounders so I will try to explore "How much does drip irrigation CAUSE yield to change?" rather "what will the yield be?", whereas classical machine learning would predict yield values based on attributes.]
- **Label Values:** [For classification: list of classes and their meanings. For regression: range of values. For other tasks: describe the label structure]
- **Label Distribution:** [Brief description of class balance for classification or value distribution for regression]

### Feature Description
1) farm_id (string/categorical): Unique identifier for each smart farm

Purpose: Farm-level clustering and random effects

2) sensor_id (string/categorical): IoT sensor device identifier

Purpose: Quality control and sensor calibration checks

3) timestamp (datetime): Random in-cycle data collection time

Purpose: Temporal data validation

4) sowing_date (datetime): Date when crop was planted

Purpose: Determines growing season and weather exposure

5) harvest_date (datetime): Date when crop was harvested

Purpose: Used with sowing_date to calculate total_days

6) total_days (integer, 60-240 days): Crop growth duration

Effect modifier: Longer duration may increase exposure to weather risks

7) region (categorical, 10-15 unique values): Geographic farming region

Values: "North India", "South USA", "East Africa", etc.

Purpose: Captures unobserved regional factors (policy, infrastructure, market access)

Use: Continuous spatial control variable

8) crop_type (categorical, 5 values): Type of crop cultivated

Values: Wheat, Rice, Maize, Cotton, Soybean

Distribution: Approximately balanced (15-25% each)

Role: Effect modifier (different crops respond differently to treatments)

9) irrigation_type (categorical, 4 values): Primary treatment variable

Values:

Drip (most efficient, targeted water delivery)

Sprinkler (overhead irrigation, moderate efficiency)

Manual (traditional, labor-intensive)

None (rain-fed only)

Binary conversion: irrigation_drip (1=Drip, 0=Other)

Role: Treatment variable for causal analysis

10) fertilizer_type (categorical, 3 values): Nutrient management approach

Values: Organic, Inorganic, Mixed

Role: Important confounder (affects both yield and irrigation choice)

11) crop_disease_status (categorical, 4 values, ordinal): Plant health condition

Values: None, Mild, Moderate, Severe

Role: Confounder/mediator (affects yield and may influence management decisions)

Note: Severe disease can reduce yield by 30-50%

12) soil_moisture_% (float, 0-100%): Water content in soil

Typical range: 15-75% for agricultural soils

Optimal: 40-60% for most crops

Role: Effect modifier (interacts with irrigation effectiveness)

13) soil_pH (float, 5.5-7.5): Soil acidity/alkalinity

Optimal range: 6.0-7.0 for most crops

Values <5.5: Acidic (requires amendment)

Values >7.5: Alkaline (nutrient lockout risk)

Role: Confounder (affects nutrient availability and yield)

14) temperature_C (float, 15-40°C): Average temperature during crop cycle

Role: Effect modifier (drip irrigation more beneficial in hot climates)

15) rainfall_mm (float, 50-300mm): Total rainfall during crop cycle

Role: Effect modifier (irrigation benefits decrease with higher rainfall)

Critical for water sustainability analysis

16) humidity_% (float, 30-90%): Average air humidity

Optimal: 40-70% for most crops

High humidity (>80%): Disease risk increases

Low humidity (<40%): Increased water demand

Role: Effect modifier (affects evapotranspiration rates)

17) sunlight_hours (float, 4-12 hours): Daily sunlight exposure

Critical for photosynthesis

Role: Effect modifier (affects water requirements and growth rate)

18) NDVI_index (float, 0.3-0.9): Normalized Difference Vegetation Index

Calculation: (NIR - Red) / (NIR + Red)

Interpretation:

0.3-0.5: Sparse vegetation, stressed crops

0.5-0.7: Moderate vegetation, healthy crops

0.7-0.9: Dense vegetation, very healthy crops

Role: Effect modifier & intermediate outcome (reflects crop health)

Key feature for understanding treatment mechanisms

19) pesticide_usage_ml (float, 0-500 ml/day): Daily pesticide application

Role: Confounder (affects yield and correlates with irrigation choice)

20) temp_rain_interaction (float): Temperature × Rainfall / 100

Captures combined weather stress

High temp + low rainfall = severe water stress

21) moisture_NDVI_interaction (float): Soil moisture × NDVI

Captures water-use efficiency

Higher values indicate better water-to-biomass conversion

22) soil_quality_index (float, 0-1.5): Composite soil health metric

Formula: (moisture/mean_moisture)×0.6 + (1 - |pH-6.5|/2)×0.4

Values >1: Above average soil quality

Values <0.7: Poor soil quality


**Example format:**
- **Feature 1 (feature_name):** [Description of what this feature represents, data type, and any relevant details]
- **Feature 2 (feature_name):** [Description of what this feature represents, data type, and any relevant details]
- **Feature Group (group_name):** [Description of a group of related features]

## Exploratory Data Analysis

The exploratory data analysis is conducted in the [exploratory_data_analysis.ipynb](exploratory_data_analysis.ipynb) notebook, which includes:

- Data loading and initial inspection
- Statistical summaries and distributions
- Missing value analysis
- Feature correlation analysis
- Data visualization and insights
- Data quality assessment
