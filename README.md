# Asteroid Data Exploration Project

## Milestone 1:
### Link To Colab:
<a target="_blank" href="https://colab.research.google.com/github/harshilxd/Asteroid-Feature-Prediction/blob/main/source/Exploring_Asteroid_Dataset.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

### Abstract:
In the study of objects within our solar system, there have been many attempts to classify groups of objects to help estimate their properties. However, the classical approach can miss the subtle correlations that machine learning techniques thrive on. This study aims to enhance the prediction of asteroid features using machine learning algorithms. We aim to utilize a dataset provided by Jet Propulsion Laboratory of California Institute of Technology, and apply various regression techniques to achieve higher accuracy and low error rates in feature prediction. The dataset comprises 31 features for 839,714 objects, including their names, semi-major axis, eccentricity, inclination, orbital period, diameter, and other orbital elements. Our project focuses on utilizing feature engineering, linear and polynomial regression models. Additionally, we aim to use clustering algorithms to attempt to classify asteroids. Our findings contribute to the growing intersection between machine learning and astronomy, providing robust tools for potential applications in space warning systems.

## Milestone 2:
### Overview
This project analyzes a dataset with 839,714 observations and 31 features. The analysis includes data cleaning, encoding, and visualization to understand correlations and distributions. 

### Data Description
The features in our data have been described below.:
<details>
  <summary>Click to view table containing details of data.</summary>
  <table>
    <tr>
      <th>Feature Name</th>
      <th>Description</th>
    </tr>
    <tr>
      <td>full_name</td>
      <td>Full Name of Body: Contains full unique name of the body.</td>
    </tr>
    <tr>
      <td>a</td>
      <td>Semi-Major Axis (Unit - au): The average distance between the object and the Sun, measured in astronomical units (au).</td>
    </tr>
    <tr>
      <td>e</td>
      <td>Eccentricity: Describes the shape of the object's orbit, with values ranging from 0 (circular) to close to 1 (highly elliptical).</td>
    </tr>
    <tr>
      <td>G</td>
      <td>Magnitude Slope Parameter: Factor in determining the brightness variation of the object, reflecting how its brightness changes with phase angle.</td>
    </tr>
    <tr>
      <td>i</td>
      <td>Inclination (Unit - deg): Angle of the object's orbital plane relative to the plane of the solar system, measured in degrees.</td>
    </tr>
    <tr>
      <td>om</td>
      <td>Longitude of the Ascending Node: Angle from the reference direction (usually the vernal equinox) to the point where the object's orbit crosses the plane of the solar system from South to North.</td>
    </tr>
    <tr>
      <td>w</td>
      <td>Argument of Perihelion: Angle between the ascending node and the point of closest approach to the Sun (perihelion).</td>
    </tr>
    <tr>
      <td>q</td>
      <td>Perihelion Distance (Unit - au): Shortest distance between the object and the Sun during its orbit, measured in astronomical units (au).</td>
    </tr>
    <tr>
      <td>ad</td>
      <td>Aphelion Distance (Unit - au): Farthest distance between the object and the Sun during its orbit, measured in astronomical units (au).</td>
    </tr>
    <tr>
      <td>per_y</td>
      <td>Orbital Period: Time taken for the object to complete one full orbit around the Sun, measured in years.</td>
    </tr>
    <tr>
      <td>data_arc</td>
      <td>Data Arc-Span (Unit - Days): Duration over which observations of the object have been collected, measured in days.</td>
    </tr>
    <tr>
      <td>condition_code</td>
      <td>Orbit Condition Code: Numerical code indicating the quality and reliability of the object's orbital data, with 0 being the most reliable.</td>
    </tr>
    <tr>
      <td>n_obs_used</td>
      <td>Number of Observations Used: Total number of observations used to determine the object's orbital parameters.</td>
    </tr>
    <tr>
      <td>H</td>
      <td>Absolute Magnitude Parameter: Measure of the object's intrinsic brightness, indicating its size and reflectivity.</td>
    </tr>
    <tr>
      <td>diameter</td>
      <td>Diameter of Asteroid (Unit - Km): Physical size of the asteroid, measured in kilometers (km).</td>
    </tr>
    <tr>
      <td>extent</td>
      <td>Object Bi/Tri-Axial Ellipsoid Dimensions (Unit - Km): Dimensions describing the shape and size of the object in terms of its three principal axes, measured in kilometers (km).</td>
    </tr>
    <tr>
      <td>albedo</td>
      <td>Geometric Albedo: Reflectivity of the object's surface, indicating the proportion of sunlight it reflects.</td>
    </tr>
    <tr>
      <td>rot_per</td>
      <td>Rotation Period (Unit - Hours): Time taken for the object to complete one full rotation on its axis, measured in hours.</td>
    </tr>
    <tr>
      <td>GM</td>
      <td>Standard Gravitational Parameter: Product of the gravitational constant and the object's mass, used in gravitational calculations.</td>
    </tr>
    <tr>
      <td>BV</td>
      <td>Color Index B-V Magnitude Difference: Difference in brightness between the object in the B (blue) and V (visual) photometric bands, indicating its color.</td>
    </tr>
    <tr>
      <td>UB</td>
      <td>Color Index U-B Magnitude Difference: Difference in brightness between the object in the U (ultraviolet) and B (blue) photometric bands, providing spectral information.</td>
    </tr>
    <tr>
      <td>IR</td>
      <td>Color Index I-R Magnitude Difference: Difference in brightness between the object in the I (infrared) and R (red) photometric bands, conveying thermal properties.</td>
    </tr>
    <tr>
      <td>spec_B</td>
      <td>Spectral Taxonomic Type (Unit - SMASSII): Spectral classification of the object based on the SMASSII scheme, indicating its mineral composition and surface features.</td>
    </tr>
    <tr>
      <td>spec_T</td>
      <td>Spectral Taxonomic Type (Unit - Tholen): Spectral classification of the object based on the Tholen system, indicating its spectral characteristics, composition, and origin.</td>
    </tr>
    <tr>
      <td>neo</td>
      <td>Near Earth Object: Indicates whether the object is classified as a Near Earth Object (NEO), meaning its orbit brings it close to Earth's orbit.</td>
    </tr>
    <tr>
      <td>pha</td>
      <td>Potentially Hazardous Asteroid: Identifies whether the object is classified as a Potentially Hazardous Asteroid (PHA), posing a potential threat to Earth.</td>
    </tr>
    <tr>
      <td>moid</td>
      <td>Earth Minimum Orbit Intersection Distance (Unit - au): Smallest distance between the object's orbit and Earth's orbit, measured in astronomical units (au), indicating potential close encounters.</td>
    </tr>
    <tr>
      <td>class</td>
      <td>Class of Asteroid: Visit nasa.com to learn more about classes</td>
    </tr>
    <tr>
      <td>n</td>
      <td>Unsure of what this is</td>
    </tr>
    <tr>
      <td>per</td>
      <td>Period</td>
    </tr>
    <tr>
      <td>ma</td>
      <td>ma</td>
    </tr>
  </table>
</details>


### Data Heatmap
We utilized a heatmap to visualize the correlations between different features in the dataset. This graphical representation helps in identifying the strength and direction of relationships among the variables, providing a clear and intuitive way to detect patterns, trends, and anomalies in the data. The heatmap is particularly useful for understanding multicollinearity, guiding feature selection, and improving model performance.

<details>
  <summary> Click to view Heatmap.</summary>
  <img src = 'https://github.com/user-attachments/assets/d684808c-b51b-430a-a1e2-da378104e964' alt = 'corr heatmap'>
</details>



### Data Distribution using `.describe()`
We employed the .describe() method to obtain a statistical summary of the features we are interested in. This summary includes metrics such as count, mean, standard deviation, minimum, and maximum values, as well as the 25th, 50th, and 75th percentiles. These statistics provide valuable insights into the central tendency, dispersion, and overall shape of the data distribution, facilitating the identification of outliers and informing subsequent data preprocessing and analysis steps.

<details>
  <summary> Click to view `.describe()` initial columns.</summary>
  <img src = 'https://github.com/user-attachments/assets/c1506d16-6e57-4fab-a8a0-98b7d3b5ddfa' alt = 'corr heatmap'>
</details>


### Data Preprocessing

To prepare the dataset for analysis, we undertook several preprocessing steps:

1. **Remove String Columns:**
   - We dropped the columns `name`, `spec_B`, `spec_T`, and `class` as they contain string values that are not suitable for numerical analysis.

2. **Handle Missing Values:**
   - We dropped the columns `rot_per`, `GM`, `BV`, and `UB` due to a high number of NaN values.
   - We removed any rows that contained NaN values for the diameter feature in order to ensure a clean dataset for analysis.\
     Original dataset size: 839714\
     Dataset size after dropping rows: 24404\
     Number of rows dropped: 815310

3. **Check Correlations:**
   - By plotting pairplots and the heatmap, we discovered a reasonably strong correlation between `diameter` and the following features: `q`, `moid`, `H`, `data_arc`, and `n`.
   - These correlations will be explored further in subsequent steps to understand their impact and relationships.

4. **Data Encoding:**
   - We change the values in the `pha` containing string values of 'Y' or 'N' to 1s and 0s to make graphing and working on them easier.
  
5. **Analyzing effects of preproccesing on data distribution:**
   - Using the scipy.stats.ks_2samp https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.ks_2samp.html we found that dropping the NAN rows did not severely effect the distribution. The KS test checks for the likelyhood that two samples were drawn from the same distribution, and for the variables we are interested in found p-values of **2.488278122363494e-60** for q, **0.0** for H and **1.4086431738613219e-53** for moid. All indicate that the effect was negligible.



### Graph Data Analysis

To better understand the relationships between various features and the diameter, we graphed several feature correlations. This graphical analysis aids in identifying potential relationships and patterns that might not be immediately evident through raw data or simple statistical summaries.

![diagrams/heatmaps/diameter vs graphs.png](https://github.com/harshilxd/Asteroid-Feature-Prediction/blob/0a965110aba28f2dfd9f969f2118bf6372483734/diagrams/heatmaps/diameter%20vs%20graphs.png)

1. **Diameter vs. q:**
   - We plotted the relationship between diameter and q (perihelion distance). This scatter plot helps us observe any direct or inverse relationships between the size of the object and its perihelion distance.

2. **Diameter vs. moid:**
   - The scatter plot between diameter and moid (minimum orbit intersection distance) was analyzed to see if there is any correlation between the object's size and its closest approach to Earth.

3. **Diameter vs. H:**
   - We also examined the correlation between diameter and H (absolute magnitude). This plot is particularly interesting as it helps in understanding how the brightness of an object might relate to its size.

5. **Diameter vs. n:**
   - Analyzing the scatter plot of diameter versus n (number of observations) can reveal whether more observations correlate with more accurate or different size estimations.
  
6. **Correlation Difference after dropping NAN values in preproccesing**
   
   <img src="https://github.com/harshilxd/Asteroid-Feature-Prediction/blob/c50bbc243a61133d703deddb63453c36aea5a690/diagrams/heatmaps/Difference%20in%20correlation%20before%20and%20after%20NAN%20drop.png" alt="histogram of q" width="400"/>

8. **Distribution Difference after dropping NAN values in preproccesing**
    - Histogram of q:
   <img src="https://github.com/harshilxd/Asteroid-Feature-Prediction/blob/ad64fd0dae7179fc48cc827d7dcccacfba86e356/diagrams/heatmaps/q%20before%20and%20after%20drop.png" alt="histogram of q" width="700"/>
   
    - Histogram of H:
   <img src="https://github.com/harshilxd/Asteroid-Feature-Prediction/blob/ad64fd0dae7179fc48cc827d7dcccacfba86e356/diagrams/heatmaps/h%20before%20and%20after%20drop.png" alt="histogram of q" width="700"/>
   
    - Histogram of moid:
   <img src="https://github.com/harshilxd/Asteroid-Feature-Prediction/blob/ad64fd0dae7179fc48cc827d7dcccacfba86e356/diagrams/heatmaps/moid%20before%20and%20after%20drop.png" alt="histogram of q" width="700"/>


These visualizations provide several insights:

- **Identifying Outliers:**
  - Scatter plots help in easily identifying any outliers that may exist in the data, which could potentially skew the analysis or indicate errors or special cases.

- **Understanding Distribution:**
  - The spread and clustering of points in these graphs can provide an understanding of how uniformly or variably the features are distributed.

## Milestone 3:

Before training our first model, we carried out few final steps of major preprocessing. We included only the `q`, `H`, `moid` and `diameter` columns to train our models since only these 3 variables had a decently strong correlation with the diameter of asteroids.

On studying the heatmap, we realized that `q` and `moid` were the same thing and hence, we also dropped the `q` column. 

Before training our model, we removed observations that were in the high top 5% of `a` and `diameter`. We did this to ensure that the big outliers do not affect our model negatively. Here is a description of the data after removing the observations :

<img src = "https://github.com/harshilxd/Asteroid-Feature-Prediction/blob/b3ad3383ddf4c7b5180297880690c7384d9d7608/diagrams/heatmaps/filtered%20data%20description.png" alt = "filtered data description">

### Model 1 :
#### Regression Model

The first model we trained was the Linear/Polynomial Regression model to predict the `diameter` using `H`

For the linear regression model, the **Training Error** was equal to 0.00713 and the **Testing Error** was equal to 0.00718 and below is a plot of the fit.

<img src = "https://github.com/harshilxd/Asteroid-Feature-Prediction/blob/d1593699a58d2d0032c4faaf1a68904509fe8722/diagrams/heatmaps/linear%20regression.png" alt = "linear regression fit" >

For the polynomial regression model with `degree = 9`, the **Training Error** was 0.00466 and the **Testing Error** was equal to 0.00468 and below is the plot of the fit.

<img src = "https://github.com/harshilxd/Asteroid-Feature-Prediction/blob/025d086d141ec3ccbcc462f6e335b85a7b624f16/diagrams/heatmaps/polynomial%20regression.png" alt = "polynomial regression fit">

