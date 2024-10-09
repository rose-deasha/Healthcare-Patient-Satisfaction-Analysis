<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>
<head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
  <meta http-equiv="Content-Style-Type" content="text/css">
  <title></title>
  <meta name="Generator" content="Cocoa HTML Writer">
  <meta name="CocoaVersion" content="2566">
  <style type="text/css">
    p.p1 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px Helvetica}
    p.p2 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px Helvetica; min-height: 14.0px}
  </style>
</head>
<body>
<p class="p1"># Healthcare Patient Satisfaction Analysis</p>
<p class="p2"><br></p>
<p class="p1">## Overview</p>
<p class="p1">This project analyzes patient satisfaction data from various healthcare facilities across the United States using HCAHPS (Hospital Consumer Assessment of Healthcare Providers and Systems) scores. The data is visualized through an interactive dashboard, displaying hospital ratings and comparisons of various factors such as communication with nurses, patient survey star ratings, and survey response rates.</p>
<p class="p2"><br></p>
<p class="p1">The project also attempts to apply linear regression to understand relationships between different HCAHPS measures and overall patient satisfaction but encountered challenges due to data limitations.</p>
<p class="p2"><br></p>
<p class="p1">## Features</p>
<p class="p1">- **Interactive Map of Hospital Ratings**: A choropleth map displays hospital ratings by state, allowing users to see which areas have the highest-rated facilities based on HCAHPS Linear Mean Values.</p>
<p class="p1">- **Interactive Scatter Plot**: This scatter plot visualizes the relationship between communication with nurses and overall hospital satisfaction, enabling exploration of how specific measures impact patient perceptions.</p>
<p class="p1">- **Top-Performing Hospitals**: The top hospitals by HCAHPS Linear Mean Value are highlighted, providing insight into facilities with the best patient feedback.</p>
<p class="p1">- **Linear Regression Analysis**: Attempts were made to apply linear regression to predict hospital satisfaction ratings, but the results were inconclusive due to data quality issues (see details below).</p>
<p class="p2"><br></p>
<p class="p1">## Code Summary</p>
<p class="p1">### Data Cleaning and Preparation</p>
<p class="p1">- **Data Import and Cleanup**: The dataset is cleaned by removing rows with missing values in key columns such as `HCAHPS Linear Mean Value` and `HCAHPS Answer Percent`.</p>
<p class="p1">- **Aggregation**: Hospitals are aggregated by `Facility Name` to ensure that multiple records from the same hospital are summarized together.</p>
<p class="p2"><br></p>
<p class="p1">### Visualization</p>
<p class="p1">1. **Choropleth Map**: Displays HCAHPS Linear Mean Value across the U.S., allowing users to hover over hospitals to see their details such as facility name and state.</p>
<p class="p2"><span class="Apple-converted-space">   </span></p>
<p class="p1">2. **Scatter Plot**: Displays the correlation between communication scores and overall patient satisfaction using the `HCAHPS Answer Percent` and `HCAHPS Linear Mean Value` columns.</p>
<p class="p2"><br></p>
<p class="p1">### Analysis Tool</p>
<p class="p1">- **Hospital Information Lookup**: A custom function allows users to input a hospital number to retrieve detailed information, such as the hospital's address, rating, number of surveys completed, and survey response rate. Footnotes provide further context on the ratings and results, helping users draw conclusions.</p>
<p class="p2"><br></p>
<p class="p1">## Linear Regression Challenges</p>
<p class="p2"><br></p>
<p class="p1">### Objective:</p>
<p class="p1">The goal was to fit a linear regression model to predict the `HCAHPS Linear Mean Value` based on various factors like `HCAHPS Answer Percent`, `Survey Response Rate Percent`, and other patient satisfaction metrics.</p>
<p class="p2"><br></p>
<p class="p1">### Issues Encountered:</p>
<p class="p1">1. **Data Inconsistency**: Many of the key columns, such as `HCAHPS Linear Mean Value` and `HCAHPS Answer Percent`, contained a large number of missing or non-numeric values (e.g., `'Not Applicable'`). Even after cleaning the dataset by converting or removing non-numeric values, the dataset became significantly smaller.</p>
<p class="p2"><br></p>
<p class="p1">2. **Insufficient Data for Training**: After cleaning, the number of valid samples that could be used to train the model was very small. Linear regression models rely on a sufficiently large dataset to accurately predict relationships between variables. With too few data points, the model cannot generalize well or find meaningful patterns.</p>
<p class="p2"><br></p>
<p class="p1">3. **Low Variability**: The data that remained after cleaning showed very little variability in certain columns. For instance, many hospitals had very similar `HCAHPS Linear Mean Value` scores and `HCAHPS Answer Percent` values, which limited the potential for the model to differentiate between different hospitals or accurately predict outcomes.</p>
<p class="p2"><br></p>
<p class="p1">4. **Collinearity Issues**: There was potential for multicollinearity in the dataset, where some predictor variables were highly correlated with each other. For example, the survey response rate might be related to other patient satisfaction metrics, making it difficult for the model to isolate the individual effects of each predictor.</p>
<p class="p2"><br></p>
<p class="p1">### Conclusion:</p>
<p class="p1">Due to the large amount of missing data, low variability in key columns, and potential multicollinearity, the linear regression model was not able to find meaningful patterns or fit the data well. In future work, additional data preprocessing, collection of more diverse samples, or the use of more advanced models (such as regularized regression or machine learning algorithms) might help improve predictive accuracy.</p>
<p class="p2"><br></p>
<p class="p1">This analysis highlights the importance of having high-quality, complete data when building statistical models and emphasizes the need for careful data preprocessing and cleaning.</p>
<p class="p2"><br></p>
<p class="p1">## How to Use</p>
<p class="p1">1. Run the code in a Jupyter Notebook or Python environment.</p>
<p class="p1">2. Follow prompts to input a hospital number to retrieve detailed analysis or explore the interactive visualizations.</p>
<p class="p1">3. Use the map and scatter plot to visually analyze trends in patient satisfaction scores across the U.S.</p>
<p class="p2"><br></p>
<p class="p1">## Libraries Used</p>
<p class="p1">- **Pandas**: For data manipulation and cleaning.</p>
<p class="p1">- **Plotly Express**: For creating interactive visualizations like the choropleth map and scatter plot.</p>
<p class="p1">- **Scikit-Learn**: Used for regression modeling.</p>
<p class="p1">- **NumPy**: For numerical operations and handling arrays.</p>
<p class="p1">- **Matplotlib**: Used for visualizing data and creating static plots.</p>
<p class="p1">- **Seaborn**: Used for creating enhanced, aesthetically pleasing statistical plots.</p>
<p class="p2"><br></p>
<p class="p1">## Future Improvements</p>
<p class="p1">- **Additional Metrics**: Incorporate more HCAHPS measures or external data sources to create a more comprehensive view of hospital performance.</p>
<p class="p1">- **Advanced Machine Learning Models**: Implement regression or clustering algorithms to further explore relationships in the data.</p>
<p class="p2"><br></p>
<p class="p1">## Requirements</p>
<p class="p1">- Python 3.x</p>
<p class="p1">- Pandas</p>
<p class="p1">- Plotly</p>
<p class="p1">- Scikit-learn</p>
<p class="p1">- NumPy</p>
<p class="p1">- Matplotlib</p>
<p class="p1">- Seaborn</p>
<p class="p2"><br></p>
<p class="p1">## How to Run</p>
<p class="p1">1. Clone the repository or download the project files.</p>
<p class="p1">2. Install the required dependencies using:</p>
<p class="p1"><span class="Apple-converted-space">   </span>```</p>
<p class="p1"><span class="Apple-converted-space">   </span>pip install -r requirements.txt</p>
<p class="p1"><span class="Apple-converted-space">   </span>```</p>
<p class="p1">3. Run the notebook or script to explore the data and visualize hospital performance across the United States.</p>
<p class="p2"><br></p>
<p class="p1">For more information, please refer to the accompanying HTML documentation in the `Healthcare Patient Satisfaction Analysis.html` file.</p>
<p class="p2"><br></p>
<p class="p1">---</p>
</body>
</html>
