# Bi-Model-Aprroach-for-feature-extraction-from-Sensor-data-for-HAV

This particular task invloves exploring various **feature** **extraction** methods and **hybrid** **model** building to capture features from raw data on its own and using a Library called **TSFEL**(**Time  Series Featrure Extraction library)** particulary used for extracting Features by domains like **Statistical**,**Temporal** and **Spectral** to understand what the story data telling to us.!

**About the Data**

The UCI HAR dataset contains smartphone **accelerometer** and **gyroscope** readings (X, Y, Z axes) from participants performing six daily activities (walking, climbing, sitting, etc.). Collected at **50Hz** from waist-mounted devices, this benchmark dataset enables the development of algorithms that can automatically recognize human activities from sensor data, with applications in health monitoring and context-aware computing.

**Approaches Used to Solve this task**

So here I used certain approaches to finish this task one is Forcing the model to learn and captures important and complex relationship  from data on its own by feeding it using a raw sensor data collected over timesteps.It can achivable by using an Hybrid Model approach **1D** **CNN** **+** **Bidirectional** **LSTM** for capturing temporal dependencies and important patterns from data.

Another approch i have used was extracting the statistical ,temporal,spectral  features from raw time series sensor data using **TSFEL** Library particulary used to process **time** **series** data like sensors data and used an **Autoencoder** architecture befor training the  classifier to reduce dimensions by capturing important aspects of data.

finally trained classifier models like **RF**,**SVM**,**LogisticRegression** using features extracted by authors without any feature extraction techniques and compared the perfomance of each approach!

Deep Learning Approach: Used a hybrid **1D** **CNN** **+** **LSTM** model to capture both spatial and temporal dependencies from raw inertial sensor data.

Machine Learning Approach: Applied models like **RandomForest**, **SVM**, and **Logistic** **Regression**, but instead of raw data, I used handcrafted features extracted via **TSFEL** (**Time Series Feature Extraction Library**).

Compared models trained on handcrafted features vs. those using features provided by the dataset authors.

**How the Approach Was Implemented**

**Deep Learning Model (1D CNN + LSTM):**

1.Preprocessed raw sensor data by **normalizing** and reshaping each sensor data for three axis(x,y,z) into **9** **channels** tensor into a structured format.

2.Designed a sequential model incorporating **Conv1D** layers followed by **Bidirectional** **LSTMs**.

3.Used **Adam** optimizer with **categorical** **cross**-**entropy** loss function.

4.Evaluated performance using accuracy, confusion matrices and classification report.

**Model Evaluation Graphs**

![perfomance](https://github.com/user-attachments/assets/25639890-8cef-4801-ba3f-412733ca653c)

**Machine Learning Approach (Random Forest, SVM, Logistic Regression):**

1.Extracted features using **TSFEL** from raw sensor signals and trained an autoencoder to capture relevent features and to reduce dimension.

2.Standardized the feature set and trained the models(RF,SVM,LR).

3.Performed hyperparameter tuning to optimize model performance.

4.Evaluated the models using **accuracy**, **confusion** **matrix** & **classication** **reports**

![download](https://github.com/user-attachments/assets/8ff7dc42-5ccb-4432-a80f-8d3b2e776ca2)

**Unique Structure or Approach Used**

To make this comparison meaningful and fair, I followed a structured methodology:

**Custom Feature Engineering with TSFEL:** Instead of relying on pre-extracted features, I generated a unique feature set based on statistical, spectral, and temporal attributes from the raw signals then 
i trained an **autoencoder** to capture relevant features from extracted data by removing irrelevant dimensions the model well **generalized** on unseen data. 

**Comparing Handcrafted Features (TSFEL) vs. Author-Extracted Features Performance Comparison**

1.Models trained on TSFEL-extracted features consistently well performed equally to those trained on author-extracted features.

2.Implementing **TSFEL** + **AEC** helped in capturing important features while reducing irrelevant ones, leading to better generalization and efficient model training.

3.Reducing dimensionality from 561 to 64 features using **AEC** made training faster and improved model interpretability without significant loss of information.

**Comparision Graph for Both Approaches**

Bar Plot explaining the difference in the Accuracy Levels for both Approaches for each classifier

![download](https://github.com/user-attachments/assets/564d1eba-0117-46bf-8f55-70228bbcec1c)

**Performance of Classifiers on Author's Extracted Data**

![download](https://github.com/user-attachments/assets/26b47b9f-32d2-4b30-bd7b-74db594894a7)











