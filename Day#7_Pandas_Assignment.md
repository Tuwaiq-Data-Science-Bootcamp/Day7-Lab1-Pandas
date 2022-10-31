```python
import pandas as pd
```

## Q1: Create a Series with indexes = 1, 2, 3 and has three names.


```python
index = [1, 2, 3]
names = ['First', 'Second', 'third']
s2 = pd.Series(names, index=index)
s2
```




    1     First
    2    Second
    3     third
    dtype: object



## Q2: Change indexes to 11, 12, 13.


```python
index = [11, 12, 13]
s2 = pd.Series(names, index=index)
s2
```




    11     First
    12    Second
    13     third
    dtype: object



## Q3: Retrieve First and second elements.


```python
s2[0:2]
```




    11     First
    12    Second
    dtype: object



## Q4: Add duplicate elements, then remove the duplication


```python
# Add elements 
index = [13]
names = ['third']
s3 = pd.Series(names, index=index)
s2 = s2.append(s3)
s2
```




    11     First
    12    Second
    13     third
    13     third
    dtype: object




```python
s2=s2.drop_duplicates()
s2
```




    11     First
    12    Second
    13     third
    dtype: object



## Q5: Create a Students DataFrame has three columns (ID, Name)


```python
data = {'ID': [1, 2, 3],
        'Name': ['Sara', 'Reem', 'Nora']}

student = pd.DataFrame(data, columns=['ID', 'Name'])
student   
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>Sara</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>Reem</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Nora</td>
    </tr>
  </tbody>
</table>
</div>



## Q6: Read educ_figdp_1_Data.csv file


```python
read = pd.read_csv('educ_figdp_1_Data.csv')
read
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>TIME</th>
      <th>GEO</th>
      <th>INDIC_ED</th>
      <th>Value</th>
      <th>Flag and Footnotes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2000</td>
      <td>European Union (28 countries)</td>
      <td>Total public expenditure on education as % of ...</td>
      <td>:</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2001</td>
      <td>European Union (28 countries)</td>
      <td>Total public expenditure on education as % of ...</td>
      <td>:</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2002</td>
      <td>European Union (28 countries)</td>
      <td>Total public expenditure on education as % of ...</td>
      <td>5.00</td>
      <td>e</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2003</td>
      <td>European Union (28 countries)</td>
      <td>Total public expenditure on education as % of ...</td>
      <td>5.03</td>
      <td>e</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2004</td>
      <td>European Union (28 countries)</td>
      <td>Total public expenditure on education as % of ...</td>
      <td>4.95</td>
      <td>e</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>379</th>
      <td>2007</td>
      <td>Finland</td>
      <td>Total public expenditure on education as % of ...</td>
      <td>5.90</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>380</th>
      <td>2008</td>
      <td>Finland</td>
      <td>Total public expenditure on education as % of ...</td>
      <td>6.10</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>381</th>
      <td>2009</td>
      <td>Finland</td>
      <td>Total public expenditure on education as % of ...</td>
      <td>6.81</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>382</th>
      <td>2010</td>
      <td>Finland</td>
      <td>Total public expenditure on education as % of ...</td>
      <td>6.85</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>383</th>
      <td>2011</td>
      <td>Finland</td>
      <td>Total public expenditure on education as % of ...</td>
      <td>6.76</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>384 rows × 5 columns</p>
</div>



## Q7: What is the difference between loc and slicing?
- loc use the index labels as references
- slice use the position as references


```python
#1- slice:  does not use the index labels as references, but the position
```


```python
read[:3]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>TIME</th>
      <th>GEO</th>
      <th>INDIC_ED</th>
      <th>Value</th>
      <th>Flag and Footnotes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2000</td>
      <td>European Union (28 countries)</td>
      <td>Total public expenditure on education as % of ...</td>
      <td>:</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2001</td>
      <td>European Union (28 countries)</td>
      <td>Total public expenditure on education as % of ...</td>
      <td>:</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2002</td>
      <td>European Union (28 countries)</td>
      <td>Total public expenditure on education as % of ...</td>
      <td>5.00</td>
      <td>e</td>
    </tr>
  </tbody>
</table>
</div>




```python
#2-loc: access row(s) and column(s) by label
```


```python
read.loc[90:94, ['TIME', 'GEO']] 
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>TIME</th>
      <th>GEO</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>90</th>
      <td>2006</td>
      <td>Belgium</td>
    </tr>
    <tr>
      <th>91</th>
      <td>2007</td>
      <td>Belgium</td>
    </tr>
    <tr>
      <th>92</th>
      <td>2008</td>
      <td>Belgium</td>
    </tr>
    <tr>
      <th>93</th>
      <td>2009</td>
      <td>Belgium</td>
    </tr>
    <tr>
      <th>94</th>
      <td>2010</td>
      <td>Belgium</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python

```
