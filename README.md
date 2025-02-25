
# Candy Distribution Analytics Report

## Executive Summary
This project analyses sales performance, product profitability, factory production performance, and shipping analysis for a national U.S. candy distributor. The dataset includes product details, factory locations, and sales transactions from 2021 to 2024.

**Key Findings:**

***Sales Performance***

- Sales have consistently grown since 2021, with a seasonal peak in Q4 each year.

- The Pacific region leads in sales growth, showing a 38% YoY increase in 2024, while the Gulf region lags significantly.

- Chocolate products dominate sales, contributing nearly 80% of total revenue, with Scrumdiddlyumptious and Triple Dazzle Caramel being the top performers.

***Product Profitability***

- The Chocolate division leads in profitability with a 67% profit margin, while the Sugar division maintains a solid 58%.

- Kazookies contributes 0% to gross profit, indicating the need for repositioning or discontinuation.

- The most profitable factory, Lot’s O’ Nuts, generates $53K in gross profit, whereas Sugar Shack and The Other Factory produce no profit.

***Factory Production Performance***

- Lot’s O’ Nuts and Wicked Choccy’s are the most efficient factories, showing strong profit margins and cost-to-sales ratios.

- The Other Factory has an unsustainable 88.13% cost-to-sales ratio, requiring urgent operational improvements or restructuring.

- Sugar Shack and Secret Factory have moderate profitability but require cost optimisation to improve efficiency.

***Shipping Analysis***

- The Pacific and Atlantic regions have the highest shipping volumes, aligning with strong sales performance.

- 3-5 day and 5-7 day shipping modes dominate across all regions, indicating cost-conscious customer preferences.

- Next-day and same-day shipping are more common in high-volume regions, suggesting demand for faster deliveries in urban centers.

**Actionable Recommendations:**

- Improve operational efficiency at Sugar Shack and Secret Factory while evaluating The Other Factory for restructuring or repurposing as The Other Factory has a high cost-to-sales ratio.

- Invest in increasing production at Lot’s O’ Nuts and Wicked Choccy’s to maximise profitability due to its large contribution of gross profit.

- Reevaluate Kazookies strategy due to its lack of profitability and consider expanding high-margin products.

- Optimise shipping routes and consider expanding next-day and same-day shipping options in high-demand regions to improve customer experience, if costs are efficient.

- Monitor Market Trends by conducting deeper market analysis for the Gulf region to improve sales and explore alternative product strategies.

This analysis provides valuable insights into optimising business operations, improving profitability, and strengthening market presence. Implementing these recommendations will drive sustained growth and operational excellence.

## Table of Content

[1. Overview](#1-overview)  
[2. Data Model](#2-data-model)  
[3. Insights](#3-insights)  
[4. Actionable Recommendations](#4-actionable-recommendations)  
[5. Conclusion](#5-conclusion)  


## 1. Overview
**1.1. Problem Statement**

This project focuses on analysing sales performance, product profitability, factory production efficiency, and shipping logistics for a national US candy distributor. The dataset covers a wide range of variables, including customer and factory locations, sales transactions, production data, and shipping type, requiring in-depth analysis to identify inefficiencies and opportunities for improvement across multiple areas of the business.

**1.2. Objective**

To address these challenges, this analysis focuses on:  

- Sales Performance: Identifying the most profitable regions and understanding sales distribution across product divisions.
- Product Profitability: Analysing profit margins and the relationship between production costs and sales prices across different product categories.
- Factory Production Performance: Assessing factory production efficiency and cost management to enhance operational effectiveness.
- Shipping Analysis: Examining shipping mode preferences and their impact on customer satisfaction across different states.


## 2. Data Model

**2.1. Relationship and Data Schema**

![Image](https://github.com/user-attachments/assets/efa3a0cf-c60b-4ad7-a090-6eeab4b9936e)

The model follows a **star schema** design, where a central fact table connects to multiple dimension tables. This structure optimises query performance and simplifies business analysis.

**2.2. Fact Table**
- **Candy_Sales**: Contains transactional data such as sales, costs, and gross profit.


| Column Name       | Data Type | Description                                      |
|-------------------|-----------|--------------------------------------------------|
| Row ID            | Text           | Unique identifier for each row                    |
| Order ID          | Text           | Unique order identifier                      |
| Order Date        | Date           | The date when the order was placed                |
| Ship Date         | Date           | The date when the order was shipped               |
| Ship Mode         | Text           | The shipping method used|
| Customer ID       | Text           | Unique identifier for the customer                |
| Country/Region    | Text           | The country where the order was placed           |
| City              | Text           | The city where the order was placed                |
| State/Province    | Text           | The state or province where the order was placed |
| Postal Code       | Text           | The postal code of the shipping address            |
| Division          | Text           | The product category (e.g., Chocolate)              |
| Region            | Text           | The geographic region (e.g., Pacific, Atlantic)|
| Product ID        | Text           | Unique identifier for the product                 |
| Product Name      | Text           | The name of the product                        |
| Sales             | Decimal Number | The total sales amount for the order            |
| Units             | Whole Number   | The number of units sold in the order               |
| Gross Profit      | Decimal Number | The profit earned before deducting costs          |
| Cost              | Decimal Number | The total cost of the products in the order      |


**2.3. Dimension Tables:**

- **Candy_Products:**   Stores product-related attributes such as product name, unit cost, and unit price.

| Column Name       | Data Type | Description                                      |
|-------------------|-----------|--------------------------------------------------|
| Division          | Text    | The product category (e.g., Chocolate, Sugar, Other) |
| Product Name      | Text    | The name of the product                        |
| Factory           | Text    | The factory that produces the product          |
| Product ID        | Text   | Unique identifier for each product            |
| Unit Price        | Decimal Number     | The price of a single unit of the product     |
| Unit Cost         | Decimal Number    | The cost to produce a single unit of the product |

- **Candy_Factories:** Contains factory details, including factory name and geographical coordinates (latitude, longitude).  

| Column Name       | Data Type | Description                                      |
|-------------------|-----------|--------------------------------------------------|
| Factory           | Text   | The name of the factory.                        |
| Latitude          | Decimal Number     | The latitude coordinate of the factory location |
| Longitude         | Decimal Number    | The longitude coordinate of the factory location |

- **DateTable:** Supports time-based analysis with a date column for filtering and aggregations.  

| Column Name       | Data Type | Description                                      |
|-------------------|-----------|--------------------------------------------------|
| Date           | Date   | A custom table manually created by DAX |


## 3. Insights
Before conducting the analysis, the dataset was cleaned and transformed using Power Query in Power BI. This process included handling missing values, removing duplicates, removing unnecessary columns, standardising formats, and creating calculated columns where necessary. The cleaned data was then loaded into Power BI for further analysis and visualisation. For a detailed breakdown of the data cleaning steps, please refer to the Workflow Report.  

**3.1. Sale Performance** 

![Image](https://github.com/user-attachments/assets/133fa527-4b6a-497d-a178-6adc2316b0ed)

- Sales have shown consistent growth since early 2021, demonstrating a positive trend across all regions and highlighting the company's resilience. The sales pattern is seasonal, peaking each Q4 from 2021 to 2024. The Pacific region stands out, consistently leading in sales growth compared to other regions.


![Image](https://github.com/user-attachments/assets/b6674915-586b-4f1e-ab24-8bd3770542db)

  
- From 2021 to 2024, total sales reached $142K, highlighting strong revenue and sustained demand for our products. With 39K units sold, this reflects high sales volume and strong customer engagement.

![Image](https://github.com/user-attachments/assets/f7d8c1d1-0f33-418d-baff-f9ef20ab2cac)

- Year-over-Year (YoY) sales growth has steadily increased since 2021, with a notable 27.43% growth in 2024 compared to 2023, indicating strong performance and significant improvement compared to the previous year.

![Image](https://github.com/user-attachments/assets/c8d7a5b1-c506-4912-915d-769f7fe1c330)

- Comparing 2024 to 2023 by region, the Pacific region shows a strong YoY sales growth of around 38%, outpacing other regions by about 20%. This indicates a significant increase in sales for the Pacific region, which is a positive signal for investors, stakeholders, and management.
- The Gulf region displays more volatility, with peaks and declines in sales, possibly due to market fluctuations or external factors. In contrast, the Pacific, Atlantic, and Interior regions show more stability, though their slower growth rates suggest a steady but less dramatic demand for products.

![Image](https://github.com/user-attachments/assets/44039c87-7d7c-467c-b323-119808754619)

- The Pacific region has been a consistent top performer, contributing around $35K in sales and 9.5K units annually from 2021 to 2024. It consistently outperforms the average across all regions, demonstrating strong demand and a loyal customer base, making it a key driver of overall sales growth.
- The Atlantic region follows closely behind the Pacific region and shows potential for further growth with focused marketing strategies that could help capture a larger market share.
- The Interior region exhibits moderate sales performance, but there are clear opportunities for growth. With more strategic initiatives, such as targeted marketing and product innovation, the region could increase its market share and boost overall performance.
- The Gulf region faces challenges with the lowest unit sales, consistently performing below half of the average. Its sales trend has remained flat with no noticeable growth, even declining to its lowest point in January 2024, indicating potential issues such as low market demand or limited reach.

![Image](https://github.com/user-attachments/assets/3cf201d3-fbc9-4243-8d6f-e0ffaa7315b7)

- The top five products consistently making up the highest sales across all regions from 2021 to 2024 are Triple Dazzle Caramel, Scrumdiddlyumptious, Milk Chocolate, Nutty Crunch Surprise, and Fudge Mallows.
- The Chocolate division is the clear leader in sales, contributing nearly 80% of total sales in all regions, demonstrating its central role in the company's revenue generation.
- Scrumdiddlyumptious and Triple Dazzle Caramel are key contributors to gross profit, each representing around 20% of total profits, solidifying their importance in the product lineup.
- On the other hand, Kazookies contributes 0% to gross profit, likely due to low-margin pricing or poor sales volume. This suggests the need for a reevaluation of its positioning or sales strategy.
- The Sugar division has a minimal share of the company’s profits, while the Chocolate division remains the primary source of profitability. The Other division also contributes less, further reinforcing the need to focus on the Chocolate division for future growth and profitability

**3.2. Product Profitability**

![Image](https://github.com/user-attachments/assets/04b22042-785e-449c-82ce-5472840da49a)

- The average profit margin has steadily increased over the years, with a notable rise between 2021 and 2022 indicating a significant shift in business strategy. Since then, it has stabilised at a high level, with the current overall average profit margin at 66.51%. 

![Image](https://github.com/user-attachments/assets/9d259488-e542-4714-9436-fb76f8a56c05)

- From 2021 to 2024, the Chocolate division is the top performer with the highest profit margin, surpassing the average. The Sugar division follows with an impressive profit margin of over 58% in 2024.
- Both Chocolate and Sugar divisions are profitable, with Chocolate showing strong growth and Sugar maintaining a high margin. However, Chocolate may face slower growth, while Sugar needs to sustain its margin without complacency.
- The Other division saw significant profit margin volatility, with a sharp drop in 2022 followed by recovery. This shows resilience, likely due to cost-cutting or improved sales strategies.
- The volatility in the Other division suggests potential market risks. Identifying the causes of the 2022 dip and addressing them through better strategic planning could help reduce future instability.

![Image](https://github.com/user-attachments/assets/43553983-746c-4e4f-8fad-d0745c8aec15)

- The Chocolate division has the highest average profit margin at 67%, indicating strong financial performance and efficiency. While the Sugar division also shows strong profitability at 58%, though slightly lower than Chocolate. However, The Other category has a significantly lower profit margin of 38%, suggesting either higher costs, lower pricing power, or operational inefficiencies.
- While Chocolate shows the highest margin, maintaining this growth might be a challenge. The Sugar division should focus on sustaining its margin, and the Other division may need strategic improvements to enhance profitability.
  
![Image](https://github.com/user-attachments/assets/52da1d8c-5ab5-453d-a9fb-fb114250616b)

- Lot’s O’ Nuts is the most profitable factory, generating $53K in gross profit from 2021 to 2024. Its strong performance presents opportunities for optimisation or expansion to further increase production capacity and profits.
- Wicked Choccy’s follows as the second most profitable factory, with $36K in gross profit. With solid profits, it could benefit from investments in capacity expansion or efficiency improvements to boost its contribution.
- Secret Factory has limited profitability, contributing only $4K in gross profit. This suggests inefficiencies or lower-margin products. A cost-benefit analysis is needed to identify potential adjustments to improve performance.
- The Other Factory and Sugar Shack are not generating profit, each showing $0K in gross profit. The company should investigate possible operational inefficiencies, low production volumes, or market challenges. If underperformance persists, restructuring or repurposing may be necessary.

![Image](https://github.com/user-attachments/assets/18f5a1d9-67cb-4f04-8035-66565bbc84c8)

- Five key products—Nutty Crunch Surprise, Scrumdiddlyumptious, Fudge Mallows, Triple Dazzle Caramel, and Milk Chocolate—drive the majority of sales with strong profit margins. Their high demand and well-managed cost structures make them valuable contributors to overall profitability, and expanding production or market presence could lead to even higher financial gains.
- Everlasting Gobstopper boasts the highest profit margin at 80%, though it does not contribute significantly to overall sales. Its impressive cost-to-price ratio makes it a prime candidate for increased production and marketing to further boost revenue.
- From 2021 to 2024, the total gross profit across all products is $93,443, indicating solid financial health and effective cost management, while maintaining strong pricing strategies.
- Total sales volume amounts to $141,784, reflecting strong revenue generation. However, ensuring that sales growth aligns with profitability goals is key to long-term success.
- There is a correlation between product margins and revenue, as the highest-selling products tend to have strong profit margins. Continued investment in these high-margin products will be essential for sustained growth.

**3.3. Factory Production Performance**

![Image](https://github.com/user-attachments/assets/b4341676-9acd-4605-a4f0-97ff80eda0a5)

- From 2021 to 2024, Lot’s O’ Nuts leads in cost efficiency with a 30.87% cost-to-sales ratio, indicating optimised production and higher profitability compared to other factories. The company may consider expanding production to capitalise on this efficiency.
- Wicked Choccy’s shows a competitive cost-to-sales ratio of 34.87%, reflecting strong cost control and solid financial health. Maintaining this efficiency while scaling production could enhance profitability.
- Both Lot’s O’ Nuts and Wicked Choccy’s contributed significantly to the highest gross profit in the previous analysis.
- Sugar Shack and Secret Factory have moderate cost-to-sales ratios of 45.14% and 49.41%, respectively. These factories have room for improvement, and reviewing operational processes or renegotiating supplier contracts could help reduce costs.
- The Other Factory faces significant challenges with an 88.13% cost-to-sales ratio, indicating that nearly all sales revenue goes into covering production costs. A major operational overhaul may be necessary, or the company could consider consolidation or shutdown for cost-effectiveness.

![Image](https://github.com/user-attachments/assets/3310cfef-8184-44c1-899c-796d7573fe20)

- With the highest gross profit and a low cost-to-sales ratio, Lot’s O’ Nuts is the standout performer. This balance indicates it’s the most profitable and efficient factory. Investing in expanding its capacity or diversifying its product lines could amplify its success. 
- Wicked Choccy’s appears to be a reliable contributor to overall company performance, positioned with a reasonable cost-to-sales ratio and solid gross profit. Continued investment in maintaining this balance could keep it competitive. 
- With one of the highest cost-to-sales ratios and minimal gross profit, it is clear that the Other Factory is underperforming significantly. Immediate action is needed to either drastically reduce costs or reconsider its role in the company’s production network. 
- Sugar Shack and Secret Factory have a middling performance, indicating potential but also clear areas for improvement. By focusing on streamlining operations and reducing waste, there’s a pathway to improved profitability to better profitability for both factories.

![Image](https://github.com/user-attachments/assets/d9073b37-0441-44ec-a6b3-ad2c98bfa416)

- Over the analysed period from 2021 to 2024, Lot’s O’ Nuts displays a consistent upward trend in gross profit. This sustained growth suggests strong market demand for its products and effective operational management. Further scaling production could leverage this positive trend. 
- Similar to Lot’s O’ Nuts, Wicked Choccy’s shows a steady increase in gross profit, reinforcing its role as a key player in the company’s success. Continued focus on innovation and efficiency will likely sustain this growth. 
- A flat gross profit line for The Other Factory indicates persistent struggles. Without significant changes, it is unlikely this factory will contribute meaningfully to the company’s financial health. 
- Secret Factory and Sugar Shack demonstrate inconsistent profit trends, suggesting potential market volatility or internal inefficiencies. Identifying the causes of these fluctuations could stabilise and improve their performance.
- Lot’s O’ Nuts and Wicked Choccy’s are the Company’s Backbone — Together, these two factories contribute the majority of gross profit, reflecting their efficient operations and strong market position. Prioritising resource allocation here could provide the best return on investment. 


**3.4. Shipping Analysis**

![Image](https://github.com/user-attachments/assets/ccdc9fb9-56d4-47d5-becc-442c7eb66ef5)

- Over the years, the Chocolate Division has seen a steady increase in shipping volume, with all shipping modes following an upward trend. This indicates growing demand, suggesting that production and logistics need to keep pace to ensure timely deliveries. 
- While the Other Division’s shipping volume has generally increased, there are noticeable fluctuations, particularly in recent years. These variations may be driven by seasonal demand shifts, supply chain disruptions, or changes in customer preferences. 
- The Sugar Division exhibits a much lower shipping volume compared to the other divisions. There is a noticeable peak followed by a decline, indicating possible supply chain inconsistencies or fluctuating demand in this segment. 
- While 3-5 day and 5-7 day shipping modes dominate across all divisions, next-day and same-day options are less frequent. This suggests that most customers prioritise cost savings over speed, or that faster shipping options are limited due to logistics constraints.

![Image](https://github.com/user-attachments/assets/df2c876f-eda0-4921-a7e8-a477e0597b6c)

- The Pacific region leads in shipping volume, with a strong mix of 3-5 day, 5-7 day, and next-day shipping. This suggests a high concentration of customers or major distribution hubs in this area. 
- The Atlantic region has a slightly lower shipping volume than the Pacific, but still maintains a strong presence across all shipping modes. Optimising shipping routes here could help reduce costs while maintaining efficiency. 
- The Interior region lags behind Pacific and Atlantic in terms of shipping volume, possibly due to fewer distribution centers or lower customer density. Expanding logistics operations here could enhance service levels. 
- The Gulf region records the lowest shipping volume, indicating either a smaller customer base or limited distribution capabilities. Understanding demand patterns here could help determine whether expansion is viable. 
- In every region, 3-5 day and 5-7 day shipping modes account for the majority of shipments. This aligns with cost-conscious customer preferences but also highlights potential areas for improving faster shipping options. 
- The Pacific and Atlantic regions see a higher proportion of next-day and same-day shipments, likely due to the presence of major urban centers with better logistics infrastructure. 

![Image](https://github.com/user-attachments/assets/b5e0955d-38da-4e35-a98e-fdbf65dad1aa)
- The U.S. dominates in terms of shipping volume, with various regions contributing significantly to total shipments. This suggests a well-established customer base and distribution network. 
- While the U.S. leads in shipments, Canada also has a notable presence, indicating strong cross-border trade. Ensuring efficient customs processing and logistics partnerships could further streamline shipping to Canada. 
- Different sales locations exhibit unique shipping mode preferences. Some areas rely heavily on standard shipping (3-5 days, 5-7 days), while others demand faster options like next-day delivery. Analysing these preferences could help tailor shipping strategies. 
- Locations with major metropolitan areas see a greater proportion of next-day and same-day shipments, indicating demand for faster deliveries in densely populated regions. 



## 4. Actionable Recommendations 

- Reevaluate Production Strategy for The Other Factory — Considering its high costs and low returns, a deep dive into The Other Factory’s operations is crucial. This could involve exploring alternative suppliers, investing in new technology, or potentially relocating production. 

- Leverage Strengths of Top Factories — Lot’s O’ Nuts and Wicked Choccy’s are clearly outperforming the rest. Investing in these facilities, whether through expanding capacity or exploring new product lines, could capitalise on their existing strengths. 

- Explore Cost Reduction Techniques — For Sugar Shack and Secret Factory, exploring lean manufacturing techniques or renegotiating key supply contracts could reduce the cost-to-sales ratio and improve profitability. 

- Investigate Market Demand and Product Fit — For factories like Sugar Shack and Secret Factory, understanding whether the market demand aligns with what they are producing could highlight opportunities to pivot to more profitable products. 

- Improve Cross-Factory Knowledge Sharing — Sharing operational best practices from top-performing factories with lower-performing ones might bring up overall efficiency and profitability across the board.
   
- Implement Performance Monitoring Systems — Introducing more rigorous performance monitoring and feedback loops across all factories could help identify inefficiencies early and apply corrective measures swiftly.

## 5. Conclusion
The analysis of sales performance, product profitability, factory production efficiency, and shipping logistics provides key insights into the company's operations. The Pacific region has emerged as the most profitable, driving revenue growth, while the Gulf region faces ongoing challenges. The Chocolate division dominates both sales and profitability, with top-performing products significantly contributing to overall margins. Factory performance varies, with Lot’s O’ Nuts and Wicked Choccy’s excelling, while The Other Factory struggles with high costs and low returns. Shipping trends indicate strong customer demand, but optimisation opportunities exist, particularly in the Gulf region.

To sustain growth and profitability, the company should focus on optimising factory operations, refining its product strategy, and improving logistics efficiency. Addressing inefficiencies in underperforming factories and regions while leveraging strengths in top-performing areas will be crucial for long-term success.
