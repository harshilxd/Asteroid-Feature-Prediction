# Asteroid Data Exploration Project



## Milestone 4: Final Submission
### Introduction:
This project aims to enhance our capabilities at understanding asteroids in our solar system using machine learning. While some features of asteroids are easily measurable, others are more difficult to measure as they may require many observations over a long period of time to calculate accurately. Our goal with the project is to apply neural networks and regression techniques to predict features of asteroids that are otherwise time or computationally intensive to figure out. We chose this topic since it was something that our team felt was personally relevant to our interests as well as technologically relevant in the era where we can collect a lot more data than we can reasonably process into usable knowledge. The traditional computational approaches still take orders of magnitude more computational resources than running a simple neural network would, and we these techniques to parse data before looking through it with more traditional and computationally intense methods. This approach is used by CERN as part of their search for high-energy particles because they deal with a similar problem of detection capacity being way beyond processing capacity. We saw the same potential use for small neural networks to filter asteroid data.

### Figures:
Orbits of 1000 random asteroids from the preprocessed data with an orbital period. less than 8 years
<img src = "https://github.com/harshilxd/Asteroid-Feature-Prediction/blob/5b426991598a6448f56a62e1fc09ab91f6bdf944/diagrams/gifs/asteroid_orbits3.gif" alt = "">
Orbits of asteroids with an orbital period less than 8 years.
<img src = "https://github.com/harshilxd/Asteroid-Feature-Prediction/blob/5b426991598a6448f56a62e1fc09ab91f6bdf944/diagrams/gifs/asteroid_orbits4.gif" alt = "">

### Methods:

#### Data Exploration:
We utilized a heatmap to visualize the correlations between different features in the dataset.
![](diagrams\heatmaps\heatmap_full.png)

#### Data Preproccessing:

1. Removed string columns: 'name', 'spec_B', 'spec_T', and 'class'.
2. Dropped columns with high NaN values: 'rot_per', 'GM', 'BV', and 'UB'.
3. Removed rows with NaN values in the diameter feature, reducing the dataset from 839, 714 to 24,404 observations.
4. Encoded 'pha' column to binary values (0 and 1).
5. Removed observations in the top 5% of 'a' and 'diameter'.
6. Normalized data using MinMaxScaler

#### Model 1:
A deep neural network with 3 hidden layers was developed, using 'q', 'H', 'a', 'i', 'ad', 'n', and 'per' as features.

| Layer (type)         | Output Shape | 128 |
|----------------------|--------------|-----|
| dense_7  (dense)     | (None, 16)   | 128 |
| dense_8  (dense)     | (None, 8)    | 136 |
| dense_9  (dense)     | (None, 6)    | 54  |
| dense_10 (dense)     | (None, 1)    | 7   |

The model was further improved through hyperparameter tuning layer count and size.

| Layer (type)         | Output Shape | Param #|
|----------------------|--------------|--------|
| dense_6  (dense)     | (None, 96)   | 768    |
| dense_7  (dense)     | (None, 96)   | 9,312  |
| dense_8  (dense)     | (None, 192)  | 18,624 |
| dense_9  (dense)     | (None, 256)  | 49,408 |
| dense_10 (dense)     | (None, 96)   | 24,672 |
| dense_11 (dense)     | (None, 1)    | 97     |

#### Model 2:

### Results:

### Discussion:


The project began with our comprehensive data exploration and preprocessing which reduced our data set size quite a lot. After looking into how to check for data culling issies we settled on the Kolmogorov-Smirnov test to make sure that our data distribution was not heavily affected, and thankfully it was not. We started with a basic linear regression model but quickly moved on to higher degree polynomial regression models because the relationship between absolute magnitude and our diameter was nonlinear. However, while this was a decent model, for this project we wanted to come up with a more original approach to make our research more useful.

We settled on using a neural network for our first model because we wanted to model more complex relationships and our regression was not giving us good enough results. We were able to use many features in combination to capture the complex relationship for prediction, and then we used hyperparameter tuning to further optimize the model.

The second model that we trained diverged quite a lot from the first since we were working on predicting a different feature after a discussion with the professor.


### Conclusion:

### Statement of Collaboration:
**Moshe Bookstein:** Project Management and Design: Creating data exploration graphs, helped with preprocessing, created figures and illustrations, documentation and organization.



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


## Milestone 3:

Before training our first model, we carried out few final steps of major preprocessing. We began by removing observations that were in the high top 5% of `a` and `diameter`. We did this to ensure that the big outliers do not affect our model negatively. We then proceeded to normalize our data using `MinMaxScaler`. This led to a data distribution between 0 and 1, which made it easier for our models to run.

We then built a baseline model. This was a simple linear regression model using `H` as the feature to predict the `diameter`.

Here is a description of the data after removing the observations :

<img src = "https://github.com/harshilxd/Asteroid-Feature-Prediction/blob/b3ad3383ddf4c7b5180297880690c7384d9d7608/diagrams/heatmaps/filtered%20data%20description.png" alt = "filtered data description">

For the linear regression model, the **Training Error** was equal to `0.00713` and the **Testing Error** was equal to `0.00718` and below is a plot of the fit.

<img src = "https://github.com/harshilxd/Asteroid-Feature-Prediction/blob/d1593699a58d2d0032c4faaf1a68904509fe8722/diagrams/heatmaps/linear%20regression.png" alt = "linear regression fit" >

We intended to use this baseline MSE to compare our future models' accuracy to. However, we felt that the relationship between `H` and `diameter` was polynomial, so to further improve upon the linear model, we ran a polynomial model of degree 6. The model reported the following: `Degree 6 - Polynomial-Training MSE: 0.0008861995114971393, Polynomial-Testing MSE: 0.000843212857156944`.

The graph for polynomial regression was as follows:

<img width="510" alt="Screenshot 2024-07-22 at 9 50 37 PM" src="https://github.com/user-attachments/assets/717c1e35-1588-4fdd-a649-9c37d9df9dde">

### Model 1 :
#### Deep Neural Net

For our first complex model, we though of improving upon the accuracy of the regression models. Initially, we used a deep neural net with 3 hidden layers. We used `adam` as the optimizer and **Mean Squared Error** to determine the loss of the function. The description of the layers of the neural net was as follows:

<img width="742" alt="Screenshot 2024-07-22 at 9 54 26 PM" src="https://github.com/user-attachments/assets/4ceb2a29-aad8-42ea-8fc3-65664e51669c">

We trained this model using `'q', 'H', 'a', 'i', 'ad', 'n', 'per'` as features. This led to an Training MSE of  `0.00073075` and a Testing MSE of `0.00069468`.

We then further improved upon this model using hyperparameter training. This led to a slight improvement in the MSE, which jumped to `0.00068175`. The model after hyperparametrizing was as follows:

<img width="758" alt="Screenshot 2024-07-22 at 10 01 08 PM" src="https://github.com/user-attachments/assets/12a9db15-4b6b-4fb7-8db9-061e73180990">

#### Potential Scopes of Improvement
While the current performance is impressive, there are always areas where improvements can be made:

1. **Model Complexity**: We need to evaluate if the model complexity is optimal. Adding more layers or neurons might not always lead to better performance and could cause overfitting.

2. **Regularization Techniques**: We might need to implement regularization techniques such as Dropout, L2 regularization, or Batch Normalization to prevent overfitting and improve model robustness.

3. **Cross-Validation**: We need to implement cross-validation to ensure the model's robustness and prevent overfitting to a particular train-test split. This will give a better estimate of the model's performance on unseen data.

4. **Model Ensembles**: We need to combine the neural network with other models (e.g., ensemble with decision trees or gradient boosting machines) to potentially capture different aspects of the data and improve overall performance.

#### Future Direction
As for the next model, we plan to use Decision Trees or Transformer Networks. We feel that decision trees will beeffective because some of our data might not be linear. And Transformer Networks are also used in regression models. Additional improvements include:

1. **Fine-Tuning the Architecture**: Experiment with the architecture by adding/removing layers or neurons. Implement regularization techniques such as Dropout or Batch Normalization to control overfitting.

2. **Hyperparameter Optimization**: Conduct a more extensive hyperparameter optimization using techniques like Grid Search or Bayesian Optimization to find the best set of hyperparameters.
 
3. **Advanced Features**: Conduct a thorough feature importance analysis to identify the most influential features and consider engineering new features.
  
4. **Cross-Validation**: Use k-fold cross-validation to ensure that the model is not overfitting and to provide a more accurate measure of its performance.





