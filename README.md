## Linear Regression to Predict MPG
--------------

*Deliverable #1:* 

>Variables measured for each vehicle include: 

- vehicle length 
- vehicle weight 
- spoiler angle
- drivetrain
- ground clearance


***Multiple linear regression data for mpg vs. all independent variables***

<img width="835" alt="Summary()" src="https://user-images.githubusercontent.com/106992995/204407292-fd08f296-5e84-4892-936c-09cd8943b5df.png">



>1. Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?

<img width="922" alt="Added-Variable Plots" src="https://user-images.githubusercontent.com/106992995/205466080-f22ba66d-0dce-47d5-b794-fd1292eaf040.png">

Vehicle length and vehicle ground clearance are variables that account for less than 5% of MPG variance.

>vehicle_length with p-value=2.60e-12 which is < 0.05

>ground_clearance with p-value=5.21e-08 which is < 0.05


>2. Is the slope of the linear model considered to be zero? Why or why not?
No. The slope of the linear model is not zero. Both Multiple R-squared = 0.7149 and Adjusted R-Squared = 0.6825 values both indicate that the model is a strong predictor (>0.5). 

These independent variables were close to zero:

- vehicle_weight had a slope of 1.245e-03
- spoiler_angle had a slope of 6.877e-02

>3. Does this linear model predict mpg of MechaCar prototypes effectively? Why or why not?
Yes. R-squared = 0.7149, which means that this model is able to predict mpg of MechaCar prototypes at 71% accuracy each time. 



## Summary Statistics on Suspension Coils
------------
*Deliverable #2:* 

>.1 The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?

The variance for all manufacturing lots in total is 62.29356 (which does not exceed 100)
<img width="515" alt="total_summary_df" src="https://user-images.githubusercontent.com/106992995/205470844-4661de0d-2f81-46b8-a279-3d09a9875227.png">


The variance for each manufacturing lot individually differs and looks like this:
<img width="536" alt="lot_summary_df" src="https://user-images.githubusercontent.com/106992995/205470847-7199dc80-2274-472d-830b-829cdac4c6d3.png">

 ✅ Lot1 = 0.9795 
 
 ✅ Lot2 = 7.4693 
 
 ❌ Lot3 = 170.2861 


      ➡️ Lot3 exceeds the limit of 100 pounds per square inch.



## T-Tests on Suspension Coils
------------
*Deliverable #3:* 

*Findings for the t-test results across all lots:*

    T-test for all lots vs. pop. mean of 1500 PSI - no statistical difference.
<img width="460" alt="AllLotsTtest" src="https://user-images.githubusercontent.com/106992995/205472222-fc9a3031-af4a-49d6-83ca-51aa61271ff4.png">


------------
    T-test for lot1 vs. population mean of 1500 PSI - no there is no statistical difference.
<img width="459" alt="lot1Ttest" src="https://user-images.githubusercontent.com/106992995/205472154-06eaf94f-b688-46f7-9b30-f7a2ee85c7be.png">


------------
    T-test for lot2 vs. population mean of 1500 PSI - no there is no statistical difference.
<img width="458" alt="lot2Ttest" src="https://user-images.githubusercontent.com/106992995/205472158-9d8170e2-b270-4bcf-97e0-7f1dbbbd50cc.png">


------------
    T-test for lot3 vs. population mean of 1500 PSI - yes there is statistical difference.
<img width="456" alt="lot3Ttest" src="https://user-images.githubusercontent.com/106992995/205472165-41efd012-e635-4c91-957f-de16930243ca.png">



## Study Design: MechaCar vs Competition
--------------
*Deliverable #4:* 

>Using your knowledge of R, design a statistical study to compare performance of the MechaCar vehicles against performance of vehicles from other manufacturers.

I would look at the following metric to compare MechCar vs Competition:
- highway fuel efficiency
- cost
- safety ratings

**Step 1.** Summary statistics on highway fuel efficiency, cost, and safety ratings for both MechaCar and the competition

**Step 2.** Formulate hypothesis:

Ho: No, there is no difference between the means of MechaCar vehicles vs the Competition across fuel efficiency data, cost, and safety ratings.
Ha: Yes, there is a difference between the means of MechaCar vehicles vs the Competition across fuel efficiency data, cost, and safety ratings.

**Step 3.** ANOVA test because this analysis could compare means across multiple competitors. In R, the aov() function would be used. 

>To perform this statistical test, I'd have to gather: fuel efficiency data, cost data, and safety ratings data from a selection of competitors and measure all variables against MechaCar data. 
