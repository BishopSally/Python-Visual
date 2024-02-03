# Welcome to Covid19 Data Analysis Notebook
------------------------------------------

### Let's Import the modules 


```python
!pip install pandas
```

    Requirement already satisfied: pandas in c:\users\bsall\appdata\local\programs\python\python312\lib\site-packages (2.1.4)

    
    [notice] A new release of pip is available: 23.2.1 -> 23.3.2
    [notice] To update, run: python.exe -m pip install --upgrade pip
    

    
    Requirement already satisfied: numpy<2,>=1.26.0 in c:\users\bsall\appdata\local\programs\python\python312\lib\site-packages (from pandas) (1.26.2)
    Requirement already satisfied: python-dateutil>=2.8.2 in c:\users\bsall\appdata\local\programs\python\python312\lib\site-packages (from pandas) (2.8.2)
    Requirement already satisfied: pytz>=2020.1 in c:\users\bsall\appdata\local\programs\python\python312\lib\site-packages (from pandas) (2023.3.post1)
    Requirement already satisfied: tzdata>=2022.1 in c:\users\bsall\appdata\local\programs\python\python312\lib\site-packages (from pandas) (2023.4)
    Requirement already satisfied: six>=1.5 in c:\users\bsall\appdata\local\programs\python\python312\lib\site-packages (from python-dateutil>=2.8.2->pandas) (1.16.0)
    


```python
import pandas as pd 
import numpy as np 
import seaborn as sns
import matplotlib.pyplot as plt 
print('Modules are imported.')
```

    Modules are imported.
    

## Task 2 

### Task 2.1: importing covid19 dataset
importing "Covid19_Confirmed_dataset.csv" from "./Dataset" folder. 



```python
corona_dataset_csv = pd.read_csv("DataSets/covid19_Confirmed_dataset.csv")
corona_dataset_csv.head()
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
      <th>Province/State</th>
      <th>Country/Region</th>
      <th>Lat</th>
      <th>Long</th>
      <th>1/22/20</th>
      <th>1/23/20</th>
      <th>1/24/20</th>
      <th>1/25/20</th>
      <th>1/26/20</th>
      <th>1/27/20</th>
      <th>...</th>
      <th>4/21/20</th>
      <th>4/22/20</th>
      <th>4/23/20</th>
      <th>4/24/20</th>
      <th>4/25/20</th>
      <th>4/26/20</th>
      <th>4/27/20</th>
      <th>4/28/20</th>
      <th>4/29/20</th>
      <th>4/30/20</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>NaN</td>
      <td>Afghanistan</td>
      <td>33.0000</td>
      <td>65.0000</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>1092</td>
      <td>1176</td>
      <td>1279</td>
      <td>1351</td>
      <td>1463</td>
      <td>1531</td>
      <td>1703</td>
      <td>1828</td>
      <td>1939</td>
      <td>2171</td>
    </tr>
    <tr>
      <th>1</th>
      <td>NaN</td>
      <td>Albania</td>
      <td>41.1533</td>
      <td>20.1683</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>609</td>
      <td>634</td>
      <td>663</td>
      <td>678</td>
      <td>712</td>
      <td>726</td>
      <td>736</td>
      <td>750</td>
      <td>766</td>
      <td>773</td>
    </tr>
    <tr>
      <th>2</th>
      <td>NaN</td>
      <td>Algeria</td>
      <td>28.0339</td>
      <td>1.6596</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>2811</td>
      <td>2910</td>
      <td>3007</td>
      <td>3127</td>
      <td>3256</td>
      <td>3382</td>
      <td>3517</td>
      <td>3649</td>
      <td>3848</td>
      <td>4006</td>
    </tr>
    <tr>
      <th>3</th>
      <td>NaN</td>
      <td>Andorra</td>
      <td>42.5063</td>
      <td>1.5218</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>717</td>
      <td>723</td>
      <td>723</td>
      <td>731</td>
      <td>738</td>
      <td>738</td>
      <td>743</td>
      <td>743</td>
      <td>743</td>
      <td>745</td>
    </tr>
    <tr>
      <th>4</th>
      <td>NaN</td>
      <td>Angola</td>
      <td>-11.2027</td>
      <td>17.8739</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>24</td>
      <td>25</td>
      <td>25</td>
      <td>25</td>
      <td>25</td>
      <td>26</td>
      <td>27</td>
      <td>27</td>
      <td>27</td>
      <td>27</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 104 columns</p>
</div>



#### Let's check the shape of the dataframe


```python
corona_dataset_csv.shape
```




    (266, 104)



### Task 2.2: Delete the useless columns


```python
corona_dataset_csv.drop(["Lat","Long"],axis=1,inplace=True)
```


```python
corona_dataset_csv.head(10)
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
      <th>Province/State</th>
      <th>Country/Region</th>
      <th>1/22/20</th>
      <th>1/23/20</th>
      <th>1/24/20</th>
      <th>1/25/20</th>
      <th>1/26/20</th>
      <th>1/27/20</th>
      <th>1/28/20</th>
      <th>1/29/20</th>
      <th>...</th>
      <th>4/21/20</th>
      <th>4/22/20</th>
      <th>4/23/20</th>
      <th>4/24/20</th>
      <th>4/25/20</th>
      <th>4/26/20</th>
      <th>4/27/20</th>
      <th>4/28/20</th>
      <th>4/29/20</th>
      <th>4/30/20</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>NaN</td>
      <td>Afghanistan</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>1092</td>
      <td>1176</td>
      <td>1279</td>
      <td>1351</td>
      <td>1463</td>
      <td>1531</td>
      <td>1703</td>
      <td>1828</td>
      <td>1939</td>
      <td>2171</td>
    </tr>
    <tr>
      <th>1</th>
      <td>NaN</td>
      <td>Albania</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>609</td>
      <td>634</td>
      <td>663</td>
      <td>678</td>
      <td>712</td>
      <td>726</td>
      <td>736</td>
      <td>750</td>
      <td>766</td>
      <td>773</td>
    </tr>
    <tr>
      <th>2</th>
      <td>NaN</td>
      <td>Algeria</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>2811</td>
      <td>2910</td>
      <td>3007</td>
      <td>3127</td>
      <td>3256</td>
      <td>3382</td>
      <td>3517</td>
      <td>3649</td>
      <td>3848</td>
      <td>4006</td>
    </tr>
    <tr>
      <th>3</th>
      <td>NaN</td>
      <td>Andorra</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>717</td>
      <td>723</td>
      <td>723</td>
      <td>731</td>
      <td>738</td>
      <td>738</td>
      <td>743</td>
      <td>743</td>
      <td>743</td>
      <td>745</td>
    </tr>
    <tr>
      <th>4</th>
      <td>NaN</td>
      <td>Angola</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>24</td>
      <td>25</td>
      <td>25</td>
      <td>25</td>
      <td>25</td>
      <td>26</td>
      <td>27</td>
      <td>27</td>
      <td>27</td>
      <td>27</td>
    </tr>
    <tr>
      <th>5</th>
      <td>NaN</td>
      <td>Antigua and Barbuda</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>23</td>
      <td>24</td>
      <td>24</td>
      <td>24</td>
      <td>24</td>
      <td>24</td>
      <td>24</td>
      <td>24</td>
      <td>24</td>
      <td>24</td>
    </tr>
    <tr>
      <th>6</th>
      <td>NaN</td>
      <td>Argentina</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>3031</td>
      <td>3144</td>
      <td>3435</td>
      <td>3607</td>
      <td>3780</td>
      <td>3892</td>
      <td>4003</td>
      <td>4127</td>
      <td>4285</td>
      <td>4428</td>
    </tr>
    <tr>
      <th>7</th>
      <td>NaN</td>
      <td>Armenia</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>1401</td>
      <td>1473</td>
      <td>1523</td>
      <td>1596</td>
      <td>1677</td>
      <td>1746</td>
      <td>1808</td>
      <td>1867</td>
      <td>1932</td>
      <td>2066</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Australian Capital Territory</td>
      <td>Australia</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>104</td>
      <td>104</td>
      <td>104</td>
      <td>105</td>
      <td>106</td>
      <td>106</td>
      <td>106</td>
      <td>106</td>
      <td>106</td>
      <td>106</td>
    </tr>
    <tr>
      <th>9</th>
      <td>New South Wales</td>
      <td>Australia</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>...</td>
      <td>2969</td>
      <td>2971</td>
      <td>2976</td>
      <td>2982</td>
      <td>2994</td>
      <td>3002</td>
      <td>3004</td>
      <td>3016</td>
      <td>3016</td>
      <td>3025</td>
    </tr>
  </tbody>
</table>
<p>10 rows × 102 columns</p>
</div>



### Task 2.3: Aggregating the rows by the country


```python
corona_dataset_aggregated = corona_dataset_csv.groupby("Country/Region").sum()
```


```python
corona_dataset_aggregated.head()
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
      <th>Province/State</th>
      <th>1/22/20</th>
      <th>1/23/20</th>
      <th>1/24/20</th>
      <th>1/25/20</th>
      <th>1/26/20</th>
      <th>1/27/20</th>
      <th>1/28/20</th>
      <th>1/29/20</th>
      <th>1/30/20</th>
      <th>...</th>
      <th>4/21/20</th>
      <th>4/22/20</th>
      <th>4/23/20</th>
      <th>4/24/20</th>
      <th>4/25/20</th>
      <th>4/26/20</th>
      <th>4/27/20</th>
      <th>4/28/20</th>
      <th>4/29/20</th>
      <th>4/30/20</th>
    </tr>
    <tr>
      <th>Country/Region</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Afghanistan</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>1092</td>
      <td>1176</td>
      <td>1279</td>
      <td>1351</td>
      <td>1463</td>
      <td>1531</td>
      <td>1703</td>
      <td>1828</td>
      <td>1939</td>
      <td>2171</td>
    </tr>
    <tr>
      <th>Albania</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>609</td>
      <td>634</td>
      <td>663</td>
      <td>678</td>
      <td>712</td>
      <td>726</td>
      <td>736</td>
      <td>750</td>
      <td>766</td>
      <td>773</td>
    </tr>
    <tr>
      <th>Algeria</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>2811</td>
      <td>2910</td>
      <td>3007</td>
      <td>3127</td>
      <td>3256</td>
      <td>3382</td>
      <td>3517</td>
      <td>3649</td>
      <td>3848</td>
      <td>4006</td>
    </tr>
    <tr>
      <th>Andorra</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>717</td>
      <td>723</td>
      <td>723</td>
      <td>731</td>
      <td>738</td>
      <td>738</td>
      <td>743</td>
      <td>743</td>
      <td>743</td>
      <td>745</td>
    </tr>
    <tr>
      <th>Angola</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>24</td>
      <td>25</td>
      <td>25</td>
      <td>25</td>
      <td>25</td>
      <td>26</td>
      <td>27</td>
      <td>27</td>
      <td>27</td>
      <td>27</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 101 columns</p>
</div>




```python
corona_dataset_aggregated.shape
```




    (187, 101)



### Task 2.4: Visualizing data related to a country for example Italy
visualization always helps for better understanding of our data.


```python
corona_dataset_aggregated.loc["Italy"].plot()
corona_dataset_aggregated.loc["Spain"].plot()
corona_dataset_aggregated.loc["Singapore"].plot()
plt.legend()
```




    <matplotlib.legend.Legend at 0x208e7477920>




    
![png](output_17_1.png)
    


### Task3: Calculating a good measure 
we need to find a good measure reperestend as a number, describing the spread of the virus in a country. 


```python
corona_dataset_aggregated.loc['Italy'].plot()
```




    <Axes: >




    
![png](output_19_1.png)
    


### task 3.1: caculating the first derivative of the curve


```python
corona_dataset_aggregated.loc["Italy"].diff().plot()
```




    <Axes: >




    
![png](output_21_1.png)
    


### task 3.2: find maxmimum infection rate for Italy, Spain, Singapore


```python
corona_dataset_aggregated.loc["Italy"].diff().max()
```




    6557




```python
corona_dataset_aggregated.loc["Spain"].diff().max()
```




    9630




```python
corona_dataset_aggregated.loc["Singapore"].diff().max()
```




    1426



### Task 3.3: find maximum infection rate for all of the countries. 


```python
countries = list(corona_dataset_aggregated.index)
max_infection_rates = []
for c in countries :
        numeric_data = pd.to_numeric(corona_dataset_aggregated.loc[c][1:], errors='coerce')
        max_infection_rate = numeric_data.diff().max()
        max_infection_rates.append(max_infection_rate)
corona_dataset_aggregated["max_infection_rate"] = max_infection_rates
```


```python
corona_dataset_aggregated.head()
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
      <th>Province/State</th>
      <th>1/22/20</th>
      <th>1/23/20</th>
      <th>1/24/20</th>
      <th>1/25/20</th>
      <th>1/26/20</th>
      <th>1/27/20</th>
      <th>1/28/20</th>
      <th>1/29/20</th>
      <th>1/30/20</th>
      <th>...</th>
      <th>4/22/20</th>
      <th>4/23/20</th>
      <th>4/24/20</th>
      <th>4/25/20</th>
      <th>4/26/20</th>
      <th>4/27/20</th>
      <th>4/28/20</th>
      <th>4/29/20</th>
      <th>4/30/20</th>
      <th>max_infection_rate</th>
    </tr>
    <tr>
      <th>Country/Region</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Afghanistan</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>1176</td>
      <td>1279</td>
      <td>1351</td>
      <td>1463</td>
      <td>1531</td>
      <td>1703</td>
      <td>1828</td>
      <td>1939</td>
      <td>2171</td>
      <td>232.0</td>
    </tr>
    <tr>
      <th>Albania</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>634</td>
      <td>663</td>
      <td>678</td>
      <td>712</td>
      <td>726</td>
      <td>736</td>
      <td>750</td>
      <td>766</td>
      <td>773</td>
      <td>34.0</td>
    </tr>
    <tr>
      <th>Algeria</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>2910</td>
      <td>3007</td>
      <td>3127</td>
      <td>3256</td>
      <td>3382</td>
      <td>3517</td>
      <td>3649</td>
      <td>3848</td>
      <td>4006</td>
      <td>199.0</td>
    </tr>
    <tr>
      <th>Andorra</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>723</td>
      <td>723</td>
      <td>731</td>
      <td>738</td>
      <td>738</td>
      <td>743</td>
      <td>743</td>
      <td>743</td>
      <td>745</td>
      <td>43.0</td>
    </tr>
    <tr>
      <th>Angola</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>25</td>
      <td>25</td>
      <td>25</td>
      <td>25</td>
      <td>26</td>
      <td>27</td>
      <td>27</td>
      <td>27</td>
      <td>27</td>
      <td>5.0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 102 columns</p>
</div>



### Task 3.4: create a new dataframe with only needed column 


```python
corona_data = pd.DataFrame(corona_dataset_aggregated["max_infection_rate"])
```


```python
corona_data.head()
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
      <th>max_infection_rate</th>
    </tr>
    <tr>
      <th>Country/Region</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Afghanistan</th>
      <td>232.0</td>
    </tr>
    <tr>
      <th>Albania</th>
      <td>34.0</td>
    </tr>
    <tr>
      <th>Algeria</th>
      <td>199.0</td>
    </tr>
    <tr>
      <th>Andorra</th>
      <td>43.0</td>
    </tr>
    <tr>
      <th>Angola</th>
      <td>5.0</td>
    </tr>
  </tbody>
</table>
</div>



### Task4: 
- Importing the WorldHappinessReport.csv dataset
- selecting needed columns for our analysis 
- join the datasets 
- calculate the correlations as the result of our analysis

### Task 4.1 : importing the dataset


```python
happiness_report_csv = pd.read_csv("DataSets/worldwide_happiness_report.csv")
```


```python
happiness_report_csv.head()
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
      <th>Overall rank</th>
      <th>Country or region</th>
      <th>Score</th>
      <th>GDP per capita</th>
      <th>Social support</th>
      <th>Healthy life expectancy</th>
      <th>Freedom to make life choices</th>
      <th>Generosity</th>
      <th>Perceptions of corruption</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>Finland</td>
      <td>7.769</td>
      <td>1.340</td>
      <td>1.587</td>
      <td>0.986</td>
      <td>0.596</td>
      <td>0.153</td>
      <td>0.393</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>Denmark</td>
      <td>7.600</td>
      <td>1.383</td>
      <td>1.573</td>
      <td>0.996</td>
      <td>0.592</td>
      <td>0.252</td>
      <td>0.410</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Norway</td>
      <td>7.554</td>
      <td>1.488</td>
      <td>1.582</td>
      <td>1.028</td>
      <td>0.603</td>
      <td>0.271</td>
      <td>0.341</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Iceland</td>
      <td>7.494</td>
      <td>1.380</td>
      <td>1.624</td>
      <td>1.026</td>
      <td>0.591</td>
      <td>0.354</td>
      <td>0.118</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Netherlands</td>
      <td>7.488</td>
      <td>1.396</td>
      <td>1.522</td>
      <td>0.999</td>
      <td>0.557</td>
      <td>0.322</td>
      <td>0.298</td>
    </tr>
  </tbody>
</table>
</div>



### Task 4.2: let's drop the useless columns 


```python
useless_cols = ["Overall rank", "Score", "Generosity", "Perceptions of corruption"] 
```


```python
happiness_report_csv.drop(useless_cols, axis=1, inplace=True)
happiness_report_csv.head()
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
      <th>Country or region</th>
      <th>GDP per capita</th>
      <th>Social support</th>
      <th>Healthy life expectancy</th>
      <th>Freedom to make life choices</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Finland</td>
      <td>1.340</td>
      <td>1.587</td>
      <td>0.986</td>
      <td>0.596</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Denmark</td>
      <td>1.383</td>
      <td>1.573</td>
      <td>0.996</td>
      <td>0.592</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Norway</td>
      <td>1.488</td>
      <td>1.582</td>
      <td>1.028</td>
      <td>0.603</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Iceland</td>
      <td>1.380</td>
      <td>1.624</td>
      <td>1.026</td>
      <td>0.591</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Netherlands</td>
      <td>1.396</td>
      <td>1.522</td>
      <td>0.999</td>
      <td>0.557</td>
    </tr>
  </tbody>
</table>
</div>



### Task 4.3: changing the indices of the dataframe


```python
happiness_report_csv.set_index("Country or region",inplace=True)
```


```python
happiness_report_csv.head()
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
      <th>Country or region</th>
      <th>GDP per capita</th>
      <th>Social support</th>
      <th>Healthy life expectancy</th>
      <th>Freedom to make life choices</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Finland</td>
      <td>1.340</td>
      <td>1.587</td>
      <td>0.986</td>
      <td>0.596</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Denmark</td>
      <td>1.383</td>
      <td>1.573</td>
      <td>0.996</td>
      <td>0.592</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Norway</td>
      <td>1.488</td>
      <td>1.582</td>
      <td>1.028</td>
      <td>0.603</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Iceland</td>
      <td>1.380</td>
      <td>1.624</td>
      <td>1.026</td>
      <td>0.591</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Netherlands</td>
      <td>1.396</td>
      <td>1.522</td>
      <td>0.999</td>
      <td>0.557</td>
    </tr>
  </tbody>
</table>
</div>



### Task4.4: now let's join two dataset we have prepared  

#### Corona Dataset :


```python
corona_data.head()
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
      <th>max_infection_rate</th>
    </tr>
    <tr>
      <th>Country/Region</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Afghanistan</th>
      <td>232.0</td>
    </tr>
    <tr>
      <th>Albania</th>
      <td>34.0</td>
    </tr>
    <tr>
      <th>Algeria</th>
      <td>199.0</td>
    </tr>
    <tr>
      <th>Andorra</th>
      <td>43.0</td>
    </tr>
    <tr>
      <th>Angola</th>
      <td>5.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
corona_data.shape
```




    (187, 1)



#### wolrd happiness report Dataset :


```python
happiness_report_csv.head()
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
      <th>Country or region</th>
      <th>GDP per capita</th>
      <th>Social support</th>
      <th>Healthy life expectancy</th>
      <th>Freedom to make life choices</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Finland</td>
      <td>1.340</td>
      <td>1.587</td>
      <td>0.986</td>
      <td>0.596</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Denmark</td>
      <td>1.383</td>
      <td>1.573</td>
      <td>0.996</td>
      <td>0.592</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Norway</td>
      <td>1.488</td>
      <td>1.582</td>
      <td>1.028</td>
      <td>0.603</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Iceland</td>
      <td>1.380</td>
      <td>1.624</td>
      <td>1.026</td>
      <td>0.591</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Netherlands</td>
      <td>1.396</td>
      <td>1.522</td>
      <td>0.999</td>
      <td>0.557</td>
    </tr>
  </tbody>
</table>
</div>




```python
happiness_report_csv.shape
```




    (156, 5)




```python
merged_data = corona_data.merge(happiness_report_csv, left_on='Country/Region', right_on='Country or region', how='inner')
```


```python

columns = list(merged_data.columns)

country_index = columns.index('Country or region')

columns.insert(country_index + 1, columns.pop(columns.index('max_infection_rate')))

merged_data = merged_data[columns]

```


```python
merged_data.head()
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
      <th>Country or region</th>
      <th>GDP per capita</th>
      <th>max_infection_rate</th>
      <th>Social support</th>
      <th>Healthy life expectancy</th>
      <th>Freedom to make life choices</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>0.350</td>
      <td>232.0</td>
      <td>0.517</td>
      <td>0.361</td>
      <td>0.000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Albania</td>
      <td>0.947</td>
      <td>34.0</td>
      <td>0.848</td>
      <td>0.874</td>
      <td>0.383</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Algeria</td>
      <td>1.002</td>
      <td>199.0</td>
      <td>1.160</td>
      <td>0.785</td>
      <td>0.086</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Argentina</td>
      <td>1.092</td>
      <td>291.0</td>
      <td>1.432</td>
      <td>0.881</td>
      <td>0.471</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Armenia</td>
      <td>0.850</td>
      <td>134.0</td>
      <td>1.055</td>
      <td>0.815</td>
      <td>0.283</td>
    </tr>
  </tbody>
</table>
</div>



### Task 5: Visualization of the results
our Analysis is not finished unless we visualize the results in terms figures and graphs so that everyone can understand what you get out of our analysis


```python
merged_data.head()
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
      <th>Country or region</th>
      <th>GDP per capita</th>
      <th>max_infection_rate</th>
      <th>Social support</th>
      <th>Healthy life expectancy</th>
      <th>Freedom to make life choices</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>0.350</td>
      <td>232.0</td>
      <td>0.517</td>
      <td>0.361</td>
      <td>0.000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Albania</td>
      <td>0.947</td>
      <td>34.0</td>
      <td>0.848</td>
      <td>0.874</td>
      <td>0.383</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Algeria</td>
      <td>1.002</td>
      <td>199.0</td>
      <td>1.160</td>
      <td>0.785</td>
      <td>0.086</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Argentina</td>
      <td>1.092</td>
      <td>291.0</td>
      <td>1.432</td>
      <td>0.881</td>
      <td>0.471</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Armenia</td>
      <td>0.850</td>
      <td>134.0</td>
      <td>1.055</td>
      <td>0.815</td>
      <td>0.283</td>
    </tr>
  </tbody>
</table>
</div>



### Task 5.1: Plotting GDP vs maximum Infection rate


```python
x = merged_data["GDP per capita"]
y = merged_data["max_infection_rate"] 
sns.scatterplot(x='GDP per capita', y='max_infection_rate', data=merged_data)
```




    <Axes: xlabel='GDP per capita', ylabel='max_infection_rate'>




    
![png](output_55_1.png)
    



```python
y_log = np.log(y + 1)
```


```python
sns.regplot(x=x, y=y_log, data=merged_data)
```




    <Axes: xlabel='GDP per capita', ylabel='max_infection_rate'>




    
![png](output_57_1.png)
    

