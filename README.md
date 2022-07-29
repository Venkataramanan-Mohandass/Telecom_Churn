# Problem Statement


### Introduction

In the telecom industry, customers are able to choose from multiple service providers and actively switch from one operator to another. In this highly competitive market, the telecommunications industry experiences an average of 15-25% annual churn rate. Given the fact that it costs 5-10 times more to acquire a new customer than to retain an existing one, customer retention has now become even more important than customer acquisition. For many incumbent operators, retaining high profitable customers is the number one business goal. To reduce customer churn, telecom companies need to predict which customers are at high risk of churn.


### Business Understanding

There are two main models of payment in the telecom industry:
1) In the postpaid model, when customers want to switch to another operator, they usually inform the existing operator to terminate the services, and you directly know that this is an instance of churn. Here, the customers pay a monthly/annual bill after using the services.
2) In the prepaid model, customers who want to switch to another network can simply stop using the services without any notice, and it is hard to know whether someone has actually churned or is simply not using the services temporarily e.g., someone may be on a trip abroad for a month or two and then intend to resume using the services again. Here, the customers pay/recharge with a certain amount in advance and then use the services.

Thus, churn prediction is usually more critical and non-trivial for prepaid customers, and the term ‘churn’ should be defined carefully. Also, prepaid is the most common model in India and Southeast Asia, while postpaid is more common in Europe in North America. This project is based on the Indian and Southeast Asian market.


### Churn definition

There are various ways to define churn, such as:
1) Revenue-based churn: Customers who have not utilised any revenue-generating facilities such as mobile internet, outgoing calls, SMS, etc., over a given period of time. One could also use aggregate metrics such as ‘customers who have generated less than INR 4 per month in total/average/median revenue’. The main shortcoming of this definition is that there are customers who only receive calls/SMSes from their wage-earning counterparts, i.e. they don’t generate revenue but use the services. For example, many users in rural areas only receive calls from their wage-earning siblings in urban areas.
2) Usage-based churn: Customers who have not done any usage, either incoming or outgoing, in terms of calls, internet etc., over a period of time. A potential shortcoming of this definition is that when the customer has stopped using the services for a while, it may be too late to take any corrective actions to retain them. For e.g., if you define churn based on a ‘two-months zero usage’ period, predicting churn could be useless since by that time the customer would have already switched to another operator.

In this project, you will use the usage-based definition to define churn.


### High-value churn

In the Indian and the Southeast Asian market, approximately 80% of revenue comes from the top 20% customers i.e., high-value customers. Thus, if we can reduce churn of these customers, we will be able to significantly reduce the revenue leakage.

In this project, you will define high-value customers based on a certain metric and predict churn only on high-value customers.


### Data Understanding

The dataset contains customer-level information for a span of four consecutive months - June, July, August and September. The months are encoded as 6, 7, 8 and 9, respectively. 


### Business Objectives

1) Analyse customer-level data and build predictive models, to identify customers at high risk of churn and, identify the main indicators of churn.
2) Understand the typical customer behaviour during churn.
3) To predict the churn in the last i.e. the ninth month using the data/features from the first three months.


### Understanding customer behaviour during churn

Customers usually do not decide to switch to another competitor instantly, but rather over a period of time (this is especially applicable to high-value customers). In churn prediction, we assume that there are three phases of customer lifecycle:
1) The ‘good’ phase: In this phase, the customer is happy with the service and behaves as usual.
2) The ‘action’ phase: The customer experience starts to sore in this phase, for e.g. he/she gets a compelling offer from a  competitor, faces unjust charges, becomes unhappy with service quality. In this phase, the customer usually shows different behaviour than the ‘good’ months. Also, it is crucial to identify high-churn-risk customers in this phase, since some corrective actions can be taken at this point such as, matching the competitor’s offer or improving the service quality.
3) The ‘churn’ phase: In this phase, the customer is said to have churned. You define churn based on this phase. Also, it is important to note that at the time of prediction i.e. the action months. This data is not available to you for prediction thus, after tagging churn as 1 or 0 based on this phase, you discard all data corresponding to this phase.

In this project, since you are working over a four-month window, the first two months are the ‘good’ phase, the third month is the ‘action’ phase, while the fourth month is the ‘churn’ phase.



*** Problem Statement given by IIIT-B with upGrad ***