
library(qcc)
library(ggplot2)
library(plotly)
library(htmlwidgets)

machine2_data_filtered <- X034..2.[X034..2.$Temperature == 338 & X034..2.$Pressure == 200 & X034..2.$Machine == 2,]

if (nrow(machine2_data_filtered) > 1) {
    qcc_obj_m2 <- qcc(machine2_data_filtered$PartLength, type="xbar.one", plot = FALSE)

    cl_m2 <- qcc_obj_m2$center
    ucl_m2 <- qcc_obj_m2$limits[1, "UCL"]
    lcl_m2 <- qcc_obj_m2$limits[1, "LCL"]

    plot_data_m2 <- data.frame(
        Index = 1:nrow(machine2_data_filtered),
        PartLength = machine2_data_filtered$PartLength,
        CL = cl_m2,
        UCL = ucl_m2,
        LCL = lcl_m2
    )

    p_m2 <- ggplot(plot_data_m2, aes(x = Index, y = PartLength)) +
        geom_line(color = "#0072B2") +
        geom_point(color = "#0072B2", size = 2) +
        geom_hline(aes(yintercept = CL, color = "CL"), linetype = "solid", size = 1) +
        geom_hline(aes(yintercept = UCL, color = "UCL"), linetype = "dashed", size = 1) +
        geom_hline(aes(yintercept = LCL, color = "LCL"), linetype = "dashed", size = 1) +
        geom_hline(aes(yintercept = 50, color = "Target"), linetype = "solid", size = 1) + 
        geom_hline(aes(yintercept = 55, color = "USL"), linetype = "dotdash", size = 1) + 
        geom_hline(aes(yintercept = 45, color = "LSL"), linetype = "dotdash", size = 1) + 
        scale_color_manual(name = "Limits",
                           values = c("CL" = "#D55E00", "UCL" = "#CC79A7", "LCL" = "#CC79A7",
                                      "Target" = "#009E73", "USL" = "#0072B2", "LSL" = "#0072B2"),
                           labels = c("CL" = "Center Line", "UCL" = "Upper Control Limit", "LCL" = "Lower Control Limit",
                                      "Target" = "Target", "USL" = "Upper Spec Limit", "LSL" = "Lower Spec Limit")) +
        labs(title = "Individuals Control Chart for PartLength (Machine 2)",
             x = "Observation Index",
             y = "PartLength") +
        theme_minimal() +
        theme(
            plot.title = element_text(size = 18, face = "bold"),
            axis.title = element_text(size = 18),
            axis.text = element_text(size = 14),
            panel.background = element_rect(fill = "white", colour = "white"),
            plot.background = element_rect(fill = "white", colour = "white"),
            legend.position = "bottom"
        )

    plotly_p_m2 <- ggplotly(p_m2)
    htmlwidgets::saveWidget(plotly_p_m2, file = "media/plots/control_chart_machine2.html", selfcontained = TRUE)
} else {
    message("Not enough data for Machine 2 to create a control chart with the specified filters.")
}
    
