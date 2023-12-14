# Customer Analysis in the Marketing Strategy of Huawei: A Social Network Analysis Approach
Social media analysis helps Huawei better understand their targeted audience, evaluate the impact of marketing campaigns and enhance their business. In this report, I used social network analysis techniques to study the Huawei's customer connecting pattern. This report is based on the data from Huawei Social Network Data on Kaggle platform. Data Link: https://www.kaggle.com/datasets/andrewlucci/huawei-social-network-data

### Exploratory Data Analysis
I initialized the analysis by exploring the properties of these three platform, including  diameter, density, clustering coefficient and average degree.

#### Network Fundamental Features
| Metric        | Facebook      | Instagram  | Twitter |
| ------------- |:-------------:| -----:| --------:|
| Number of Vertices | 1000 | 1000 | 1000 |
| Number of Edges     | 50153      |   4933 | 250315|
| Diameter | 3      |   5 | 2|
| Density | 0.1004      |    0.0098 | 0.5011|
| Clustering Coefficient | 0.1002      |    0.0083 | 	0.5012|
| Average Degree | 	100.306  |   	9.866  | 	500.63 |


![Degree Distribution of FBNetwork](https://github.com/peijin0405/Customer-Analysis-in-the-Marketing-Strategy-of-Huawei-A-Social-Network-Analysis-Approach/assets/89746479/1634416e-ee95-44d9-a0a7-0f1ece483fc7)

![Degree Distribution of InsNetwork](https://github.com/peijin0405/Customer-Analysis-in-the-Marketing-Strategy-of-Huawei-A-Social-Network-Analysis-Approach/assets/89746479/1ab17453-9e34-4594-9c3e-c70cd2b33385)

![Degree Distribution of TwitterNetwork](https://github.com/peijin0405/Customer-Analysis-in-the-Marketing-Strategy-of-Huawei-A-Social-Network-Analysis-Approach/assets/89746479/8fb47c95-fe7b-4c6f-9c1c-da2db5714da7)


### Centrality Analysis
Centrality Analysis aims to answer the question "What characterizes an important vertex?"  Between centrality measures the extent to which a node acts as a bridge or intermediary between other nodes in the network. Nodes with high betweenness centrality are those that lie on many of the shortest paths between pairs of other nodes. This can make them critical nodes in terms of network structure and function, as their removal can lead to the fragmentation or breakdown of the network. 

![Correlation of Betweenness Centrality and Degree Centrality  (Facebook)](https://github.com/peijin0405/Customer-Analysis-in-the-Marketing-Strategy-of-Huawei-A-Social-Network-Analysis-Approach/assets/89746479/3cfe59dc-b514-453c-8c30-e2eb3a2c2908)

![Correlation of Betweenness Centrality and Degree Centrality  (Twitter)](https://github.com/peijin0405/Customer-Analysis-in-the-Marketing-Strategy-of-Huawei-A-Social-Network-Analysis-Approach/assets/89746479/7549ff91-cc33-45bc-9a25-6696487533f4)

![Correlation of Betweenness Centrality and Degree Centrality (Instagram)](https://github.com/peijin0405/Customer-Analysis-in-the-Marketing-Strategy-of-Huawei-A-Social-Network-Analysis-Approach/assets/89746479/80bf9b2a-64f1-4335-a2c4-3bea29bd1ff1)

Largest ego network is representative for the patterning of the social network in which it is located. As revealed in the previous exploratory data analysis, it can be seen that the Twitter and Facebook network are highly interconnected and there are many closely-knit communities within the network. The Instagram network is a sparse and disconnected network.

![Largest Ego Network in FacebookNetwork](https://github.com/peijin0405/Customer-Analysis-in-the-Marketing-Strategy-of-Huawei-A-Social-Network-Analysis-Approach/assets/89746479/4822f328-c164-44bf-82ca-4be60a5f6cd1)

![Largest Ego Network in InstagramNetwork](https://github.com/peijin0405/Customer-Analysis-in-the-Marketing-Strategy-of-Huawei-A-Social-Network-Analysis-Approach/assets/89746479/3d04aca5-b5fb-4cad-8fe8-f5eea8c85508)

![Largest Ego Network in TwitterNetwork](https://github.com/peijin0405/Customer-Analysis-in-the-Marketing-Strategy-of-Huawei-A-Social-Network-Analysis-Approach/assets/89746479/87289d85-8df4-4c38-9281-2a2a8d2fd828)

### Exponential Random Graph Models
Before conducting the ERGM analysis, I used the **"rethnicity" package**  to predict the race of 1,000 users by their last names. According to the prediction results, out of 1,000 users, there are 502 Asian people, 166 Black people, 113 Hispanic people and 219 White people. Huawei, as a Chinese brand, has a large proportion of Asian users, so there are more comments on social media on topics related to Huawei products/services come from Asian consumers.

![Race Prediction for the Users](https://github.com/peijin0405/Customer-Analysis-in-the-Marketing-Strategy-of-Huawei-A-Social-Network-Analysis-Approach/assets/89746479/6e527106-151c-47a1-99ea-191933debf7c)

Then, using race as the attributes of the network, I used ERGM to analyze the three platforms separately.

![ERGM Results for FacebookNetwork](https://github.com/peijin0405/Customer-Analysis-in-the-Marketing-Strategy-of-Huawei-A-Social-Network-Analysis-Approach/assets/89746479/acb36e93-e5b6-4100-9bfc-5435532f4c44)
ERGM Results for FacebookNetwork

![ERGM Results for InstagramNetwork](https://github.com/peijin0405/Customer-Analysis-in-the-Marketing-Strategy-of-Huawei-A-Social-Network-Analysis-Approach/assets/89746479/a3dd93cd-1704-4151-aa68-5608953108ca)
ERGM Results for InstagramNetwork

![ERGM Results for TwitterNetwork](https://github.com/peijin0405/Customer-Analysis-in-the-Marketing-Strategy-of-Huawei-A-Social-Network-Analysis-Approach/assets/89746479/3d486111-50d5-4721-9cea-88e9c010cbf1)
ERGM Results for TwitterNetwork

### Conclusion
Based on the analysis of network data from the three platforms, we could learn that the Twitter network and Facebook network are highly interconnected and there are many closely-knit communities within the Twitter network. Information spreads quickly in both communities, and because of the presence of close-knit communities, discussions about new products/services are very lively. Therefore, Twitter and Facebook are good platforms to promote information about the latest product/service launches, as well as events that have recently taken place. **Twitter could be the best platform to launch a marketing campaign.**

Compared to users on Twitter and Facebook, the Instagram has the lowest clustering coefficient and the lowest average degree, indicating that it is a sparse and disconnected network. Information is less mobile on Instagram.
According to the results of Exponential Random Graph Models, we found that race of an individual has an impact on the formation of edges between nodes. Specifically, on Instagram, the race of White has a negative impact on the number of his/her connections. On Twitter, the race of Black has a negative impact on the number of his/her connections. However, the formation of a tie is not based on whether two people are from the same race. Such results do not necessarily mean that the Huawei community on Twitter and Instagram is racially biased, because, as a Chinese brand with a strong national spirit, Huawei is also influenced by countries’ relations and the international situation. Moreover, the results are also influenced by the number of different ethnic users on different platforms. Future research could further validate the study's findings by controlling for these variables. 


