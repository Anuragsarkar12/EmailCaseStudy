The project focused on analyzing an email marketing campaign for an e-commerce platform, with the main objective of understanding campaign performance and building a predictive model to optimize future email targeting to maximize user clicks on the embedded link.

Initially, three datasets were loaded containing information about the emails sent, emails opened, and links clicked. Key performance indicators (KPIs) were calculated: the open rate was found to be approximately 10.345%, the click-through rate (CTR) about 2.119%, and the click-to-open rate (CTOR) around 20.48%. Among these, CTR was emphasized as the most important metric because it measures the proportion of all recipients who clicked the link, directly reflecting the campaign’s success in driving user action.

A funnel visualization was created to illustrate user progression through the stages of the campaign—emails sent, opened, and clicked highlighting where user drop-off occurs.

For model building, we created a binary target variable indicating whether a user clicked the link. The hour of sending was cyclically encoded using sine and cosine transformations to preserve its circular nature, while categorical variables such as email text type, email version, user country, and weekday were one-hot encoded. This approach was chosen to ensure compatibility with the XGBoost model and to avoid misleading feature importance values.

The data was split into training and testing sets with stratification to maintain class balance. An XGBoost classifier was trained with parameters optimized for the task, achieving a ROC AUC score of approximately 0.737, demonstrating good predictive capability to identify users likely to click the email link.

Feature importance analysis revealed that factors such as user past purchases, email personalization, user country, weekday, and email length significantly influenced click likelihood. These insights inform targeted strategies to improve engagement.

To estimate the practical impact of the model, a simulation was conducted by selecting the top 20% of users ranked by predicted click probability. This targeted group exhibited a simulated CTR of 6.06%, which is an improvement of 186% compared to the baseline CTR of 2.119%. This substantial increase demonstrates the value of model-driven targeting in enhancing campaign effectiveness.

Several interesting patterns emerged from segment analysis. Users with more past purchases showed higher engagement, indicating loyalty as a key driver. Personalized emails outperformed generic versions, underscoring the importance of relevance. Geographic differences were observed, with French users showing notably higher click rates. Timing also mattered, with emails sent on certain weekdays and hours performing better. Additionally, shorter email texts led to higher click rates, suggesting concise messaging is more effective.

In summary, the project successfully measured baseline campaign performance, developed a predictive model to optimize email targeting, quantified the expected uplift in click-through rates through model application, and uncovered actionable insights about user behavior and campaign factors. These findings provide a clear roadmap for improving future email marketing campaigns by focusing on personalization, segment targeting, timing, and content optimization.

