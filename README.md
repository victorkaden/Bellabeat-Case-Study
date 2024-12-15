# Bellabeat Case Study

## Overview
This project is part of the **Google Data Analytics Professional Certificate**, focusing on analyzing smart device usage data to gain insights into user behavior. Bellabeat, a high-tech manufacturer of health-focused smart products, aims to improve user engagement and expand its market presence.

### Objective
The primary goal is to analyze Bellabeat's user data and compare it with general non-user trends to identify actionable insights and recommendations for enhancing user engagement and health outcomes.

---

## Tools and Methods
- **Data Cleaning and Transformation**: R (tidyverse, dplyr, ggplot2)
- **Data Analysis**: R and SQL
- **Data Visualization**: R (ggplot2) and Tableau

---

## Key Insights

### 1. Activity Levels Comparison
- **Insight**: Bellabeat users are more active than the average population but still spend a significant amount of time in sedentary activities.
- **Comparison**: Non-users have overall lower activity levels.
- **Recommendation**: Introduce in-app prompts to reduce sedentary behavior and gamify activity goals.

![Activity Levels Chart](activity_levels_chart.png)

### 2. Steps vs. Calories Burned
- **Insight**: A strong positive correlation exists between steps taken and calories burned, highlighting the importance of daily movement.
- **Comparison**: Bellabeat users burn more calories than non-users.
- **Recommendation**: Promote daily step challenges and rewards to encourage consistent activity.

```r
# R Code Example
library(ggplot2)
ggplot(merged_data, aes(x = TotalSteps, y = Calories)) +
  geom_point(color = "red", alpha = 0.6) +
  geom_smooth(method = "lm", se = FALSE, color = "blue") +
  labs(
    title = "Calories Burned vs. Steps Taken",
    x = "Total Steps",
    y = "Calories Burned"
  ) +
  theme_minimal()
```

![Steps vs. Calories Burned](steps_vs_calories_burned.png)

### 3. Sleep Patterns
- **Insight**: Bellabeat users have slightly better sleep efficiency but do not outperform non-users significantly in total sleep duration.
- **Comparison**: Non-users show more fragmented sleep patterns.
- **Recommendation**: Offer personalized sleep tips to help users gain a sleep-quality advantage.

![Sleep Patterns Chart](sleep_patterns_chart.png)

### 4. Steps Taken per Day
- **Insight**: Bellabeat users walk more steps daily than non-users, though some inactive users match non-user activity levels.
- **Recommendation**: Use motivational notifications to convert low-activity users into moderate-activity users.

![Steps Over Time](steps_over_time.png)

### 5. Weekly Trends
- **Insight**: Bellabeat users are more consistent in activity levels throughout the week compared to non-users.
- **Comparison**: Non-users show significant drops in activity during weekends.
- **Recommendation**: Launch weekend-specific challenges to maintain activity levels.

```r
# Weekly Trends Code Example
merged_data <- merged_data %>%
  mutate(week_day = weekdays(date))

ggplot(merged_data, aes(x = week_day, y = TotalSteps, fill = week_day)) +
  geom_boxplot() +
  labs(
    title = "Steps Distribution by Weekday",
    x = "Weekday",
    y = "Total Steps"
  ) +
  theme_minimal() +
  theme(axis.text.x = element_text(angle = 45, hjust = 1))
```

![Weekly Trends Chart](weekly_trends_chart.png)

---

## Full Presentation
[View the Full Presentation Here](https://link-to-your-presentation)

---

## Conclusion
Bellabeat can significantly improve user engagement and health outcomes by:
- Encouraging consistent daily activity through gamified challenges and rewards.
- Providing personalized feedback and tips for improving sleep quality.
- Highlighting measurable benefits over non-users in marketing campaigns.
- Maintaining user activity on weekends with targeted initiatives.

These recommendations, backed by data, align with Bellabeat's mission to promote healthier lifestyles and grow its user base.


