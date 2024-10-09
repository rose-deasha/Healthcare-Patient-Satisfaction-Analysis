<h1>Healthcare Patient Satisfaction Analysis</h1>

<h2>Overview</h2>
<p>This project analyzes patient satisfaction data from various healthcare facilities across the United States using HCAHPS (Hospital Consumer Assessment of Healthcare Providers and Systems) scores. The data is visualized through an interactive dashboard, displaying hospital ratings and comparisons of various factors such as communication with nurses, patient survey star ratings, and survey response rates.</p>

<p>The project also attempts to apply linear regression to understand relationships between different HCAHPS measures and overall patient satisfaction but encountered challenges due to data limitations.</p>

<h2>Features</h2>
<ul>
  <li><strong>Interactive Map of Hospital Ratings</strong>: A choropleth map displays hospital ratings by state, allowing users to see which areas have the highest-rated facilities based on HCAHPS Linear Mean Values.</li>
  <li><strong>Interactive Scatter Plot</strong>: This scatter plot visualizes the relationship between communication with nurses and overall hospital satisfaction, enabling exploration of how specific measures impact patient perceptions.</li>
  <li><strong>Top-Performing Hospitals</strong>: The top hospitals by HCAHPS Linear Mean Value are highlighted, providing insight into facilities with the best patient feedback.</li>
  <li><strong>Linear Regression Analysis</strong>: Attempts were made to apply linear regression to predict hospital satisfaction ratings, but the results were inconclusive due to data quality issues (see details below).</li>
</ul>

<h2>Code Summary</h2>
<h3>Data Cleaning and Preparation</h3>
<ul>
  <li><strong>Data Import and Cleanup</strong>: The dataset is cleaned by removing rows with missing values in key columns such as <code>HCAHPS Linear Mean Value</code> and <code>HCAHPS Answer Percent</code>.</li>
  <li><strong>Aggregation</strong>: Hospitals are aggregated by <code>Facility Name</code> to ensure that multiple records from the same hospital are summarized together.</li>
</ul>

<h3>Visualization</h3>
<ol>
  <li><strong>Choropleth Map</strong>: Displays HCAHPS Linear Mean Value across the U.S., allowing users to hover over hospitals to see their details such as facility name and state.</li>
  <li><strong>Scatter Plot</strong>: Displays the correlation between communication scores and overall patient satisfaction using the <code>HCAHPS Answer Percent</code> and <code>HCAHPS Linear Mean Value</code> columns.</li>
</ol>

<h3>Analysis Tool</h3>
<ul>
  <li><strong>Hospital Information Lookup</strong>: A custom function allows users to input a hospital number to retrieve detailed information, such as the hospital's address, rating, number of surveys completed, and survey response rate. Footnotes provide further context on the ratings and results, helping users draw conclusions.</li>
</ul>

<h2>Linear Regression Challenges</h2>

<h3>Objective:</h3>
<p>The goal was to fit a linear regression model to predict the <code>HCAHPS Linear Mean Value</code> based on various factors like <code>HCAHPS Answer Percent</code>, <code>Survey Response Rate Percent</code>, and other patient satisfaction metrics.</p>

<h3>Issues Encountered:</h3>
<ol>
  <li><strong>Data Inconsistency</strong>: Many of the key columns, such as <code>HCAHPS Linear Mean Value</code> and <code>HCAHPS Answer Percent</code>, contained a large number of missing or non-numeric values (e.g., <code>'Not Applicable'</code>). Even after cleaning the dataset by converting or removing non-numeric values, the dataset became significantly smaller.</li>
  <li><strong>Insufficient Data for Training</strong>: After cleaning, the number of valid samples that could be used to train the model was very small. Linear regression models rely on a sufficiently large dataset to accurately predict relationships between variables. With too few data points, the model cannot generalize well or find meaningful patterns.</li>
  <li><strong>Low Variability</strong>: The data that remained after cleaning showed very little variability in certain columns. For instance, many hospitals had very similar <code>HCAHPS Linear Mean Value</code> scores and <code>HCAHPS Answer Percent</code> values, which limited the potential for the model to differentiate between different hospitals or accurately predict outcomes.</li>
  <li><strong>Collinearity Issues</strong>: There was potential for multicollinearity in the dataset, where some predictor variables were highly correlated with each other. For example, the survey response rate might be related to other patient satisfaction metrics, making it difficult for the model to isolate the individual effects of each predictor.</li>
</ol>

<h3>Conclusion:</h3>
<p>Due to the large amount of missing data, low variability in key columns, and potential multicollinearity, the linear regression model was not able to find meaningful patterns or fit the data well. In future work, additional data preprocessing, collection of more diverse samples, or the use of more advanced models (such as regularized regression or machine learning algorithms) might help improve predictive accuracy.</p>

<p>This analysis highlights the importance of having high-quality, complete data when building statistical models and emphasizes the need for careful data preprocessing and cleaning.</p>

<h2>How to Use</h2>
<ol>
  <li>Run the code in a Jupyter Notebook or Python environment.</li>
  <li>Follow prompts to input a hospital number to retrieve detailed analysis or explore the interactive visualizations.</li>
  <li>Use the map and scatter plot to visually analyze trends in patient satisfaction scores across the U.S.</li>
</ol>

<h2>Libraries Used</h2>
<ul>
  <li><strong>Pandas</strong>: For data manipulation and cleaning.</li>
  <li><strong>Plotly Express</strong>: For creating interactive visualizations like the choropleth map and scatter plot.</li>
  <li><strong>Scikit-Learn</strong>: Used for regression modeling.</li>
  <li><strong>NumPy</strong>: For numerical operations and handling arrays.</li>
  <li><strong>Matplotlib</strong>: Used for visualizing data and creating static plots.</li>
  <li><strong>Seaborn</strong>: Used for creating enhanced, aesthetically pleasing statistical plots.</li>
</ul>

<h2>Future Improvements</h2>
<ul>
  <li><strong>Additional Metrics</strong>: Incorporate more HCAHPS measures or external data sources to create a more comprehensive view of hospital performance.</li>
  <li><strong>Advanced Machine Learning Models</strong>: Implement regression or clustering algorithms to further explore relationships in the data.</li>
</ul>

<h2>Requirements</h2>
<ul>
  <li>Python 3.x</li>
  <li>Pandas</li>
  <li>Plotly</li>
  <li>Scikit-learn</li>
  <li>NumPy</li>
  <li>Matplotlib</li>
  <li>Seaborn</li>
</ul>

<h2>How to Run</h2>
<ol>
  <li>Clone the repository or download the juypter notebook.</li>
  <li> Download data from: https://data.cms.gov/provider-data/dataset/dgck-syfz#data-table </li>
  <li>Install the required dependencies using:
    <pre><code>pip install -r requirements.txt</code></pre>
  </li>
  <li>Run the notebook or script to explore the data and visualize hospital performance across the United States.</li>
</ol>
