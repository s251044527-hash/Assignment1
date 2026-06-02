# R code for Machine 2 Control Chart
library(tidyverse)
library(ggplot2)
library(plotly)

TARGET <- 50
USL <- 55
LSL <- 45

machine2_data <- X034..2. %>%
  filter(Machine == 2, Pressure == 200, Temperature == 338)
machine2_data$PartLength <- as.numeric(machine2_data$PartLength)

sd_val_m2 <- sd(machine2_data$PartLength)
Cp_m2 <- (USL - LSL) / (6 * sd_val_m2)
Cpk_upper_m2 <- (USL - mean(machine2_data$PartLength)) / (3 * sd_val_m2)
Cpk_lower_m2 <- (mean(machine2_data$PartLength) - LSL) / (3 * sd_val_m2)
Cpk_m2 <- min(Cpk_upper_m2, Cpk_lower_m2)

control_chart_m2_plot <- ggplot(machine2_data, aes(x = seq_along(PartLength), y = PartLength)) +
  geom_line(color = "#D55E00") +
  geom_point(color = "#D55E00") +
  geom_hline(yintercept = TARGET, linetype = "dashed", color = "black", size = 1, alpha = 0.7) +
  geom_hline(yintercept = USL, linetype = "dotted", color = "red", size = 1, alpha = 0.7) +
  geom_hline(yintercept = LSL, linetype = "dotted", color = "red", size = 1, alpha = 0.7) +
  labs(
    title = "Control Chart for Machine 2 Part Length",
    x = "Observation Index",
    y = "Part Length (mm)"
  ) +
  theme_minimal() +
  theme(
    plot.title = element_text(size = 18, face = "bold"),
    axis.title.x = element_text(size = 18),
    axis.title.y = element_text(size = 18),
    axis.text.x = element_text(size = 14),
    axis.text.y = element_text(size = 14),
    panel.background = element_rect(fill = "white", colour = NA),
    plot.background = element_rect(fill = "white", colour = NA)
  )

# Cp and Cpk values (formatted to 4 decimal places):
# Cp: 1.9205
# Cpk: 1.5899

