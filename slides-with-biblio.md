---
title-slide: false
bibliography: references.bib
csl: vancouver.csl
citeproc: true
theme: serif
background-color: "#ffffff"
transition: slide
navigationMode: linear
hash: true
---

:::: {.columns}
::: {.column width="50%"}

## Sample slides
#### PlaceHolderName
#### Universiti Malaysia Perlis
#### [placeholder@email.com](mailto:placeholder@email.com)

<audio id="bg-music" src="media/audio/sb.m4a" loop></audio>

<div id="audio-credit"
     style="position: absolute; bottom: 40px; right: 20px; font-size: 0.6em; opacity: 0.6;">
  Music: “Adrift” by Scott Buckley (CC BY 4.0)
</div>

<script>
  document.addEventListener('DOMContentLoaded', () => {
    const audio = document.getElementById('bg-music');
    const credit = document.getElementById('audio-credit');

    // hide credit by default
    credit.style.display = 'none';

    const test = new Audio('media/audio/bgm.mp3');

    test.addEventListener('canplaythrough', () => {
      // bgm.mp3 exists → use it, keep credit hidden
      audio.src = 'media/audio/bgm.mp3';
    }, { once: true });

    test.addEventListener('error', () => {
      // bgm.mp3 missing → sb.m4a will play → show credit
      credit.style.display = 'block';
    }, { once: true });

    document.addEventListener('click', () => {
      if (Reveal.getIndices().h === 0) {
        audio.volume = 0.5;
        audio.play();
      }
    }, { once: true });

    Reveal.on('slidechanged', (event) => {
      if (event.indexh > 0) { audio.pause(); }
      else { audio.play(); }
    });
  });
</script>

:::

::: {.column width="50%"}
![](media/pics/logo1.png)
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### Slide one
**Key Concepts:**
- Energy conservation per @carnot1824.
- $\Delta U = Q - W$
:::

::: {.column width="50%"}
![](media/pics/sample.png)
:::
::::

---

<span class="slide-title" data-title="My Hidden Slide Name"></span>

![](media/pics/wide.jpeg)

---

:::: {.columns}
::: {.column width="50%"}
### The Master Equation
The fundamental relation of thermodynamics:

$$\Delta U = Q - W$$

The work done $W$ is positive when the system expands against an external pressure.
:::

::: {.column width="50%"}
<video data-src="media/videos/sample.mp4" data-autoplay loop muted width="100%"></video>
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### Visualizing the Gas Law
**Interactive Model:**

- P, V, and T relationships.
- Use the slider to adjust pressure.
- Observe the phase boundary.
:::

::: {.column width="50%"}
<iframe 
  data-src="media/plots/sample.html" 
  width="100%" 
  height="500px" 
  style="border:none;" 
  scrolling="no">
</iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Control Chart for PartLength (Machine 1)
This chart displays the `PartLength` measurements for Machine 1, with an Individuals (I) control chart.
- **Center Line (CL):** Represents the average `PartLength`.
- **Upper Control Limit (UCL):** The maximum expected variation.
- **Lower Control Limit (LCL):** The minimum expected variation.

The data is filtered for:
- Pressure = 200kPa
- Temperature = 338K
:::

::: {.column width="50%"}
<iframe data-src='media/plots/control_chart_machine1.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Control Chart for PartLength (Machine 2)
This chart displays the `PartLength` measurements for Machine 2, with an Individuals (I) control chart.
- **Center Line (CL):** Represents the average `PartLength`.
- **Upper Control Limit (UCL):** The maximum expected variation.
- **Lower Control Limit (LCL):** The minimum expected variation.

The data is filtered for:
- Pressure = 200kPa
- Temperature = 338K
:::

::: {.column width="50%"}
<iframe data-src='media/plots/control_chart_machine2.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Control Chart for PartLength (Machine 3)
This chart displays the `PartLength` measurements for Machine 3, with an Individuals (I) control chart.
- **Center Line (CL):** Represents the average `PartLength`.
- **Upper Control Limit (UCL):** The maximum expected variation.
- **Lower Control Limit (LCL):** The minimum expected variation.

The data is filtered for:
- Pressure = 200kPa
- Temperature = 338K
:::

::: {.column width="50%"}
<iframe data-src='media/plots/control_chart_machine3.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Control Chart for PartLength (Machine 1)
This chart displays the `PartLength` measurements for Machine 1, with an Individuals (I) control chart.
- **Center Line (CL):** Represents the average `PartLength`.
- **Upper Control Limit (UCL):** The maximum expected variation.
- **Lower Control Limit (LCL):** The minimum expected variation.

The data is filtered for:
- Pressure = 200kPa
- Temperature = 338K
:::

::: {.column width="50%"}
<iframe data-src='media/plots/control_chart_machine1.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Control Chart for PartLength (Machine 2)
This chart displays the `PartLength` measurements for Machine 2, with an Individuals (I) control chart.
- **Center Line (CL):** Represents the average `PartLength`.
- **Upper Control Limit (UCL):** The maximum expected variation.
- **Lower Control Limit (LCL):** The minimum expected variation.

The data is filtered for:
- Pressure = 200kPa
- Temperature = 338K
:::

::: {.column width="50%"}
<iframe data-src='media/plots/control_chart_machine2.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Control Chart for PartLength (Machine 3)
This chart displays the `PartLength` measurements for Machine 3, with an Individuals (I) control chart.
- **Center Line (CL):** Represents the average `PartLength`.
- **Upper Control Limit (UCL):** The maximum expected variation.
- **Lower Control Limit (LCL):** The minimum expected variation.

The data is filtered for:
- Pressure = 200kPa
- Temperature = 338K
:::

::: {.column width="50%"}
<iframe data-src='media/plots/control_chart_machine3.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Control Chart for PartLength (Machine 1)
This chart displays the `PartLength` measurements for Machine 1, with an Individuals (I) control chart.
- **Center Line (CL):** Represents the average `PartLength`.
- **Upper Control Limit (UCL):** The maximum expected variation.
- **Lower Control Limit (LCL):** The minimum expected variation.
- **Target (T):** The desired process mean (set at 50).
- **Upper Specification Limit (USL):** The upper boundary for acceptable product quality (set at 55).
- **Lower Specification Limit (LSL):** The lower boundary for acceptable product quality (set at 45).

The data is filtered for:
- Pressure = 200kPa
- Temperature = 338K
:::

::: {.column width="50%"}
<iframe data-src='media/plots/control_chart_machine1.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Control Chart for PartLength (Machine 2)
This chart displays the `PartLength` measurements for Machine 2, with an Individuals (I) control chart.
- **Center Line (CL):** Represents the average `PartLength`.
- **Upper Control Limit (UCL):** The maximum expected variation.
- **Lower Control Limit (LCL):** The minimum expected variation.
- **Target (T):** The desired process mean (set at 50).
- **Upper Specification Limit (USL):** The upper boundary for acceptable product quality (set at 55).
- **Lower Specification Limit (LSL):** The lower boundary for acceptable product quality (set at 45).

The data is filtered for:
- Pressure = 200kPa
- Temperature = 338K
:::

::: {.column width="50%"}
<iframe data-src='media/plots/control_chart_machine2.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Control Chart for PartLength (Machine 3)
This chart displays the `PartLength` measurements for Machine 3, with an Individuals (I) control chart.
- **Center Line (CL):** Represents the average `PartLength`.
- **Upper Control Limit (UCL):** The maximum expected variation.
- **Lower Control Limit (LCL):** The minimum expected variation.
- **Target (T):** The desired process mean (set at 50).
- **Upper Specification Limit (USL):** The upper boundary for acceptable product quality (set at 55).
- **Lower Specification Limit (LSL):** The lower boundary for acceptable product quality (set at 45).

The data is filtered for:
- Pressure = 200kPa
- Temperature = 338K
:::

::: {.column width="50%"}
<iframe data-src='media/plots/control_chart_machine3.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Machine 1 Capability Analysis
Analysis of Machine 1 at 200kPa and 338K.

- **Target:** 50.0000
- **Specs:** [45.0000, 55.0000]
- **Process Stability:** Check control limits for outliers.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/control_chart_m1.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Machine 2 Capability Analysis
Analysis of Machine 2 at 200kPa and 338K.

- **Process Control:** Monitored via Individuals chart.
- **Objective:** Maintain PartLength within $\pm 5$ of target.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/control_chart_m2.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Machine 3 Capability Analysis
Analysis of Machine 3 at 200kPa and 338K.

- **Assessment:** Capability indices $C_p$ and $C_{pk}$ shown in plot header.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/control_chart_m3.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Machine 1 Capability Analysis
Analysis of Machine 1 at 200kPa and 338K.

- **Target:** 50.0000
- **Specs:** [45.0000, 55.0000]
- **Process Stability:** Check control limits for outliers.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/control_chart_m1.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Machine 2 Capability Analysis
Analysis of Machine 2 at 200kPa and 338K.

- **Process Control:** Monitored via Individuals chart.
- **Objective:** Maintain PartLength within $\pm 5$ of target.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/control_chart_m2.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Machine 3 Capability Analysis
Analysis of Machine 3 at 200kPa and 338K.

- **Assessment:** Capability indices $C_p$ and $C_{pk}$ shown in plot header.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/control_chart_m3.html' width='100%' height='500px' style='border:none;'></iframe>
:::
::::

---
# Bibliography
<div id="refs"></div>
