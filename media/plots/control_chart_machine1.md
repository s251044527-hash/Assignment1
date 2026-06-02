# R code for Machine 1 Control Chart
library(tidyverse)
library(ggplot2)
library(plotly)

TARGET <- 50
USL <- 55
LSL <- 45

machine1_data <- X034..2. %>%
  filter(Machine == 1, Pressure == 200, Temperature == 338)
machine1_data$PartLength <- as.numeric(machine1_data$PartLength)

sd_val <- sd(machine1_data$PartLength)
Cp <- (USL - LSL) / (6 * sd_val)
Cpk_upper <- (USL - mean(machine1_data$PartLength)) / (3 * sd_val)
Cpk_lower <- (mean(machine1_data$PartLength) - LSL) / (3 * sd_val)
Cpk <- min(Cpk_upper, Cpk_lower)

control_chart_m1_plot <- ggplot(machine1_data, aes(x = seq_along(PartLength), y = PartLength)) +
  geom_line(color = "#0072B2") +
  geom_point(color = "#0072B2") +
  geom_hline(yintercept = TARGET, linetype = "dashed", color = "black", size = 1, alpha = 0.7) +
  geom_hline(yintercept = USL, linetype = "dotted", color = "red", size = 1, alpha = 0.7) +
  geom_hline(yintercept = LSL, linetype = "dotted", color = "red", size = 1, alpha = 0.7) +
  labs(
    title = "Control Chart for Machine 1 Part Length",
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

# To display the plot (in an interactive R environment):
# print(control_chart_m1_plot)

# Save as HTML (for Colab/Reveal.js integration):
# htmlwidgets::saveWidget(ggplotly(control_chart_m1_plot), file = "media/plots/control_chart_machine1.html", selfcontained = TRUE)

# Cp and Cpk values (formatted to 4 decimal places):
# Cp: 2.2423
# Cpk: 1.8774

