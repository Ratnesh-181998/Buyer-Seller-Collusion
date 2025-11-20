Buyer Seller Collusion: 

Business Requirement:  

Detect and report patterns of one buyer buying only from certain sellers and details around those 
purchase. To develop a methodology which can identify buyer seller collusions. 
Proposed solution: 
Instead of establishing predefined business rules, we should allow the data to define the criteria for 
identifying collusions. By analyzing data at the category level, we can capture the inherent behavior 
within each category, setting a benchmark for what constitutes an anomaly. This approach involves 
considering buyer-related data such as purchase frequency within a category, price paid, historical 
pricing, and repeated transactions with the same buyer.  
From the seller's perspective, we examine factors like price trends for the specific product and price 
comparisons with other (re)sellers offering the same catalog specifications.

<img width="2132" height="1198" alt="image" src="https://github.com/user-attachments/assets/ecad305b-b33c-4bad-98e6-e21cb076b9a5" />

<img width="2209" height="1180" alt="image" src="https://github.com/user-attachments/assets/c7eaf27b-8e14-45a7-8274-546ab7db0a59" />


Data: 

To build this solution, required data consist of 
• Buyer Details  
• Seller Details 
• Product / Variant Details 
• Bid Details 
• Transaction Details


<img width="805" height="750" alt="image" src="https://github.com/user-attachments/assets/24fe0fb3-d56f-4b4f-8f75-f378406e201e" />


<img width="1392" height="606" alt="image" src="https://github.com/user-attachments/assets/697c7dcf-ce0c-4c07-90d2-2e3d80e63be8" />


Steps In Model:  
1. Data pre-processing: Generate the following external variables for further analysis: 
• Percentage mean/median distance – Calculate the percentage mean/median distance from the 
lowest price quoted in the bid.  
• pt_ratio - Determine the ratio of the number of qualified sellers to the total number of sellers 
participating in the bid. 
• sb_trans_ratio - Calculate the ratio of the number of orders between a specific seller and buyer 
to the total number of orders placed by that buyer across categories.

2. Model Training: Train the mixture model to identify potential cases of collusion. 
3. Final Report: Compile a report detailing pairs of buyers and sellers who may be colluding within a 
given product category. 
To reduce false positives and minimize the number of results requiring validation, the following rules are 
recommended for identifying outliers: 
• The number of qualified sellers should be fewer than 5 
• The Qualified Ratio should be less than 30 % 
• The Median Distance should be greater than 15%

Business Value:  
1. Ensures the GeM portal operates at peak efficiency, maintaining the integrity of free competition 
within the platform. 
2. Fosters a competitive and equitable marketplace for both buyers and sellers.


Solution Consumption: 

The solution is integrated into Qlik Dashboards, highlighting potential collusion cases. The GeM team 
can then review these flagged bids and notify the respective buyers and sellers if necessary.  
The dashboard is updated monthly with the latest data.

<img width="1232" height="447" alt="image" src="https://github.com/user-attachments/assets/e8ce4315-7a7d-45db-acf8-a670f5ff419a" />


Integration & API: Developed and integrated using FlaskAPI.

Input: Solution requires Month and year for which data has to be extracted. 

<img width="1091" height="542" alt="image" src="https://github.com/user-attachments/assets/bf07806a-c2d5-4fd9-8bf6-17b8a1c68519" />

Output: Output will be the path of the report created along with the Retrieved row and columns. 

<img width="1145" height="378" alt="image" src="https://github.com/user-attachments/assets/887635d9-ebcf-467d-acce-e50d40c89d63" />

<img width="1285" height="450" alt="image" src="https://github.com/user-attachments/assets/660079bf-7555-4394-8cbf-a0db3a19a3f6" />











