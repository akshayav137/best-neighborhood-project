# best-neighborhood-project

Introduction:


```python
import pandas as pd
import matplotlib.pyplot as plt


url = "https://data.wprdc.org/api/3/action/datastore_search?resource_id=e419c20c-8df4-4729-830c-e49427a656e0&limit=50000"


df = pd.read_json(url)

df = pd.json_normalize(df["result"]["records"])

# Counts how many arrests per neighborhood
arrest_counts = df["Neighborhood"].value_counts()

# Plots bar graph :)
plt.figure(figsize=(14, 7))
plt.bar(arrest_counts.index, arrest_counts.values, color = "magenta")
plt.xlabel("Neighborhood")
plt.ylabel("Number of Arrests")
plt.title("Arrests by Neighborhood")
plt.xticks(rotation=90)

plt.show()



