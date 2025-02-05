﻿# SeaTelChurn

### Business Problem Overview
In the telecom industry, customers are able to choose from multiple service providers and actively switch from one operator to another. In this highly competitive market, the telecommunications industry experiences an average of 15-25% annual churn rate. Given the fact that it costs 5-10 times more to acquire a new customer than to retain an existing one, customer retention has now become even more important than customer acquisition. So we need to analyse telecom industry data and predict high value customers who are at high risk of churn and identify main indicators of churn. In this project, you will analyse customer-level data of a leading telecom firm, build predictive models to identify customers at high risk of churn and identify the main indicators of churn.

### Business objective
The business objective is to predict the churn in the last (i.e. the ninth) month using the features/data from the first three months. To do this task well, understanding the typical customer behaviour during churn will be helpful.

### Understanding Customer Behaviour During Churn
Customers usually do not decide to switch to another competitor instantly, but rather over a period of time (this is especially applicable to high-value customers). In churn prediction, we assume that there are three phases of customer lifecycle :

The ‘good’ phase: In this phase, the customer is happy with the service and behaves as usual.

The ‘action’ phase: The customer experience starts to sore in this phase, for e.g. he/she gets a compelling offer from a competitor, faces unjust charges, becomes unhappy with service quality etc. In this phase, the customer usually shows different behaviour than the ‘good’ months. Also, it is crucial to identify high-churn-risk customers in this phase, since some corrective actions can be taken at this point (such as matching the competitor’s offer/improving the service quality etc.)

The ‘churn’ phase: In this phase, the customer is said to have churned. You define churn based on this phase. Also, it is important to note that at the time of prediction (i.e. the action months), this data is not available to you for prediction. Thus, after tagging churn as 1/0 based on this phase, you discard all data corresponding to this phase.

In this case, since you are working over a four-month window, the first two months are the ‘good’ phase, the third month is the ‘action’ phase, while the fourth month is the ‘churn’ phase.


![heatmap](https://github.com/arduinto/SEATelChurn/assets/142419799/fa550ede-6a94-463c-95e9-ad876a4cb582)

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/10e2987b-7a7f-4b22-a53b-f80b4996a7b6)

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/cbf75b74-e55d-416a-a41b-257edde0611c)

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/952a1e32-5fb5-4c67-aa5f-4fbd2f9d668d)
> ARPU is increasing from 6th to 8th month for churn customers who hasn't taken Night Pack service. And ARPU is getting decreased from 6th to 8th month for night pack users. Means moslty churn customers have stopped their night pack facility

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/72478d0b-e2cd-4b14-9fef-255518eea1cf)
> Significant drop in average revenue in 8th month (churn customers)  for the users who are availing fb_user facility.However ARPU is increasing for churn users who arent avaialing fb_users facility.

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/334dbe37-8b2e-422b-808e-7c6cc833dcac)

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/9880ff1e-4b59-4a5d-b83b-3381e515f517)
> Significant drop in total incoming calls and total outgoing calls for churn customers , however for non churn customer its increasing.

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/65ac23ae-c31e-4586-9e41-d93dfe7ccb72)
> **Total Outgoing mou to incoming mou**
>> As the ratio of outgoing to incoming seem to be getting dropped for churn customer , we can say incoming calls were less in Jun and singificantly increases which cause the ratio to drop.

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/d3b6d357-bc50-4111-b29e-2c6169f79e43)
> Ratio is getting dropped for churn customers

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/4b528206-dd1f-44c4-82f4-b5f40f891763)
> **Std outgoing mou to incoming mou**
>> The sharp decline in MOU among churn customers suggests that as they approach the point of churning, their usage decreases significantly. This could indicate dissatisfaction or reduced engagement with the service. The stable MOU for non-churn customers indicates consistent usage patterns, suggesting a steady engagement with the service.

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/d28e0d91-750d-4b6f-a89b-773920d3bfdf)
> Churn customers exhibit a significant decrease in their total amount spent over the three-month period, suggesting a gradual disengagement from the service before ultimately leaving. In contrast, non-churn customers maintain stable spending levels, reflecting consistent and possibly satisfied usage.

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/d62141e0-5f97-4078-9edb-694bbbd51b9e)
> Churn customers exhibit a marked decrease in total volume from June to August, suggesting a gradual disengagement from the service. In contrast, non-churn customers maintain a stable total volume, indicating continuous and consistent usage.

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/04df721a-47b7-4c3d-b2a5-676b9cfe8286)


![image](https://github.com/arduinto/SEATelChurn/assets/142419799/29dc8db5-608c-4ce9-bd42-0078e0c1a6df)
> All principal components are correlated with each other

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/da1b4be6-1dc7-4eaa-ad24-fff7ffaccd7b)
> **Trade-off between Recall and Specificity:**
> - There is a trade-off between recall and specificity. As the threshold increases, recall >decreases while specificity increases. This means the model gets better at avoiding false >positives, but could miss some true positives.

>**Optimal Threshold:**
> - Choose the optimal threshold depending on business needs. If the primary goal is to >identify as many customers as possible who will churn (minimize churn), you may want to use a >lower threshold to ensure high recall. However, if the cost of false positives is high, you >may want to use a higher threshold to increase specificity.

>**Stable Accuracy:**
> - Model accuracy tends to stabilize after a certain threshold (around 0.5). This shows that >the model has a good balance between recall and specificity around this threshold.

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/2c0bbe28-6873-4e61-9995-adf3ecf47109)

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/c7242947-f8ea-46b7-b118-5b3cee480e87)

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/3dfde1a1-1f7a-4746-90d5-c39d28f526f9)

### Interpretable model for Business understanding: Logistic Regression

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/b66f7ffb-098e-4f0c-9964-7cf4f986ecd1)
> At low threshold values, recall is high but specificity is low, meaning the model tends to detect all positive cases but also provides many false positive predictions At a high threshold value, specificity is high but recall is low, meaning the model tends to be correct in identifying negative cases but misses many positive cases. Accuracy peaks in the middle, when there is a balance between recall and specificity.

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/0bab5f0b-e159-420b-bc21-a8a8f230b5b5)

>### Insights and Summary:

>1. **High Importance Features:**
>   - **`total_ic_mou_8` (15.9%)**: This feature, representing the total incoming minutes of >usage in month 8, is the most significant factor in predicting churn. Customers with high or >low usage might be more likely to churn.
>   - **`days_since_last_rech` (14.6%)**: The number of days since the last recharge is also >highly influential. Customers who haven't recharged recently might be more prone to churn.
>   - **`roam_og_to_ic_mou_8` (12.3%)**: Roaming outgoing to incoming minutes of usage in month >8 is another critical factor, suggesting that roaming behavior affects churn likelihood.

>2. **Moderate Importance Features:**
>   - **`last_day_rch_amt_8` (10.2%)**: The recharge amount on the last day of month 8 is a >moderately important feature, indicating that recent recharge behavior impacts churn.
>   - **`av_rech_amt_data_8` (9.7%)**: The average recharge amount for data in month 8 shows a >significant influence, highlighting the role of data usage in customer retention.
>   - **`aon` (4.2%)**: Age on network, representing the duration of the customer's >relationship with the service provider, is a notable feature.
>   - **`tot_og_to_ic_mou_8` (5.0%)**: Total outgoing to incoming minutes of usage in month 8 >also plays a role, suggesting that overall call behavior is important.

>3. **Low Importance Features:**
>   - **`total_rech_num_7` (2.9%)**: The number of recharges in month 7 has a lower but still >relevant impact on churn prediction.
>   - **Other Features (2-5% range)**: Features like `isd_ic_mou_8`, `date_of_last_rech_dow_8`, >and various average differences in minutes of usage contribute less significantly but are >still part of the model's decision-making process.

### Random Forest Interpretable Model

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/68aab195-8d20-4cc3-b3b1-1b18863d264f)

![image](https://github.com/arduinto/SEATelChurn/assets/142419799/088c4782-a760-4f04-8d40-43d805bd3134)
> ### Summary and Insights:

>1. **Most Important Features:**
>   - **Total Incoming Minutes of Usage (total_ic_mou_8) (14.3%)**: This is the most >significant feature. It shows that how much time customers spend on incoming calls in the >last month is a strong indicator of whether they will leave the service.
>   - **Total Outgoing Minutes of Usage (total_og_mou_8) (13.9%)**: Similarly, the total time >spent on outgoing calls is also very important. This highlights that both incoming and >outgoing call activity are critical in understanding customer behavior.

>2. **Moderately Important Features:**
>   - **Total Recharge Amount Difference (tot_amt_avgdiff8) (8.2%)**: This feature shows the >difference in total recharge amounts over time. Significant changes in recharge behavior can >indicate potential churn.
>   - **Total Recharge Amount in Last Month (total_rech_amt_8) (7.7%)**: The total amount >customers recharged in the last month is another key indicator. Consistent or large recharges >are associated with customer retention.
>   - **Total Outgoing to Incoming Call Minutes (tot_og_to_ic_mou_8) (7.4%)**: This represents >the balance between outgoing and incoming calls, further emphasizing the importance of call >activity patterns.

>3. **Less Important but Still Relevant Features:**
>   - **Days Since Last Recharge (days_since_last_rech) (5.7%)**: How recently customers >recharged is important but less so compared to the total amount recharged and call minutes.
>   - **Other Usage Metrics**: Features like the total amount recharged on a specific day, the >average difference in recharge amounts, and specific call behaviors (local and roaming calls) >each contribute between 4% to 5.5% to the prediction. These are important but secondary to >the primary call and recharge metrics.

As we can see both logistic regression and random forest classifier provides us similar predictor variables for making business decision to decrease or stop customer from churning who are likely to churn. Telcom company can introduce promotional offers to those customers who are likely to churn. Also, we have implemented all our models for high value customers. Now, Business people can make decision on those most important preidctor variables. Since, we have use different models for predicting these feature variable and difference techniques for feature selection we are getting similar predicting variable but order is slightly different. Hence we recommend  Telecom company to consider these feature variables which are strong indicators to manage customer churn.
