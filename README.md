Customer Segmentation using K-Means Clustering

📌 Project Title

Customer Segmentation using K-Means Clustering

📝 Project Description

This project performs customer segmentation using K-Means Clustering, an unsupervised machine learning algorithm.

The project uses the Mall Customers dataset and analyzes customer characteristics such as:

Age

Annual Income (k$)

Spending Score (1-100)

The data is explored and checked for missing values and duplicate records. Exploratory Data Analysis (EDA) is performed using histograms. The selected features are standardized using StandardScaler, and K-Means clustering is applied to divide customers into meaningful groups.

The Elbow Method is used to analyze the appropriate number of clusters, and the project uses 5 clusters for customer segmentation. A scatter plot is used to visualize the resulting customer groups.

The notebook also demonstrates how a new customer can be assigned to one of the existing clusters using the trained K-Means model.

🎯 Objectives

Understand the Mall Customers dataset.

Perform basic data exploration and EDA.

Check missing values and duplicate records.

Standardize numerical features.

Apply K-Means clustering.

Use the Elbow Method to evaluate the number of clusters.

Segment customers into different groups.

Visualize the customer segments.

Predict the cluster of a new customer.

🛠️ Technologies Used

Python

Pandas

NumPy

Matplotlib

Scikit-learn

Google Colab / Jupyter Notebook

🤖 Machine Learning Algorithm

K-Means Clustering

K-Means is an unsupervised learning algorithm that groups similar data points into a predefined number of clusters.

In this project:

Number of Clusters (K) = 5

The model is created using:

KMeans(
    n_clusters=5,
    random_state=42,
    n_init=10
)

🔄 Project Workflow

Load Dataset
     ↓
Understand Dataset
     ↓
Check Missing Values & Duplicates
     ↓
Exploratory Data Analysis
     ↓
Select Features
     ↓
Standardize Features
     ↓
Apply K-Means
     ↓
Elbow Method
     ↓
Create Customer Clusters
     ↓
Visualize Clusters
     ↓
Analyze Cluster Summary
     ↓
Predict Cluster for New Customer

📊 Dataset

The project uses:

Mall_Customers.csv

The notebook works with the following columns:

Age

Annual Income (k$)

Spending Score (1-100)

A cluster label is added to the dataset as:

Cluster

📈 Exploratory Data Analysis

Histograms are used to understand the distributions of:

Customer Age

Annual Income

Spending Score

These visualizations help understand the characteristics of the customers before clustering.

⚙️ Data Preprocessing

The numerical features are standardized using StandardScaler.

scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

Standardization is useful because the features may have different scales.

📐 Elbow Method

The Elbow Method is used to calculate WCSS (Within-Cluster Sum of Squares) for different values of K.

The notebook evaluates:

K = 1 to 10

and plots the WCSS values to help select an appropriate number of clusters.

👥 Customer Segmentation

After clustering, the cluster number is stored in the dataframe:

df["Cluster"] = clusters

The project then visualizes the customer segments using a scatter plot based on standardized Annual Income and Spending Score.

🔍 Cluster Analysis

The average values of:

Age

Annual Income

Spending Score

are calculated for each cluster using:

cluster_summary = df.groupby("Cluster")[[
    "Age",
    "Annual Income (k$)",
    "Spending Score (1-100)"
]].mean()

This helps understand the characteristics of each customer segment.

🧪 New Customer Prediction

The notebook also demonstrates cluster prediction for a new customer:

new_customer = np.array([[80, 75]])

The new customer is standardized and passed to the trained K-Means model to determine its cluster.

💡 Real-World Applications

Customer segmentation can help businesses:

Identify different customer groups.

Create targeted marketing campaigns.

Understand customer spending behavior.

Personalize offers and promotions.

Improve customer relationship management.

Support business decision-making.

📁 Project Structure

Customer-Segmentation/
│
├── Customer_segmentation.ipynb
├── Mall_Customers.csv
└── README.md

▶️ How to Run

Open Customer_segmentation.ipynb in Google Colab or Jupyter Notebook.

Upload Mall_Customers.csv.

Run the cells in sequence.

Review the EDA visualizations.

Check the Elbow Method graph.

Analyze the generated customer clusters.

Test the new customer prediction.

⚠️ Important Note

Before running the scaling step, make sure the feature matrix X is defined using the intended numerical features. For example:

X = df[["Annual Income (k$)", "Spending Score (1-100)"]]

Then run:

scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

This definition is required because the notebook's scaling cell uses X.

📌 Conclusion

This project demonstrates how K-Means Clustering can be used for customer segmentation. By analyzing Annual Income and Spending Score, customers can be grouped into different segments based on their characteristics and behavior.

Such segmentation can provide useful insights for targeted marketing, personalized customer strategies, and better business decisions.

👩‍💻 Author

Rukhsar Hashmi
