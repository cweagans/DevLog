---
id: MNDCwq42qIOgdeEX1bbBR
title: Profili
desc: ''
updated: 1641426210038
created: 1641426210038
---

## Profiling

---

```python
pip install pandas-profiling
#  get the analysis of a data frame and save the analysis in web format we can use
from pandas_profiling import ProfileReport
report = ProfileReport(dataframe)
report.to_file(output_file=’output.html’)
```

---