```python
import sys
import pandas as pd
import numpy as np
import IPython
from IPython.display import display

import matplotlib as mpl
%matplotlib inline
import matplotlib.pyplot as plt

# https://matplotlib.org/stable/gallery/style_sheets/style_sheets_reference.html
plt.style.use('seaborn-v0_8')   # The 'seaborn' style is deprecated

print( f"Python {sys.version}" )
print( f"Pandas {pd.__version__}" )
print( f"NumPy {np.__version__}" )
print( f"IPython {IPython.__version__}" )
print( f"Matplotlib {mpl.__version__}" )
```

    Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0]
    Pandas 2.2.2
    NumPy 1.26.4
    IPython 7.34.0
    Matplotlib 3.7.1
    

#Import data

###Cause of Death


```python
df_cause_of_death = pd.read_csv('https://raw.githubusercontent.com/imyajaii/dads5001-mini-project-01/refs/heads/main/dataset/cause_of_deaths.csv')
# Preview
df_cause_of_death.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 6120 entries, 0 to 6119
    Data columns (total 34 columns):
     #   Column                                      Non-Null Count  Dtype 
    ---  ------                                      --------------  ----- 
     0   Country/Territory                           6120 non-null   object
     1   Code                                        6120 non-null   object
     2   Year                                        6120 non-null   int64 
     3   Meningitis                                  6120 non-null   int64 
     4   Alzheimer's Disease and Other Dementias     6120 non-null   int64 
     5   Parkinson's Disease                         6120 non-null   int64 
     6   Nutritional Deficiencies                    6120 non-null   int64 
     7   Malaria                                     6120 non-null   int64 
     8   Drowning                                    6120 non-null   int64 
     9   Interpersonal Violence                      6120 non-null   int64 
     10  Maternal Disorders                          6120 non-null   int64 
     11  HIV/AIDS                                    6120 non-null   int64 
     12  Drug Use Disorders                          6120 non-null   int64 
     13  Tuberculosis                                6120 non-null   int64 
     14  Cardiovascular Diseases                     6120 non-null   int64 
     15  Lower Respiratory Infections                6120 non-null   int64 
     16  Neonatal Disorders                          6120 non-null   int64 
     17  Alcohol Use Disorders                       6120 non-null   int64 
     18  Self-harm                                   6120 non-null   int64 
     19  Exposure to Forces of Nature                6120 non-null   int64 
     20  Diarrheal Diseases                          6120 non-null   int64 
     21  Environmental Heat and Cold Exposure        6120 non-null   int64 
     22  Neoplasms                                   6120 non-null   int64 
     23  Conflict and Terrorism                      6120 non-null   int64 
     24  Diabetes Mellitus                           6120 non-null   int64 
     25  Chronic Kidney Disease                      6120 non-null   int64 
     26  Poisonings                                  6120 non-null   int64 
     27  Protein-Energy Malnutrition                 6120 non-null   int64 
     28  Road Injuries                               6120 non-null   int64 
     29  Chronic Respiratory Diseases                6120 non-null   int64 
     30  Cirrhosis and Other Chronic Liver Diseases  6120 non-null   int64 
     31  Digestive Diseases                          6120 non-null   int64 
     32  Fire, Heat, and Hot Substances              6120 non-null   int64 
     33  Acute Hepatitis                             6120 non-null   int64 
    dtypes: int64(32), object(2)
    memory usage: 1.6+ MB
    


```python
df_cause_of_death.head()
```





  <div id="df-9e0b54ff-a23e-4b70-acc3-7e15b999a4ff" class="colab-df-container">
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
      <th>Country/Territory</th>
      <th>Code</th>
      <th>Year</th>
      <th>Meningitis</th>
      <th>Alzheimer's Disease and Other Dementias</th>
      <th>Parkinson's Disease</th>
      <th>Nutritional Deficiencies</th>
      <th>Malaria</th>
      <th>Drowning</th>
      <th>Interpersonal Violence</th>
      <th>...</th>
      <th>Diabetes Mellitus</th>
      <th>Chronic Kidney Disease</th>
      <th>Poisonings</th>
      <th>Protein-Energy Malnutrition</th>
      <th>Road Injuries</th>
      <th>Chronic Respiratory Diseases</th>
      <th>Cirrhosis and Other Chronic Liver Diseases</th>
      <th>Digestive Diseases</th>
      <th>Fire, Heat, and Hot Substances</th>
      <th>Acute Hepatitis</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1990</td>
      <td>2159</td>
      <td>1116</td>
      <td>371</td>
      <td>2087</td>
      <td>93</td>
      <td>1370</td>
      <td>1538</td>
      <td>...</td>
      <td>2108</td>
      <td>3709</td>
      <td>338</td>
      <td>2054</td>
      <td>4154</td>
      <td>5945</td>
      <td>2673</td>
      <td>5005</td>
      <td>323</td>
      <td>2985</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1991</td>
      <td>2218</td>
      <td>1136</td>
      <td>374</td>
      <td>2153</td>
      <td>189</td>
      <td>1391</td>
      <td>2001</td>
      <td>...</td>
      <td>2120</td>
      <td>3724</td>
      <td>351</td>
      <td>2119</td>
      <td>4472</td>
      <td>6050</td>
      <td>2728</td>
      <td>5120</td>
      <td>332</td>
      <td>3092</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1992</td>
      <td>2475</td>
      <td>1162</td>
      <td>378</td>
      <td>2441</td>
      <td>239</td>
      <td>1514</td>
      <td>2299</td>
      <td>...</td>
      <td>2153</td>
      <td>3776</td>
      <td>386</td>
      <td>2404</td>
      <td>5106</td>
      <td>6223</td>
      <td>2830</td>
      <td>5335</td>
      <td>360</td>
      <td>3325</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1993</td>
      <td>2812</td>
      <td>1187</td>
      <td>384</td>
      <td>2837</td>
      <td>108</td>
      <td>1687</td>
      <td>2589</td>
      <td>...</td>
      <td>2195</td>
      <td>3862</td>
      <td>425</td>
      <td>2797</td>
      <td>5681</td>
      <td>6445</td>
      <td>2943</td>
      <td>5568</td>
      <td>396</td>
      <td>3601</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1994</td>
      <td>3027</td>
      <td>1211</td>
      <td>391</td>
      <td>3081</td>
      <td>211</td>
      <td>1809</td>
      <td>2849</td>
      <td>...</td>
      <td>2231</td>
      <td>3932</td>
      <td>451</td>
      <td>3038</td>
      <td>6001</td>
      <td>6664</td>
      <td>3027</td>
      <td>5739</td>
      <td>420</td>
      <td>3816</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 34 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-9e0b54ff-a23e-4b70-acc3-7e15b999a4ff')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-9e0b54ff-a23e-4b70-acc3-7e15b999a4ff button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-9e0b54ff-a23e-4b70-acc3-7e15b999a4ff');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-8f058872-3c52-453b-8db7-8878be8b8519">
  <button class="colab-df-quickchart" onclick="quickchart('df-8f058872-3c52-453b-8db7-8878be8b8519')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-8f058872-3c52-453b-8db7-8878be8b8519 button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>





```python
df_cause_of_death['Code'].unique()
```




    array(['AFG', 'ALB', 'DZA', 'ASM', 'AND', 'AGO', 'ATG', 'ARG', 'ARM',
           'AUS', 'AUT', 'AZE', 'BHS', 'BHR', 'BGD', 'BRB', 'BLR', 'BEL',
           'BLZ', 'BEN', 'BMU', 'BTN', 'BOL', 'BIH', 'BWA', 'BRA', 'BRN',
           'BGR', 'BFA', 'BDI', 'KHM', 'CMR', 'CAN', 'CPV', 'CAF', 'TCD',
           'CHL', 'CHN', 'COL', 'COM', 'COG', 'COK', 'CRI', 'CIV', 'HRV',
           'CUB', 'CYP', 'CZE', 'COD', 'DNK', 'DJI', 'DMA', 'DOM', 'ECU',
           'EGY', 'SLV', 'GNQ', 'ERI', 'EST', 'SWZ', 'ETH', 'FJI', 'FIN',
           'FRA', 'GAB', 'GMB', 'GEO', 'DEU', 'GHA', 'GRC', 'GRL', 'GRD',
           'GUM', 'GTM', 'GIN', 'GNB', 'GUY', 'HTI', 'HND', 'HUN', 'ISL',
           'IND', 'IDN', 'IRN', 'IRQ', 'IRL', 'ISR', 'ITA', 'JAM', 'JPN',
           'JOR', 'KAZ', 'KEN', 'KIR', 'KWT', 'KGZ', 'LAO', 'LVA', 'LBN',
           'LSO', 'LBR', 'LBY', 'LTU', 'LUX', 'MDG', 'MWI', 'MYS', 'MDV',
           'MLI', 'MLT', 'MHL', 'MRT', 'MUS', 'MEX', 'FSM', 'MDA', 'MCO',
           'MNG', 'MNE', 'MAR', 'MOZ', 'MMR', 'NAM', 'NRU', 'NPL', 'NLD',
           'NZL', 'NIC', 'NER', 'NGA', 'NIU', 'PRK', 'MKD', 'MNP', 'NOR',
           'OMN', 'PAK', 'PLW', 'PSE', 'PAN', 'PNG', 'PRY', 'PER', 'PHL',
           'POL', 'PRT', 'PRI', 'QAT', 'ROU', 'RUS', 'RWA', 'KNA', 'LCA',
           'VCT', 'WSM', 'SMR', 'STP', 'SAU', 'SEN', 'SRB', 'SYC', 'SLE',
           'SGP', 'SVK', 'SVN', 'SLB', 'SOM', 'ZAF', 'KOR', 'SSD', 'ESP',
           'LKA', 'SDN', 'SUR', 'SWE', 'CHE', 'SYR', 'TWN', 'TJK', 'TZA',
           'THA', 'TLS', 'TGO', 'TKL', 'TON', 'TTO', 'TUN', 'TUR', 'TKM',
           'TUV', 'UGA', 'UKR', 'ARE', 'GBR', 'USA', 'VIR', 'URY', 'UZB',
           'VUT', 'VEN', 'VNM', 'YEM', 'ZMB', 'ZWE'], dtype=object)




```python
df_cause_of_death['Code'].unique()
lst = df_cause_of_death['Code'].unique()
len(lst)
```




    204



###Continent


```python
df_continent = pd.read_csv('https://raw.githubusercontent.com/imyajaii/dads5001-mini-project-01/refs/heads/main/dataset/countryContinent.csv',encoding='latin-1') # Try 'latin-1' encoding

# Preview
df_continent.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 249 entries, 0 to 248
    Data columns (total 9 columns):
     #   Column           Non-Null Count  Dtype  
    ---  ------           --------------  -----  
     0   country          249 non-null    object 
     1   code_2           248 non-null    object 
     2   code_3           249 non-null    object 
     3   country_code     249 non-null    int64  
     4   iso_3166_2       249 non-null    object 
     5   continent        240 non-null    object 
     6   sub_region       240 non-null    object 
     7   region_code      240 non-null    float64
     8   sub_region_code  240 non-null    float64
    dtypes: float64(2), int64(1), object(6)
    memory usage: 17.6+ KB
    

###World Population


```python
df_population = pd.read_csv('https://raw.githubusercontent.com/imyajaii/dads5001-mini-project-01/refs/heads/main/dataset/World-population-by-countries-dataset.csv')

# Preview
df_population.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 266 entries, 0 to 265
    Data columns (total 64 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   Country Name  266 non-null    object 
     1   Country Code  266 non-null    object 
     2   1960          264 non-null    float64
     3   1961          264 non-null    float64
     4   1962          264 non-null    float64
     5   1963          264 non-null    float64
     6   1964          264 non-null    float64
     7   1965          264 non-null    float64
     8   1966          264 non-null    float64
     9   1967          264 non-null    float64
     10  1968          264 non-null    float64
     11  1969          264 non-null    float64
     12  1970          264 non-null    float64
     13  1971          264 non-null    float64
     14  1972          264 non-null    float64
     15  1973          264 non-null    float64
     16  1974          264 non-null    float64
     17  1975          264 non-null    float64
     18  1976          264 non-null    float64
     19  1977          264 non-null    float64
     20  1978          264 non-null    float64
     21  1979          264 non-null    float64
     22  1980          264 non-null    float64
     23  1981          264 non-null    float64
     24  1982          264 non-null    float64
     25  1983          264 non-null    float64
     26  1984          264 non-null    float64
     27  1985          264 non-null    float64
     28  1986          264 non-null    float64
     29  1987          264 non-null    float64
     30  1988          264 non-null    float64
     31  1989          264 non-null    float64
     32  1990          265 non-null    float64
     33  1991          265 non-null    float64
     34  1992          264 non-null    float64
     35  1993          264 non-null    float64
     36  1994          264 non-null    float64
     37  1995          265 non-null    float64
     38  1996          265 non-null    float64
     39  1997          265 non-null    float64
     40  1998          265 non-null    float64
     41  1999          265 non-null    float64
     42  2000          265 non-null    float64
     43  2001          265 non-null    float64
     44  2002          265 non-null    float64
     45  2003          265 non-null    float64
     46  2004          265 non-null    float64
     47  2005          265 non-null    float64
     48  2006          265 non-null    float64
     49  2007          265 non-null    float64
     50  2008          265 non-null    float64
     51  2009          265 non-null    float64
     52  2010          265 non-null    float64
     53  2011          265 non-null    float64
     54  2012          264 non-null    float64
     55  2013          264 non-null    float64
     56  2014          264 non-null    float64
     57  2015          264 non-null    float64
     58  2016          264 non-null    float64
     59  2017          264 non-null    float64
     60  2018          264 non-null    float64
     61  2019          264 non-null    float64
     62  2020          264 non-null    float64
     63  2021          264 non-null    float64
    dtypes: float64(62), object(2)
    memory usage: 133.1+ KB
    

#Cleansing

##World Population

### Drop unnecessary column


```python
df_population.head()
```





  <div id="df-49bc2366-fe6e-49b6-be57-d74ac2c0d982" class="colab-df-container">
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
      <th>Country Name</th>
      <th>Country Code</th>
      <th>1960</th>
      <th>1961</th>
      <th>1962</th>
      <th>1963</th>
      <th>1964</th>
      <th>1965</th>
      <th>1966</th>
      <th>1967</th>
      <th>...</th>
      <th>2012</th>
      <th>2013</th>
      <th>2014</th>
      <th>2015</th>
      <th>2016</th>
      <th>2017</th>
      <th>2018</th>
      <th>2019</th>
      <th>2020</th>
      <th>2021</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Aruba</td>
      <td>ABW</td>
      <td>54208.0</td>
      <td>55434.0</td>
      <td>56234.0</td>
      <td>56699.0</td>
      <td>57029.0</td>
      <td>57357.0</td>
      <td>57702.0</td>
      <td>58044.0</td>
      <td>...</td>
      <td>102565.0</td>
      <td>103165.0</td>
      <td>103776.0</td>
      <td>104339.0</td>
      <td>104865.0</td>
      <td>105361.0</td>
      <td>105846.0</td>
      <td>106310.0</td>
      <td>106766.0</td>
      <td>107195.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Africa Eastern and Southern</td>
      <td>AFE</td>
      <td>130836765.0</td>
      <td>134159786.0</td>
      <td>137614644.0</td>
      <td>141202036.0</td>
      <td>144920186.0</td>
      <td>148769974.0</td>
      <td>152752671.0</td>
      <td>156876454.0</td>
      <td>...</td>
      <td>547482863.0</td>
      <td>562601578.0</td>
      <td>578075373.0</td>
      <td>593871847.0</td>
      <td>609978946.0</td>
      <td>626392880.0</td>
      <td>643090131.0</td>
      <td>660046272.0</td>
      <td>677243299.0</td>
      <td>694665117.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>8996967.0</td>
      <td>9169406.0</td>
      <td>9351442.0</td>
      <td>9543200.0</td>
      <td>9744772.0</td>
      <td>9956318.0</td>
      <td>10174840.0</td>
      <td>10399936.0</td>
      <td>...</td>
      <td>31161378.0</td>
      <td>32269592.0</td>
      <td>33370804.0</td>
      <td>34413603.0</td>
      <td>35383028.0</td>
      <td>36296111.0</td>
      <td>37171922.0</td>
      <td>38041757.0</td>
      <td>38928341.0</td>
      <td>39835428.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Africa Western and Central</td>
      <td>AFW</td>
      <td>96396419.0</td>
      <td>98407221.0</td>
      <td>100506960.0</td>
      <td>102691339.0</td>
      <td>104953470.0</td>
      <td>107289875.0</td>
      <td>109701811.0</td>
      <td>112195950.0</td>
      <td>...</td>
      <td>370243017.0</td>
      <td>380437896.0</td>
      <td>390882979.0</td>
      <td>401586651.0</td>
      <td>412551299.0</td>
      <td>423769930.0</td>
      <td>435229381.0</td>
      <td>446911598.0</td>
      <td>458803476.0</td>
      <td>470898870.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Angola</td>
      <td>AGO</td>
      <td>5454938.0</td>
      <td>5531451.0</td>
      <td>5608499.0</td>
      <td>5679409.0</td>
      <td>5734995.0</td>
      <td>5770573.0</td>
      <td>5781305.0</td>
      <td>5774440.0</td>
      <td>...</td>
      <td>25107925.0</td>
      <td>26015786.0</td>
      <td>26941773.0</td>
      <td>27884380.0</td>
      <td>28842482.0</td>
      <td>29816769.0</td>
      <td>30809787.0</td>
      <td>31825299.0</td>
      <td>32866268.0</td>
      <td>33933611.0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 64 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-49bc2366-fe6e-49b6-be57-d74ac2c0d982')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-49bc2366-fe6e-49b6-be57-d74ac2c0d982 button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-49bc2366-fe6e-49b6-be57-d74ac2c0d982');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-c30acad1-02d4-4ebd-be13-ca42a5a13bd8">
  <button class="colab-df-quickchart" onclick="quickchart('df-c30acad1-02d4-4ebd-be13-ca42a5a13bd8')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-c30acad1-02d4-4ebd-be13-ca42a5a13bd8 button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>





```python
# prompt: drop column 1960 - 1989 , 2020 , 2021 of df_population

columns_to_drop = [str(year) for year in range(1960, 1990)] + ['2020', '2021']
df_population = df_population.drop(columns=columns_to_drop)
df_population

```





  <div id="df-7941d092-d26a-4935-b325-a7f68b6f834a" class="colab-df-container">
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
      <th>Country Name</th>
      <th>Country Code</th>
      <th>1990</th>
      <th>1991</th>
      <th>1992</th>
      <th>1993</th>
      <th>1994</th>
      <th>1995</th>
      <th>1996</th>
      <th>1997</th>
      <th>...</th>
      <th>2010</th>
      <th>2011</th>
      <th>2012</th>
      <th>2013</th>
      <th>2014</th>
      <th>2015</th>
      <th>2016</th>
      <th>2017</th>
      <th>2018</th>
      <th>2019</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Aruba</td>
      <td>ABW</td>
      <td>62152.0</td>
      <td>64623.0</td>
      <td>68240.0</td>
      <td>72495.0</td>
      <td>76705.0</td>
      <td>80324.0</td>
      <td>83211.0</td>
      <td>85450.0</td>
      <td>...</td>
      <td>101665.0</td>
      <td>102050.0</td>
      <td>102565.0</td>
      <td>103165.0</td>
      <td>103776.0</td>
      <td>104339.0</td>
      <td>104865.0</td>
      <td>105361.0</td>
      <td>105846.0</td>
      <td>106310.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Africa Eastern and Southern</td>
      <td>AFE</td>
      <td>304648010.0</td>
      <td>313394693.0</td>
      <td>322270073.0</td>
      <td>331265579.0</td>
      <td>340379934.0</td>
      <td>349605660.0</td>
      <td>358953595.0</td>
      <td>368440591.0</td>
      <td>...</td>
      <td>518468229.0</td>
      <td>532760424.0</td>
      <td>547482863.0</td>
      <td>562601578.0</td>
      <td>578075373.0</td>
      <td>593871847.0</td>
      <td>609978946.0</td>
      <td>626392880.0</td>
      <td>643090131.0</td>
      <td>660046272.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>12412311.0</td>
      <td>13299016.0</td>
      <td>14485543.0</td>
      <td>15816601.0</td>
      <td>17075728.0</td>
      <td>18110662.0</td>
      <td>18853444.0</td>
      <td>19357126.0</td>
      <td>...</td>
      <td>29185511.0</td>
      <td>30117411.0</td>
      <td>31161378.0</td>
      <td>32269592.0</td>
      <td>33370804.0</td>
      <td>34413603.0</td>
      <td>35383028.0</td>
      <td>36296111.0</td>
      <td>37171922.0</td>
      <td>38041757.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Africa Western and Central</td>
      <td>AFW</td>
      <td>204803865.0</td>
      <td>210332267.0</td>
      <td>215976366.0</td>
      <td>221754806.0</td>
      <td>227692136.0</td>
      <td>233807627.0</td>
      <td>240114179.0</td>
      <td>246613750.0</td>
      <td>...</td>
      <td>350556886.0</td>
      <td>360285439.0</td>
      <td>370243017.0</td>
      <td>380437896.0</td>
      <td>390882979.0</td>
      <td>401586651.0</td>
      <td>412551299.0</td>
      <td>423769930.0</td>
      <td>435229381.0</td>
      <td>446911598.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Angola</td>
      <td>AGO</td>
      <td>11848385.0</td>
      <td>12248901.0</td>
      <td>12657361.0</td>
      <td>13075044.0</td>
      <td>13503753.0</td>
      <td>13945205.0</td>
      <td>14400722.0</td>
      <td>14871572.0</td>
      <td>...</td>
      <td>23356247.0</td>
      <td>24220660.0</td>
      <td>25107925.0</td>
      <td>26015786.0</td>
      <td>26941773.0</td>
      <td>27884380.0</td>
      <td>28842482.0</td>
      <td>29816769.0</td>
      <td>30809787.0</td>
      <td>31825299.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>261</th>
      <td>Kosovo</td>
      <td>XKX</td>
      <td>1862000.0</td>
      <td>1898000.0</td>
      <td>1932000.0</td>
      <td>1965000.0</td>
      <td>1997000.0</td>
      <td>2029000.0</td>
      <td>2059000.0</td>
      <td>2086000.0</td>
      <td>...</td>
      <td>1775680.0</td>
      <td>1791000.0</td>
      <td>1807106.0</td>
      <td>1818117.0</td>
      <td>1812771.0</td>
      <td>1788196.0</td>
      <td>1777557.0</td>
      <td>1791003.0</td>
      <td>1797085.0</td>
      <td>1788878.0</td>
    </tr>
    <tr>
      <th>262</th>
      <td>Yemen, Rep.</td>
      <td>YEM</td>
      <td>11709987.0</td>
      <td>12302127.0</td>
      <td>12954157.0</td>
      <td>13634082.0</td>
      <td>14297617.0</td>
      <td>14913313.0</td>
      <td>15469274.0</td>
      <td>15975676.0</td>
      <td>...</td>
      <td>23154854.0</td>
      <td>23807586.0</td>
      <td>24473176.0</td>
      <td>25147112.0</td>
      <td>25823488.0</td>
      <td>26497881.0</td>
      <td>27168210.0</td>
      <td>27834811.0</td>
      <td>28498683.0</td>
      <td>29161922.0</td>
    </tr>
    <tr>
      <th>263</th>
      <td>South Africa</td>
      <td>ZAF</td>
      <td>36800507.0</td>
      <td>37718952.0</td>
      <td>38672611.0</td>
      <td>39633754.0</td>
      <td>40564061.0</td>
      <td>41435761.0</td>
      <td>42241007.0</td>
      <td>42987456.0</td>
      <td>...</td>
      <td>51216967.0</td>
      <td>52003759.0</td>
      <td>52832659.0</td>
      <td>53687125.0</td>
      <td>54544184.0</td>
      <td>55386369.0</td>
      <td>56207649.0</td>
      <td>57009751.0</td>
      <td>57792520.0</td>
      <td>58558267.0</td>
    </tr>
    <tr>
      <th>264</th>
      <td>Zambia</td>
      <td>ZMB</td>
      <td>8036849.0</td>
      <td>8246662.0</td>
      <td>8451346.0</td>
      <td>8656484.0</td>
      <td>8869745.0</td>
      <td>9096608.0</td>
      <td>9339740.0</td>
      <td>9597610.0</td>
      <td>...</td>
      <td>13605986.0</td>
      <td>14023199.0</td>
      <td>14465148.0</td>
      <td>14926551.0</td>
      <td>15399793.0</td>
      <td>15879370.0</td>
      <td>16363449.0</td>
      <td>16853608.0</td>
      <td>17351714.0</td>
      <td>17861034.0</td>
    </tr>
    <tr>
      <th>265</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>10432409.0</td>
      <td>10681008.0</td>
      <td>10900511.0</td>
      <td>11092775.0</td>
      <td>11261752.0</td>
      <td>11410721.0</td>
      <td>11541215.0</td>
      <td>11653254.0</td>
      <td>...</td>
      <td>12697728.0</td>
      <td>12894323.0</td>
      <td>13115149.0</td>
      <td>13350378.0</td>
      <td>13586710.0</td>
      <td>13814642.0</td>
      <td>14030338.0</td>
      <td>14236599.0</td>
      <td>14438812.0</td>
      <td>14645473.0</td>
    </tr>
  </tbody>
</table>
<p>266 rows × 32 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-7941d092-d26a-4935-b325-a7f68b6f834a')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-7941d092-d26a-4935-b325-a7f68b6f834a button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-7941d092-d26a-4935-b325-a7f68b6f834a');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-6f1a831f-183f-44a9-93ef-6ac8df6909e0">
  <button class="colab-df-quickchart" onclick="quickchart('df-6f1a831f-183f-44a9-93ef-6ac8df6909e0')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-6f1a831f-183f-44a9-93ef-6ac8df6909e0 button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

  <div id="id_b0a862ee-6032-40be-a913-a5841aa799f7">
    <style>
      .colab-df-generate {
        background-color: #E8F0FE;
        border: none;
        border-radius: 50%;
        cursor: pointer;
        display: none;
        fill: #1967D2;
        height: 32px;
        padding: 0 0 0 0;
        width: 32px;
      }

      .colab-df-generate:hover {
        background-color: #E2EBFA;
        box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
        fill: #174EA6;
      }

      [theme=dark] .colab-df-generate {
        background-color: #3B4455;
        fill: #D2E3FC;
      }

      [theme=dark] .colab-df-generate:hover {
        background-color: #434B5C;
        box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
        filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
        fill: #FFFFFF;
      }
    </style>
    <button class="colab-df-generate" onclick="generateWithVariable('df_population')"
            title="Generate code using this dataframe."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M7,19H8.4L18.45,9,17,7.55,7,17.6ZM5,21V16.75L18.45,3.32a2,2,0,0,1,2.83,0l1.4,1.43a1.91,1.91,0,0,1,.58,1.4,1.91,1.91,0,0,1-.58,1.4L9.25,21ZM18.45,9,17,7.55Zm-12,3A5.31,5.31,0,0,0,4.9,8.1,5.31,5.31,0,0,0,1,6.5,5.31,5.31,0,0,0,4.9,4.9,5.31,5.31,0,0,0,6.5,1,5.31,5.31,0,0,0,8.1,4.9,5.31,5.31,0,0,0,12,6.5,5.46,5.46,0,0,0,6.5,12Z"/>
  </svg>
    </button>
    <script>
      (() => {
      const buttonEl =
        document.querySelector('#id_b0a862ee-6032-40be-a913-a5841aa799f7 button.colab-df-generate');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      buttonEl.onclick = () => {
        google.colab.notebook.generateWithVariable('df_population');
      }
      })();
    </script>
  </div>

    </div>
  </div>




###Reshape data of Pupulation


```python
# prompt: i want to reshape  df_population of column 1990 - 2019 into row of each of Column Country Code (the new name of column is Population) keep column Country Name

df_population_melted = df_population.melt(id_vars=['Country Name', 'Country Code'],
                                         var_name='Year',
                                         value_name='Population')

df_population_melted.head()

```





  <div id="df-65514841-7b53-4092-83ea-d5ca84887978" class="colab-df-container">
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
      <th>Country Name</th>
      <th>Country Code</th>
      <th>Year</th>
      <th>Population</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Aruba</td>
      <td>ABW</td>
      <td>1990</td>
      <td>62152.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Africa Eastern and Southern</td>
      <td>AFE</td>
      <td>1990</td>
      <td>304648010.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1990</td>
      <td>12412311.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Africa Western and Central</td>
      <td>AFW</td>
      <td>1990</td>
      <td>204803865.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Angola</td>
      <td>AGO</td>
      <td>1990</td>
      <td>11848385.0</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-65514841-7b53-4092-83ea-d5ca84887978')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-65514841-7b53-4092-83ea-d5ca84887978 button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-65514841-7b53-4092-83ea-d5ca84887978');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-8eeff589-8c26-436e-bcbc-85e0188db02d">
  <button class="colab-df-quickchart" onclick="quickchart('df-8eeff589-8c26-436e-bcbc-85e0188db02d')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-8eeff589-8c26-436e-bcbc-85e0188db02d button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>





```python
df_population_melted.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 7980 entries, 0 to 7979
    Data columns (total 4 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   Country Name  7980 non-null   object 
     1   Country Code  7980 non-null   object 
     2   Year          7980 non-null   object 
     3   Population    7939 non-null   float64
    dtypes: float64(1), object(3)
    memory usage: 249.5+ KB
    

##Continent

###Drop unnecessary column of continent


```python
df_continent = df_continent.drop(['country', 'code_2', 'country_code', 'iso_3166_2', 'region_code', 'sub_region_code'], axis=1)

```


```python
df_continent.info()
df_continent.head()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 249 entries, 0 to 248
    Data columns (total 3 columns):
     #   Column      Non-Null Count  Dtype 
    ---  ------      --------------  ----- 
     0   code_3      249 non-null    object
     1   continent   240 non-null    object
     2   sub_region  240 non-null    object
    dtypes: object(3)
    memory usage: 6.0+ KB
    





  <div id="df-4cad1f4c-a17e-4762-b351-d45e29098af0" class="colab-df-container">
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
      <th>code_3</th>
      <th>continent</th>
      <th>sub_region</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
    </tr>
    <tr>
      <th>1</th>
      <td>ALA</td>
      <td>Europe</td>
      <td>Northern Europe</td>
    </tr>
    <tr>
      <th>2</th>
      <td>ALB</td>
      <td>Europe</td>
      <td>Southern Europe</td>
    </tr>
    <tr>
      <th>3</th>
      <td>DZA</td>
      <td>Africa</td>
      <td>Northern Africa</td>
    </tr>
    <tr>
      <th>4</th>
      <td>ASM</td>
      <td>Oceania</td>
      <td>Polynesia</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-4cad1f4c-a17e-4762-b351-d45e29098af0')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-4cad1f4c-a17e-4762-b351-d45e29098af0 button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-4cad1f4c-a17e-4762-b351-d45e29098af0');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-84a42266-f739-43ac-a0fc-c21bda66a7ac">
  <button class="colab-df-quickchart" onclick="quickchart('df-84a42266-f739-43ac-a0fc-c21bda66a7ac')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-84a42266-f739-43ac-a0fc-c21bda66a7ac button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>




##Cause of Death

###Merge data by Country code 3 digits


```python
# prompt: check if the column Code of df_cause_of_death was all in column code_3 of df_cintinent

# Convert both columns to sets for efficient comparison
cause_of_death_codes = set(df_cause_of_death['Code'].unique())
continent_codes = set(df_continent['code_3'].unique())

# Check if all codes in df_cause_of_death are present in df_continent
all_codes_present = cause_of_death_codes.issubset(continent_codes)

print(f"Are all 'Code' values from df_cause_of_death present in 'code_3' of df_continent? {all_codes_present}")

```

    Are all 'Code' values from df_cause_of_death present in 'code_3' of df_continent? True
    


```python
df_join1 = pd.merge( df_cause_of_death, df_continent, left_on='Code', right_on='code_3', how='left' )
df_join1.head()
```





  <div id="df-e041f548-a69b-4fb9-b70e-1f36eacd769f" class="colab-df-container">
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
      <th>Country/Territory</th>
      <th>Code</th>
      <th>Year</th>
      <th>Meningitis</th>
      <th>Alzheimer's Disease and Other Dementias</th>
      <th>Parkinson's Disease</th>
      <th>Nutritional Deficiencies</th>
      <th>Malaria</th>
      <th>Drowning</th>
      <th>Interpersonal Violence</th>
      <th>...</th>
      <th>Protein-Energy Malnutrition</th>
      <th>Road Injuries</th>
      <th>Chronic Respiratory Diseases</th>
      <th>Cirrhosis and Other Chronic Liver Diseases</th>
      <th>Digestive Diseases</th>
      <th>Fire, Heat, and Hot Substances</th>
      <th>Acute Hepatitis</th>
      <th>code_3</th>
      <th>continent</th>
      <th>sub_region</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1990</td>
      <td>2159</td>
      <td>1116</td>
      <td>371</td>
      <td>2087</td>
      <td>93</td>
      <td>1370</td>
      <td>1538</td>
      <td>...</td>
      <td>2054</td>
      <td>4154</td>
      <td>5945</td>
      <td>2673</td>
      <td>5005</td>
      <td>323</td>
      <td>2985</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1991</td>
      <td>2218</td>
      <td>1136</td>
      <td>374</td>
      <td>2153</td>
      <td>189</td>
      <td>1391</td>
      <td>2001</td>
      <td>...</td>
      <td>2119</td>
      <td>4472</td>
      <td>6050</td>
      <td>2728</td>
      <td>5120</td>
      <td>332</td>
      <td>3092</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1992</td>
      <td>2475</td>
      <td>1162</td>
      <td>378</td>
      <td>2441</td>
      <td>239</td>
      <td>1514</td>
      <td>2299</td>
      <td>...</td>
      <td>2404</td>
      <td>5106</td>
      <td>6223</td>
      <td>2830</td>
      <td>5335</td>
      <td>360</td>
      <td>3325</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1993</td>
      <td>2812</td>
      <td>1187</td>
      <td>384</td>
      <td>2837</td>
      <td>108</td>
      <td>1687</td>
      <td>2589</td>
      <td>...</td>
      <td>2797</td>
      <td>5681</td>
      <td>6445</td>
      <td>2943</td>
      <td>5568</td>
      <td>396</td>
      <td>3601</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1994</td>
      <td>3027</td>
      <td>1211</td>
      <td>391</td>
      <td>3081</td>
      <td>211</td>
      <td>1809</td>
      <td>2849</td>
      <td>...</td>
      <td>3038</td>
      <td>6001</td>
      <td>6664</td>
      <td>3027</td>
      <td>5739</td>
      <td>420</td>
      <td>3816</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 37 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-e041f548-a69b-4fb9-b70e-1f36eacd769f')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-e041f548-a69b-4fb9-b70e-1f36eacd769f button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-e041f548-a69b-4fb9-b70e-1f36eacd769f');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-ee437b9c-ef28-4e58-8ec3-1dc0561b492f">
  <button class="colab-df-quickchart" onclick="quickchart('df-ee437b9c-ef28-4e58-8ec3-1dc0561b492f')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-ee437b9c-ef28-4e58-8ec3-1dc0561b492f button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>





```python
df_join1.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 6120 entries, 0 to 6119
    Data columns (total 37 columns):
     #   Column                                      Non-Null Count  Dtype 
    ---  ------                                      --------------  ----- 
     0   Country/Territory                           6120 non-null   object
     1   Code                                        6120 non-null   object
     2   Year                                        6120 non-null   int64 
     3   Meningitis                                  6120 non-null   int64 
     4   Alzheimer's Disease and Other Dementias     6120 non-null   int64 
     5   Parkinson's Disease                         6120 non-null   int64 
     6   Nutritional Deficiencies                    6120 non-null   int64 
     7   Malaria                                     6120 non-null   int64 
     8   Drowning                                    6120 non-null   int64 
     9   Interpersonal Violence                      6120 non-null   int64 
     10  Maternal Disorders                          6120 non-null   int64 
     11  HIV/AIDS                                    6120 non-null   int64 
     12  Drug Use Disorders                          6120 non-null   int64 
     13  Tuberculosis                                6120 non-null   int64 
     14  Cardiovascular Diseases                     6120 non-null   int64 
     15  Lower Respiratory Infections                6120 non-null   int64 
     16  Neonatal Disorders                          6120 non-null   int64 
     17  Alcohol Use Disorders                       6120 non-null   int64 
     18  Self-harm                                   6120 non-null   int64 
     19  Exposure to Forces of Nature                6120 non-null   int64 
     20  Diarrheal Diseases                          6120 non-null   int64 
     21  Environmental Heat and Cold Exposure        6120 non-null   int64 
     22  Neoplasms                                   6120 non-null   int64 
     23  Conflict and Terrorism                      6120 non-null   int64 
     24  Diabetes Mellitus                           6120 non-null   int64 
     25  Chronic Kidney Disease                      6120 non-null   int64 
     26  Poisonings                                  6120 non-null   int64 
     27  Protein-Energy Malnutrition                 6120 non-null   int64 
     28  Road Injuries                               6120 non-null   int64 
     29  Chronic Respiratory Diseases                6120 non-null   int64 
     30  Cirrhosis and Other Chronic Liver Diseases  6120 non-null   int64 
     31  Digestive Diseases                          6120 non-null   int64 
     32  Fire, Heat, and Hot Substances              6120 non-null   int64 
     33  Acute Hepatitis                             6120 non-null   int64 
     34  code_3                                      6120 non-null   object
     35  continent                                   6120 non-null   object
     36  sub_region                                  6120 non-null   object
    dtypes: int64(32), object(5)
    memory usage: 1.7+ MB
    


```python
df_join1 = df_join1.drop(['code_3'], axis=1) # Drop duplicate column
df_join1.head()
```





  <div id="df-5d939d8e-ec72-449d-86bd-0facdb9dfe1a" class="colab-df-container">
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
      <th>Country/Territory</th>
      <th>Code</th>
      <th>Year</th>
      <th>Meningitis</th>
      <th>Alzheimer's Disease and Other Dementias</th>
      <th>Parkinson's Disease</th>
      <th>Nutritional Deficiencies</th>
      <th>Malaria</th>
      <th>Drowning</th>
      <th>Interpersonal Violence</th>
      <th>...</th>
      <th>Poisonings</th>
      <th>Protein-Energy Malnutrition</th>
      <th>Road Injuries</th>
      <th>Chronic Respiratory Diseases</th>
      <th>Cirrhosis and Other Chronic Liver Diseases</th>
      <th>Digestive Diseases</th>
      <th>Fire, Heat, and Hot Substances</th>
      <th>Acute Hepatitis</th>
      <th>continent</th>
      <th>sub_region</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1990</td>
      <td>2159</td>
      <td>1116</td>
      <td>371</td>
      <td>2087</td>
      <td>93</td>
      <td>1370</td>
      <td>1538</td>
      <td>...</td>
      <td>338</td>
      <td>2054</td>
      <td>4154</td>
      <td>5945</td>
      <td>2673</td>
      <td>5005</td>
      <td>323</td>
      <td>2985</td>
      <td>Asia</td>
      <td>Southern Asia</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1991</td>
      <td>2218</td>
      <td>1136</td>
      <td>374</td>
      <td>2153</td>
      <td>189</td>
      <td>1391</td>
      <td>2001</td>
      <td>...</td>
      <td>351</td>
      <td>2119</td>
      <td>4472</td>
      <td>6050</td>
      <td>2728</td>
      <td>5120</td>
      <td>332</td>
      <td>3092</td>
      <td>Asia</td>
      <td>Southern Asia</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1992</td>
      <td>2475</td>
      <td>1162</td>
      <td>378</td>
      <td>2441</td>
      <td>239</td>
      <td>1514</td>
      <td>2299</td>
      <td>...</td>
      <td>386</td>
      <td>2404</td>
      <td>5106</td>
      <td>6223</td>
      <td>2830</td>
      <td>5335</td>
      <td>360</td>
      <td>3325</td>
      <td>Asia</td>
      <td>Southern Asia</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1993</td>
      <td>2812</td>
      <td>1187</td>
      <td>384</td>
      <td>2837</td>
      <td>108</td>
      <td>1687</td>
      <td>2589</td>
      <td>...</td>
      <td>425</td>
      <td>2797</td>
      <td>5681</td>
      <td>6445</td>
      <td>2943</td>
      <td>5568</td>
      <td>396</td>
      <td>3601</td>
      <td>Asia</td>
      <td>Southern Asia</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1994</td>
      <td>3027</td>
      <td>1211</td>
      <td>391</td>
      <td>3081</td>
      <td>211</td>
      <td>1809</td>
      <td>2849</td>
      <td>...</td>
      <td>451</td>
      <td>3038</td>
      <td>6001</td>
      <td>6664</td>
      <td>3027</td>
      <td>5739</td>
      <td>420</td>
      <td>3816</td>
      <td>Asia</td>
      <td>Southern Asia</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 36 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-5d939d8e-ec72-449d-86bd-0facdb9dfe1a')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-5d939d8e-ec72-449d-86bd-0facdb9dfe1a button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-5d939d8e-ec72-449d-86bd-0facdb9dfe1a');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-b16d67b5-d01b-4a99-a135-60150c24bb16">
  <button class="colab-df-quickchart" onclick="quickchart('df-b16d67b5-d01b-4a99-a135-60150c24bb16')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-b16d67b5-d01b-4a99-a135-60150c24bb16 button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>





```python
# prompt: move column continent and sub_region into next of column Code

cols = list(df_join1.columns)
continent_index = cols.index('continent')
sub_region_index = cols.index('sub_region')
code_index = cols.index('Code')

# Move 'continent' and 'sub_region' columns to the right of 'Code'
new_cols = cols[:code_index+1] + [cols[continent_index]] + [cols[sub_region_index]] + cols[code_index+1:continent_index] + cols[continent_index+1:sub_region_index] + cols[sub_region_index+1:]
df_join1 = df_join1[new_cols]

df_join1.head()

```





  <div id="df-975373ef-8dfa-4de9-b271-a85ef9599cd5" class="colab-df-container">
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
      <th>Country/Territory</th>
      <th>Code</th>
      <th>continent</th>
      <th>sub_region</th>
      <th>Year</th>
      <th>Meningitis</th>
      <th>Alzheimer's Disease and Other Dementias</th>
      <th>Parkinson's Disease</th>
      <th>Nutritional Deficiencies</th>
      <th>Malaria</th>
      <th>...</th>
      <th>Diabetes Mellitus</th>
      <th>Chronic Kidney Disease</th>
      <th>Poisonings</th>
      <th>Protein-Energy Malnutrition</th>
      <th>Road Injuries</th>
      <th>Chronic Respiratory Diseases</th>
      <th>Cirrhosis and Other Chronic Liver Diseases</th>
      <th>Digestive Diseases</th>
      <th>Fire, Heat, and Hot Substances</th>
      <th>Acute Hepatitis</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1990</td>
      <td>2159</td>
      <td>1116</td>
      <td>371</td>
      <td>2087</td>
      <td>93</td>
      <td>...</td>
      <td>2108</td>
      <td>3709</td>
      <td>338</td>
      <td>2054</td>
      <td>4154</td>
      <td>5945</td>
      <td>2673</td>
      <td>5005</td>
      <td>323</td>
      <td>2985</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1991</td>
      <td>2218</td>
      <td>1136</td>
      <td>374</td>
      <td>2153</td>
      <td>189</td>
      <td>...</td>
      <td>2120</td>
      <td>3724</td>
      <td>351</td>
      <td>2119</td>
      <td>4472</td>
      <td>6050</td>
      <td>2728</td>
      <td>5120</td>
      <td>332</td>
      <td>3092</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1992</td>
      <td>2475</td>
      <td>1162</td>
      <td>378</td>
      <td>2441</td>
      <td>239</td>
      <td>...</td>
      <td>2153</td>
      <td>3776</td>
      <td>386</td>
      <td>2404</td>
      <td>5106</td>
      <td>6223</td>
      <td>2830</td>
      <td>5335</td>
      <td>360</td>
      <td>3325</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1993</td>
      <td>2812</td>
      <td>1187</td>
      <td>384</td>
      <td>2837</td>
      <td>108</td>
      <td>...</td>
      <td>2195</td>
      <td>3862</td>
      <td>425</td>
      <td>2797</td>
      <td>5681</td>
      <td>6445</td>
      <td>2943</td>
      <td>5568</td>
      <td>396</td>
      <td>3601</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1994</td>
      <td>3027</td>
      <td>1211</td>
      <td>391</td>
      <td>3081</td>
      <td>211</td>
      <td>...</td>
      <td>2231</td>
      <td>3932</td>
      <td>451</td>
      <td>3038</td>
      <td>6001</td>
      <td>6664</td>
      <td>3027</td>
      <td>5739</td>
      <td>420</td>
      <td>3816</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 36 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-975373ef-8dfa-4de9-b271-a85ef9599cd5')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-975373ef-8dfa-4de9-b271-a85ef9599cd5 button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-975373ef-8dfa-4de9-b271-a85ef9599cd5');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-3157e4ec-8cf4-4804-aed4-1ef21b81917a">
  <button class="colab-df-quickchart" onclick="quickchart('df-3157e4ec-8cf4-4804-aed4-1ef21b81917a')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-3157e4ec-8cf4-4804-aed4-1ef21b81917a button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>




###Check Invalid Country


```python
join1_codes = set(df_join1['Code'].unique())
population_codes = set(df_population_melted['Country Code'].unique())

codes_not_in_population = join1_codes - population_codes

print("Codes in df_join1['Code'] that are not in df_population['Country Code']:\n", codes_not_in_population)
```

    Codes in df_join1['Code'] that are not in df_population['Country Code']:
     {'TKL', 'TWN', 'NIU', 'COK'}
    


```python
join1 = set(df_join1['Code'].unique())
population = set(df_population_melted['Country Code'].unique())

# Check if all codes in df_cause_of_death are present in df_continent
all_codes_present = join1.issubset(population)

print(f"Are all 'Code' values from df_cause_of_death present in 'code_3' of df_continent? {all_codes_present}")
```

    Are all 'Code' values from df_cause_of_death present in 'code_3' of df_continent? False
    

####Import Taiwan


```python
df_taiwan = pd.read_csv('https://raw.githubusercontent.com/imyajaii/dads5001-mini-project-01/refs/heads/develop/dataset/taiwan-population.csv')
# Preview
df_taiwan.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 151 entries, 0 to 150
    Data columns (total 3 columns):
     #   Column            Non-Null Count  Dtype  
    ---  ------            --------------  -----  
     0   date              151 non-null    object 
     1    Population       151 non-null    int64  
     2    Annual % Change  150 non-null    float64
    dtypes: float64(1), int64(1), object(1)
    memory usage: 3.7+ KB
    


```python
df_taiwan.head()
```





  <div id="df-9b3109c9-a1f7-4038-a1bb-f66fcdef6188" class="colab-df-container">
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
      <th>date</th>
      <th>Population</th>
      <th>Annual % Change</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>31/12/1950</td>
      <td>7623130</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>31/12/1951</td>
      <td>7934689</td>
      <td>4.09</td>
    </tr>
    <tr>
      <th>2</th>
      <td>31/12/1952</td>
      <td>8251039</td>
      <td>3.99</td>
    </tr>
    <tr>
      <th>3</th>
      <td>31/12/1953</td>
      <td>8572131</td>
      <td>3.89</td>
    </tr>
    <tr>
      <th>4</th>
      <td>31/12/1954</td>
      <td>8897776</td>
      <td>3.80</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-9b3109c9-a1f7-4038-a1bb-f66fcdef6188')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-9b3109c9-a1f7-4038-a1bb-f66fcdef6188 button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-9b3109c9-a1f7-4038-a1bb-f66fcdef6188');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-e2052a92-459d-4fe3-b891-34680586b289">
  <button class="colab-df-quickchart" onclick="quickchart('df-e2052a92-459d-4fe3-b891-34680586b289')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-e2052a92-459d-4fe3-b891-34680586b289 button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>





```python
# prompt: change date of column date into year
# Assuming 'df_taiwan' is your DataFrame and 'date' is the column containing dates
df_taiwan['Year'] = pd.to_datetime(df_taiwan['date']).dt.year
df_taiwan
```

    <ipython-input-23-22807dbae3d2>:3: UserWarning: Parsing dates in %d/%m/%Y format when dayfirst=False (the default) was specified. Pass `dayfirst=True` or specify a format to silence this warning.
      df_taiwan['Year'] = pd.to_datetime(df_taiwan['date']).dt.year
    





  <div id="df-9265caaf-2141-4149-8b07-e498dffe6f1a" class="colab-df-container">
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
      <th>date</th>
      <th>Population</th>
      <th>Annual % Change</th>
      <th>Year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>31/12/1950</td>
      <td>7623130</td>
      <td>NaN</td>
      <td>1950</td>
    </tr>
    <tr>
      <th>1</th>
      <td>31/12/1951</td>
      <td>7934689</td>
      <td>4.09</td>
      <td>1951</td>
    </tr>
    <tr>
      <th>2</th>
      <td>31/12/1952</td>
      <td>8251039</td>
      <td>3.99</td>
      <td>1952</td>
    </tr>
    <tr>
      <th>3</th>
      <td>31/12/1953</td>
      <td>8572131</td>
      <td>3.89</td>
      <td>1953</td>
    </tr>
    <tr>
      <th>4</th>
      <td>31/12/1954</td>
      <td>8897776</td>
      <td>3.80</td>
      <td>1954</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>146</th>
      <td>31/12/2096</td>
      <td>15590180</td>
      <td>-0.62</td>
      <td>2096</td>
    </tr>
    <tr>
      <th>147</th>
      <td>31/12/2097</td>
      <td>15497260</td>
      <td>-0.60</td>
      <td>2097</td>
    </tr>
    <tr>
      <th>148</th>
      <td>31/12/2098</td>
      <td>15408434</td>
      <td>-0.57</td>
      <td>2098</td>
    </tr>
    <tr>
      <th>149</th>
      <td>31/12/2099</td>
      <td>15323545</td>
      <td>-0.55</td>
      <td>2099</td>
    </tr>
    <tr>
      <th>150</th>
      <td>31/12/2100</td>
      <td>15241961</td>
      <td>-0.53</td>
      <td>2100</td>
    </tr>
  </tbody>
</table>
<p>151 rows × 4 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-9265caaf-2141-4149-8b07-e498dffe6f1a')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-9265caaf-2141-4149-8b07-e498dffe6f1a button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-9265caaf-2141-4149-8b07-e498dffe6f1a');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-5c25c3d9-10d9-4f06-b012-1d0f7686955b">
  <button class="colab-df-quickchart" onclick="quickchart('df-5c25c3d9-10d9-4f06-b012-1d0f7686955b')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-5c25c3d9-10d9-4f06-b012-1d0f7686955b button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

  <div id="id_f3e72966-f952-4d8d-a97a-74abdb3e39f5">
    <style>
      .colab-df-generate {
        background-color: #E8F0FE;
        border: none;
        border-radius: 50%;
        cursor: pointer;
        display: none;
        fill: #1967D2;
        height: 32px;
        padding: 0 0 0 0;
        width: 32px;
      }

      .colab-df-generate:hover {
        background-color: #E2EBFA;
        box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
        fill: #174EA6;
      }

      [theme=dark] .colab-df-generate {
        background-color: #3B4455;
        fill: #D2E3FC;
      }

      [theme=dark] .colab-df-generate:hover {
        background-color: #434B5C;
        box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
        filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
        fill: #FFFFFF;
      }
    </style>
    <button class="colab-df-generate" onclick="generateWithVariable('df_taiwan')"
            title="Generate code using this dataframe."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M7,19H8.4L18.45,9,17,7.55,7,17.6ZM5,21V16.75L18.45,3.32a2,2,0,0,1,2.83,0l1.4,1.43a1.91,1.91,0,0,1,.58,1.4,1.91,1.91,0,0,1-.58,1.4L9.25,21ZM18.45,9,17,7.55Zm-12,3A5.31,5.31,0,0,0,4.9,8.1,5.31,5.31,0,0,0,1,6.5,5.31,5.31,0,0,0,4.9,4.9,5.31,5.31,0,0,0,6.5,1,5.31,5.31,0,0,0,8.1,4.9,5.31,5.31,0,0,0,12,6.5,5.46,5.46,0,0,0,6.5,12Z"/>
  </svg>
    </button>
    <script>
      (() => {
      const buttonEl =
        document.querySelector('#id_f3e72966-f952-4d8d-a97a-74abdb3e39f5 button.colab-df-generate');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      buttonEl.onclick = () => {
        google.colab.notebook.generateWithVariable('df_taiwan');
      }
      })();
    </script>
  </div>

    </div>
  </div>





```python
# prompt: create column Country in first column all data was Taiwan , column Code in second column all data was TWN and move column Year into third column

# Create new columns 'Country' and 'Code'
df_taiwan['Country'] = 'Taiwan'
df_taiwan['Code'] = 'TWN'

# Get the list of column names
cols = list(df_taiwan.columns)

# Find the index of the 'Year' column
year_index = cols.index('Year')

# Remove 'Year' from its original position
cols.pop(year_index)

# Insert 'Year' at the third position (index 2)
cols.insert(2, 'Year')

# Reorder the DataFrame columns based on the new list
df_taiwan = df_taiwan[cols]

df_taiwan.head()

```





  <div id="df-4598810d-a018-4154-ae6a-c4082e2cc3e2" class="colab-df-container">
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
      <th>date</th>
      <th>Population</th>
      <th>Year</th>
      <th>Annual % Change</th>
      <th>Country</th>
      <th>Code</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>31/12/1950</td>
      <td>7623130</td>
      <td>1950</td>
      <td>NaN</td>
      <td>Taiwan</td>
      <td>TWN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>31/12/1951</td>
      <td>7934689</td>
      <td>1951</td>
      <td>4.09</td>
      <td>Taiwan</td>
      <td>TWN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>31/12/1952</td>
      <td>8251039</td>
      <td>1952</td>
      <td>3.99</td>
      <td>Taiwan</td>
      <td>TWN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>31/12/1953</td>
      <td>8572131</td>
      <td>1953</td>
      <td>3.89</td>
      <td>Taiwan</td>
      <td>TWN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>31/12/1954</td>
      <td>8897776</td>
      <td>1954</td>
      <td>3.80</td>
      <td>Taiwan</td>
      <td>TWN</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-4598810d-a018-4154-ae6a-c4082e2cc3e2')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-4598810d-a018-4154-ae6a-c4082e2cc3e2 button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-4598810d-a018-4154-ae6a-c4082e2cc3e2');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-2fcd7677-7bc0-430e-a7b7-9ccfad5d4d2e">
  <button class="colab-df-quickchart" onclick="quickchart('df-2fcd7677-7bc0-430e-a7b7-9ccfad5d4d2e')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-2fcd7677-7bc0-430e-a7b7-9ccfad5d4d2e button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>





```python
# prompt: drop column date , Annual % Change

df_taiwan = df_taiwan.drop(['date', ' Annual % Change'], axis=1)

```


```python
df_taiwan.head()
```





  <div id="df-b49ef1c5-b01f-43c2-b2df-fac101a4f91d" class="colab-df-container">
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
      <th>Population</th>
      <th>Year</th>
      <th>Country</th>
      <th>Code</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>7623130</td>
      <td>1950</td>
      <td>Taiwan</td>
      <td>TWN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>7934689</td>
      <td>1951</td>
      <td>Taiwan</td>
      <td>TWN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>8251039</td>
      <td>1952</td>
      <td>Taiwan</td>
      <td>TWN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>8572131</td>
      <td>1953</td>
      <td>Taiwan</td>
      <td>TWN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>8897776</td>
      <td>1954</td>
      <td>Taiwan</td>
      <td>TWN</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-b49ef1c5-b01f-43c2-b2df-fac101a4f91d')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-b49ef1c5-b01f-43c2-b2df-fac101a4f91d button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-b49ef1c5-b01f-43c2-b2df-fac101a4f91d');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-8d8d33b8-fced-4085-bda2-f2219e4ea30c">
  <button class="colab-df-quickchart" onclick="quickchart('df-8d8d33b8-fced-4085-bda2-f2219e4ea30c')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-8d8d33b8-fced-4085-bda2-f2219e4ea30c button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>





```python
df_taiwan.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 151 entries, 0 to 150
    Data columns (total 4 columns):
     #   Column       Non-Null Count  Dtype 
    ---  ------       --------------  ----- 
     0    Population  151 non-null    int64 
     1   Year         151 non-null    int32 
     2   Country      151 non-null    object
     3   Code         151 non-null    object
    dtypes: int32(1), int64(1), object(2)
    memory usage: 4.3+ KB
    


```python
# prompt: change name of column

df_taiwan = df_taiwan.rename(columns={' Population': 'Population', 'Country': 'Country Name', 'Code': 'Country Code'})
df_taiwan.head()

```





  <div id="df-d50282d9-7e58-4e4c-b97d-ba22a78163d0" class="colab-df-container">
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
      <th>Population</th>
      <th>Year</th>
      <th>Country Name</th>
      <th>Country Code</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>7623130</td>
      <td>1950</td>
      <td>Taiwan</td>
      <td>TWN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>7934689</td>
      <td>1951</td>
      <td>Taiwan</td>
      <td>TWN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>8251039</td>
      <td>1952</td>
      <td>Taiwan</td>
      <td>TWN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>8572131</td>
      <td>1953</td>
      <td>Taiwan</td>
      <td>TWN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>8897776</td>
      <td>1954</td>
      <td>Taiwan</td>
      <td>TWN</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-d50282d9-7e58-4e4c-b97d-ba22a78163d0')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-d50282d9-7e58-4e4c-b97d-ba22a78163d0 button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-d50282d9-7e58-4e4c-b97d-ba22a78163d0');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-906a6cf4-4d5c-438f-a956-2b6f58d035df">
  <button class="colab-df-quickchart" onclick="quickchart('df-906a6cf4-4d5c-438f-a956-2b6f58d035df')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-906a6cf4-4d5c-438f-a956-2b6f58d035df button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>





```python
# prompt: move column in this way Country Name , Country Code , Year , Population

new_order = ['Country Name', 'Country Code', 'Year', 'Population']
df_taiwan = df_taiwan[new_order]
df_taiwan.head()

```





  <div id="df-3ad789d8-3897-4c07-afca-10d238b4c4bb" class="colab-df-container">
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
      <th>Country Name</th>
      <th>Country Code</th>
      <th>Year</th>
      <th>Population</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1950</td>
      <td>7623130</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1951</td>
      <td>7934689</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1952</td>
      <td>8251039</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1953</td>
      <td>8572131</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1954</td>
      <td>8897776</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-3ad789d8-3897-4c07-afca-10d238b4c4bb')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-3ad789d8-3897-4c07-afca-10d238b4c4bb button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-3ad789d8-3897-4c07-afca-10d238b4c4bb');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-60f5610e-1bb9-414a-beee-32794e621f89">
  <button class="colab-df-quickchart" onclick="quickchart('df-60f5610e-1bb9-414a-beee-32794e621f89')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-60f5610e-1bb9-414a-beee-32794e621f89 button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>





```python
df_taiwan
```





  <div id="df-a9b62e64-516b-4a2c-a3b3-971709740284" class="colab-df-container">
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
      <th>Country Name</th>
      <th>Country Code</th>
      <th>Year</th>
      <th>Population</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1950</td>
      <td>7623130</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1951</td>
      <td>7934689</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1952</td>
      <td>8251039</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1953</td>
      <td>8572131</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1954</td>
      <td>8897776</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>146</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2096</td>
      <td>15590180</td>
    </tr>
    <tr>
      <th>147</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2097</td>
      <td>15497260</td>
    </tr>
    <tr>
      <th>148</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2098</td>
      <td>15408434</td>
    </tr>
    <tr>
      <th>149</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2099</td>
      <td>15323545</td>
    </tr>
    <tr>
      <th>150</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2100</td>
      <td>15241961</td>
    </tr>
  </tbody>
</table>
<p>151 rows × 4 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-a9b62e64-516b-4a2c-a3b3-971709740284')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-a9b62e64-516b-4a2c-a3b3-971709740284 button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-a9b62e64-516b-4a2c-a3b3-971709740284');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-d86b09e2-da7d-43f0-83ce-1d27b87f21b4">
  <button class="colab-df-quickchart" onclick="quickchart('df-d86b09e2-da7d-43f0-83ce-1d27b87f21b4')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-d86b09e2-da7d-43f0-83ce-1d27b87f21b4 button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

  <div id="id_3fb41250-a231-44d5-a308-b6e7051c63b6">
    <style>
      .colab-df-generate {
        background-color: #E8F0FE;
        border: none;
        border-radius: 50%;
        cursor: pointer;
        display: none;
        fill: #1967D2;
        height: 32px;
        padding: 0 0 0 0;
        width: 32px;
      }

      .colab-df-generate:hover {
        background-color: #E2EBFA;
        box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
        fill: #174EA6;
      }

      [theme=dark] .colab-df-generate {
        background-color: #3B4455;
        fill: #D2E3FC;
      }

      [theme=dark] .colab-df-generate:hover {
        background-color: #434B5C;
        box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
        filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
        fill: #FFFFFF;
      }
    </style>
    <button class="colab-df-generate" onclick="generateWithVariable('df_taiwan')"
            title="Generate code using this dataframe."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M7,19H8.4L18.45,9,17,7.55,7,17.6ZM5,21V16.75L18.45,3.32a2,2,0,0,1,2.83,0l1.4,1.43a1.91,1.91,0,0,1,.58,1.4,1.91,1.91,0,0,1-.58,1.4L9.25,21ZM18.45,9,17,7.55Zm-12,3A5.31,5.31,0,0,0,4.9,8.1,5.31,5.31,0,0,0,1,6.5,5.31,5.31,0,0,0,4.9,4.9,5.31,5.31,0,0,0,6.5,1,5.31,5.31,0,0,0,8.1,4.9,5.31,5.31,0,0,0,12,6.5,5.46,5.46,0,0,0,6.5,12Z"/>
  </svg>
    </button>
    <script>
      (() => {
      const buttonEl =
        document.querySelector('#id_3fb41250-a231-44d5-a308-b6e7051c63b6 button.colab-df-generate');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      buttonEl.onclick = () => {
        google.colab.notebook.generateWithVariable('df_taiwan');
      }
      })();
    </script>
  </div>

    </div>
  </div>





```python
# prompt: drop row that was Year 1950 - 1989 , 2020 - 2100 of df_taiwan

years_to_drop = list(range(1950, 1990)) + list(range(2020, 2101))
df_taiwan = df_taiwan[~df_taiwan['Year'].isin(years_to_drop)]

```


```python
df_taiwan
```





  <div id="df-197e4fc9-c74b-449b-b165-605fa5a35d3d" class="colab-df-container">
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
      <th>Country Name</th>
      <th>Country Code</th>
      <th>Year</th>
      <th>Population</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>40</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1990</td>
      <td>20586174</td>
    </tr>
    <tr>
      <th>41</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1991</td>
      <td>20770620</td>
    </tr>
    <tr>
      <th>42</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1992</td>
      <td>20952222</td>
    </tr>
    <tr>
      <th>43</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1993</td>
      <td>21125717</td>
    </tr>
    <tr>
      <th>44</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1994</td>
      <td>21293437</td>
    </tr>
    <tr>
      <th>45</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1995</td>
      <td>21455813</td>
    </tr>
    <tr>
      <th>46</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1996</td>
      <td>21612429</td>
    </tr>
    <tr>
      <th>47</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1997</td>
      <td>21764843</td>
    </tr>
    <tr>
      <th>48</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1998</td>
      <td>21913672</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>1999</td>
      <td>22057214</td>
    </tr>
    <tr>
      <th>50</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2000</td>
      <td>22194731</td>
    </tr>
    <tr>
      <th>51</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2001</td>
      <td>22333125</td>
    </tr>
    <tr>
      <th>52</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2002</td>
      <td>22469616</td>
    </tr>
    <tr>
      <th>53</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2003</td>
      <td>22593681</td>
    </tr>
    <tr>
      <th>54</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2004</td>
      <td>22703099</td>
    </tr>
    <tr>
      <th>55</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2005</td>
      <td>22796306</td>
    </tr>
    <tr>
      <th>56</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2006</td>
      <td>22874975</td>
    </tr>
    <tr>
      <th>57</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2007</td>
      <td>22942308</td>
    </tr>
    <tr>
      <th>58</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2008</td>
      <td>22998321</td>
    </tr>
    <tr>
      <th>59</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2009</td>
      <td>23044082</td>
    </tr>
    <tr>
      <th>60</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2010</td>
      <td>23083083</td>
    </tr>
    <tr>
      <th>61</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2011</td>
      <td>23143071</td>
    </tr>
    <tr>
      <th>62</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2012</td>
      <td>23234058</td>
    </tr>
    <tr>
      <th>63</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2013</td>
      <td>23330334</td>
    </tr>
    <tr>
      <th>64</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2014</td>
      <td>23422513</td>
    </tr>
    <tr>
      <th>65</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2015</td>
      <td>23512136</td>
    </tr>
    <tr>
      <th>66</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2016</td>
      <td>23594471</td>
    </tr>
    <tr>
      <th>67</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2017</td>
      <td>23665024</td>
    </tr>
    <tr>
      <th>68</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2018</td>
      <td>23726185</td>
    </tr>
    <tr>
      <th>69</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2019</td>
      <td>23777737</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-197e4fc9-c74b-449b-b165-605fa5a35d3d')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-197e4fc9-c74b-449b-b165-605fa5a35d3d button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-197e4fc9-c74b-449b-b165-605fa5a35d3d');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-aba2db5d-6af6-4778-a610-683aeb66f938">
  <button class="colab-df-quickchart" onclick="quickchart('df-aba2db5d-6af6-4778-a610-683aeb66f938')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-aba2db5d-6af6-4778-a610-683aeb66f938 button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

  <div id="id_d273958f-74c3-45d2-a5af-2e98901c6cad">
    <style>
      .colab-df-generate {
        background-color: #E8F0FE;
        border: none;
        border-radius: 50%;
        cursor: pointer;
        display: none;
        fill: #1967D2;
        height: 32px;
        padding: 0 0 0 0;
        width: 32px;
      }

      .colab-df-generate:hover {
        background-color: #E2EBFA;
        box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
        fill: #174EA6;
      }

      [theme=dark] .colab-df-generate {
        background-color: #3B4455;
        fill: #D2E3FC;
      }

      [theme=dark] .colab-df-generate:hover {
        background-color: #434B5C;
        box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
        filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
        fill: #FFFFFF;
      }
    </style>
    <button class="colab-df-generate" onclick="generateWithVariable('df_taiwan')"
            title="Generate code using this dataframe."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M7,19H8.4L18.45,9,17,7.55,7,17.6ZM5,21V16.75L18.45,3.32a2,2,0,0,1,2.83,0l1.4,1.43a1.91,1.91,0,0,1,.58,1.4,1.91,1.91,0,0,1-.58,1.4L9.25,21ZM18.45,9,17,7.55Zm-12,3A5.31,5.31,0,0,0,4.9,8.1,5.31,5.31,0,0,0,1,6.5,5.31,5.31,0,0,0,4.9,4.9,5.31,5.31,0,0,0,6.5,1,5.31,5.31,0,0,0,8.1,4.9,5.31,5.31,0,0,0,12,6.5,5.46,5.46,0,0,0,6.5,12Z"/>
  </svg>
    </button>
    <script>
      (() => {
      const buttonEl =
        document.querySelector('#id_d273958f-74c3-45d2-a5af-2e98901c6cad button.colab-df-generate');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      buttonEl.onclick = () => {
        google.colab.notebook.generateWithVariable('df_taiwan');
      }
      })();
    </script>
  </div>

    </div>
  </div>




####Join missing TWN


```python
# prompt: add row of df_taiwan in to df_population_melted

df_population_melted = pd.concat([df_population_melted, df_taiwan], ignore_index=True)
df_population_melted

```





  <div id="df-644728fb-a07d-48cd-8927-75da42070b5d" class="colab-df-container">
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
      <th>Country Name</th>
      <th>Country Code</th>
      <th>Year</th>
      <th>Population</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Aruba</td>
      <td>ABW</td>
      <td>1990</td>
      <td>62152.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Africa Eastern and Southern</td>
      <td>AFE</td>
      <td>1990</td>
      <td>304648010.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1990</td>
      <td>12412311.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Africa Western and Central</td>
      <td>AFW</td>
      <td>1990</td>
      <td>204803865.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Angola</td>
      <td>AGO</td>
      <td>1990</td>
      <td>11848385.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>8005</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2015</td>
      <td>23512136.0</td>
    </tr>
    <tr>
      <th>8006</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2016</td>
      <td>23594471.0</td>
    </tr>
    <tr>
      <th>8007</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2017</td>
      <td>23665024.0</td>
    </tr>
    <tr>
      <th>8008</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2018</td>
      <td>23726185.0</td>
    </tr>
    <tr>
      <th>8009</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2019</td>
      <td>23777737.0</td>
    </tr>
  </tbody>
</table>
<p>8010 rows × 4 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-644728fb-a07d-48cd-8927-75da42070b5d')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-644728fb-a07d-48cd-8927-75da42070b5d button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-644728fb-a07d-48cd-8927-75da42070b5d');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-f799901b-bae1-401b-b61d-19db49e9810b">
  <button class="colab-df-quickchart" onclick="quickchart('df-f799901b-bae1-401b-b61d-19db49e9810b')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-f799901b-bae1-401b-b61d-19db49e9810b button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

  <div id="id_731543e4-af79-4549-8c5c-c5111528d673">
    <style>
      .colab-df-generate {
        background-color: #E8F0FE;
        border: none;
        border-radius: 50%;
        cursor: pointer;
        display: none;
        fill: #1967D2;
        height: 32px;
        padding: 0 0 0 0;
        width: 32px;
      }

      .colab-df-generate:hover {
        background-color: #E2EBFA;
        box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
        fill: #174EA6;
      }

      [theme=dark] .colab-df-generate {
        background-color: #3B4455;
        fill: #D2E3FC;
      }

      [theme=dark] .colab-df-generate:hover {
        background-color: #434B5C;
        box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
        filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
        fill: #FFFFFF;
      }
    </style>
    <button class="colab-df-generate" onclick="generateWithVariable('df_population_melted')"
            title="Generate code using this dataframe."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M7,19H8.4L18.45,9,17,7.55,7,17.6ZM5,21V16.75L18.45,3.32a2,2,0,0,1,2.83,0l1.4,1.43a1.91,1.91,0,0,1,.58,1.4,1.91,1.91,0,0,1-.58,1.4L9.25,21ZM18.45,9,17,7.55Zm-12,3A5.31,5.31,0,0,0,4.9,8.1,5.31,5.31,0,0,0,1,6.5,5.31,5.31,0,0,0,4.9,4.9,5.31,5.31,0,0,0,6.5,1,5.31,5.31,0,0,0,8.1,4.9,5.31,5.31,0,0,0,12,6.5,5.46,5.46,0,0,0,6.5,12Z"/>
  </svg>
    </button>
    <script>
      (() => {
      const buttonEl =
        document.querySelector('#id_731543e4-af79-4549-8c5c-c5111528d673 button.colab-df-generate');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      buttonEl.onclick = () => {
        google.colab.notebook.generateWithVariable('df_population_melted');
      }
      })();
    </script>
  </div>

    </div>
  </div>





```python
df_population_melted
```





  <div id="df-4bc1f400-653f-41a5-bef1-48c64bb157d4" class="colab-df-container">
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
      <th>Country Name</th>
      <th>Country Code</th>
      <th>Year</th>
      <th>Population</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Aruba</td>
      <td>ABW</td>
      <td>1990</td>
      <td>62152.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Africa Eastern and Southern</td>
      <td>AFE</td>
      <td>1990</td>
      <td>304648010.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>1990</td>
      <td>12412311.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Africa Western and Central</td>
      <td>AFW</td>
      <td>1990</td>
      <td>204803865.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Angola</td>
      <td>AGO</td>
      <td>1990</td>
      <td>11848385.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>8005</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2015</td>
      <td>23512136.0</td>
    </tr>
    <tr>
      <th>8006</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2016</td>
      <td>23594471.0</td>
    </tr>
    <tr>
      <th>8007</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2017</td>
      <td>23665024.0</td>
    </tr>
    <tr>
      <th>8008</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2018</td>
      <td>23726185.0</td>
    </tr>
    <tr>
      <th>8009</th>
      <td>Taiwan</td>
      <td>TWN</td>
      <td>2019</td>
      <td>23777737.0</td>
    </tr>
  </tbody>
</table>
<p>8010 rows × 4 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-4bc1f400-653f-41a5-bef1-48c64bb157d4')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-4bc1f400-653f-41a5-bef1-48c64bb157d4 button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-4bc1f400-653f-41a5-bef1-48c64bb157d4');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-6c6ef928-4623-46d8-9f18-5270a931d051">
  <button class="colab-df-quickchart" onclick="quickchart('df-6c6ef928-4623-46d8-9f18-5270a931d051')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-6c6ef928-4623-46d8-9f18-5270a931d051 button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

  <div id="id_778acbf4-34d3-4547-a3e7-12df031cc381">
    <style>
      .colab-df-generate {
        background-color: #E8F0FE;
        border: none;
        border-radius: 50%;
        cursor: pointer;
        display: none;
        fill: #1967D2;
        height: 32px;
        padding: 0 0 0 0;
        width: 32px;
      }

      .colab-df-generate:hover {
        background-color: #E2EBFA;
        box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
        fill: #174EA6;
      }

      [theme=dark] .colab-df-generate {
        background-color: #3B4455;
        fill: #D2E3FC;
      }

      [theme=dark] .colab-df-generate:hover {
        background-color: #434B5C;
        box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
        filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
        fill: #FFFFFF;
      }
    </style>
    <button class="colab-df-generate" onclick="generateWithVariable('df_population_melted')"
            title="Generate code using this dataframe."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M7,19H8.4L18.45,9,17,7.55,7,17.6ZM5,21V16.75L18.45,3.32a2,2,0,0,1,2.83,0l1.4,1.43a1.91,1.91,0,0,1,.58,1.4,1.91,1.91,0,0,1-.58,1.4L9.25,21ZM18.45,9,17,7.55Zm-12,3A5.31,5.31,0,0,0,4.9,8.1,5.31,5.31,0,0,0,1,6.5,5.31,5.31,0,0,0,4.9,4.9,5.31,5.31,0,0,0,6.5,1,5.31,5.31,0,0,0,8.1,4.9,5.31,5.31,0,0,0,12,6.5,5.46,5.46,0,0,0,6.5,12Z"/>
  </svg>
    </button>
    <script>
      (() => {
      const buttonEl =
        document.querySelector('#id_778acbf4-34d3-4547-a3e7-12df031cc381 button.colab-df-generate');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      buttonEl.onclick = () => {
        google.colab.notebook.generateWithVariable('df_population_melted');
      }
      })();
    </script>
  </div>

    </div>
  </div>




###Check invalid after


```python
# prompt: show column Code in df_join1 was not in column Country Code in df_population

join1_codes = set(df_join1['Code'].unique())
population_codes = set(df_population_melted['Country Code'].unique())

codes_not_in_population = join1_codes - population_codes

print("Codes in df_join1['Code'] that are not in df_population['Country Code']:\n", codes_not_in_population)

```

    Codes in df_join1['Code'] that are not in df_population['Country Code']:
     {'TKL', 'NIU', 'COK'}
    


```python
join1_codes = set(df_join1['Year'].unique())
population_codes = set(df_population_melted['Year'].unique())

codes_not_in_population = join1_codes - population_codes

print("Codes in df_join1['Year'] that are not in df_population['Year']:\n", codes_not_in_population)
```

    Codes in df_join1['Year'] that are not in df_population['Year']:
     set()
    


```python
# prompt: check type of Year in df_join1

print(df_join1['Year'].dtype)

```

    int64
    


```python
df_population_melted['Year'].unique()
```




    array(['1990', '1991', '1992', '1993', '1994', '1995', '1996', '1997',
           '1998', '1999', '2000', '2001', '2002', '2003', '2004', '2005',
           '2006', '2007', '2008', '2009', '2010', '2011', '2012', '2013',
           '2014', '2015', '2016', '2017', '2018', '2019', 1990, 1991, 1992,
           1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2002, 2003,
           2004, 2005, 2006, 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014,
           2015, 2016, 2017, 2018, 2019], dtype=object)




```python
# Match type of Year before Merge

df_population_melted['Year'] = df_population_melted['Year'].astype('int64')

```


```python
df_population_melted[df_population_melted['Population'].isnull()]
```





  <div id="df-89eb96f1-fa58-4ec4-ad19-988df3237a7c" class="colab-df-container">
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
      <th>Country Name</th>
      <th>Country Code</th>
      <th>Year</th>
      <th>Population</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>110</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>1990</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>376</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>1991</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>642</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>1992</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>659</th>
      <td>Kuwait</td>
      <td>KWT</td>
      <td>1992</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>908</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>1993</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>925</th>
      <td>Kuwait</td>
      <td>KWT</td>
      <td>1993</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1174</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>1994</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1191</th>
      <td>Kuwait</td>
      <td>KWT</td>
      <td>1994</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1440</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>1995</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1706</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>1996</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1972</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>1997</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2238</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>1998</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2504</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>1999</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2770</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2000</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3036</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2001</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3302</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2002</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3568</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2003</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3834</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2004</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4100</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2005</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4366</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2006</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4632</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2007</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4898</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2008</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5164</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2009</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5430</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2010</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5696</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2011</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5921</th>
      <td>Eritrea</td>
      <td>ERI</td>
      <td>2012</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5962</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2012</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6187</th>
      <td>Eritrea</td>
      <td>ERI</td>
      <td>2013</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6228</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2013</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6453</th>
      <td>Eritrea</td>
      <td>ERI</td>
      <td>2014</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6494</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2014</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6719</th>
      <td>Eritrea</td>
      <td>ERI</td>
      <td>2015</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6760</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2015</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6985</th>
      <td>Eritrea</td>
      <td>ERI</td>
      <td>2016</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7026</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2016</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7251</th>
      <td>Eritrea</td>
      <td>ERI</td>
      <td>2017</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7292</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2017</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7517</th>
      <td>Eritrea</td>
      <td>ERI</td>
      <td>2018</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7558</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2018</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7783</th>
      <td>Eritrea</td>
      <td>ERI</td>
      <td>2019</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7824</th>
      <td>Not classified</td>
      <td>INX</td>
      <td>2019</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-89eb96f1-fa58-4ec4-ad19-988df3237a7c')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-89eb96f1-fa58-4ec4-ad19-988df3237a7c button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-89eb96f1-fa58-4ec4-ad19-988df3237a7c');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-f3f9028a-735a-4f3d-85e6-136650b582b6">
  <button class="colab-df-quickchart" onclick="quickchart('df-f3f9028a-735a-4f3d-85e6-136650b582b6')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-f3f9028a-735a-4f3d-85e6-136650b582b6 button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>




##Creat Main Table

###Merge all data to be main Table


```python
# Merge on multiple keys: Inner join

# Alternative 1
#pd.merge(df_join1, df_population_melted, on=['StudentID', 'CourseID'], how='inner')

# Alternative 2
df_Main_data = pd.merge(df_join1, df_population_melted, left_on=['Code', 'Year'], right_on=['Country Code', 'Year'], how='outer')
df_Main_data
```





  <div id="df-3d671f7a-073f-4877-a481-5ff598d1de43" class="colab-df-container">
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
      <th>Country/Territory</th>
      <th>Code</th>
      <th>continent</th>
      <th>sub_region</th>
      <th>Year</th>
      <th>Meningitis</th>
      <th>Alzheimer's Disease and Other Dementias</th>
      <th>Parkinson's Disease</th>
      <th>Nutritional Deficiencies</th>
      <th>Malaria</th>
      <th>...</th>
      <th>Protein-Energy Malnutrition</th>
      <th>Road Injuries</th>
      <th>Chronic Respiratory Diseases</th>
      <th>Cirrhosis and Other Chronic Liver Diseases</th>
      <th>Digestive Diseases</th>
      <th>Fire, Heat, and Hot Substances</th>
      <th>Acute Hepatitis</th>
      <th>Country Name</th>
      <th>Country Code</th>
      <th>Population</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1990</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Aruba</td>
      <td>ABW</td>
      <td>62152.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1991</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Aruba</td>
      <td>ABW</td>
      <td>64623.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1992</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Aruba</td>
      <td>ABW</td>
      <td>68240.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1993</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Aruba</td>
      <td>ABW</td>
      <td>72495.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1994</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Aruba</td>
      <td>ABW</td>
      <td>76705.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>8095</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>Africa</td>
      <td>Eastern Africa</td>
      <td>2015</td>
      <td>1439.0</td>
      <td>754.0</td>
      <td>215.0</td>
      <td>3019.0</td>
      <td>2518.0</td>
      <td>...</td>
      <td>2990.0</td>
      <td>2373.0</td>
      <td>2751.0</td>
      <td>1956.0</td>
      <td>4202.0</td>
      <td>632.0</td>
      <td>146.0</td>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>13814642.0</td>
    </tr>
    <tr>
      <th>8096</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>Africa</td>
      <td>Eastern Africa</td>
      <td>2016</td>
      <td>1457.0</td>
      <td>767.0</td>
      <td>219.0</td>
      <td>3056.0</td>
      <td>2050.0</td>
      <td>...</td>
      <td>3027.0</td>
      <td>2436.0</td>
      <td>2788.0</td>
      <td>1962.0</td>
      <td>4264.0</td>
      <td>648.0</td>
      <td>146.0</td>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>14030338.0</td>
    </tr>
    <tr>
      <th>8097</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>Africa</td>
      <td>Eastern Africa</td>
      <td>2017</td>
      <td>1460.0</td>
      <td>781.0</td>
      <td>223.0</td>
      <td>2990.0</td>
      <td>2116.0</td>
      <td>...</td>
      <td>2962.0</td>
      <td>2473.0</td>
      <td>2818.0</td>
      <td>2007.0</td>
      <td>4342.0</td>
      <td>654.0</td>
      <td>144.0</td>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>14236599.0</td>
    </tr>
    <tr>
      <th>8098</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>Africa</td>
      <td>Eastern Africa</td>
      <td>2018</td>
      <td>1450.0</td>
      <td>795.0</td>
      <td>227.0</td>
      <td>2918.0</td>
      <td>2088.0</td>
      <td>...</td>
      <td>2890.0</td>
      <td>2509.0</td>
      <td>2849.0</td>
      <td>2030.0</td>
      <td>4377.0</td>
      <td>657.0</td>
      <td>139.0</td>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>14438812.0</td>
    </tr>
    <tr>
      <th>8099</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>Africa</td>
      <td>Eastern Africa</td>
      <td>2019</td>
      <td>1450.0</td>
      <td>812.0</td>
      <td>232.0</td>
      <td>2884.0</td>
      <td>2068.0</td>
      <td>...</td>
      <td>2855.0</td>
      <td>2554.0</td>
      <td>2891.0</td>
      <td>2065.0</td>
      <td>4437.0</td>
      <td>662.0</td>
      <td>136.0</td>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>14645473.0</td>
    </tr>
  </tbody>
</table>
<p>8100 rows × 39 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-3d671f7a-073f-4877-a481-5ff598d1de43')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-3d671f7a-073f-4877-a481-5ff598d1de43 button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-3d671f7a-073f-4877-a481-5ff598d1de43');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-27da8bf3-a1d7-4409-9a80-59bf332f9547">
  <button class="colab-df-quickchart" onclick="quickchart('df-27da8bf3-a1d7-4409-9a80-59bf332f9547')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-27da8bf3-a1d7-4409-9a80-59bf332f9547 button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

  <div id="id_afb53f13-7a3d-4a5a-9804-fbac60d43f29">
    <style>
      .colab-df-generate {
        background-color: #E8F0FE;
        border: none;
        border-radius: 50%;
        cursor: pointer;
        display: none;
        fill: #1967D2;
        height: 32px;
        padding: 0 0 0 0;
        width: 32px;
      }

      .colab-df-generate:hover {
        background-color: #E2EBFA;
        box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
        fill: #174EA6;
      }

      [theme=dark] .colab-df-generate {
        background-color: #3B4455;
        fill: #D2E3FC;
      }

      [theme=dark] .colab-df-generate:hover {
        background-color: #434B5C;
        box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
        filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
        fill: #FFFFFF;
      }
    </style>
    <button class="colab-df-generate" onclick="generateWithVariable('df_Main_data')"
            title="Generate code using this dataframe."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M7,19H8.4L18.45,9,17,7.55,7,17.6ZM5,21V16.75L18.45,3.32a2,2,0,0,1,2.83,0l1.4,1.43a1.91,1.91,0,0,1,.58,1.4,1.91,1.91,0,0,1-.58,1.4L9.25,21ZM18.45,9,17,7.55Zm-12,3A5.31,5.31,0,0,0,4.9,8.1,5.31,5.31,0,0,0,1,6.5,5.31,5.31,0,0,0,4.9,4.9,5.31,5.31,0,0,0,6.5,1,5.31,5.31,0,0,0,8.1,4.9,5.31,5.31,0,0,0,12,6.5,5.46,5.46,0,0,0,6.5,12Z"/>
  </svg>
    </button>
    <script>
      (() => {
      const buttonEl =
        document.querySelector('#id_afb53f13-7a3d-4a5a-9804-fbac60d43f29 button.colab-df-generate');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      buttonEl.onclick = () => {
        google.colab.notebook.generateWithVariable('df_Main_data');
      }
      })();
    </script>
  </div>

    </div>
  </div>




###Drop Null and Duplicate columns


```python
# prompt: drop row in column Code that was NaN

df_Main_data = df_Main_data.dropna(subset=['Code'])
df_Main_data = df_Main_data.drop(['Country Name', 'Country Code'], axis=1)
```


```python
df_Main_data
```





  <div id="df-82dfd7bf-0cd1-4fbe-9a0f-ce5ea90fb9b2" class="colab-df-container">
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
      <th>Country/Territory</th>
      <th>Code</th>
      <th>continent</th>
      <th>sub_region</th>
      <th>Year</th>
      <th>Meningitis</th>
      <th>Alzheimer's Disease and Other Dementias</th>
      <th>Parkinson's Disease</th>
      <th>Nutritional Deficiencies</th>
      <th>Malaria</th>
      <th>...</th>
      <th>Chronic Kidney Disease</th>
      <th>Poisonings</th>
      <th>Protein-Energy Malnutrition</th>
      <th>Road Injuries</th>
      <th>Chronic Respiratory Diseases</th>
      <th>Cirrhosis and Other Chronic Liver Diseases</th>
      <th>Digestive Diseases</th>
      <th>Fire, Heat, and Hot Substances</th>
      <th>Acute Hepatitis</th>
      <th>Population</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>60</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1990</td>
      <td>2159.0</td>
      <td>1116.0</td>
      <td>371.0</td>
      <td>2087.0</td>
      <td>93.0</td>
      <td>...</td>
      <td>3709.0</td>
      <td>338.0</td>
      <td>2054.0</td>
      <td>4154.0</td>
      <td>5945.0</td>
      <td>2673.0</td>
      <td>5005.0</td>
      <td>323.0</td>
      <td>2985.0</td>
      <td>12412311.0</td>
    </tr>
    <tr>
      <th>61</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1991</td>
      <td>2218.0</td>
      <td>1136.0</td>
      <td>374.0</td>
      <td>2153.0</td>
      <td>189.0</td>
      <td>...</td>
      <td>3724.0</td>
      <td>351.0</td>
      <td>2119.0</td>
      <td>4472.0</td>
      <td>6050.0</td>
      <td>2728.0</td>
      <td>5120.0</td>
      <td>332.0</td>
      <td>3092.0</td>
      <td>13299016.0</td>
    </tr>
    <tr>
      <th>62</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1992</td>
      <td>2475.0</td>
      <td>1162.0</td>
      <td>378.0</td>
      <td>2441.0</td>
      <td>239.0</td>
      <td>...</td>
      <td>3776.0</td>
      <td>386.0</td>
      <td>2404.0</td>
      <td>5106.0</td>
      <td>6223.0</td>
      <td>2830.0</td>
      <td>5335.0</td>
      <td>360.0</td>
      <td>3325.0</td>
      <td>14485543.0</td>
    </tr>
    <tr>
      <th>63</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1993</td>
      <td>2812.0</td>
      <td>1187.0</td>
      <td>384.0</td>
      <td>2837.0</td>
      <td>108.0</td>
      <td>...</td>
      <td>3862.0</td>
      <td>425.0</td>
      <td>2797.0</td>
      <td>5681.0</td>
      <td>6445.0</td>
      <td>2943.0</td>
      <td>5568.0</td>
      <td>396.0</td>
      <td>3601.0</td>
      <td>15816601.0</td>
    </tr>
    <tr>
      <th>64</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1994</td>
      <td>3027.0</td>
      <td>1211.0</td>
      <td>391.0</td>
      <td>3081.0</td>
      <td>211.0</td>
      <td>...</td>
      <td>3932.0</td>
      <td>451.0</td>
      <td>3038.0</td>
      <td>6001.0</td>
      <td>6664.0</td>
      <td>3027.0</td>
      <td>5739.0</td>
      <td>420.0</td>
      <td>3816.0</td>
      <td>17075728.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>8095</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>Africa</td>
      <td>Eastern Africa</td>
      <td>2015</td>
      <td>1439.0</td>
      <td>754.0</td>
      <td>215.0</td>
      <td>3019.0</td>
      <td>2518.0</td>
      <td>...</td>
      <td>2108.0</td>
      <td>381.0</td>
      <td>2990.0</td>
      <td>2373.0</td>
      <td>2751.0</td>
      <td>1956.0</td>
      <td>4202.0</td>
      <td>632.0</td>
      <td>146.0</td>
      <td>13814642.0</td>
    </tr>
    <tr>
      <th>8096</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>Africa</td>
      <td>Eastern Africa</td>
      <td>2016</td>
      <td>1457.0</td>
      <td>767.0</td>
      <td>219.0</td>
      <td>3056.0</td>
      <td>2050.0</td>
      <td>...</td>
      <td>2160.0</td>
      <td>393.0</td>
      <td>3027.0</td>
      <td>2436.0</td>
      <td>2788.0</td>
      <td>1962.0</td>
      <td>4264.0</td>
      <td>648.0</td>
      <td>146.0</td>
      <td>14030338.0</td>
    </tr>
    <tr>
      <th>8097</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>Africa</td>
      <td>Eastern Africa</td>
      <td>2017</td>
      <td>1460.0</td>
      <td>781.0</td>
      <td>223.0</td>
      <td>2990.0</td>
      <td>2116.0</td>
      <td>...</td>
      <td>2196.0</td>
      <td>398.0</td>
      <td>2962.0</td>
      <td>2473.0</td>
      <td>2818.0</td>
      <td>2007.0</td>
      <td>4342.0</td>
      <td>654.0</td>
      <td>144.0</td>
      <td>14236599.0</td>
    </tr>
    <tr>
      <th>8098</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>Africa</td>
      <td>Eastern Africa</td>
      <td>2018</td>
      <td>1450.0</td>
      <td>795.0</td>
      <td>227.0</td>
      <td>2918.0</td>
      <td>2088.0</td>
      <td>...</td>
      <td>2240.0</td>
      <td>400.0</td>
      <td>2890.0</td>
      <td>2509.0</td>
      <td>2849.0</td>
      <td>2030.0</td>
      <td>4377.0</td>
      <td>657.0</td>
      <td>139.0</td>
      <td>14438812.0</td>
    </tr>
    <tr>
      <th>8099</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>Africa</td>
      <td>Eastern Africa</td>
      <td>2019</td>
      <td>1450.0</td>
      <td>812.0</td>
      <td>232.0</td>
      <td>2884.0</td>
      <td>2068.0</td>
      <td>...</td>
      <td>2292.0</td>
      <td>405.0</td>
      <td>2855.0</td>
      <td>2554.0</td>
      <td>2891.0</td>
      <td>2065.0</td>
      <td>4437.0</td>
      <td>662.0</td>
      <td>136.0</td>
      <td>14645473.0</td>
    </tr>
  </tbody>
</table>
<p>6120 rows × 37 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-82dfd7bf-0cd1-4fbe-9a0f-ce5ea90fb9b2')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-82dfd7bf-0cd1-4fbe-9a0f-ce5ea90fb9b2 button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-82dfd7bf-0cd1-4fbe-9a0f-ce5ea90fb9b2');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-192edf6e-87fd-40bd-b8f8-3abbdd2dc79d">
  <button class="colab-df-quickchart" onclick="quickchart('df-192edf6e-87fd-40bd-b8f8-3abbdd2dc79d')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-192edf6e-87fd-40bd-b8f8-3abbdd2dc79d button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

  <div id="id_4b1873d7-c41d-4e49-bec4-0709f65bfc1c">
    <style>
      .colab-df-generate {
        background-color: #E8F0FE;
        border: none;
        border-radius: 50%;
        cursor: pointer;
        display: none;
        fill: #1967D2;
        height: 32px;
        padding: 0 0 0 0;
        width: 32px;
      }

      .colab-df-generate:hover {
        background-color: #E2EBFA;
        box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
        fill: #174EA6;
      }

      [theme=dark] .colab-df-generate {
        background-color: #3B4455;
        fill: #D2E3FC;
      }

      [theme=dark] .colab-df-generate:hover {
        background-color: #434B5C;
        box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
        filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
        fill: #FFFFFF;
      }
    </style>
    <button class="colab-df-generate" onclick="generateWithVariable('df_Main_data')"
            title="Generate code using this dataframe."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M7,19H8.4L18.45,9,17,7.55,7,17.6ZM5,21V16.75L18.45,3.32a2,2,0,0,1,2.83,0l1.4,1.43a1.91,1.91,0,0,1,.58,1.4,1.91,1.91,0,0,1-.58,1.4L9.25,21ZM18.45,9,17,7.55Zm-12,3A5.31,5.31,0,0,0,4.9,8.1,5.31,5.31,0,0,0,1,6.5,5.31,5.31,0,0,0,4.9,4.9,5.31,5.31,0,0,0,6.5,1,5.31,5.31,0,0,0,8.1,4.9,5.31,5.31,0,0,0,12,6.5,5.46,5.46,0,0,0,6.5,12Z"/>
  </svg>
    </button>
    <script>
      (() => {
      const buttonEl =
        document.querySelector('#id_4b1873d7-c41d-4e49-bec4-0709f65bfc1c button.colab-df-generate');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      buttonEl.onclick = () => {
        google.colab.notebook.generateWithVariable('df_Main_data');
      }
      })();
    </script>
  </div>

    </div>
  </div>





```python
# prompt: show null data in column Population

df_Main_data[df_Main_data['Population'].isnull()]['Code'].unique()

```




    array(['COK', 'ERI', 'KWT', 'NIU', 'TKL'], dtype=object)




```python
# prompt: list of name of column

column_names = df_Main_data.columns.tolist()
print(column_names)
```

    ['Country/Territory', 'Code', 'continent', 'sub_region', 'Year', 'Meningitis', "Alzheimer's Disease and Other Dementias", "Parkinson's Disease", 'Nutritional Deficiencies', 'Malaria', 'Drowning', 'Interpersonal Violence', 'Maternal Disorders', 'HIV/AIDS', 'Drug Use Disorders', 'Tuberculosis', 'Cardiovascular Diseases', 'Lower Respiratory Infections', 'Neonatal Disorders', 'Alcohol Use Disorders', 'Self-harm', 'Exposure to Forces of Nature', 'Diarrheal Diseases', 'Environmental Heat and Cold Exposure', 'Neoplasms', 'Conflict and Terrorism', 'Diabetes Mellitus', 'Chronic Kidney Disease', 'Poisonings', 'Protein-Energy Malnutrition', 'Road Injuries', 'Chronic Respiratory Diseases', 'Cirrhosis and Other Chronic Liver Diseases', 'Digestive Diseases', 'Fire, Heat, and Hot Substances', 'Acute Hepatitis', 'Population']
    

###Rename Columns


```python
#change name of column of df_Main_data replace blank with "_" and Capitalized

df_Main_data = df_Main_data.rename(columns={'Country/Territory': 'Country', 'continent': 'Continent', 'sub_region': 'Sub_region', "Alzheimer's Disease and Other Dementias": 'Alzheimers_Disease_and_Other_Dementias', "Parkinson's Disease": 'Parkinsons_Disease', 'Nutritional Deficiencies': 'Nutritional_Deficiencies', 'Interpersonal Violence': 'Interpersonal_Violence', 'Maternal Disorders': 'Maternal_Disorders', 'HIV/AIDS': 'HIV', 'Drug Use Disorders': 'Drug_Use_Disorders', 'Cardiovascular Diseases': 'Cardiovascular_Diseases', 'Lower Respiratory Infections': 'Lower_Respiratory_Infections', 'Neonatal Disorders': 'Neonatal_Disorders', 'Alcohol Use Disorders': 'Alcohol_Use_Disorders', 'Self-harm': 'Self_harm', 'Exposure to Forces of Nature': 'Exposure_to_Forces_of_Nature', 'Diarrheal Diseases': 'Diarrheal_Diseases', 'Environmental Heat and Cold Exposure': 'Environmental_Heat_and_Cold_Exposure', 'Conflict and Terrorism': 'Conflict_and_Terrorism', 'Diabetes Mellitus': 'Diabetes_Mellitus', 'Chronic Kidney Disease': 'Chronic_Kidney_Disease', 'Protein-Energy Malnutrition': 'Protein_Energy_Malnutrition', 'Road Injuries': 'Road_Injuries', 'Chronic Respiratory Diseases': 'Chronic_Respiratory_Diseases', 'Cirrhosis and Other Chronic Liver Diseases': 'Cirrhosis_and_Other_Chronic_Liver_Diseases', 'Digestive Diseases': 'Digestive_Diseases', 'Fire, Heat, and Hot Substances': 'Fire_Heat_and_Hot_Substances', 'Acute Hepatitis': 'Acute_Hepatitis'})
```


```python
df_Main_data.head()
```





  <div id="df-4ad6c372-ba7e-4180-932e-f65eaff49fae" class="colab-df-container">
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
      <th>Country</th>
      <th>Code</th>
      <th>Continent</th>
      <th>Sub_region</th>
      <th>Year</th>
      <th>Meningitis</th>
      <th>Alzheimers_Disease_and_Other_Dementias</th>
      <th>Parkinsons_Disease</th>
      <th>Nutritional_Deficiencies</th>
      <th>Malaria</th>
      <th>...</th>
      <th>Chronic_Kidney_Disease</th>
      <th>Poisonings</th>
      <th>Protein_Energy_Malnutrition</th>
      <th>Road_Injuries</th>
      <th>Chronic_Respiratory_Diseases</th>
      <th>Cirrhosis_and_Other_Chronic_Liver_Diseases</th>
      <th>Digestive_Diseases</th>
      <th>Fire_Heat_and_Hot_Substances</th>
      <th>Acute_Hepatitis</th>
      <th>Population</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>60</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1990</td>
      <td>2159.0</td>
      <td>1116.0</td>
      <td>371.0</td>
      <td>2087.0</td>
      <td>93.0</td>
      <td>...</td>
      <td>3709.0</td>
      <td>338.0</td>
      <td>2054.0</td>
      <td>4154.0</td>
      <td>5945.0</td>
      <td>2673.0</td>
      <td>5005.0</td>
      <td>323.0</td>
      <td>2985.0</td>
      <td>12412311.0</td>
    </tr>
    <tr>
      <th>61</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1991</td>
      <td>2218.0</td>
      <td>1136.0</td>
      <td>374.0</td>
      <td>2153.0</td>
      <td>189.0</td>
      <td>...</td>
      <td>3724.0</td>
      <td>351.0</td>
      <td>2119.0</td>
      <td>4472.0</td>
      <td>6050.0</td>
      <td>2728.0</td>
      <td>5120.0</td>
      <td>332.0</td>
      <td>3092.0</td>
      <td>13299016.0</td>
    </tr>
    <tr>
      <th>62</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1992</td>
      <td>2475.0</td>
      <td>1162.0</td>
      <td>378.0</td>
      <td>2441.0</td>
      <td>239.0</td>
      <td>...</td>
      <td>3776.0</td>
      <td>386.0</td>
      <td>2404.0</td>
      <td>5106.0</td>
      <td>6223.0</td>
      <td>2830.0</td>
      <td>5335.0</td>
      <td>360.0</td>
      <td>3325.0</td>
      <td>14485543.0</td>
    </tr>
    <tr>
      <th>63</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1993</td>
      <td>2812.0</td>
      <td>1187.0</td>
      <td>384.0</td>
      <td>2837.0</td>
      <td>108.0</td>
      <td>...</td>
      <td>3862.0</td>
      <td>425.0</td>
      <td>2797.0</td>
      <td>5681.0</td>
      <td>6445.0</td>
      <td>2943.0</td>
      <td>5568.0</td>
      <td>396.0</td>
      <td>3601.0</td>
      <td>15816601.0</td>
    </tr>
    <tr>
      <th>64</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1994</td>
      <td>3027.0</td>
      <td>1211.0</td>
      <td>391.0</td>
      <td>3081.0</td>
      <td>211.0</td>
      <td>...</td>
      <td>3932.0</td>
      <td>451.0</td>
      <td>3038.0</td>
      <td>6001.0</td>
      <td>6664.0</td>
      <td>3027.0</td>
      <td>5739.0</td>
      <td>420.0</td>
      <td>3816.0</td>
      <td>17075728.0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 37 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-4ad6c372-ba7e-4180-932e-f65eaff49fae')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-4ad6c372-ba7e-4180-932e-f65eaff49fae button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-4ad6c372-ba7e-4180-932e-f65eaff49fae');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-0b2cddf8-261e-4872-b646-8f7aef9ab86f">
  <button class="colab-df-quickchart" onclick="quickchart('df-0b2cddf8-261e-4872-b646-8f7aef9ab86f')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-0b2cddf8-261e-4872-b646-8f7aef9ab86f button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>





```python
column_names = df_Main_data.columns.tolist()
print(column_names)
```

    ['Country', 'Code', 'Continent', 'Sub_region', 'Year', 'Meningitis', 'Alzheimers_Disease_and_Other_Dementias', 'Parkinsons_Disease', 'Nutritional_Deficiencies', 'Malaria', 'Drowning', 'Interpersonal_Violence', 'Maternal_Disorders', 'HIV', 'Drug_Use_Disorders', 'Tuberculosis', 'Cardiovascular_Diseases', 'Lower_Respiratory_Infections', 'Neonatal_Disorders', 'Alcohol_Use_Disorders', 'Self_harm', 'Exposure_to_Forces_of_Nature', 'Diarrheal_Diseases', 'Environmental_Heat_and_Cold_Exposure', 'Neoplasms', 'Conflict_and_Terrorism', 'Diabetes_Mellitus', 'Chronic_Kidney_Disease', 'Poisonings', 'Protein_Energy_Malnutrition', 'Road_Injuries', 'Chronic_Respiratory_Diseases', 'Cirrhosis_and_Other_Chronic_Liver_Diseases', 'Digestive_Diseases', 'Fire_Heat_and_Hot_Substances', 'Acute_Hepatitis', 'Population']
    

###Add Column Total amount of Death by Cause and Ratio of Death per Population


```python
# prompt: add column total_dead that sum from column Meningitis to column Acute_Hepatitis
#Use column_to_sum for represent all cause of death
columns_to_sum = ['Meningitis', 'Alzheimers_Disease_and_Other_Dementias', 'Parkinsons_Disease',
                  'Nutritional_Deficiencies', 'Malaria', 'Drowning', 'Interpersonal_Violence',
                  'Maternal_Disorders', 'HIV', 'Drug_Use_Disorders', 'Tuberculosis', 'Cardiovascular_Diseases',
                  'Lower_Respiratory_Infections', 'Neonatal_Disorders', 'Alcohol_Use_Disorders', 'Self_harm',
                  'Exposure_to_Forces_of_Nature', 'Diarrheal_Diseases', 'Environmental_Heat_and_Cold_Exposure',
                  'Neoplasms', 'Conflict_and_Terrorism', 'Diabetes_Mellitus', 'Chronic_Kidney_Disease',
                  'Poisonings', 'Protein_Energy_Malnutrition', 'Road_Injuries', 'Chronic_Respiratory_Diseases',
                  'Cirrhosis_and_Other_Chronic_Liver_Diseases', 'Digestive_Diseases', 'Fire_Heat_and_Hot_Substances', 'Acute_Hepatitis']

df_Main_data['Total_Dead'] = df_Main_data[columns_to_sum].sum(axis=1)

```


```python
df_Main_data
```





  <div id="df-a4e06551-99d5-4937-b3ab-03da006f6ae1" class="colab-df-container">
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
      <th>Country</th>
      <th>Code</th>
      <th>Continent</th>
      <th>Sub_region</th>
      <th>Year</th>
      <th>Meningitis</th>
      <th>Alzheimers_Disease_and_Other_Dementias</th>
      <th>Parkinsons_Disease</th>
      <th>Nutritional_Deficiencies</th>
      <th>Malaria</th>
      <th>...</th>
      <th>Poisonings</th>
      <th>Protein_Energy_Malnutrition</th>
      <th>Road_Injuries</th>
      <th>Chronic_Respiratory_Diseases</th>
      <th>Cirrhosis_and_Other_Chronic_Liver_Diseases</th>
      <th>Digestive_Diseases</th>
      <th>Fire_Heat_and_Hot_Substances</th>
      <th>Acute_Hepatitis</th>
      <th>Population</th>
      <th>Total_Dead</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>60</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1990</td>
      <td>2159.0</td>
      <td>1116.0</td>
      <td>371.0</td>
      <td>2087.0</td>
      <td>93.0</td>
      <td>...</td>
      <td>338.0</td>
      <td>2054.0</td>
      <td>4154.0</td>
      <td>5945.0</td>
      <td>2673.0</td>
      <td>5005.0</td>
      <td>323.0</td>
      <td>2985.0</td>
      <td>12412311.0</td>
      <td>147971.0</td>
    </tr>
    <tr>
      <th>61</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1991</td>
      <td>2218.0</td>
      <td>1136.0</td>
      <td>374.0</td>
      <td>2153.0</td>
      <td>189.0</td>
      <td>...</td>
      <td>351.0</td>
      <td>2119.0</td>
      <td>4472.0</td>
      <td>6050.0</td>
      <td>2728.0</td>
      <td>5120.0</td>
      <td>332.0</td>
      <td>3092.0</td>
      <td>13299016.0</td>
      <td>156844.0</td>
    </tr>
    <tr>
      <th>62</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1992</td>
      <td>2475.0</td>
      <td>1162.0</td>
      <td>378.0</td>
      <td>2441.0</td>
      <td>239.0</td>
      <td>...</td>
      <td>386.0</td>
      <td>2404.0</td>
      <td>5106.0</td>
      <td>6223.0</td>
      <td>2830.0</td>
      <td>5335.0</td>
      <td>360.0</td>
      <td>3325.0</td>
      <td>14485543.0</td>
      <td>169156.0</td>
    </tr>
    <tr>
      <th>63</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1993</td>
      <td>2812.0</td>
      <td>1187.0</td>
      <td>384.0</td>
      <td>2837.0</td>
      <td>108.0</td>
      <td>...</td>
      <td>425.0</td>
      <td>2797.0</td>
      <td>5681.0</td>
      <td>6445.0</td>
      <td>2943.0</td>
      <td>5568.0</td>
      <td>396.0</td>
      <td>3601.0</td>
      <td>15816601.0</td>
      <td>182230.0</td>
    </tr>
    <tr>
      <th>64</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1994</td>
      <td>3027.0</td>
      <td>1211.0</td>
      <td>391.0</td>
      <td>3081.0</td>
      <td>211.0</td>
      <td>...</td>
      <td>451.0</td>
      <td>3038.0</td>
      <td>6001.0</td>
      <td>6664.0</td>
      <td>3027.0</td>
      <td>5739.0</td>
      <td>420.0</td>
      <td>3816.0</td>
      <td>17075728.0</td>
      <td>194795.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>8095</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>Africa</td>
      <td>Eastern Africa</td>
      <td>2015</td>
      <td>1439.0</td>
      <td>754.0</td>
      <td>215.0</td>
      <td>3019.0</td>
      <td>2518.0</td>
      <td>...</td>
      <td>381.0</td>
      <td>2990.0</td>
      <td>2373.0</td>
      <td>2751.0</td>
      <td>1956.0</td>
      <td>4202.0</td>
      <td>632.0</td>
      <td>146.0</td>
      <td>13814642.0</td>
      <td>130080.0</td>
    </tr>
    <tr>
      <th>8096</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>Africa</td>
      <td>Eastern Africa</td>
      <td>2016</td>
      <td>1457.0</td>
      <td>767.0</td>
      <td>219.0</td>
      <td>3056.0</td>
      <td>2050.0</td>
      <td>...</td>
      <td>393.0</td>
      <td>3027.0</td>
      <td>2436.0</td>
      <td>2788.0</td>
      <td>1962.0</td>
      <td>4264.0</td>
      <td>648.0</td>
      <td>146.0</td>
      <td>14030338.0</td>
      <td>128274.0</td>
    </tr>
    <tr>
      <th>8097</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>Africa</td>
      <td>Eastern Africa</td>
      <td>2017</td>
      <td>1460.0</td>
      <td>781.0</td>
      <td>223.0</td>
      <td>2990.0</td>
      <td>2116.0</td>
      <td>...</td>
      <td>398.0</td>
      <td>2962.0</td>
      <td>2473.0</td>
      <td>2818.0</td>
      <td>2007.0</td>
      <td>4342.0</td>
      <td>654.0</td>
      <td>144.0</td>
      <td>14236599.0</td>
      <td>126515.0</td>
    </tr>
    <tr>
      <th>8098</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>Africa</td>
      <td>Eastern Africa</td>
      <td>2018</td>
      <td>1450.0</td>
      <td>795.0</td>
      <td>227.0</td>
      <td>2918.0</td>
      <td>2088.0</td>
      <td>...</td>
      <td>400.0</td>
      <td>2890.0</td>
      <td>2509.0</td>
      <td>2849.0</td>
      <td>2030.0</td>
      <td>4377.0</td>
      <td>657.0</td>
      <td>139.0</td>
      <td>14438812.0</td>
      <td>123506.0</td>
    </tr>
    <tr>
      <th>8099</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>Africa</td>
      <td>Eastern Africa</td>
      <td>2019</td>
      <td>1450.0</td>
      <td>812.0</td>
      <td>232.0</td>
      <td>2884.0</td>
      <td>2068.0</td>
      <td>...</td>
      <td>405.0</td>
      <td>2855.0</td>
      <td>2554.0</td>
      <td>2891.0</td>
      <td>2065.0</td>
      <td>4437.0</td>
      <td>662.0</td>
      <td>136.0</td>
      <td>14645473.0</td>
      <td>123540.0</td>
    </tr>
  </tbody>
</table>
<p>6120 rows × 38 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-a4e06551-99d5-4937-b3ab-03da006f6ae1')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-a4e06551-99d5-4937-b3ab-03da006f6ae1 button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-a4e06551-99d5-4937-b3ab-03da006f6ae1');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-0bac3190-c3d1-45c8-b88d-cd1376184fa3">
  <button class="colab-df-quickchart" onclick="quickchart('df-0bac3190-c3d1-45c8-b88d-cd1376184fa3')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-0bac3190-c3d1-45c8-b88d-cd1376184fa3 button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

  <div id="id_ce17167b-e31f-4148-bf8e-39b0bf46b81d">
    <style>
      .colab-df-generate {
        background-color: #E8F0FE;
        border: none;
        border-radius: 50%;
        cursor: pointer;
        display: none;
        fill: #1967D2;
        height: 32px;
        padding: 0 0 0 0;
        width: 32px;
      }

      .colab-df-generate:hover {
        background-color: #E2EBFA;
        box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
        fill: #174EA6;
      }

      [theme=dark] .colab-df-generate {
        background-color: #3B4455;
        fill: #D2E3FC;
      }

      [theme=dark] .colab-df-generate:hover {
        background-color: #434B5C;
        box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
        filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
        fill: #FFFFFF;
      }
    </style>
    <button class="colab-df-generate" onclick="generateWithVariable('df_Main_data')"
            title="Generate code using this dataframe."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M7,19H8.4L18.45,9,17,7.55,7,17.6ZM5,21V16.75L18.45,3.32a2,2,0,0,1,2.83,0l1.4,1.43a1.91,1.91,0,0,1,.58,1.4,1.91,1.91,0,0,1-.58,1.4L9.25,21ZM18.45,9,17,7.55Zm-12,3A5.31,5.31,0,0,0,4.9,8.1,5.31,5.31,0,0,0,1,6.5,5.31,5.31,0,0,0,4.9,4.9,5.31,5.31,0,0,0,6.5,1,5.31,5.31,0,0,0,8.1,4.9,5.31,5.31,0,0,0,12,6.5,5.46,5.46,0,0,0,6.5,12Z"/>
  </svg>
    </button>
    <script>
      (() => {
      const buttonEl =
        document.querySelector('#id_ce17167b-e31f-4148-bf8e-39b0bf46b81d button.colab-df-generate');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      buttonEl.onclick = () => {
        google.colab.notebook.generateWithVariable('df_Main_data');
      }
      })();
    </script>
  </div>

    </div>
  </div>





```python
# prompt: move column Population in to last column

# Get a list of column names
cols = list(df_Main_data.columns)

# Find the index of the 'Population' column
population_index = cols.index('Population')

# Remove 'Population' from its original position
cols.pop(population_index)

# Append 'Population' to the end of the list
cols.append('Population')

# Reorder the DataFrame columns based on the new list
df_Main_data = df_Main_data[cols]

df_Main_data.head()

```





  <div id="df-a32e923d-ae01-4726-980d-b5338a961794" class="colab-df-container">
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
      <th>Country</th>
      <th>Code</th>
      <th>Continent</th>
      <th>Sub_region</th>
      <th>Year</th>
      <th>Meningitis</th>
      <th>Alzheimers_Disease_and_Other_Dementias</th>
      <th>Parkinsons_Disease</th>
      <th>Nutritional_Deficiencies</th>
      <th>Malaria</th>
      <th>...</th>
      <th>Poisonings</th>
      <th>Protein_Energy_Malnutrition</th>
      <th>Road_Injuries</th>
      <th>Chronic_Respiratory_Diseases</th>
      <th>Cirrhosis_and_Other_Chronic_Liver_Diseases</th>
      <th>Digestive_Diseases</th>
      <th>Fire_Heat_and_Hot_Substances</th>
      <th>Acute_Hepatitis</th>
      <th>Total_Dead</th>
      <th>Population</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>60</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1990</td>
      <td>2159.0</td>
      <td>1116.0</td>
      <td>371.0</td>
      <td>2087.0</td>
      <td>93.0</td>
      <td>...</td>
      <td>338.0</td>
      <td>2054.0</td>
      <td>4154.0</td>
      <td>5945.0</td>
      <td>2673.0</td>
      <td>5005.0</td>
      <td>323.0</td>
      <td>2985.0</td>
      <td>147971.0</td>
      <td>12412311.0</td>
    </tr>
    <tr>
      <th>61</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1991</td>
      <td>2218.0</td>
      <td>1136.0</td>
      <td>374.0</td>
      <td>2153.0</td>
      <td>189.0</td>
      <td>...</td>
      <td>351.0</td>
      <td>2119.0</td>
      <td>4472.0</td>
      <td>6050.0</td>
      <td>2728.0</td>
      <td>5120.0</td>
      <td>332.0</td>
      <td>3092.0</td>
      <td>156844.0</td>
      <td>13299016.0</td>
    </tr>
    <tr>
      <th>62</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1992</td>
      <td>2475.0</td>
      <td>1162.0</td>
      <td>378.0</td>
      <td>2441.0</td>
      <td>239.0</td>
      <td>...</td>
      <td>386.0</td>
      <td>2404.0</td>
      <td>5106.0</td>
      <td>6223.0</td>
      <td>2830.0</td>
      <td>5335.0</td>
      <td>360.0</td>
      <td>3325.0</td>
      <td>169156.0</td>
      <td>14485543.0</td>
    </tr>
    <tr>
      <th>63</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1993</td>
      <td>2812.0</td>
      <td>1187.0</td>
      <td>384.0</td>
      <td>2837.0</td>
      <td>108.0</td>
      <td>...</td>
      <td>425.0</td>
      <td>2797.0</td>
      <td>5681.0</td>
      <td>6445.0</td>
      <td>2943.0</td>
      <td>5568.0</td>
      <td>396.0</td>
      <td>3601.0</td>
      <td>182230.0</td>
      <td>15816601.0</td>
    </tr>
    <tr>
      <th>64</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>Asia</td>
      <td>Southern Asia</td>
      <td>1994</td>
      <td>3027.0</td>
      <td>1211.0</td>
      <td>391.0</td>
      <td>3081.0</td>
      <td>211.0</td>
      <td>...</td>
      <td>451.0</td>
      <td>3038.0</td>
      <td>6001.0</td>
      <td>6664.0</td>
      <td>3027.0</td>
      <td>5739.0</td>
      <td>420.0</td>
      <td>3816.0</td>
      <td>194795.0</td>
      <td>17075728.0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 38 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-a32e923d-ae01-4726-980d-b5338a961794')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-a32e923d-ae01-4726-980d-b5338a961794 button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-a32e923d-ae01-4726-980d-b5338a961794');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


<div id="df-c3a28fa1-aa41-48e8-abed-e5e64a91868f">
  <button class="colab-df-quickchart" onclick="quickchart('df-c3a28fa1-aa41-48e8-abed-e5e64a91868f')"
            title="Suggest charts"
            style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
  </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

  <script>
    async function quickchart(key) {
      const quickchartButtonEl =
        document.querySelector('#' + key + ' button');
      quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
      quickchartButtonEl.classList.add('colab-df-spinner');
      try {
        const charts = await google.colab.kernel.invokeFunction(
            'suggestCharts', [key], {});
      } catch (error) {
        console.error('Error during call to suggestCharts:', error);
      }
      quickchartButtonEl.classList.remove('colab-df-spinner');
      quickchartButtonEl.classList.add('colab-df-quickchart-complete');
    }
    (() => {
      let quickchartButtonEl =
        document.querySelector('#df-c3a28fa1-aa41-48e8-abed-e5e64a91868f button');
      quickchartButtonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';
    })();
  </script>
</div>

    </div>
  </div>




#Analyze

# Book

## Detail of Event during 1990 - 2019

Events That Increased Mortality Rates
1. **HIV/AIDS Epidemic**: 1990 - Throughout the 1990s, particularly in Africa and Asia.
2. **Malaria Outbreak in Africa**: 1990s and 2000s - The African region experienced high malaria mortality rates until the distribution of bed nets and antimalarial medications helped reduce deaths.
3. **Yugoslav Wars**: 1991-2001 - Conflicts and civil wars in Yugoslavia resulted in numerous fatalities.
4. **Rwandan Genocide**: 1994 - This event led to over 800,000 deaths within a few months.
5. **Food Shortage in North Korea**: 1994-1998 - Severe food shortages in North Korea resulted in significant loss of life due to famine.
6. **Kobe Earthquake, Japan**: 1995 - Claimed the lives of over 6,000 people.
7. **Sierra Leone Civil War**: 1991-2002 - The violence from the civil war caused many deaths and displaced persons.
8. **Tuberculosis (TB) Resurgence**: Throughout the 1990s - TB re-emerged as a global health threat in many countries.
9. **War in Afghanistan**: 2001-Present - Ongoing conflict in Afghanistan has resulted in continuous casualties from fighting and airstrikes.
10. **Indian Ocean Earthquake and Tsunami**: 2004 - Claimed over 230,000 lives across several countries.
11. **Pakistan Earthquake**: 2005 - A major earthquake resulted in approximately 80,000 deaths in Pakistan.
12. **Iraq War**: 2003-2011 - Wars and conflicts in Iraq led to significant mortality.
13. **Cyclone Nargis in Myanmar**: 2008 - The cyclone resulted in over 130,000 deaths in Myanmar.
14. **H1N1 Influenza**: 2009 - The H1N1 virus outbreak resulted in global fatalities.
15. **SARS Epidemic**: 2002-2003 - The SARS virus caused several hundred deaths worldwide.
16. **Syrian Civil War**: 2011-Present - The conflict in Syria has resulted in numerous fatalities.
17. **Hurricane Katrina**: 2005 - The devastating hurricane in the United States caused significant loss of life and damage.
18. **Wildfires in Russia**: 2010 - Wildfires and the subsequent heatwave led to numerous respiratory-related deaths.
19. **Haiti Earthquake**: 2010 - One of the deadliest earthquakes, resulting in over 200,000 deaths.
20. **Dengue Fever Outbreak in Southeast Asia**: 2010-2019 - Resulted in significant fatalities, especially in the Philippines and Vietnam.
21. **Famine in Africa**: Particularly in Somalia, 2011 - Resulted in tens of thousands of deaths due to severe food shortages.
22. **Heatwave in Europe**: 2013 - The heatwave caused deaths related to high temperatures, especially in France and Germany.
23. **Ebola Outbreak**: 2014-2016 - A major outbreak in West Africa resulted in tens of thousands of deaths.
24. **Nepal Earthquake**: 2015 - A major earthquake resulted in over 9,000 deaths.
25. **Dengue Fever Epidemic**: Throughout the 2010s - The dengue outbreak in Asia and South America resulted in numerous fatalities.

Events That Decreased Mortality Rates
1. **HIV/AIDS Prevention Campaign**: 1990-1999 - Campaigns promoting condom use and regular health checks, along with the development of antiretroviral drugs, helped reduce AIDS mortality rates in developed countries and some countries in Africa and Asia.
2. **Expansion of Childhood Vaccination**: 1990s - Widespread vaccination against measles, polio, and pneumonia significantly reduced child mortality rates from infectious diseases.
3. **Access to Antiretroviral Drugs for HIV/AIDS**: 2000-2009 - Countries began to widely access antiretroviral medications, particularly in Africa, leading to a decrease in mortality from this disease.
4. **Development of Malaria Vaccines**: 2000-2009 - The use of bed nets and insecticides, along with access to antimalarial drugs, helped reduce malaria mortality in Africa.
5. **Use of Anticoagulants and Treatments for Cardiovascular Diseases**: 2000-2009 - Advances in medical technology and treatment for heart diseases reduced mortality rates from cardiovascular diseases in many countries.
6. **Use of Influenza Vaccines and Antiviral Medications**: 2000-2009 - Influenza vaccines and access to antiviral medications improved the control of influenza outbreaks, reducing mortality.
7. **Anti-Smoking Campaigns**: 2010-2019 - Many countries initiated anti-smoking policies, helping reduce deaths from lung-related diseases such as lung cancer and chronic obstructive pulmonary disease (COPD).
8. **Improved Access to Cancer Treatments**: 2010-2019 - Chemotherapy and new technology treatments reduced cancer mortality in developed countries.
9. **Traffic Safety Campaigns**: 2010-2019 - Campaigns promoting seatbelt use, helmet use, and speed limit laws in many countries helped reduce traffic fatalities.
10. **Development of HPV Vaccines**: 2007-2009 - Vaccination against the HPV virus, which causes cervical cancer, helped reduce cervical cancer mortality rates in many countries.
11. **Access to Clean Drinking Water**: 2000-2010 - Clean water and sanitation projects in many countries, especially in Africa and Asia, significantly reduced mortality rates from waterborne diseases, such as diarrhea.

Events in Thailand
Events that Increased Mortality Rates:
1. **HIV/AIDS Epidemic (1990s - Early 2000s)**: Thailand was heavily affected by the HIV/AIDS crisis in the 1990s before access to antiretroviral drugs began to reduce deaths in the following decade.
2. **Indian Ocean Tsunami (2004)**: The tsunami that hit southern Thailand in 2004 resulted in approximately 5,400 deaths.
3. **Severe Flooding in Thailand (2011)**: The massive flooding in central and northern Thailand resulted in hundreds of fatalities.

Events that Decreased Mortality Rates:
1. **Universal Health Coverage Scheme (2002)**: The introduction of the Universal Health Coverage scheme in 2002 improved access to healthcare services, resulting in a decrease in mortality from preventable and treatable diseases.
2. **Reduction in Maternal and Infant Mortality Rates (2000s)**: Increased investments in maternal and infant health programs led to lower mortality rates.
3. **Decrease in Malaria Deaths (2000s)**: Malaria prevention campaigns, especially in border areas, significantly reduced malaria-related deaths.
4. **Advances in Treatment and Prevention of Cardiovascular Diseases (1990s)**: Improved treatment methods and anti-smoking campaigns in the 2000s contributed to reduced mortality rates from cardiovascular diseases.

### Make time line for the Event during 1990 - 2019


```python
import plotly.express as px
import pandas as pd

# ตัวอย่างข้อมูลเหตุการณ์
events = [
    {"event": "HIV/AIDS Epidemic", "start": 1990, "end": 2005, "category": "Increase"},
    {"event": "Malaria Outbreak in Africa", "start": 1990, "end": 2000, "category": "Increase"},
    {"event": "Yugoslav Wars", "start": 1991, "end": 2001, "category": "Increase"},
    {"event": "Rwandan Genocide", "start": 1994, "end": 1994, "category": "Increase"},
    {"event": "Food Shortage in North Korea", "start": 1994, "end": 1998, "category": "Increase"},
    {"event": "Kobe Earthquake, Japan", "start": 1995, "end": 1995, "category": "Increase"},
    {"event": "Sierra Leone Civil War", "start": 1991, "end": 2002, "category": "Increase"},
    {"event": "Tuberculosis (TB) Resurgence", "start": 1990, "end": 1999, "category": "Increase"},
    {"event": "War in Afghanistan", "start": 2001, "end": 2023, "category": "Increase"},
    {"event": "Indian Ocean Earthquake and Tsunami", "start": 2004, "end": 2004, "category": "Increase"},
    {"event": "Pakistan Earthquake", "start": 2005, "end": 2005, "category": "Increase"},
    {"event": "Iraq War", "start": 2003, "end": 2011, "category": "Increase"},
    {"event": "Cyclone Nargis in Myanmar", "start": 2008, "end": 2008, "category": "Increase"},
    {"event": "H1N1 Influenza", "start": 2009, "end": 2009, "category": "Increase"},
    {"event": "SARS Epidemic", "start": 2002, "end": 2003, "category": "Increase"},
    {"event": "Syrian Civil War", "start": 2011, "end": 2023, "category": "Increase"},
    {"event": "Hurricane Katrina", "start": 2005, "end": 2005, "category": "Increase"},
    {"event": "Wildfires in Russia", "start": 2010, "end": 2010, "category": "Increase"},
    {"event": "Haiti Earthquake", "start": 2010, "end": 2010, "category": "Increase"},
    {"event": "Dengue Fever Outbreak in Southeast Asia", "start": 2010, "end": 2019, "category": "Increase"},
    {"event": "Famine in Africa", "start": 2011, "end": 2011, "category": "Increase"},
    {"event": "Heatwave in Europe", "start": 2013, "end": 2013, "category": "Increase"},
    {"event": "Ebola Outbreak", "start": 2014, "end": 2016, "category": "Increase"},
    {"event": "Nepal Earthquake", "start": 2015, "end": 2015, "category": "Increase"},
    {"event": "Dengue Fever Epidemic", "start": 2010, "end": 2019, "category": "Increase"},
    {"event": "HIV/AIDS Prevention Campaign", "start": 1990, "end": 1999, "category": "Decrease"},
    {"event": "Expansion of Childhood Vaccination", "start": 1990, "end": 1999, "category": "Decrease"},
    {"event": "Access to Antiretroviral Drugs for HIV/AIDS", "start": 2000, "end": 2009, "category": "Decrease"},
    {"event": "Development of Malaria Vaccines", "start": 2000, "end": 2009, "category": "Decrease"},
    {"event": "Use of Anticoagulants and Treatments for Cardiovascular Diseases", "start": 2000, "end": 2009, "category": "Decrease"},
    {"event": "Use of Influenza Vaccines and Antiviral Medications", "start": 2000, "end": 2009, "category": "Decrease"},
    {"event": "Anti-Smoking Campaigns", "start": 2010, "end": 2019, "category": "Decrease"},
    {"event": "Improved Access to Cancer Treatments", "start": 2010, "end": 2019, "category": "Decrease"},
    {"event": "Traffic Safety Campaigns", "start": 2010, "end": 2019, "category": "Decrease"},
    {"event": "Development of HPV Vaccines", "start": 2007, "end": 2009, "category": "Decrease"},
    {"event": "Access to Clean Drinking Water", "start": 2000, "end": 2010, "category": "Decrease"},
    {"event": "HIV/AIDS Epidemic in Thailand", "start": 1990, "end": 2000, "category": "Increase"},
    {"event": "Indian Ocean Tsunami in Thailand", "start": 2004, "end": 2004, "category": "Increase"},
    {"event": "Severe Flooding in Thailand", "start": 2011, "end": 2011, "category": "Increase"},
    {"event": "Universal Health Coverage Scheme in Thailand", "start": 2002, "end": 2023, "category": "Decrease"},
    {"event": "Reduction in Maternal and Infant Mortality Rates in Thailand", "start": 2000, "end": 2009, "category": "Decrease"},
    {"event": "Decrease in Malaria Deaths in Thailand", "start": 2000, "end": 2009, "category": "Decrease"},
    {"event": "Advances in Treatment and Prevention of Cardiovascular Diseases in Thailand", "start": 1990, "end": 2000, "category": "Decrease"}
]

# สร้าง DataFrame
df = pd.DataFrame(events)

# แปลงวันที่เป็น datetime objects
df["start"] = pd.to_datetime(df["start"], format="%Y")
df["end"] = pd.to_datetime(df["end"], format="%Y")

# สร้าง DataFrame แยกสำหรับเหตุการณ์ที่เพิ่มขึ้นและลดลง
df_increase = df[df["category"] == "Increase"]
df_decrease = df[df["category"] == "Decrease"]

# แยกกราฟเหตุการณ์ที่เพิ่มขึ้น
df_increase_single_year = df_increase[df_increase["start"] == df_increase["end"]]
df_increase_multi_year = df_increase[df_increase["start"] != df_increase["end"]]

# สร้างกราฟระยะเวลาสำหรับเหตุการณ์ที่เพิ่มขึ้น (ปีเดียว) พร้อมสีแดง
fig_increase_single_year = px.timeline(
    df_increase_single_year,
    x_start="start",
    x_end="end",
    y="event",
    title="Timeline of Single-Year Events Increasing Mortality (1990-2023)",
    color_discrete_sequence=["red"]  # กำหนดสีเป็นสีแดง
)

# สร้างกราฟระยะเวลาสำหรับเหตุการณ์ที่เพิ่มขึ้น (หลายปี) พร้อมสีแดง
fig_increase_multi_year = px.timeline(
    df_increase_multi_year,
    x_start="start",
    x_end="end",
    y="event",
    title="Timeline of Multi-Year Events Increasing Mortality (1990-2023)",
    color_discrete_sequence=["red"]  # กำหนดสีเป็นสีแดง
)

# สร้างกราฟระยะเวลาสำหรับเหตุการณ์ที่ลดลง พร้อมสีเขียว
fig_decrease = px.timeline(
    df_decrease,
    x_start="start",
    x_end="end",
    y="event",
    title="Timeline of Events Decreasing Mortality (1990-2023)",
    color_discrete_sequence=["#0000FF"]  # กำหนดสีเป็นสีเขียว
)

# จัดเรียงเหตุการณ์ตามเวลา
fig_increase_single_year.update_yaxes(categoryorder="total ascending")
fig_increase_multi_year.update_yaxes(categoryorder="total ascending")
fig_decrease.update_yaxes(categoryorder="total ascending")

# ตั้งค่า x-axis ให้ครอบคลุมเหตุการณ์ทั้งหมด
fig_increase_single_year.update_layout(xaxis_range=[df["start"].min(), df["end"].max()])
fig_increase_multi_year.update_layout(xaxis_range=[df["start"].min(), df["end"].max()])
fig_decrease.update_layout(xaxis_range=[df["start"].min(), df["end"].max()])

# เพิ่ม categoryarray เพื่อให้แสดงทุกเหตุการณ์ในแกน Y
fig_increase_single_year.update_yaxes(categoryarray=df_increase_single_year['event'])
fig_increase_multi_year.update_yaxes(categoryarray=df_increase_multi_year['event'])
fig_decrease.update_yaxes(categoryarray=df_decrease['event'])

# เพิ่มจุดปีลงไปในกราฟ
for index, row in df_increase_single_year.iterrows():
    fig_increase_single_year.add_annotation(
        x=row["start"],
        y=row["event"],
        text=str(row["start"].year),
        showarrow=True,
        arrowhead=2,
        ax=0,
        ay=-40,
        font=dict(size=10),
        bgcolor="white",
        bordercolor="black",
        borderwidth=1,
        borderpad=4,
    )


# เพิ่ม grid แนวนอน
fig_increase_single_year.update_yaxes(showgrid=True)

# แสดงกราฟ
fig_increase_single_year.show()
fig_increase_multi_year.show()
fig_decrease.show()

```


<html>
<head><meta charset="utf-8" /></head>
<body>
    <div>            <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-AMS-MML_SVG"></script><script type="text/javascript">if (window.MathJax && window.MathJax.Hub && window.MathJax.Hub.Config) {window.MathJax.Hub.Config({SVG: {font: "STIX-Web"}});}</script>                <script type="text/javascript">window.PlotlyConfig = {MathJaxConfig: 'local'};</script>
        <script charset="utf-8" src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>                <div id="28c1efc5-39aa-4937-92bb-f2e712d97e18" class="plotly-graph-div" style="height:525px; width:100%;"></div>            <script type="text/javascript">                                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("28c1efc5-39aa-4937-92bb-f2e712d97e18")) {                    Plotly.newPlot(                        "28c1efc5-39aa-4937-92bb-f2e712d97e18",                        [{"alignmentgroup":"True","base":["1994-01-01T00:00:00","1995-01-01T00:00:00","2004-01-01T00:00:00","2005-01-01T00:00:00","2008-01-01T00:00:00","2009-01-01T00:00:00","2005-01-01T00:00:00","2010-01-01T00:00:00","2010-01-01T00:00:00","2011-01-01T00:00:00","2013-01-01T00:00:00","2015-01-01T00:00:00","2004-01-01T00:00:00","2011-01-01T00:00:00"],"hovertemplate":"start=%{base}\u003cbr\u003eend=%{x}\u003cbr\u003eevent=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"","marker":{"color":"red","pattern":{"shape":""}},"name":"","offsetgroup":"","orientation":"h","showlegend":false,"textposition":"auto","x":[0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0],"xaxis":"x","y":["Rwandan Genocide","Kobe Earthquake, Japan","Indian Ocean Earthquake and Tsunami","Pakistan Earthquake","Cyclone Nargis in Myanmar","H1N1 Influenza","Hurricane Katrina","Wildfires in Russia","Haiti Earthquake","Famine in Africa","Heatwave in Europe","Nepal Earthquake","Indian Ocean Tsunami in Thailand","Severe Flooding in Thailand"],"yaxis":"y","type":"bar"}],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"type":"date","range":["1990-01-01T00:00:00","2023-01-01T00:00:00"]},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"event"},"categoryorder":"total ascending","categoryarray":["Rwandan Genocide","Kobe Earthquake, Japan","Indian Ocean Earthquake and Tsunami","Pakistan Earthquake","Cyclone Nargis in Myanmar","H1N1 Influenza","Hurricane Katrina","Wildfires in Russia","Haiti Earthquake","Famine in Africa","Heatwave in Europe","Nepal Earthquake","Indian Ocean Tsunami in Thailand","Severe Flooding in Thailand"],"showgrid":true},"legend":{"tracegroupgap":0},"title":{"text":"Timeline of Single-Year Events Increasing Mortality (1990-2023)"},"barmode":"overlay","annotations":[{"arrowhead":2,"ax":0,"ay":-40,"bgcolor":"white","bordercolor":"black","borderpad":4,"borderwidth":1,"font":{"size":10},"showarrow":true,"text":"1994","x":"1994-01-01T00:00:00","y":"Rwandan Genocide"},{"arrowhead":2,"ax":0,"ay":-40,"bgcolor":"white","bordercolor":"black","borderpad":4,"borderwidth":1,"font":{"size":10},"showarrow":true,"text":"1995","x":"1995-01-01T00:00:00","y":"Kobe Earthquake, Japan"},{"arrowhead":2,"ax":0,"ay":-40,"bgcolor":"white","bordercolor":"black","borderpad":4,"borderwidth":1,"font":{"size":10},"showarrow":true,"text":"2004","x":"2004-01-01T00:00:00","y":"Indian Ocean Earthquake and Tsunami"},{"arrowhead":2,"ax":0,"ay":-40,"bgcolor":"white","bordercolor":"black","borderpad":4,"borderwidth":1,"font":{"size":10},"showarrow":true,"text":"2005","x":"2005-01-01T00:00:00","y":"Pakistan Earthquake"},{"arrowhead":2,"ax":0,"ay":-40,"bgcolor":"white","bordercolor":"black","borderpad":4,"borderwidth":1,"font":{"size":10},"showarrow":true,"text":"2008","x":"2008-01-01T00:00:00","y":"Cyclone Nargis in Myanmar"},{"arrowhead":2,"ax":0,"ay":-40,"bgcolor":"white","bordercolor":"black","borderpad":4,"borderwidth":1,"font":{"size":10},"showarrow":true,"text":"2009","x":"2009-01-01T00:00:00","y":"H1N1 Influenza"},{"arrowhead":2,"ax":0,"ay":-40,"bgcolor":"white","bordercolor":"black","borderpad":4,"borderwidth":1,"font":{"size":10},"showarrow":true,"text":"2005","x":"2005-01-01T00:00:00","y":"Hurricane Katrina"},{"arrowhead":2,"ax":0,"ay":-40,"bgcolor":"white","bordercolor":"black","borderpad":4,"borderwidth":1,"font":{"size":10},"showarrow":true,"text":"2010","x":"2010-01-01T00:00:00","y":"Wildfires in Russia"},{"arrowhead":2,"ax":0,"ay":-40,"bgcolor":"white","bordercolor":"black","borderpad":4,"borderwidth":1,"font":{"size":10},"showarrow":true,"text":"2010","x":"2010-01-01T00:00:00","y":"Haiti Earthquake"},{"arrowhead":2,"ax":0,"ay":-40,"bgcolor":"white","bordercolor":"black","borderpad":4,"borderwidth":1,"font":{"size":10},"showarrow":true,"text":"2011","x":"2011-01-01T00:00:00","y":"Famine in Africa"},{"arrowhead":2,"ax":0,"ay":-40,"bgcolor":"white","bordercolor":"black","borderpad":4,"borderwidth":1,"font":{"size":10},"showarrow":true,"text":"2013","x":"2013-01-01T00:00:00","y":"Heatwave in Europe"},{"arrowhead":2,"ax":0,"ay":-40,"bgcolor":"white","bordercolor":"black","borderpad":4,"borderwidth":1,"font":{"size":10},"showarrow":true,"text":"2015","x":"2015-01-01T00:00:00","y":"Nepal Earthquake"},{"arrowhead":2,"ax":0,"ay":-40,"bgcolor":"white","bordercolor":"black","borderpad":4,"borderwidth":1,"font":{"size":10},"showarrow":true,"text":"2004","x":"2004-01-01T00:00:00","y":"Indian Ocean Tsunami in Thailand"},{"arrowhead":2,"ax":0,"ay":-40,"bgcolor":"white","bordercolor":"black","borderpad":4,"borderwidth":1,"font":{"size":10},"showarrow":true,"text":"2011","x":"2011-01-01T00:00:00","y":"Severe Flooding in Thailand"}]},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('28c1efc5-39aa-4937-92bb-f2e712d97e18');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                            </script>        </div>
</body>
</html>



<html>
<head><meta charset="utf-8" /></head>
<body>
    <div>            <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-AMS-MML_SVG"></script><script type="text/javascript">if (window.MathJax && window.MathJax.Hub && window.MathJax.Hub.Config) {window.MathJax.Hub.Config({SVG: {font: "STIX-Web"}});}</script>                <script type="text/javascript">window.PlotlyConfig = {MathJaxConfig: 'local'};</script>
        <script charset="utf-8" src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>                <div id="bcc0ea5d-f860-4dc0-8ab3-a26c5cb4329f" class="plotly-graph-div" style="height:525px; width:100%;"></div>            <script type="text/javascript">                                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("bcc0ea5d-f860-4dc0-8ab3-a26c5cb4329f")) {                    Plotly.newPlot(                        "bcc0ea5d-f860-4dc0-8ab3-a26c5cb4329f",                        [{"alignmentgroup":"True","base":["1990-01-01T00:00:00","1990-01-01T00:00:00","1991-01-01T00:00:00","1994-01-01T00:00:00","1991-01-01T00:00:00","1990-01-01T00:00:00","2001-01-01T00:00:00","2003-01-01T00:00:00","2002-01-01T00:00:00","2011-01-01T00:00:00","2010-01-01T00:00:00","2014-01-01T00:00:00","2010-01-01T00:00:00","1990-01-01T00:00:00"],"hovertemplate":"start=%{base}\u003cbr\u003eend=%{x}\u003cbr\u003eevent=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"","marker":{"color":"red","pattern":{"shape":""}},"name":"","offsetgroup":"","orientation":"h","showlegend":false,"textposition":"auto","x":[473385600000.0,315532800000.0,315619200000.0,126230400000.0,347155200000.0,283996800000.0,694224000000.0,252460800000.0,31536000000.0,378691200000.0,283996800000.0,63072000000.0,283996800000.0,315532800000.0],"xaxis":"x","y":["HIV\u002fAIDS Epidemic","Malaria Outbreak in Africa","Yugoslav Wars","Food Shortage in North Korea","Sierra Leone Civil War","Tuberculosis (TB) Resurgence","War in Afghanistan","Iraq War","SARS Epidemic","Syrian Civil War","Dengue Fever Outbreak in Southeast Asia","Ebola Outbreak","Dengue Fever Epidemic","HIV\u002fAIDS Epidemic in Thailand"],"yaxis":"y","type":"bar"}],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"type":"date","range":["1990-01-01T00:00:00","2023-01-01T00:00:00"]},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"event"},"categoryorder":"total ascending","categoryarray":["HIV\u002fAIDS Epidemic","Malaria Outbreak in Africa","Yugoslav Wars","Food Shortage in North Korea","Sierra Leone Civil War","Tuberculosis (TB) Resurgence","War in Afghanistan","Iraq War","SARS Epidemic","Syrian Civil War","Dengue Fever Outbreak in Southeast Asia","Ebola Outbreak","Dengue Fever Epidemic","HIV\u002fAIDS Epidemic in Thailand"]},"legend":{"tracegroupgap":0},"title":{"text":"Timeline of Multi-Year Events Increasing Mortality (1990-2023)"},"barmode":"overlay"},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('bcc0ea5d-f860-4dc0-8ab3-a26c5cb4329f');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                            </script>        </div>
</body>
</html>



<html>
<head><meta charset="utf-8" /></head>
<body>
    <div>            <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-AMS-MML_SVG"></script><script type="text/javascript">if (window.MathJax && window.MathJax.Hub && window.MathJax.Hub.Config) {window.MathJax.Hub.Config({SVG: {font: "STIX-Web"}});}</script>                <script type="text/javascript">window.PlotlyConfig = {MathJaxConfig: 'local'};</script>
        <script charset="utf-8" src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>                <div id="334ec9e6-6390-47e6-b165-f3e0187a5e91" class="plotly-graph-div" style="height:525px; width:100%;"></div>            <script type="text/javascript">                                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("334ec9e6-6390-47e6-b165-f3e0187a5e91")) {                    Plotly.newPlot(                        "334ec9e6-6390-47e6-b165-f3e0187a5e91",                        [{"alignmentgroup":"True","base":["1990-01-01T00:00:00","1990-01-01T00:00:00","2000-01-01T00:00:00","2000-01-01T00:00:00","2000-01-01T00:00:00","2000-01-01T00:00:00","2010-01-01T00:00:00","2010-01-01T00:00:00","2010-01-01T00:00:00","2007-01-01T00:00:00","2000-01-01T00:00:00","2002-01-01T00:00:00","2000-01-01T00:00:00","2000-01-01T00:00:00","1990-01-01T00:00:00"],"hovertemplate":"start=%{base}\u003cbr\u003eend=%{x}\u003cbr\u003eevent=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"","marker":{"color":"#0000FF","pattern":{"shape":""}},"name":"","offsetgroup":"","orientation":"h","showlegend":false,"textposition":"auto","x":[283996800000.0,283996800000.0,284083200000.0,284083200000.0,284083200000.0,284083200000.0,283996800000.0,283996800000.0,283996800000.0,63158400000.0,315619200000.0,662688000000.0,284083200000.0,284083200000.0,315532800000.0],"xaxis":"x","y":["HIV\u002fAIDS Prevention Campaign","Expansion of Childhood Vaccination","Access to Antiretroviral Drugs for HIV\u002fAIDS","Development of Malaria Vaccines","Use of Anticoagulants and Treatments for Cardiovascular Diseases","Use of Influenza Vaccines and Antiviral Medications","Anti-Smoking Campaigns","Improved Access to Cancer Treatments","Traffic Safety Campaigns","Development of HPV Vaccines","Access to Clean Drinking Water","Universal Health Coverage Scheme in Thailand","Reduction in Maternal and Infant Mortality Rates in Thailand","Decrease in Malaria Deaths in Thailand","Advances in Treatment and Prevention of Cardiovascular Diseases in Thailand"],"yaxis":"y","type":"bar"}],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"type":"date","range":["1990-01-01T00:00:00","2023-01-01T00:00:00"]},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"event"},"categoryorder":"total ascending","categoryarray":["HIV\u002fAIDS Prevention Campaign","Expansion of Childhood Vaccination","Access to Antiretroviral Drugs for HIV\u002fAIDS","Development of Malaria Vaccines","Use of Anticoagulants and Treatments for Cardiovascular Diseases","Use of Influenza Vaccines and Antiviral Medications","Anti-Smoking Campaigns","Improved Access to Cancer Treatments","Traffic Safety Campaigns","Development of HPV Vaccines","Access to Clean Drinking Water","Universal Health Coverage Scheme in Thailand","Reduction in Maternal and Infant Mortality Rates in Thailand","Decrease in Malaria Deaths in Thailand","Advances in Treatment and Prevention of Cardiovascular Diseases in Thailand"]},"legend":{"tracegroupgap":0},"title":{"text":"Timeline of Events Decreasing Mortality (1990-2023)"},"barmode":"overlay"},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('334ec9e6-6390-47e6-b165-f3e0187a5e91');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                            </script>        </div>
</body>
</html>


## Event for analyze

ในช่วงระยะเวลาที่ผ่านมา ประวัติศาสตร์โลกได้ผ่านพ้นเหตุการณ์ที่สำคัญมากมาย ซึ่งไม่เพียงแต่ส่งผลกระทบต่อชีวิตและความเป็นอยู่ของประชาชนในพื้นที่ที่เกิดเหตุการณ์เท่านั้น แต่ยังมีผลกระทบต่อสุขภาพของประชากรโลกในวงกว้าง โดยเฉพาะอย่างยิ่งเหตุการณ์ที่เกิดขึ้นระหว่างปี 1990-2010 เช่น การระบาดของโรค HIV/AIDS, การฆ่าล้างเผ่าพันธุ์ในรวันดา, และภัยพิบัติจากแผ่นดินไหวและสึนามิในเอเชีย

เหตุการณ์เหล่านี้ถูกเลือกเพื่อการวิเคราะห์เนื่องจากความสัมพันธ์ที่ชัดเจนกับอัตราการเสียชีวิต รวมถึงการดำเนินการแก้ไขปัญหาที่ส่งผลต่อการพัฒนาในด้านสุขภาพและคุณภาพชีวิตของประชาชน เช่น การเข้าถึงยาต้านไวรัส HIV/AIDS, การพัฒนาวัคซีนมาลาเรีย, และความพยายามในการจัดการน้ำดื่มที่สะอาด ซึ่งล้วนแต่มีผลกระทบที่สำคัญต่อการลดอัตราการเสียชีวิตจากโรคที่สามารถป้องกันได้

การเลือกเหตุการณ์เหล่านี้ช่วยให้เราเข้าใจถึงความซับซ้อนของการพัฒนาในด้านสุขภาพโลก และวิธีการที่เหตุการณ์แต่ละอย่างมีผลต่อกันในบริบทที่กว้างขึ้น โดยการวิเคราะห์ความสัมพันธ์ระหว่างเหตุการณ์เหล่านี้และการเปลี่ยนแปลงในอัตราการเสียชีวิต เราจะสามารถให้ข้อมูลเชิงลึกที่มีคุณค่าและเป็นประโยชน์ในการพัฒนานโยบายและกลยุทธ์เพื่อสุขภาพในอนาคต

**Events That Increased Mortality Rates**

1. **HIV/AIDS Pandemic (1990s - early 2000s)**  
   - Increased mortality globally, especially in Sub-Saharan Africa.  
   - [WHO HIV Statistics](https://www.who.int/health-topics/hiv-aids#tab=tab_1)
   
2. **Rwandan Genocide (1994)**  
   - Over 800,000 people were killed in just a few months due to ethnic violence.  
   - [UN Report on Rwanda](https://www.un.org/en/preventgenocide/rwanda)

2. **Asian Tsunami (2004)**  
   - Affected Southeast Asia, causing over 230,000 deaths.  
   - [NOAA Tsunami Report](https://www.noaa.gov/news/15-years-after-deadly-tsunami-world-better-prepared-for-disasters)

**Events That Decreased Mortality Rates**

1. **Access to Antiretroviral Drugs for HIV/AIDS** (2000-2009)
   - Widespread access to antiretroviral therapy (ART) greatly reduced the death rate from HIV/AIDS.  
   - [UNAIDS HIV Update](https://www.unaids.org/en/resources/fact-sheet)

2. **Development of Malaria Vaccines** (2000-2009)
   - Use of insecticide-treated bed nets and anti-malaria programs led to a significant decline.  
   - [WHO Malaria Report](https://www.who.int/news-room/fact-sheets/detail/malaria)

3. **Access to Clean Drinking Water** (2000-2010)
   - Global initiatives to provide clean water reduced mortality from waterborne diseases like cholera, dysentery, and diarrhea..  
   - [INDIA Water Portal](https://www.indiawaterportal.org/health-and-sanitation/sanitation/2010-unwater-global-annual-assessment-sanitation-and-drinkingwater-glaas)
   - [Our World in Data](https://ourworldindata.org/diarrheal-diseases)

###HIV


```python
# prompt: plot graph HIV by year for continent

# Assuming 'df_Main_data' is your DataFrame containing the HIV data
# and it has columns like 'Year', 'Continent', and 'HIV_Deaths'

# Group data by year and continent, summing HIV deaths
hiv_by_year_continent = df_Main_data.groupby(['Year', 'Continent'])['HIV'].sum().reset_index()

# Create the plot using Plotly Express
fig = px.line(hiv_by_year_continent, x='Year', y='HIV', color='Continent',
             title='HIV Deaths by Year and Continent')
fig.show()
```


<html>
<head><meta charset="utf-8" /></head>
<body>
    <div>            <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-AMS-MML_SVG"></script><script type="text/javascript">if (window.MathJax && window.MathJax.Hub && window.MathJax.Hub.Config) {window.MathJax.Hub.Config({SVG: {font: "STIX-Web"}});}</script>                <script type="text/javascript">window.PlotlyConfig = {MathJaxConfig: 'local'};</script>
        <script charset="utf-8" src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>                <div id="785c8e16-dbf2-49b1-a825-37747056e769" class="plotly-graph-div" style="height:525px; width:100%;"></div>            <script type="text/javascript">                                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("785c8e16-dbf2-49b1-a825-37747056e769")) {                    Plotly.newPlot(                        "785c8e16-dbf2-49b1-a825-37747056e769",                        [{"hovertemplate":"Continent=Africa\u003cbr\u003eYear=%{x}\u003cbr\u003eHIV=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Africa","line":{"color":"#636efa","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Africa","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[265848.0,344006.0,434744.0,536654.0,646951.0,762466.0,878671.0,993390.0,1105601.0,1209221.0,1300824.0,1377221.0,1438235.0,1482329.0,1500897.0,1479894.0,1417983.0,1328491.0,1228654.0,1139313.0,1066544.0,998164.0,926426.0,863016.0,815149.0,779299.0,753149.0,717505.0,670655.0,645654.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Continent=Americas\u003cbr\u003eYear=%{x}\u003cbr\u003eHIV=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Americas","line":{"color":"#EF553B","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Americas","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[46944.0,56442.0,66036.0,76109.0,86609.0,91895.0,82817.0,67462.0,63919.0,66977.0,67147.0,68112.0,68664.0,69152.0,68261.0,67092.0,65742.0,63878.0,62209.0,60477.0,59169.0,57917.0,56922.0,56794.0,56600.0,56100.0,55089.0,53659.0,52317.0,51301.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Continent=Asia\u003cbr\u003eYear=%{x}\u003cbr\u003eHIV=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Asia","line":{"color":"#00cc96","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Asia","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[7197.0,10783.0,16355.0,24672.0,35673.0,50347.0,67893.0,88904.0,113620.0,140426.0,167180.0,192617.0,214716.0,230910.0,247290.0,254663.0,253792.0,245590.0,236310.0,221311.0,206102.0,193757.0,181584.0,174662.0,166887.0,157825.0,149013.0,139749.0,134506.0,132427.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Continent=Europe\u003cbr\u003eYear=%{x}\u003cbr\u003eHIV=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Europe","line":{"color":"#ab63fa","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Europe","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[15621.0,18974.0,22363.0,26358.0,30242.0,33031.0,31437.0,23745.0,19720.0,22099.0,22853.0,22351.0,22320.0,23486.0,23583.0,27256.0,26990.0,27953.0,28915.0,28603.0,29100.0,30035.0,29892.0,27887.0,30554.0,32652.0,34948.0,32103.0,30827.0,29615.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Continent=Oceania\u003cbr\u003eYear=%{x}\u003cbr\u003eHIV=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Oceania","line":{"color":"#FFA15A","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Oceania","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[449.0,520.0,572.0,670.0,694.0,701.0,762.0,653.0,791.0,1054.0,1385.0,1763.0,2169.0,2568.0,2923.0,3169.0,3361.0,3394.0,3411.0,3554.0,3704.0,3846.0,3874.0,3837.0,3780.0,3791.0,3899.0,3990.0,4036.0,4059.0],"yaxis":"y","type":"scatter"}],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"Year"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"HIV"}},"legend":{"title":{"text":"Continent"},"tracegroupgap":0},"title":{"text":"HIV Deaths by Year and Continent"}},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('785c8e16-dbf2-49b1-a825-37747056e769');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                            </script>        </div>
</body>
</html>


HIV นั้นถูกค้นพบครั้งแรกในช่วงปี 1980s และแพร่ระบาดไปทั่วโลก โดยเฉพาะอย่างยิ่ง ในแถบแอฟริกาตอนใต้ จากเหตุการณ์ดังกล่าวพบว่ากราฟในช่วงปี 1990s-2000s มีการเสียชีวิตจากโรค HIV เพิ่มขึ้น โดยเฉพาะในแถบแอฟริกา จึงทำให้ในช่วงปี 2000 - 2009 ได้มีการรณรงค์ให้ความรู้เกี่ยวกับการใช้ถุงยางอนามัยและการตรวจสุขภาพเป็นประจำช่วยลดอัตราการเสียชีวิตจากโรค HIV/AIDS ในหลายประเทศ โดยเฉพาะอย่างยิ่งในแถบแอฟริกา ซึ่งสอดคล้องกับกราฟสถิติการตายของโรค HIV ดังด้านบน

###Rwanda Genocide


```python
# prompt: plot graph conflict_and_terrorism of rwanda by year

# Filter for Rwanda
df_rwanda = df_Main_data[df_Main_data['Code'] == 'RWA']

# Group by year and sum conflict and terrorism deaths
df_rwanda_conflict = df_rwanda.groupby('Year')['Conflict_and_Terrorism'].sum().reset_index()

# Plot the graph
fig = px.line(df_rwanda_conflict, x='Year', y='Conflict_and_Terrorism',
             title='Conflict and Terrorism Deaths in Rwanda by Year')
fig.show()
```


<html>
<head><meta charset="utf-8" /></head>
<body>
    <div>            <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-AMS-MML_SVG"></script><script type="text/javascript">if (window.MathJax && window.MathJax.Hub && window.MathJax.Hub.Config) {window.MathJax.Hub.Config({SVG: {font: "STIX-Web"}});}</script>                <script type="text/javascript">window.PlotlyConfig = {MathJaxConfig: 'local'};</script>
        <script charset="utf-8" src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>                <div id="e07ee336-890d-4366-8629-5878e80ea5cb" class="plotly-graph-div" style="height:525px; width:100%;"></div>            <script type="text/javascript">                                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("e07ee336-890d-4366-8629-5878e80ea5cb")) {                    Plotly.newPlot(                        "e07ee336-890d-4366-8629-5878e80ea5cb",                        [{"hovertemplate":"Year=%{x}\u003cbr\u003eConflict_and_Terrorism=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"","line":{"color":"#636efa","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"","orientation":"v","showlegend":false,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[2644.0,1102.0,1084.0,959.0,503532.0,4342.0,438.0,6357.0,2610.0,365.0,168.0,2047.0,5.0,503.0,16.0,5.0,13.0,18.0,9.0,1844.0,226.0,120.0,103.0,11.0,5.0,11.0,166.0,37.0,38.0,1.0],"yaxis":"y","type":"scatter"}],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"Year"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"Conflict_and_Terrorism"}},"legend":{"tracegroupgap":0},"title":{"text":"Conflict and Terrorism Deaths in Rwanda by Year"}},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('e07ee336-890d-4366-8629-5878e80ea5cb');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                            </script>        </div>
</body>
</html>


ในปี 1994 เกิดเหตุการณ์ฆ่าล้างเผ่าพันธุ์ซึ่งเกิดขึ้นจากความขัดแย้งทางชาติพันธุ์ระหว่างสองกลุ่มหลักในรวันดา เหตุการณ์นี้นำไปสู่การเสียชีวิตของประชาชนกว่า 800,000 คน ภายในระยะเวลาเพียง 100 วัน ส่งผลทำให้กราฟการเสียชีวิตจาก Conflict and Terrorism เพิ่มขึ้นอย่างมีนัยสำคัญในปี 1994 ดังกราฟข้างต้น

###Asian Tsunami


```python
# prompt: plot graph Exposure to forces of nature by year for asia

# Assuming 'df_Main_data' is your DataFrame containing the data
# and it has columns like 'Year', 'Continent', and 'Exposure_to_Forces_of_Nature'

# Filter for Asia
df_asia = df_Main_data[df_Main_data['Continent'] == 'Asia']

# Group data by year, summing Exposure_to_Forces_of_Nature
exposure_by_year_asia = df_asia.groupby(['Year'])['Exposure_to_Forces_of_Nature'].sum().reset_index()

# Create the plot using Plotly Express
fig = px.line(exposure_by_year_asia, x='Year', y='Exposure_to_Forces_of_Nature',
             title='Exposure to Forces of Nature by Year for Asia')
fig.show()
```


<html>
<head><meta charset="utf-8" /></head>
<body>
    <div>            <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-AMS-MML_SVG"></script><script type="text/javascript">if (window.MathJax && window.MathJax.Hub && window.MathJax.Hub.Config) {window.MathJax.Hub.Config({SVG: {font: "STIX-Web"}});}</script>                <script type="text/javascript">window.PlotlyConfig = {MathJaxConfig: 'local'};</script>
        <script charset="utf-8" src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>                <div id="c00aabf0-03b1-4ebf-bab7-77af6c066e51" class="plotly-graph-div" style="height:525px; width:100%;"></div>            <script type="text/javascript">                                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("c00aabf0-03b1-4ebf-bab7-77af6c066e51")) {                    Plotly.newPlot(                        "c00aabf0-03b1-4ebf-bab7-77af6c066e51",                        [{"hovertemplate":"Year=%{x}\u003cbr\u003eExposure_to_Forces_of_Nature=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"","line":{"color":"#636efa","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"","orientation":"v","showlegend":false,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[48703.0,154508.0,10512.0,18841.0,8555.0,16718.0,12909.0,12253.0,22706.0,35750.0,6120.0,25450.0,6210.0,31192.0,233615.0,82739.0,17302.0,12496.0,232471.0,8221.0,13673.0,26080.0,6577.0,24580.0,5629.0,13016.0,4865.0,5846.0,8956.0,3979.0],"yaxis":"y","type":"scatter"}],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"Year"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"Exposure_to_Forces_of_Nature"}},"legend":{"tracegroupgap":0},"title":{"text":"Exposure to Forces of Nature by Year for Asia"}},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('c00aabf0-03b1-4ebf-bab7-77af6c066e51');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                            </script>        </div>
</body>
</html>



```python
# prompt: plot graph Exposure to forces of nature top 10 country for year 2004

# Assuming df_Main_data is your DataFrame
df_2004 = df_Main_data[df_Main_data['Year'] == 2004]

# Sort by Exposure_to_Forces_of_Nature in descending order
top_10_2004 = df_2004.sort_values('Exposure_to_Forces_of_Nature', ascending=False).head(10)

# Create a bar plot
plt.figure(figsize=(12, 6))
plt.bar(top_10_2004['Country'], top_10_2004['Exposure_to_Forces_of_Nature'])
plt.xlabel('Country')
plt.ylabel('Exposure to Forces of Nature')
plt.title('Top 10 Countries with Highest Exposure to Forces of Nature in 2004')
plt.xticks(rotation=45, ha='right')
plt.tight_layout()
plt.show()
```


    
![png](Event_Analysis_files/Event_Analysis_89_0.png)
    


ในวันที่ 26 ธันวาคม 2004 เกิดแผ่นดินไหวขนาด 9.1-9.3 แมกนิจูด นอกชายฝั่งของเกาะสุมาตรา ประเทศอินโดนีเซีย ทำให้เกิดคลื่นสึนามิขนาดใหญ่ที่ซัดเข้าถล่มชายฝั่งของหลายประเทศรอบมหาสมุทรอินเดีย ส่งผลให้มีผู้เสียชีวิตจำนวนมาก และสร้างความเสียหายทางทรัพย์สินอย่างมหาศาล เห็นได้ดังกราฟข้างต้น

###Malaria


```python
# prompt: plot graph Malaria by year for continent

# Assuming df_Main_data is your DataFrame
# and it has columns like 'Year', 'Continent', and 'Malaria_Deaths'

# Group data by year and continent, summing Malaria deaths
malaria_by_year_continent = df_Main_data.groupby(['Year', 'Continent'])['Malaria'].sum().reset_index()

# Create the plot using Plotly Express
fig = px.line(malaria_by_year_continent, x='Year', y='Malaria', color='Continent',
             title='Malaria Deaths by Year and Continent')
fig.show()
```


<html>
<head><meta charset="utf-8" /></head>
<body>
    <div>            <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-AMS-MML_SVG"></script><script type="text/javascript">if (window.MathJax && window.MathJax.Hub && window.MathJax.Hub.Config) {window.MathJax.Hub.Config({SVG: {font: "STIX-Web"}});}</script>                <script type="text/javascript">window.PlotlyConfig = {MathJaxConfig: 'local'};</script>
        <script charset="utf-8" src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>                <div id="430eb25a-6c9f-4a11-8594-b889b7dfe9b7" class="plotly-graph-div" style="height:525px; width:100%;"></div>            <script type="text/javascript">                                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("430eb25a-6c9f-4a11-8594-b889b7dfe9b7")) {                    Plotly.newPlot(                        "430eb25a-6c9f-4a11-8594-b889b7dfe9b7",                        [{"hovertemplate":"Continent=Africa\u003cbr\u003eYear=%{x}\u003cbr\u003eMalaria=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Africa","line":{"color":"#636efa","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Africa","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[597606.0,616287.0,629688.0,648401.0,660776.0,678985.0,698525.0,718766.0,737166.0,754056.0,774814.0,804628.0,813477.0,843576.0,848292.0,837920.0,840016.0,840598.0,836269.0,825002.0,806967.0,767184.0,730914.0,699272.0,661671.0,637768.0,611259.0,584965.0,584779.0,596585.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Continent=Americas\u003cbr\u003eYear=%{x}\u003cbr\u003eMalaria=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Americas","line":{"color":"#EF553B","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Americas","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[7888.0,9679.0,9209.0,7741.0,7128.0,7426.0,5638.0,4757.0,6894.0,5384.0,5510.0,4299.0,3411.0,2746.0,2125.0,2461.0,2577.0,2216.0,1926.0,2314.0,2674.0,1596.0,1539.0,1341.0,945.0,966.0,1130.0,1115.0,1141.0,1340.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Continent=Asia\u003cbr\u003eYear=%{x}\u003cbr\u003eMalaria=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Asia","line":{"color":"#00cc96","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Asia","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[233940.0,232234.0,216760.0,205150.0,186732.0,175109.0,167370.0,168469.0,156435.0,133577.0,100620.0,102504.0,110933.0,111639.0,108397.0,98109.0,96873.0,95292.0,92286.0,87793.0,98147.0,98285.0,72361.0,49452.0,60201.0,63173.0,46465.0,42121.0,44606.0,44260.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Continent=Europe\u003cbr\u003eYear=%{x}\u003cbr\u003eMalaria=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Europe","line":{"color":"#ab63fa","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Europe","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0,0.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Continent=Oceania\u003cbr\u003eYear=%{x}\u003cbr\u003eMalaria=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Oceania","line":{"color":"#FFA15A","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Oceania","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[863.0,784.0,758.0,924.0,1035.0,1106.0,943.0,954.0,843.0,771.0,1111.0,1278.0,1374.0,1693.0,1970.0,2050.0,2280.0,2087.0,2429.0,2687.0,2026.0,1499.0,1369.0,1711.0,1507.0,983.0,1510.0,1452.0,1042.0,1016.0],"yaxis":"y","type":"scatter"}],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"Year"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"Malaria"}},"legend":{"title":{"text":"Continent"},"tracegroupgap":0},"title":{"text":"Malaria Deaths by Year and Continent"}},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('430eb25a-6c9f-4a11-8594-b889b7dfe9b7');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                            </script>        </div>
</body>
</html>


โรคมาลาเรียเป็นหนึ่งในโรคติดเชื้อที่ร้ายแรงที่สุดในโลก โดยเฉพาะในภูมิภาคเขตร้อนและกึ่งเขตร้อน ซึ่งแพร่เชื้อสู่มนุษย์ผ่านการกัดของยุงก้นปล่อง ช่วงปี 2000 - 2009 เป็นช่วงเวลาที่มีความก้าวหน้าอย่างมากในการพัฒนาวัคซีนมาลาเรีย แม้จะยังไม่สามารถป้องกันโรคได้อย่างสมบูรณ์ แต่การวิจัยและการทดสอบวัคซีน ก็ถือเป็นก้าวสำคัญที่ช่วยให้เกิดการพัฒนาในอนาคต เห็นได้จากกราฟข้างต้น ที่มีการลดลงของการเสียชีวิตของโรค Malaria ภายหลังช่วงปี 2009 เป็นต้นไป

###Diarrheal


```python
# prompt: plot graph Diarrheal diseases by year for continent

# Assuming df_Main_data is your DataFrame
# and it has columns like 'Year', 'Continent', and 'Diarrheal_diseases_Deaths'

# Group data by year and continent, summing Diarrheal diseases deaths
diarrheal_by_year_continent = df_Main_data.groupby(['Year', 'Continent'])['Diarrheal_Diseases'].sum().reset_index()

# Create the plot using Plotly Express
fig = px.line(diarrheal_by_year_continent, x='Year', y='Diarrheal_Diseases', color='Continent',
             title='Diarrheal diseases Deaths by Year and Continent')
fig.show()
```


<html>
<head><meta charset="utf-8" /></head>
<body>
    <div>            <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-AMS-MML_SVG"></script><script type="text/javascript">if (window.MathJax && window.MathJax.Hub && window.MathJax.Hub.Config) {window.MathJax.Hub.Config({SVG: {font: "STIX-Web"}});}</script>                <script type="text/javascript">window.PlotlyConfig = {MathJaxConfig: 'local'};</script>
        <script charset="utf-8" src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>                <div id="f7fb7b03-93a1-48a6-9e10-dc039dc62ce2" class="plotly-graph-div" style="height:525px; width:100%;"></div>            <script type="text/javascript">                                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("f7fb7b03-93a1-48a6-9e10-dc039dc62ce2")) {                    Plotly.newPlot(                        "f7fb7b03-93a1-48a6-9e10-dc039dc62ce2",                        [{"hovertemplate":"Continent=Africa\u003cbr\u003eYear=%{x}\u003cbr\u003eDiarrheal_Diseases=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Africa","line":{"color":"#636efa","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Africa","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[1017532.0,1035701.0,1021925.0,1015838.0,1034168.0,1022889.0,1023213.0,1017601.0,1013139.0,1001471.0,985544.0,968918.0,946408.0,919645.0,894703.0,876171.0,873856.0,857814.0,836394.0,819142.0,794961.0,769964.0,745952.0,728524.0,712259.0,693412.0,680434.0,670237.0,636071.0,610398.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Continent=Americas\u003cbr\u003eYear=%{x}\u003cbr\u003eDiarrheal_Diseases=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Americas","line":{"color":"#EF553B","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Americas","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[126421.0,120641.0,111323.0,104209.0,96345.0,88422.0,80934.0,74305.0,69170.0,63847.0,59455.0,56509.0,54721.0,53664.0,51989.0,50771.0,49162.0,47799.0,46844.0,45767.0,46098.0,49654.0,43654.0,43789.0,43002.0,42698.0,42894.0,41976.0,42055.0,42313.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Continent=Asia\u003cbr\u003eYear=%{x}\u003cbr\u003eDiarrheal_Diseases=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Asia","line":{"color":"#00cc96","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Asia","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[1742532.0,1738310.0,1730048.0,1669809.0,1600838.0,1553158.0,1502494.0,1478475.0,1453332.0,1422243.0,1385664.0,1342639.0,1300388.0,1257662.0,1207160.0,1185297.0,1171571.0,1155001.0,1145052.0,1095200.0,1070114.0,1065567.0,1027067.0,997304.0,951813.0,923761.0,897296.0,901084.0,881096.0,862418.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Continent=Europe\u003cbr\u003eYear=%{x}\u003cbr\u003eDiarrheal_Diseases=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Europe","line":{"color":"#ab63fa","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Europe","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[5483.0,5402.0,5457.0,5704.0,5900.0,5734.0,5583.0,5540.0,5735.0,6117.0,6574.0,7032.0,7686.0,8516.0,9087.0,10007.0,10899.0,11823.0,12539.0,13039.0,13421.0,13535.0,14053.0,14433.0,14600.0,15198.0,15234.0,14864.0,14763.0,14725.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Continent=Oceania\u003cbr\u003eYear=%{x}\u003cbr\u003eDiarrheal_Diseases=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Oceania","line":{"color":"#FFA15A","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Oceania","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[2989.0,3031.0,3056.0,3055.0,3048.0,3060.0,3089.0,3106.0,3209.0,3279.0,3333.0,3367.0,3438.0,3474.0,3557.0,3715.0,3851.0,3920.0,3940.0,4100.0,4110.0,4042.0,4043.0,4031.0,4019.0,3974.0,3968.0,4022.0,3968.0,3923.0],"yaxis":"y","type":"scatter"}],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"Year"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"Diarrheal_Diseases"}},"legend":{"title":{"text":"Continent"},"tracegroupgap":0},"title":{"text":"Diarrheal diseases Deaths by Year and Continent"}},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('f7fb7b03-93a1-48a6-9e10-dc039dc62ce2');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                            </script>        </div>
</body>
</html>



```python
# prompt: plot line graph top 5 country in Asia by year for Diarrheal Diseases

# Assuming df_Main_data is your DataFrame
# and it has columns like 'Year', 'Country', and 'Diarrheal_Diseases'

# Filter for Asia
df_asia = df_Main_data[df_Main_data['Continent'] == 'Asia']

# Group data by year and country, summing Diarrheal diseases deaths
diarrheal_by_year_country_asia = df_asia.groupby(['Year', 'Country'])['Diarrheal_Diseases'].sum().reset_index()

# Find top 5 countries in Asia by total Diarrheal diseases deaths across all years
top_5_countries = diarrheal_by_year_country_asia.groupby('Country')['Diarrheal_Diseases'].sum().nlargest(5).index.tolist()

# Filter data for the top 5 countries
df_top_5 = diarrheal_by_year_country_asia[diarrheal_by_year_country_asia['Country'].isin(top_5_countries)]

# Create the plot using Plotly Express
fig = px.line(df_top_5, x='Year', y='Diarrheal_Diseases', color='Country',
             title='Top 5 Countries in Asia by Diarrheal Diseases Deaths (1990-2019)')
fig.show()
```


<html>
<head><meta charset="utf-8" /></head>
<body>
    <div>            <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-AMS-MML_SVG"></script><script type="text/javascript">if (window.MathJax && window.MathJax.Hub && window.MathJax.Hub.Config) {window.MathJax.Hub.Config({SVG: {font: "STIX-Web"}});}</script>                <script type="text/javascript">window.PlotlyConfig = {MathJaxConfig: 'local'};</script>
        <script charset="utf-8" src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>                <div id="b2d80ccc-d93d-46fc-b149-46935e46360f" class="plotly-graph-div" style="height:525px; width:100%;"></div>            <script type="text/javascript">                                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("b2d80ccc-d93d-46fc-b149-46935e46360f")) {                    Plotly.newPlot(                        "b2d80ccc-d93d-46fc-b149-46935e46360f",                        [{"hovertemplate":"Country=Bangladesh\u003cbr\u003eYear=%{x}\u003cbr\u003eDiarrheal_Diseases=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Bangladesh","line":{"color":"#636efa","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Bangladesh","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[114670.0,110115.0,102810.0,96556.0,89424.0,82577.0,74608.0,67320.0,61254.0,56314.0,52596.0,48730.0,46072.0,43132.0,40571.0,38978.0,37507.0,35610.0,33338.0,32312.0,31548.0,30285.0,29560.0,30075.0,30824.0,31321.0,32195.0,33537.0,33110.0,32927.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Country=China\u003cbr\u003eYear=%{x}\u003cbr\u003eDiarrheal_Diseases=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"China","line":{"color":"#EF553B","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"China","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[93302.0,87548.0,79015.0,71456.0,65172.0,58142.0,52455.0,46586.0,41994.0,37415.0,33220.0,29084.0,25318.0,22164.0,19279.0,16432.0,13769.0,11643.0,10058.0,8901.0,7891.0,7198.0,6779.0,6452.0,6131.0,6078.0,6243.0,6050.0,5618.0,5440.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Country=India\u003cbr\u003eYear=%{x}\u003cbr\u003eDiarrheal_Diseases=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"India","line":{"color":"#00cc96","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"India","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[1081098.0,1100375.0,1119477.0,1081215.0,1036372.0,1015476.0,994967.0,997437.0,994597.0,984335.0,969230.0,948163.0,923203.0,896411.0,862040.0,854406.0,853721.0,849219.0,845116.0,802659.0,787963.0,791919.0,761001.0,738243.0,697780.0,674059.0,650963.0,654727.0,645030.0,632345.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Country=Indonesia\u003cbr\u003eYear=%{x}\u003cbr\u003eDiarrheal_Diseases=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Indonesia","line":{"color":"#ab63fa","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Indonesia","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[133685.0,126918.0,121095.0,115849.0,111085.0,106166.0,101048.0,96922.0,94441.0,91996.0,90092.0,89040.0,88060.0,86467.0,84928.0,83441.0,81466.0,79695.0,77723.0,75605.0,72855.0,70271.0,68494.0,66978.0,65593.0,64578.0,63106.0,62584.0,60886.0,59589.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Country=Pakistan\u003cbr\u003eYear=%{x}\u003cbr\u003eDiarrheal_Diseases=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Pakistan","line":{"color":"#FFA15A","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Pakistan","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[133214.0,131305.0,130725.0,131228.0,130701.0,128251.0,125230.0,123043.0,120460.0,117595.0,113732.0,109718.0,107011.0,104517.0,101923.0,98429.0,96699.0,94786.0,98703.0,99408.0,97611.0,96761.0,95625.0,92577.0,90732.0,88656.0,86393.0,85201.0,80264.0,77024.0],"yaxis":"y","type":"scatter"}],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"Year"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"Diarrheal_Diseases"}},"legend":{"title":{"text":"Country"},"tracegroupgap":0},"title":{"text":"Top 5 Countries in Asia by Diarrheal Diseases Deaths (1990-2019)"}},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('b2d80ccc-d93d-46fc-b149-46935e46360f');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                            </script>        </div>
</body>
</html>



```python
# prompt: plot line graph top 5 country in Africa by year for Diarrheal Diseases

# Assuming df_Main_data is your DataFrame
# and it has columns like 'Year', 'Country', and 'Diarrheal_Diseases'

# Filter for Africa
df_africa = df_Main_data[df_Main_data['Continent'] == 'Africa']

# Group data by year and country, summing Diarrheal diseases deaths
diarrheal_by_year_country_africa = df_africa.groupby(['Year', 'Country'])['Diarrheal_Diseases'].sum().reset_index()

# Find top 5 countries in Africa by total Diarrheal diseases deaths across all years
top_5_countries = diarrheal_by_year_country_africa.groupby('Country')['Diarrheal_Diseases'].sum().nlargest(5).index.tolist()

# Filter data for the top 5 countries
df_top_5 = diarrheal_by_year_country_africa[diarrheal_by_year_country_africa['Country'].isin(top_5_countries)]

# Create the plot using Plotly Express
fig = px.line(df_top_5, x='Year', y='Diarrheal_Diseases', color='Country',
             title='Top 5 Countries in Africa by Diarrheal Diseases Deaths (1990-2019)')
fig.show()
```


<html>
<head><meta charset="utf-8" /></head>
<body>
    <div>            <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-AMS-MML_SVG"></script><script type="text/javascript">if (window.MathJax && window.MathJax.Hub && window.MathJax.Hub.Config) {window.MathJax.Hub.Config({SVG: {font: "STIX-Web"}});}</script>                <script type="text/javascript">window.PlotlyConfig = {MathJaxConfig: 'local'};</script>
        <script charset="utf-8" src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>                <div id="42aa1fe0-e120-4f7e-afb1-d8b447ac373b" class="plotly-graph-div" style="height:525px; width:100%;"></div>            <script type="text/javascript">                                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("42aa1fe0-e120-4f7e-afb1-d8b447ac373b")) {                    Plotly.newPlot(                        "42aa1fe0-e120-4f7e-afb1-d8b447ac373b",                        [{"hovertemplate":"Country=Angola\u003cbr\u003eYear=%{x}\u003cbr\u003eDiarrheal_Diseases=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Angola","line":{"color":"#636efa","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Angola","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[35849.0,36176.0,36301.0,36931.0,38031.0,38567.0,37603.0,36872.0,36356.0,35307.0,34141.0,32011.0,29837.0,27656.0,26567.0,24854.0,25475.0,23500.0,22463.0,21581.0,21148.0,20827.0,20245.0,19421.0,18053.0,17058.0,15703.0,15071.0,13608.0,12936.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Country=Democratic Republic of Congo\u003cbr\u003eYear=%{x}\u003cbr\u003eDiarrheal_Diseases=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Democratic Republic of Congo","line":{"color":"#EF553B","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Democratic Republic of Congo","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[36694.0,38475.0,40073.0,42429.0,49447.0,48718.0,54091.0,59696.0,66843.0,69794.0,72918.0,72545.0,71648.0,71494.0,69282.0,68753.0,68691.0,69116.0,68640.0,68197.0,66246.0,63898.0,60708.0,56518.0,52751.0,48720.0,45007.0,41081.0,37209.0,34003.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Country=Ethiopia\u003cbr\u003eYear=%{x}\u003cbr\u003eDiarrheal_Diseases=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Ethiopia","line":{"color":"#00cc96","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Ethiopia","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[110201.0,113036.0,114992.0,115972.0,118202.0,119343.0,117673.0,115039.0,110457.0,106409.0,102300.0,97308.0,91998.0,85874.0,79435.0,75835.0,72648.0,70063.0,67239.0,64467.0,61050.0,60392.0,58455.0,56649.0,57555.0,56335.0,55289.0,55938.0,53665.0,50773.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Country=Niger\u003cbr\u003eYear=%{x}\u003cbr\u003eDiarrheal_Diseases=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Niger","line":{"color":"#ab63fa","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Niger","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[36074.0,36801.0,37344.0,37904.0,38157.0,38557.0,38202.0,38100.0,37875.0,38040.0,37949.0,37911.0,37527.0,37146.0,35561.0,37520.0,36468.0,34486.0,31812.0,30289.0,28084.0,27747.0,27141.0,28274.0,28893.0,29194.0,30036.0,30771.0,29377.0,28694.0],"yaxis":"y","type":"scatter"},{"hovertemplate":"Country=Nigeria\u003cbr\u003eYear=%{x}\u003cbr\u003eDiarrheal_Diseases=%{y}\u003cextra\u003e\u003c\u002fextra\u003e","legendgroup":"Nigeria","line":{"color":"#FFA15A","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"Nigeria","orientation":"v","showlegend":true,"x":[1990,1991,1992,1993,1994,1995,1996,1997,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017,2018,2019],"xaxis":"x","y":[284419.0,297403.0,281303.0,276528.0,273916.0,271658.0,274988.0,272445.0,272459.0,273760.0,273848.0,272987.0,268973.0,262567.0,256236.0,248877.0,254013.0,253568.0,246594.0,243669.0,240708.0,228309.0,221382.0,215679.0,210178.0,203706.0,200794.0,198476.0,188747.0,181138.0],"yaxis":"y","type":"scatter"}],                        {"template":{"data":{"histogram2dcontour":[{"type":"histogram2dcontour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"choropleth":[{"type":"choropleth","colorbar":{"outlinewidth":0,"ticks":""}}],"histogram2d":[{"type":"histogram2d","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmap":[{"type":"heatmap","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"heatmapgl":[{"type":"heatmapgl","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"contourcarpet":[{"type":"contourcarpet","colorbar":{"outlinewidth":0,"ticks":""}}],"contour":[{"type":"contour","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"surface":[{"type":"surface","colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]}],"mesh3d":[{"type":"mesh3d","colorbar":{"outlinewidth":0,"ticks":""}}],"scatter":[{"fillpattern":{"fillmode":"overlay","size":10,"solidity":0.2},"type":"scatter"}],"parcoords":[{"type":"parcoords","line":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolargl":[{"type":"scatterpolargl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"scattergeo":[{"type":"scattergeo","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterpolar":[{"type":"scatterpolar","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"scattergl":[{"type":"scattergl","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatter3d":[{"type":"scatter3d","line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattermapbox":[{"type":"scattermapbox","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scatterternary":[{"type":"scatterternary","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"scattercarpet":[{"type":"scattercarpet","marker":{"colorbar":{"outlinewidth":0,"ticks":""}}}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"pie":[{"automargin":true,"type":"pie"}]},"layout":{"autotypenumbers":"strict","colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"hovermode":"closest","hoverlabel":{"align":"left"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"bgcolor":"#E5ECF6","angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"ternary":{"bgcolor":"#E5ECF6","aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]]},"xaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"yaxis":{"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","automargin":true,"zerolinewidth":2},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white","gridwidth":2}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"geo":{"bgcolor":"white","landcolor":"#E5ECF6","subunitcolor":"white","showland":true,"showlakes":true,"lakecolor":"white"},"title":{"x":0.05},"mapbox":{"style":"light"}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"Year"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"Diarrheal_Diseases"}},"legend":{"title":{"text":"Country"},"tracegroupgap":0},"title":{"text":"Top 5 Countries in Africa by Diarrheal Diseases Deaths (1990-2019)"}},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('42aa1fe0-e120-4f7e-afb1-d8b447ac373b');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                            </script>        </div>
</body>
</html>


โรคท้องร่วงเป็นหนึ่งในสาเหตุสำคัญของการเสียชีวิตของประชากรโลก เนื่องจากการขาดความเข้าถึงของน้ำสะอาดและการมีสุขาภิบาลที่ดี ในช่วงปี 2000-2010 จึงมีการริเริ่มโครงการระดับโลกที่มุ่งเน้นการเพิ่มการเข้าถึงน้ำดื่มที่สะอาดเพื่อลดการเสียชีวิตจากโรคที่เกี่ยวกับน้ำ ส่งผลให้การเสียชีวิตจากโรคท้องร่วงลดลงอย่างมีนัยสำคัญ ซึ่งเห็นได้ดังกราฟข้างต้น

##Summary

**สรุปภาพรวมการวิเคราะห์ข้อมูลการเสียชีวิตทั่วโลก (1990-2019)**

จากข้อมูลที่นำเสนอในช่วงปี 1990-2019 จะเห็นว่าอัตราการเสียชีวิตและเหตุการณ์ต่าง ๆ มีความเกี่ยวข้องกันและดำเนินไปในทิศทางเดียวกัน ซึ่งช่วยให้เราเข้าใจถึงสาเหตุที่ทำให้จำนวนผู้เสียชีวิตเพิ่มขึ้นในบางช่วงเวลาและลดลงในช่วงอื่น ๆ ตัวอย่างเช่น การเข้าถึงน้ำดื่มสะอาดได้มีส่วนสำคัญในการลดอัตราการเสียชีวิตจากโรคที่เกิดจากน้ำอย่างเช่น อหิวาตกโรคและอุจจาระร่วง

นอกจากนี้ การพัฒนาวัคซีนในการรักษาโรคมาลาเรียในหลายประเทศก็มีผลอย่างมากต่อการลดอัตราการเสียชีวิตในกลุ่มเด็กและประชากรที่อาศัยอยู่ในพื้นที่ที่มีการแพร่ระบาดของโรคนี้ การระบาดของโรคที่เกิดจากน้ำและมาลาเรียนั้นสามารถควบคุมได้มากขึ้นด้วยการใช้วิธีการที่มีประสิทธิภาพ

ในทางกลับกัน เหตุการณ์ทางธรรมชาติ เช่น แผ่นดินไหวและสึนามิในปี 2004 ทำให้จำนวนผู้เสียชีวิตเพิ่มขึ้นอย่างรวดเร็วในบางพื้นที่ ซึ่งเป็นการเตือนให้เห็นถึงความสำคัญของการเตรียมความพร้อมและระบบการป้องกันภัยพิบัติ

การวิเคราะห์ข้อมูลเหล่านี้ไม่เพียงแค่แสดงให้เห็นถึงความสัมพันธ์ระหว่างอัตราการเสียชีวิตและเหตุการณ์ต่าง ๆ แต่ยังสามารถนำไปประยุกต์ใช้เพื่อป้องกันและแก้ไขปัญหาที่อาจเกิดขึ้นในอนาคตได้อย่างมีประสิทธิภาพ โดยการพัฒนานโยบายและกลยุทธ์ที่มุ่งเน้นการลดความเสี่ยงและการป้องกันการเกิดโรคในประชากรที่เปราะบาง
