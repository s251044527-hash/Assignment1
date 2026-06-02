# R code for Machine 3 Control Chart
library(tidyverse)
library(ggplot2)
library(plotly)

TARGET <- 50
USL <- 55
LSL <- 45

machine3_data <- X034..2. %>%
  filter(Machine == 3, Pressure == 200, Temperature == 338)
machine3_data$PartLength <- as.numeric(machine3_data$PartLength)

sd_val_m3 <- sd(machine3_data$PartLength)
Cp_m3 <- (USL - LSL) / (6 * sd_val_m3)
Cpk_upper_m3 <- (USL - mean(machine3_data$PartLength)) / (3 * sd_val_m3)
Cpk_lower_m3 <- (mean(machine3_data$PartLength) - LSL) / (3 * sd_val_m3)
Cpk_m3 <- min(Cpk_upper_m3, Cpk_lower_m3)

control_chart_m3_plot <- ggplot(machine3_data, aes(x = seq_along(PartLength), y = PartLength)) +
  geom_line(color = "#009E73") +
  geom_point(color = "#009E73") +
  geom_hline(yintercept = TARGET, linetype = "dashed", color = "black", size = 1, alpha = 0.7) +
  geom_hline(yintercept = USL, linetype = "dotted", color = "red", size = 1, alpha = 0.7) +
  geom_hline(yintercept = LSL, linetype = "dotted", color = "red", size = 1, alpha = 0.7) +
  labs(
    title = "Control Chart for Machine 3 Part Length",
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
# Cp: 1.9206
# Cpk: 1.5975

