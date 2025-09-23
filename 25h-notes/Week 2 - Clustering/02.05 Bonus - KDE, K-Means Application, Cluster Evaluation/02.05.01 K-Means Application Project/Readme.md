# K-Means Application: Strategic Ambulance Placement

This project explores the use of **K-Means Clustering** to strategically place ambulances in Nairobi, aiming to optimize response times to road accidents. Inspired by the [Uber Nairobi Ambulance Perambulation Challenge](https://zindi.africa/competitions/uber-nairobi-ambulance-perambulation-challenge), we use accident location data to identify optimal ambulance stations.

## Problem Statement

The goal is to determine fixed locations for ambulances such that all accident sites are served efficiently. While this is a simplified approach, real-world solutions would require dynamic placement based on time, traffic, and accident patterns.

## Approach

- **Varied Approaches:**
There are many ways one could approach this challenge. For example, one could:
- Create a model to predict the likelihood of an accident given a location, the features of the nearby road segments, the weather, the traffic speed and the time of day. 
- Use this model to predict the probability of crashes for different times+locations over the test period, and then sample from this probability distribution to generate plausible crash locations.
- Use an optimization technique to minimise the travel distance for the ambulances to your fake crash points. 

This might seem too complicated - perhaps simply picking 6 fixed locations based on the existing data will be enough. And this is the approach we will be taking. We will group the accident sites, with each cluster center representing a proposed ambulance station. 

- **Evaluation:** The solution is evaluated by measuring distances from accident sites to their nearest ambulance station. Scoring is based on the distance from each crash in the test period to the nearest ambulance

## Data Description

The dataset contains crash records compiled by the World Bank DIME research team and Flare. The primary file, `Train.csv`, includes the time and location details for 6,318 crashes that occurred during the training period (2018-01-01 to 2019-06-30).

## Limitations

- Ambulance locations are static; in reality, they should adapt to changing patterns.
- Factors like traffic, time of day, and resource availability are not considered.

## Usage

1. Prepare accident location data.
2. Run the K-Means clustering script.
3. Analyze cluster centers for proposed ambulance locations.

## References

- [Uber Nairobi Ambulance Perambulation Challenge](https://zindi.africa/competitions/uber-nairobi-ambulance-perambulation-challenge)
- Scikit-learn documentation on [K-Means Clustering](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html)

## Future 
- A more advanced solution, using the cluster centeres as the starting point and using stochastic gradient descent will be explored in the future. 
