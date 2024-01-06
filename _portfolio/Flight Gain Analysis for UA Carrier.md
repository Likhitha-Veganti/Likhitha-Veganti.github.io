---
title: "Flight Gain Analysis for United Airlines (R Project)"
excerpt: "This project delves into the analysis of flight gains for United Airlines (UA) using data from the nycflights13 package. The primary focus is on understanding how much quicker flights conclude compared to their planned schedules, measured by the net gain – the difference between departure delay and arrival delay."
---

Link to my GitHub Repository [Github Code](https://github.com/Likhitha-Veganti/data-science-projects/tree/main/NYC%20Flights%20UA%20Carrier%20Flight%20Gain%20Analysis).

## Introduction:

Suppose you're part of United Airlines, code-named UA. After a previous exploration of departure delays, the current investigation centers on gain per flight. The net gain is a crucial metric, representing the disparity between departure and arrival delays. By introducing a new variable to measure this net gain, this analysis aims to provide insights using confidence intervals, hypothesis tests, and exploratory data analysis.

## Project Objectives:

1. **Late Departures Analysis:**
   - Explore if the average gain differs for flights that departed late versus those that did not.
   - Examine the average gain for flights departing more than 30 minutes late.

2. **Common Destination Airports:**
   - Identify and describe the five most common destination airports for UA flights from New York City.
   - Analyze the distribution and average gain for each of these top airports.

3. **Gain per Hour Analysis:**
   - Calculate the gain per hour by dividing the total gain by the flight duration.
   - Investigate if the average gain per hour differs for late versus non-late flights and for flights departing more than 30 minutes late.

4. **Flight Duration Impact:**
   - Assess whether the average gain per hour varies for longer versus shorter flights.

## Executive Summary:

In this analysis, we filter the nycflights data to focus on United Airlines flights and introduce new variables, including late, very_late, gain, and gain per hour. The exploratory data analysis involves boxplots, histograms, and statistical tests to answer the project's questions. Here's a summary of key findings:

### 1. Average Gain for Delayed Flights

- Late vs. Not Late: Permutation tests and t-tests suggest a significant difference in net gain between flights that are delayed and those that are not, with non-delayed flights having a higher average gain.

- Very Late vs. Not Very Late: Similar findings indicate that flights not delayed by 30 minutes or more have a higher average gain than very late flights.

### 2. Most Common Destination Airports

- The five most common destination airports for UA flights from NYC are IAH, ORD, SFO, LAX, and DEN.

- Detailed distributions and average gains for each airport are presented, showing normal distributions with various skewness.

### 3. Average Gain per Hour for Delayed Flights

- Late vs. Not Late: Permutation tests and t-tests reveal a significant difference in gain per hour between late and non-late flights, with non-late flights having a higher average gain per hour.

- Very Late vs. Not Very Late: Similar results indicate that flights not delayed by 30 minutes or more have a higher average gain per hour than very late flights.

### 4. Gain per Hour for Longer and Shorter Flights

- Permutation tests and t-tests show a significant difference in gain per hour between shorter and longer flights, with shorter flights having a higher average gain per hour.
