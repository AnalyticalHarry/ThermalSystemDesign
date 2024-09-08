# Thermal System Design 

**Author:** Hemant Thapa  

**LinkedIn:** [Hemant Thapa](https://www.linkedin.com/in/thapahemant/)

**Email:** hemantthapa1998@gmail.com

This project is an open-research study on Thermal System Design, a core topic in Mechanical Engineering. The research utilizes open-source software and resources, including Jupyter Notebook, Pandas, Matplotlib, Seaborn, NumPy, Python in-built libraries, and previously published journals.


## Libraries

The following Python libraries are used in this project:

```python
import pandas as pd
import math
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np
from itertools import chain
import warnings
warnings.filterwarnings('ignore')
log = math.log10
```

### Topics Covered

1. Microbial Survivor Curves
2. Decimal Reduction Times

### What are Microbial Survivor Curves?

Microbial survivor curves represent the cumulative distribution of cell death times or the times when microorganisms lose their ability to regenerate.

### What are Decimal Reduction Times?

The D-value (decimal reduction time) is the time required to reduce the viable microbial population by 90% at a defined temperature.

### Objectives

Food Processing: Utilizing solar thermal energy to evaporate water from food products and using natural ice for preservation.

Obtain and maintain product microbial safety.

Increase the product's lifespan.

```python
temperature_requirements = {
    "Optimum temperature": ["-8°C to -18°C"],
    "Psychrophiles": ["0°C to -32°C"],
    "Mesophiles": ["20°C - 40°C; human pathogens"],
    "Thermophiles": [">45°C; hot springs & compost piles"],
    "Hyperthermophiles": [">80°C; hot vents"]
}
df_temperature_requirements = pd.DataFrame(temperature_requirements)
df_temperature_requirements
```

### Thermal Processing

Thermal processing involves heating, holding, and cooling processes required to eliminate potential food-borne illnesses.

Pasteurisation: Intended for specific pathogenic microorganisms but does not produce a shelf-stable product without refrigeration.

Commercial Sterilization: Intense thermal process that results in shelf-stable products by reducing the microbial population.

### Factors Influencing Processing Time : 

1. Heat resistance of microorganisms or enzymes
2. pH value
3. Heating conditions
4. Physical state of food
5. Size of the container


### Microbial Growth Curve

Bacterial Division: Bacteria primarily reproduce through binary fission, a type of asexual reproduction.

Growth Curve: Bacteria develop in a predictable manner with four distinct phases: lag phase, exponential phase, stationary phase, and death phase.

### Decimal Reduction Time (D)

The Decimal Reduction Time (D) is defined as the time required for a 90% reduction in the microbial population.

### Example: Thermal resistance experiment data at 112°C:

- Time (minutes)

- Number of Survivors

- Log N

``` python

time = [0, 4, 8, 12]
number_of_survivors = [10**6, 1.1*10**5, 1.2*10**4, 1.2*10**3]
log_n = np.round(np.log10(number_of_survivors), 4)

data = {
    "Time (minutes)": time,
    "Number of Survivors (N)": number_of_survivors,
    "Log N": log_n
}
df_data_table = pd.DataFrame(data)
df_data_table
```

### Decimal Reduction Time Calculation:

```python
total_time = time[3] - time[0]
log_initial = log_n[0]
log_final = log_n[3]
decimal_reduction_time = total_time / (log_initial - log_final)
print(f"Decimal reduction time: {round(decimal_reduction_time, 4)} minutes")
```

### Result: Decimal reduction time is approximately 4.1085 minutes.

### Jupyter Notebook 

https://github.com/AnalyticalHarry/ThermalSystemDesign/blob/main/Thermal%20System%20Design.ipynb

```python
MIT License

Copyright (c) 2023 Hemant Thapa

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
