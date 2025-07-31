This folder contains different codes for synthetic data generation.
Below are the details for Markov Chain (MC) versions
version 1: buckets have 10% difference < 200 , 50% > 200

version 2: there is no cluster data. Directly apply % difference on the home data and generate buckets from it. This will increase the probability value of few buckets, but the total number of buckets representing the time series data will increase. However, not preferred because mean of a group of homes gives a more definite distribution of a cluster or group of homes.

version 3: reduce bucket size : 5% for 0 to 100, 10% for 100-200 and 50% for > 200

version 4: bucket size  = 5% for < 200, 50% for > 200

version 5: bucket size = version 3. Uniform random selection of electricity value between current_value_sum that is generated from selected bucket (b) and previous_value_sum that is generated from previous of selected bucket i.e b-1
version 6: Apply Exponential decay (current_value - deltaE) x e ^(- lambda x t). deltaE = current_value - max_value. t=1 because we are generating values only based on previous value t-1 and not from the 1st or 2nd timestep where t=1 or t=2. Also the max value for each timestep will be different for each cluster (7 x 24). lambda will range between 0.1 to 1 

version 7: Apply Exponential decay (current_value - deltaE) x e ^(- lambda x t). deltaE = current_value - mean_value. t=1 because we are generating values only based on previous value t-1 and not from the 1st or 2nd timestep where t=1 or t=2. Also the mean value for each timestep will be different for each cluster (7 x 24). lambda will range between 0.1 to 1 

version 8: Apply Exponential decay (current_value - deltaE) x e ^(- lambda x t). deltaE = current_value - 75%_value. t=1 because we are generating values only based on previous value t-1 and not from the 1st or 2nd timestep where t=1 or t=2. Also the 75% value for each timestep will be different for each cluster (7 x 24). lambda will range between 0.1 to 1 

version 9: Apply min threshold on ED
