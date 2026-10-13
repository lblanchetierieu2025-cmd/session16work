# Session 16 – How Many Worlds? PCA and Clustering of UN Country Data

**Research question:** Can the world be meaningfully divided into only two groups—developed and developing countries—or does the data suggest a more complex structure?

## Repository contents

- `session16work.ipynb` – Jupyter Notebook with the complete analysis (data preparation, PCA, K-Means clustering)
- `session16work - Colab.pdf` – PDF version of the notebook with all outputs and visualizations
- `UN.csv` – Dataset used in the analysis
- `README.md` – Answers to the research questions

To reproduce the analysis, open the notebook in Google Colab or Jupyter and run all cells.

---

## 1. Can the world be meaningfully divided into only two clusters (developed vs. developing)?

The PCA plot shows a clear general separation between two groups of countries. The silhouette score is 0.520, which means that the two clusters are reasonably well separated. This suggests that the traditional division between countries with stronger development conditions and countries with greater development challenges does appear in the data.

However, the separation is not perfect. The countries are spread continuously across the graph, and some are located between the two main groups. This means that not every country can be clearly described as either developed or developing.

Therefore, two clusters are useful for showing the main general difference between countries, but they are too simple to explain the complete structure of the world. More clusters may reveal the intermediate development levels hidden inside these two large groups. We will test this using the Elbow Rule, silhouette scores and additional cluster solutions.

## 2. How many clusters are suggested by the data according to the Elbow Rule and other evaluation metrics?

The Elbow Rule shows that the within-cluster variation drops sharply when moving from two to three and four clusters. After four clusters, adding more groups only produces small improvements. This means that the "elbow" of the curve is located around three to four clusters.

The silhouette score is highest for two clusters and becomes lower as more clusters are added. This is expected, because one main dimension (development) dominates the data, and dividing a long continuous line into two halves always produces groups that look well separated. A high silhouette score for two clusters does not mean that there are only two natural groups in the world.

Taking the Elbow Rule, the silhouette scores and the PCA visualization together, we consider four clusters to be the best solution. Four clusters give a good balance between simplicity and detail, and each group can be clearly interpreted.

## 3. How much of the data structure is captured by two clusters compared with the preferred number of clusters?

Two clusters capture the main difference between countries, but a large part of the variation remains inside each group. For example, the "developed" cluster contains very different countries, from middle-income countries in Latin America and North Africa to high-income countries in Europe and North America.

With four clusters, the within-cluster variation is clearly lower, which means that countries inside each group are more similar to each other. The four-cluster solution separates the intermediate countries that were mixed together in the two-cluster solution. Therefore, four clusters capture considerably more of the real structure of the data than two clusters.

## 4. Does the evidence support the argument in Factfulness that the world should not be understood as simply two groups, but rather as four or more?

Yes, the evidence supports the argument in Factfulness. Hans Rosling argues that there is no real gap between "developed" and "developing" countries, and that most people actually live in the middle. Our data shows the same pattern.

On the PCA plot, countries are distributed continuously along the development axis, without a clear empty space between rich and poor countries. Many countries are located in the middle, and they do not fit well into either of the two traditional groups.

The four-cluster solution is similar to Rosling's four income levels: a group of countries with very low income and high fertility, a group in transition, a group of middle-income countries with good health and education, and a group of high-income countries. This shows that the world is better understood as several levels of development than as two separate groups.

## 5. What does PCA tell you about the variables that differentiate countries?

PCA shows that most of the differences between countries can be summarized by one main dimension. The first principal component explains the largest share of the variance and combines life expectancy, infant mortality, fertility rate, literacy, contraception and GDP per capita. These variables move together: countries with higher life expectancy usually also have lower infant mortality, fewer children per woman, higher literacy and higher income. We interpret this component as the general level of development.

The second principal component is mainly related to female economic activity. It separates countries that have a similar level of development but very different participation of women in the labour market.

This shows that health, fertility, education and economic conditions are the main factors that differentiate countries, while the role of women in the economy adds a second, smaller dimension. PCA was also useful to reduce the number of variables before clustering, because a few components keep most of the information.

## 6. Using one representative country from each cluster, how would you describe and interpret the clusters?

**Cluster 1 – Ethiopia (low income, high fertility).** Ethiopia has a very high fertility rate, high infant mortality, low life expectancy and high illiteracy. Most countries in this cluster are in sub-Saharan Africa, such as Niger, Mali and Chad. This cluster represents countries where basic health and education conditions are still limited.

**Cluster 2 – India (countries in transition).** India has a lower fertility rate than Cluster 1, but infant mortality and female illiteracy are still high. This cluster also includes countries such as Egypt, Morocco and Pakistan. A surprising result is that some rich countries like Saudi Arabia are also in this group, because they share high fertility and very low female participation in the labour market. This shows that income alone does not define a cluster.

**Cluster 3 – Colombia (middle income, good health and education).** Colombia has a moderate fertility rate, good life expectancy and low illiteracy, but its income is still lower than in rich countries. This cluster includes countries such as Mexico, Brazil, China and Thailand. It is the group that the traditional "developed vs. developing" view tends to ignore.

**Cluster 4 – Portugal (high income).** Portugal has a low fertility rate, high life expectancy, very low infant mortality and high income. This cluster includes most of Europe, North America, Japan and South Korea. It represents the countries with the highest level of development in the data.

---

## Conclusion

Our analysis suggests that four clusters provide a more detailed understanding of global development than the traditional division into two groups. Although two clusters achieve a higher Silhouette Score, the four-cluster solution reveals important intermediate differences between countries. Furthermore, PCA shows that health, fertility, literacy, and economic conditions all contribute to these differences. Overall, our findings support the argument in Factfulness that the world cannot be adequately understood through a simple developed-versus-developing classification.
