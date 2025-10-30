# Festive_Expenditure_Analysis
Data analysis project in RStudio examining patterns of festive expenditure across religions in India. Includes data cleaning, aggregation, and visualization using ggplot2 and dplyr.


# Rcode
library(dplyr)
library(ggplot2)
festive <- "festive_expenditure_100_csv"
festive <- read.csv("festive_expenditure_100_csv", header = TRUE)


# Summarise average expenditure by religion (adjust column name if needed)
avg_religion <- festive_expenditure_100_csv %>%
  group_by(Religion) %>%
  summarise(Average_Expenditure = mean(`Expenditure (INR)`, na.rm = TRUE))

# Plot bar chart
ggplot(avg_religion, aes(x = Religion, y = Average_Expenditure, fill = Religion)) +
  geom_col() +
  theme_minimal() +
  labs(
    title = "Average Festive Expenditure by Religion",
    x = "Religion",
    y = "Average Expenditure (INR)"
  ) +
  theme(
    plot.title = element_text(hjust = 0.5, face = "bold"),
    axis.text.x = element_text(angle = 45, hjust = 1)
  )
