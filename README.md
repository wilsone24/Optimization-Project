# Diamond Price Prediction

![Diseño sin título](https://github.com/wilsone24/Optimization-Project/assets/118389840/00704de8-ad2e-408e-b2c7-7f3410716ddd)


## Dataset selection

After examining various datasets from which a future model could be derived, we chose this one due to certain variables, such as the quantity of data it contains, around 53,940 rows where valuable information can be extracted. This substantial amount of data allows for a more profound, clear, and optimal analysis of the problem. Additionally, it is known that diamond prices pose a problem that affects people every day, creating economic difficulties, primarily focusing on individuals with the economic capacity to access these goods or entrepreneurs engaged in this business. Therefore, its impact on both the economy and the daily lives of people makes it a suitable dataset and problem to address. Similarly, the variables included in the dataset are well-known, easy to relate to when analyzing the problem, and the correlations found would facilitate the creation of our model. Finally, we consider that dealing with diamonds is not common, and for that reason, it seemed more interesting to us.

### Our Team

| ![Integrante 1](https://github.com/wilsone24/Optimization-Project/assets/118389840/1ad141ba-4520-4d3e-add6-724df3f272ce)  | ![Integrante 2](https://github.com/wilsone24/Optimization-Project/assets/118389840/92da7de6-a034-40f4-affa-2887ebc5fed3)  |
| --- | --- |
| **Data engineer** Wilson Estrada Ortega is a student at the Universidad del Norte in the systems engineering program in seventh semester, graduated from Biffi La Salle school in 2020, his area of interest is focused on the management of big data, cloud computing and technology sales. He has knowledge in various programming languages but focuses mainly on python and sql for data manipulation. He is passionate about sports and learning new things. The role he will develop in the team will be a data engineer and he will be one of the people in charge of data manipulation and data cleaning. | **Data engineer** Yuli Meza Barros, 22 years old student on 9th-semester of systems engineering at Universidad del Norte, completed her studies at Nuestra Señora de Lourdes School in 2019. With a profound interest in cybersecurity, she demonstrates proficiency in Java and Python programming languages. Her fascination extends to data analytics, showcasing a versatile skill set. In the team, Yuli plays a vital role as a data engineer, specializing in meticulous data manipulation and cleaning processes  Her diverse interests and skills contribute to the dynamic and collaborative environment within the team. |

| ![Integrante 3](https://github.com/wilsone24/Optimization-Project/assets/118389840/d1a88f04-6a50-42de-9387-6965a03343dd)  | ![Integrante 4](https://github.com/wilsone24/Optimization-Project/assets/118389840/85134bbd-01ca-44b2-8ed7-af2ecd0a8bcb)  |
| --- | --- |
| **Backend engineer** Felipe Benítez, a seventh-semester student at Universidad del Norte, graduated from nuevo colegio del prado, has a keen interest in backend development, databases, and distributed systems. With a passion for crafting robust solutions and learning from existent ones. Outside of the tech realm, Felipe enjoys expressing his creativity through drawing and has a particular fondness for manga. | **Frontend engineer** Yordi González, a seventh-semester systems engineering student at Universidad del Norte, graduated from I.E.T.C. Francisco Javier Cisneros at 2020, who has some experience in backend development and database management. Proficient in Python, SQL, and relational databases. Dedicated to designing efficient systems to meet project goals. I am responsible for the visual part of the project emphasizing the user experience. |

### Visualizations

![graphs](https://github.com/wilsone24/Optimization-Project/assets/118389840/b730627f-6528-478d-a752-e4925849b160)

### Statistical insights

Taking into account the following analysis and observing the dataset, we can derive the following premises:

* Diamond prices range from $326 to $18,823, with a mean of 3932.79. Additionally, the objective is to analyze the distribution and identify patterns in different price ranges.

* Despite the presence of outliers, concerning the dimensions x, y, z of the diamonds, they follow a trend that can be linearly modeled in each of the proposed graphs. The respective means for each dimension are: x (5.731157), y (5.734526), z (3.538734). The dimensions include length (x) ranging from 0 to 10.74 mm, width (y) ranging from 0 to 58.9 mm, and depth (z) ranging from 0 to 31.8 mm. The goal is to explore the relationship between physical dimensions and diamond prices, considering the importance of shape and proportions.

* Other observations: We observe that the trend of carats concerning the price of diamonds follows a quadratic function, where the data is not dispersed as much. Carat weights vary from 0.2 to 5.01, with a mean of 0.797940. The correlation coefficient of this variable with respect to the diamond price is the highest and is 0.92.

* There is much more density of data and diamonds at a lower price than those at a significantly higher price.

* The other variables, both qualitative and quantitative, also influence the diamond price but not as much as those mentioned earlier. We observe that as the count decreases, the price is lower, and the density concerning the price follows two trends, first rising and then declining.

![Matriz de correlación](https://github.com/wilsone24/Optimization-Project/assets/118389840/cf952684-999a-4dfd-baf5-8bac9e6194fe)

### Hypothesis

Taking into account various observations, it is necessary to highlight the initial hypothesis that the working team has about the dataset. Diamond prices do not depend solely on a particular variable; instead, they are determined and influenced by multiple variables, such as each of the different dimensions and weight, which collectively impact the price. This is the hypothesis we will be developing throughout the model with the objective of identifying which variables have a greater influence on diamond prices and in what manner.

## Model Selection I

### Objectives

* Identify the variables (dimensions and characteristics) that explain to a greater extent the behavior of diamond prices to build the predictive model and understand how these variables affect them.

* Compare different models to determine which one offers the best accuracy.

* Have an impact on the diamond market analysis by allowing for a more effective evaluation of their prices.



### Details about your selection

First, we clean the data to remove dimensionless diamonds and eliminate highly atypical diamonds that could pose difficulties for model development. Based on the initial analysis, we choose a linear regression model due to the high correlation between price and many variables, considering that there could be a linear relationship and price is a continuous variable. We select carat and z as variables for our model.

![Diamond dimension](https://github.com/wilsone24/Optimization-Project/assets/118389840/b96a148f-89b6-4daa-a256-ecff1550e735)


We opted for carat and z because, in our opinion and according to our descriptive analysis, they are the variables that most characterize the price of diamonds. Carat represents the weight of the diamond, and z represents the depth. According to our research, the greater the weight and depth of the diamond, the higher its cost. We discarded the other dimensions (x, y) because when included in the model alongside carat and z, a high correlation was observed among them, and the model's outcome did not significantly vary. Therefore, we selected the variable that had the most influence on the model among the three dimensions. In this initial part of the analysis, we did not use the categorical variables from the dataset because we considered them not highly relevant in this context.

### Validation method and metrics

For the model validation process, a cross-validation technique was employed to detect issues such as overfitting or selection bias. The data was divided into training and testing sets, with an 80-20 ratio, respectively. The process was repeated 1000 times, where in each iteration, a linear regression model was first fitted using the training data, and then the obtained model was validated using the testing data to evaluate its performance against unseen data during the model training. This allows us to have a better insight and overview of the overall model quality rather than just under one data split, so in each iteration, samples were taken to better understand the model's behavior.



![Score and Residuals](https://github.com/wilsone24/Optimization-Project/assets/118389840/39263c05-fecb-45b2-9a39-140bb3661a3f)


To primarily evaluate the predictive capability and performance of the model, the $R^{2}$ score or coefficient of determination was used as a metric to analyze the correlation between the model's predictions and the actual data. We consider this to be the best measure as it provides an idea of the quality of the model's fit to the data. Additionally, the MSE and RMSE were calculated to assess how close the model's predictions are to the actual values. All of this was done considering the model created from the average of the coefficients and intercept, which resulted in a slightly higher score than the average.

| Metric    | Value     |
|-----------|-----------|
| Score    | 0.8669998  |
| MSE      | 2077644.93 |
| RMSE     | 1441.403   |

### Preliminary conclusions

* It can be established by observing the score that the model is good and largely describes the variability of the price.

* I t is noted that the model is not the most precise; price predictions are not exact and have a margin within which the predicted value can differ from the actual one.

* After many tests, it has been determined that the variable that most influences the model is carat.

* A pattern is observed where the model does a much better job of predicting relatively low diamond prices than high prices, where precision is lower.

* It is essential to evaluate how significant the difference between actual and predicted values would be for practical use in the market. If exact precision is not needed, the diamond price could be adequately described in this manner.

## Model Selection II

![New Project - Made with Clipchamp](https://github.com/wilsone24/Optimization-Project/assets/118389840/cd9f4dee-b8ba-4409-bc9d-6d03c171929d)


### Details about your selection

In this case, we chose a type of neural network known as an MLP (Multilayer Perceptron). After cleaning the data and removing dimensionless data, we eliminated outliers that exhibited highly unusual behavior compared to the distributions of other diamond features and measurements. We opted for neural networks because we observed that the data's behavior was not strictly linear, and we wanted to capture that non-linearity in some way. Neural networks offer us the possibility to do this thanks to their multiple layers and the weights between neurons that adjust with the data. Additionally, their strength lies in their ability to learn complex patterns and relationships, making them suitable given that the customizable architecture of MLP allows us to adjust the network's topology to optimize performance.

![RN ARCH](https://github.com/wilsone24/Optimization-Project/assets/118389840/276c172b-8880-4180-8329-57c2ee6b3fa6)

The next step was to discretize the qualitative variables, assigning them a corresponding value to observe their influence on the model's quality. After conducting tests, we chose Carat and Z as our inputs, which, as mentioned in the previous model, largely explain the diamond's price. Additionally, we added 'cut', 'color', and 'clarity', initially categorical and now numerical, as inputs because we observed that they have a greater influence than the other numerical variables. After several benchmarks with different architectures to find the optimal one, we used the following configuration: 5 inputs, 7 hidden layers (20 neurons per layer), 1 output, default Alpha, maximum 600 iterations, and Relu activation function (which provided the best result).

### Validation method and metrics

Cross-validation technique was used to avoid overfitting or bias issues, with an 80% data partition for training and the remaining 20% for testing. This allowed us to evaluate the model with data it hadn't seen before. Due to the prolonged duration of the process and the associated computational cost, attributed to the large amount of data, only 20 iterations were conducted to observe the score distribution across different data partitions. This helped us determine how sensitive the score is to data partitioning and how scattered the values are around the most likely score.

![Regression RN](https://github.com/wilsone24/Optimization-Project/assets/118389840/6255603a-459f-4f43-88e6-a8a1b2bb3ad2)

We obtained an average score of 0.9757, which is where the highest density is observed, with an operational margin of 0.5%. This means that the score can fluctuate between values close to 97% and 98% with the same probability. These results give us a good idea of the model's quality in relation to the data.

![Scores Rn](https://github.com/wilsone24/Optimization-Project/assets/118389840/bfe83748-4967-40ea-81c0-80346283f111)

Afterward, the loss curve was observed to understand how the process improves over iterations. It can be seen that only 175 iterations out of the initially indicated 600 were necessary, and the process stopped there because no substantial changes in the loss function were observed.

![Loss Curve Rn](https://github.com/wilsone24/Optimization-Project/assets/118389840/36d594ee-5625-4f70-ac99-16b59b932826)

The correlation between the variables and the weights assigned in the last layer concerning the output is evident.

![Both_2 RN](https://github.com/wilsone24/Optimization-Project/assets/118389840/c945c06e-04dd-4ba9-b666-b9e1efa53e39)

The last iteration was chosen to observe its score (how good the model is) and to get a good idea of the MSE and RMSE, which allows us to evaluate how close the model's predictions are to the actual values.

| Metric    | Value     |
|-----------|-----------|
| Score    | 0.973224   |
| MSE      | 427736.75  |
| RMSE     | 654.0158   |

The distribution of residuals and predicted values was verified compared to the actual data to evaluate the model's quality more accurately. It was found that the highest density of residuals is centered around 0, and the distribution of predicted values is very similar graphically to that of the actual values. Although there are certain peaks where they differ, the difference is minimal.

![Both_1 RN](https://github.com/wilsone24/Optimization-Project/assets/118389840/2be81d1b-ec71-4ab7-877d-d80109430336)

### Preliminary conclusions

* The model achieved an excellent score, indicating that it is very good and describes the output variable well.

* It is noted that, although the score is very high, there is still some lack of precision in predicting the price given the values of MSE and RMSE.

* The proposed categorical variables have a significant influence on the diamond price behavior.

* The number of layers in the proposed architecture allows for representing much more complex relationships, aiding in capturing a greater variability of the data.

* In other words, the high number of layers and neurons significantly influence the model's quality.

* The predictions align very well graphically with reality, increasing confidence in the model and suggesting it could be implemented in the market.

### How does this model compare to the first one?

* The score was improved, increasing from 0.88 to 0.975, indicating an improvement in the model's quality.

* Regarding the obtained residuals, there is a reduction in their dispersion in the neural network compared to linear regression.

* Metrics such as MSE and RMSE were lower in the neural network than in linear regression, indicating an improvement in accuracy when predicting the data.

* When comparing the regression plots in both the neural network and linear regression to visualize the relationship between the model's prediction and the actual values, a reduction in the variability of the slope, which would be the score, is observed.

* When comparing the distribution plots of predictions and actual values of both models, it can be seen how in the neural network, the predictions more closely resemble the actual values, although not perfectly, but the distribution is very similar.

* All of this suggests that with the neural network architecture, much more complex relationships can be captured than with linear regression.
