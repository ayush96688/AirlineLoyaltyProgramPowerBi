# Northern Light Airlines Loyalty Program Analysis

## Project Overview
This project focuses on analyzing the impact of Northern Light Airlines' customer loyalty program, particularly evaluating the 2018 Promotion compared to subsequent years. Utilizing Power BI, we explore customer behavior, enrollment trends, and flight booking patterns to assess the program's effectiveness and identify areas for improvement.

## Objectives
- Design and implement a comprehensive customer loyalty program tailored to airline passengers' needs.
- Utilize Power BI for in-depth data analysis to gain insights into customer behavior, preferences, and trends.
- Develop personalized rewards and incentives to enhance customer satisfaction and retention.
- Optimize operational efficiency by identifying areas for improvement through data-driven insights.

## Key Components
1. **Loyalty Program Infrastructure**
   - Membership tiers, points accrual systems, redemption options, and communication channels were established.

2. **Data Collection and Integration**
   - Data from bookings, flights, onboard purchases, surveys, and social media interactions were collected and integrated into a centralized database.

3. **Data Modeling in Power BI**
   - Imported CSV files into PowerQuery Editor.
   - Adjusted data types, promoted headers, and established relationships between fact and lookup tables.
   - **Data Model Overview**:
     - **Calendar Table**: Contains fields like Date, Start of Month, Start of Quarter, and Start of Year.
     - **Customer Flight Activity**: Includes Distance, Dollar Cost Points Redeemed, Flight Booked Start of Month, Loyalty Number, Month, Points Accumulated, Points Redeemed, and Total Flights.
     - **Customer Loyalty History**: Features Cancellation Month, Cancellation Start of Month, Cancellation Year, City, CLV (Customer Lifetime Value), Country, Education, Enrollment Month, and Enrollment Start of Month.
     - Relationships were created between the Calendar, Customer Flight Activity, and Customer Loyalty History tables to ensure seamless data integration and analysis.

4. **DAX Formulas Used**
   - Created DAX measures to calculate key metrics:
     - **Total Flights Booked**:
       ```DAX
       Total Flights Booked = SUM('Customer Flight Activity'[Total Flights])
       ```
     - **Total Flights Booked for Previous Year**:
       ```DAX
       Total Flights Booked Previous Year = CALCULATE([Total Flights Booked], PREVIOUSYEAR('Calendar'[Date]))
       ```
     - **Total Flight Booked Running Totals**:
       ```DAX
       Running Total Flights = CALCULATE([Total Flights Booked], FILTER(ALL('Calendar'), 'Calendar'[Date] <= MAX('Calendar'[Date])))
       ```
     - **Total Enrollments**:
       ```DAX
       Total Enrollments = COUNT('Customer Loyalty History'[Enrollment Month])
       ```
     - **Total Cancellations**:
       ```DAX
       Total Cancellations = COUNT('Customer Loyalty History'[Cancellation Month])
       ```
     - **Net Enrollments**:
       ```DAX
       Net Enrollments = [Total Enrollments] - [Total Cancellations]
       ```

5. **Personalized Rewards and Incentives**
   - Based on analysis insights, personalized rewards and incentives were developed to enhance the customer experience.

6. **Implementation and Integration**
   - Rewards were integrated into the loyalty program framework, ensuring seamless delivery to customers.

7. **Monitoring and Optimization**
   - Continuous monitoring and optimization based on feedback and changing market dynamics.

## Power BI Visualizations
- **Line Charts**: Visualizing total enrollments and cancellations by year.
- **Bar Charts**: Showing net loyalty members and running totals.
- **Stacked Line & Bar Charts**: Displaying enrollments by month and enrollment type.
- **Map Visualization**: Highlighting flight bookings by province.
- **Slicers**: Filtering results by enrollment type (2018 Promotion vs. Standard).

## Insights from Analysis
1. **Membership Growth**
   - Out of 16,740 loyalty members, 971 joined through the 2018 promotion, representing approximately 6% new signups.
2. **Revenue Impact**
   - The campaign generated $8 million in revenue, with higher female signups.
3. **Geographical Insights**
   - Toronto, Vancouver, and Montreal were key cities in revenue generation.
   - Top-performing provinces: Ontario, British Columbia, and Quebec.
4. **Seasonal Trends**
   - Summer months (June to September) saw 64K flights booked, with 51K members traveling alone and 13K with companions.
5. **Educational Influence**
   - Bachelor and college students traveled more, accumulating 1.49M points and redeeming 390K points.

## Expected Outcomes
- **Increased Customer Retention**: Personalized rewards are expected to boost loyalty and retention rates.
- **Enhanced Customer Satisfaction**: Tailored offerings improve overall satisfaction.
- **Improved Operational Efficiency**: Data-driven insights identify inefficiencies and optimize resources.
- **Competitive Advantage**: A robust loyalty program differentiates the airline from competitors.

## Conclusion
The 2018 promotions significantly impacted the loyalty program, driving enrollment and revenue. However, cancellations need to be managed to ensure sustained growth. Leveraging Power BI for data analysis has provided valuable insights to refine the loyalty program, optimize operations, and enhance customer satisfaction.

## Repository Structure
```
/airline-loyalty-program
|-- /images
|   |-- dashboard_1.png
|   |-- dashboard_2.png
|   |-- dashboard_3.png
|   |-- dashboard_4.png
|   |-- dashboard_5.png
|   |-- insights.png
|   |-- data_model.png
|-- /data
|   |-- [CSV files used in the project]
|-- Airline_Loyalty_Program.pbix
|-- README.md
```

## How to Use
1. Clone the repository.
2. Open `Airline_Loyalty_Program.pbix` in Power BI Desktop.
3. Explore the various dashboards and insights.

---

**Note**: Ensure the CSV files are correctly linked to the Power BI file if any issues arise while loading the data.

