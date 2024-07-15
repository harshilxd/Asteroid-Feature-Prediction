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
1. Our data consists of: 
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

2. We used a heatmap to look at the correlations between different features
   ![image](https://github.com/user-attachments/assets/d684808c-b51b-430a-a1e2-da378104e964)


3. We used data.describe() to look at the distribution for the features that we interested: 
![image](https://github.com/user-attachments/assets/c1506d16-6e57-4fab-a8a0-98b7d3b5ddfa)


### Data Preprocess
1. Remove String Columns: we dropped the columns name, spec_B, spec_T, and class as they contain string values that are not suitable for numerical analysis
2. Handle Missing Values: we dropped the columns rot_per, GM, BV, and UB due to a high number of NaN values. We also drop any rows that contain NaN values.
3. Checked Correlation : On plotting the pairplots and the heatmap, we found a reasonably strong correlation between the diameter and the following features: q, moid, H, data_arc, n for which we could explore their correlations in further steps.
4. Data Splitting : we split the data into training and testing sets with an 80/20 ratio

