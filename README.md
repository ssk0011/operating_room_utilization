# operating_room_utilization
Testing analysis of synthetic operating room dataset for understanding of CPT codes and determining actionable insights.

Source: https://www.kaggle.com/datasets/drjfalk/operating-room-utilization

## Context
The data in question detailed schedules for operations in various services for a hypothetical hospital setting, ranging from podiatry to orthopedics. The goal was to determine ways to optimize usage of the OR, i.e. find the outliers. This code could also form the basis for future predictive models.

### Feature Engineering
Identify, in minutes, differences in time between features included in the dataset, such as Wheels In minus OR Schedule, End - Start, etc. This was the basis for determining any issues.

### Pandas Profiling
We could use the Profile Report package to interact with an exploratory data analysis finding from the dataset for a more general understanding and to create a baseline for expectations.

### Calculating Averages
Find the averages for engineered features, along with count, based on CPT code/description. Description was used for easier reading for any user.

### Z Score
Use the Z score, a measurement of the number of standard deviations from the mean, to identify outliers.

## Key Results
Although initially I considered a Z score calculation across all columns to identify what was within 3 STDs from the mean, I used the inverse operation to find outliers per feature.

Lapidus bunionectomy operations were significally quicker compared to booking times, meaning less time needed to be reserved.

For Arthroplasty, knee, hinge prothesis, there is a larger than normal delay time for starting the operation versus once the patient is in the OR suite.

Finally, for Extracapsular cataract removal, there was a significant amount of operations more compared to all other categories, though this may not be within the hospital's control.