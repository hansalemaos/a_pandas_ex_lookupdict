# Creates a lookup dict from a Pandas DataFrame (tuples as keys / np as values)

```python
pip install a-pandas-ex-lookupdict
```


```python

from a_pandas_ex_lookupdict import pd_add_lookup_dict
import pandas as pd
pd_add_lookup_dict()
df = pd.read_csv(
    "https://raw.githubusercontent.com/pandas-dev/pandas/main/doc/data/titanic.csv"
)
di1 = df[:5].d_get_lookup_dict(as_index=["Name", "PassengerId"])
di2 = df[:5].d_get_lookup_dict(
    as_values=["Cabin", "Fare"], as_index=["Name", "PassengerId"]
)

di1
Out[4]: 
{('Braund, Mr. Owen Harris',
  1): array([[0, 3, 'male', 22.0, 1, 0, 'A/5 21171', 7.25, nan, 'S']],
       dtype=object),
 ('Cumings, Mrs. John Bradley (Florence Briggs Thayer)',
  2): array([[1, 1, 'female', 38.0, 1, 0, 'PC 17599', 71.2833, 'C85', 'C']],
       dtype=object),
 ('Heikkinen, Miss. Laina',
  3): array([[1, 3, 'female', 26.0, 0, 0, 'STON/O2. 3101282', 7.925, nan, 'S']],
       dtype=object),
 ('Futrelle, Mrs. Jacques Heath (Lily May Peel)',
  4): array([[1, 1, 'female', 35.0, 1, 0, '113803', 53.1, 'C123', 'S']],
       dtype=object)}
	   
	   
di2
Out[5]: 
{('Braund, Mr. Owen Harris', 1): array([[nan, 7.25]], dtype=object),
 ('Cumings, Mrs. John Bradley (Florence Briggs Thayer)',
  2): array([['C85', 71.2833]], dtype=object),
 ('Heikkinen, Miss. Laina', 3): array([[nan, 7.925]], dtype=object),
 ('Futrelle, Mrs. Jacques Heath (Lily May Peel)',
  4): array([['C123', 53.1]], dtype=object)}

```
