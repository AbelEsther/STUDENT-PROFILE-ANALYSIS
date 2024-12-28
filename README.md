# STUDENT-PROFILE-ANALYSIS
### **KMEANS,DBSCAN, HIERARCHICAL CLUSTERING**

## **Notebook used in Data analysis and Model Building**
[student_profile_analysis.ipynb](https://github.com/AbelEsther/STUDENT-PROFILE-ANALYSIS/blob/3ea9725fed8e896a2a3a1648db66e230dcbd3c0f/student_profile_analysis.ipynb)

## **Dataset Link**
[Student_info.csv](https://github.com/AbelEsther/STUDENT-PROFILE-ANALYSIS/blob/3ea9725fed8e896a2a3a1648db66e230dcbd3c0f/Student_info.csv)


## **Problem Definition**
The primary challenge in educational institutions is to effectively address the diverse learning needs of students while improving overall academic success rates. Traditional one-size-fits-all approaches often fail to account for variations in student demographics, socio-economic backgrounds, and academic performances, leading to suboptimal outcomes. By clustering students with similar profiles, this project aims to provide actionable insights to enable personalized learning and targeted interventions that can reduce dropouts and enhance student success.


---
## **Importance**

- **Enhanced Student Success:** Personalized interventions based on clustering insights can improve student outcomes.
- **Resource Optimization:** Institutions can allocate resources efficiently by targeting specific groups with tailored support.
- **Proactive Dropout Prevention:** Identifying at-risk groups enables early interventions, minimizing dropouts.
- **Data-Driven Decision Making:** Leveraging machine learning ensures decisions are based on reliable patterns and trends.


---

## **Key Stakeholders**
- **Students and Families:** The primary beneficiaries of personalized support that enhances academic success and reduces barriers to learning.
- **Educational Institutions:** Gain insights for designing effective programs, improving retention rates, and optimizing resource allocation.
- **Policy Makers and Administrators:** Use insights for shaping policies that address educational challenges at scale.
- **Educational Technology Providers:** Build adaptive learning solutions and tools using insights from clustering outcomes.



---

# **DATA SECTION**

## **Dataset Description**
The dataset contains **4,424 records**, where each record represents a unique student profile. The purpose of the dataset is to analyze student characteristics to identify patterns using machine learning clustering techniques. Below are the key features included in the dataset:

1. **Marital Status**: Indicates the marital status of the student, which may influence their academic and financial situation.
2. **Application Mode**: Reflects the application process or type used, providing insight into admission patterns.
3. **Application Order**: Order in which applications were processed, which could relate to preferences or availability.
4. **Course**: The program or course the student is enrolled in, affecting their academic trajectory.
5. **Daytime/Evening Attendance**: Identifies whether a student attends during the day or evening, indicating flexibility in scheduling.
6. **Previous Qualification**: The level of qualification the student had before enrolling, showing academic readiness.
7. **Previous Qualification (Grade)**: The grades obtained in the previous qualification, reflecting academic performance.
8. **Nationality**: Indicates the country of origin, useful for analyzing diversity and geographical trends.
9. **Mother’s Qualification**: Educational level of the student's mother, providing socio-economic context.
10. **Father’s Qualification**: Educational level of the student's father, adding further socio-economic context.
11. **Mother’s Occupation**: Type of employment held by the mother, reflecting family background.
12. **Father’s Occupation**: Type of employment held by the father, further reflecting family background.
13. **Admission Grade**: The grade obtained during admission, which could correlate with academic success.
14. **Curricular Units (1st Semester)**:
    - **Enrolled**: Number of units the student is enrolled in for the first semester.
    - **Evaluations**: Number of evaluations completed in the first semester.
    - **Approved**: Number of units passed.
    - **Grade**: Average grade achieved.
    - **Without Evaluations**: Number of units without evaluations.
15. **Curricular Units (2nd Semester)**: Similar metrics for the second semester.
16. **Unemployment Rate**: The unemployment rate in the student's region, reflecting socio-economic conditions.
17. **Inflation Rate**: Regional inflation rate, which may affect the student's financial stability.
18. **GDP**: Gross Domestic Product of the region, providing an economic context.

This dataset enables analysis of student demographics, academic performance, and socio-economic factors to uncover patterns for personalized learning and interventions.

---

# **SUMMARY**

### **1. How well are the clusters separated in each method?**
- **KMeans**:
  - The clusters are moderately separated. The method works well for compact and spherical clusters, but performance declines for irregular or overlapping cluster shapes.
  - Optimal \( K \) was determined using the elbow method and silhouette scores, which guided better separation.

- **Hierarchical Clustering (Ward)**:
  - Clusters are reasonably well-separated when a clear threshold is chosen from the dendrogram. However, as the dataset size increases or clusters overlap, separation quality declines.
  - Works well for small datasets or exploratory purposes but is computationally expensive for large datasets.

- **DBSCAN**:
  - DBSCAN showed the best separation, particularly for irregularly shaped clusters and noisy data points. Noise points were effectively isolated, and cluster boundaries were not limited to predefined shapes.

---
### **2. What info is most useful for you?**
- **Feature Contributions**:
  - Understanding which features (e.g., "Admission Grade," "Attendance") dominate specific clusters provided insights for targeted interventions.
- **Cluster Composition**:
  - Knowing cluster sizes and distributions (via pie charts and summaries) helped identify the most prevalent and outlier groups.
- **Noise Points (DBSCAN)**:
  - DBSCAN effectively identified noise points, highlighting unusual data points that could represent edge cases or anomalies.
- **Optimal \( K \) for KMeans**:
  - Determining the optimal \( K \) (number of clusters) using silhouette scores and elbow methods ensured meaningful groupings.

 ---
 ### **3. Which method produced the highest silhouette score?**
- **DBSCAN**:
  - DBSCAN produced the highest silhouette score due to its flexibility in handling arbitrary cluster shapes and isolating noise points.
  - The optimized parameters improved the clustering quality.
- **KMeans**:
  - Provided a decent silhouette score when \( K \) was chosen carefully but struggled with non-spherical clusters.
- **Hierarchical Clustering**:
  - The silhouette score was reasonable but lower than DBSCAN. Its dependency on the chosen dendrogram threshold limited its clustering quality.

---
### **4. What are the strengths and weaknesses of each method based on your results?**

| **Clustering Method** | **Strengths**                                                                                   | **Weaknesses**                                                                                   |
|------------------------|-----------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| **KMeans**             | - Fast and scalable for large datasets.<br>- Works well for compact and equally-sized clusters.<br>- Provides clear centroids for interpretation. | - Requires predefining \( K \).<br>- Sensitive to outliers.<br>- Struggles with irregular or varying-density clusters. |
| **Hierarchical**       | - No need to predefine \( K \).<br>- Provides a hierarchical view of clusters.<br>- Easy to visualize relationships via dendrograms. | - Computationally expensive for larger datasets.<br>- Highly sensitive to noise.<br>- Threshold selection impacts results. |
| **DBSCAN**             | - Handles arbitrary cluster shapes.<br>- Isolates noise effectively.<br>- No need to predefine \( K \).         | - Requires careful tuning of \( \text{eps} \) and \( \text{min\_samples} \).<br>- Struggles with clusters of varying densities. |

---
### **Recommendations**:
- **Best Overall Method**: DBSCAN, as it effectively handled noise, irregular cluster shapes, and did not require predefining \( K \).
- **Exploratory Analysis**: Hierarchical clustering is ideal for understanding relationships at smaller scales.
- **Large Datasets with Clear Clusters**: KMeans works well if \( K \) is predefined and clusters are compact.




