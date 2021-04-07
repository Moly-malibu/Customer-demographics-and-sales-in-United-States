
#  Customer demographics and sales in United States

# ADD - Architectural Decisions 

The cicle to analysis and to take decisions we will supporte be CRISP-DN: 

                        Business Understanding 
                        
                        Data Understanding 
                        
                        Data Preparation 
                        
                        Modeling
                        
                        Evaluation
                        
                        Deployment

## BUSINESS UNDERSTANDING:

This project will start from the assumption that the company will launch a new product, so it must carry out the market segmentation study in order to determine which will be the market niche? where it will offer the product? what characteristics the target market and consumers must meet? objective, so a database was selected that shows the demographic composition and sales, and what are these customers consume on a daily basis? and finally, the company will determine the actions to take supported by the analysis of the Data Scientist and its algorithms.


```python

import os, types
import pandas as pd
from botocore.client import Config
import ibm_boto3

def __iter__(self): return 0

# @hidden_cell
# The following code accesses a file in your IBM Cloud Object Storage. It includes your credentials.
# You might want to remove those credentials before you share the notebook.

if os.environ.get('RUNTIME_ENV_LOCATION_TYPE') == 'external':
    endpoint_ed5a7e0f2a8a492f8001ec525a7957cd = 'https://s3-api.us-geo.objectstorage.softlayer.net'
else:
    endpoint_ed5a7e0f2a8a492f8001ec525a7957cd = 'https://s3-api.us-geo.objectstorage.service.networklayer.com'

client_ed5a7e0f2a8a492f8001ec525a7957cd = ibm_boto3.client(service_name='s3',
    ibm_api_key_id='dsoVjIx8W61Wp_BA7Zrj1icRfSl3EpjBekCK5S3amH-4',
    ibm_auth_endpoint="https://iam.cloud.ibm.com/oidc/token",
    config=Config(signature_version='oauth'),
    endpoint_url=endpoint_ed5a7e0f2a8a492f8001ec525a7957cd)

body = client_ed5a7e0f2a8a492f8001ec525a7957cd.get_object(Bucket='starpython-donotdelete-pr-dmfouols9cjvn8',Key='Customer demographics and sales.csv')['Body']
# add missing __iter__ method, so pandas accepts body as file-like object
if not hasattr(body, "__iter__"): body.__iter__ = types.MethodType( __iter__, body )

df = pd.read_csv(body)
df.head()
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
      <th>CUSTNAME</th>
      <th>GenderCode</th>
      <th>ADDRESS1</th>
      <th>CITY</th>
      <th>STATE</th>
      <th>COUNTRY_CODE</th>
      <th>POSTAL_CODE</th>
      <th>POSTAL_CODE_PLUS4</th>
      <th>ADDRESS2</th>
      <th>EMAIL_ADDRESS</th>
      <th>...</th>
      <th>Cleaning Products</th>
      <th>Condiments</th>
      <th>Frozen Foods</th>
      <th>Kitchen Items</th>
      <th>Meat</th>
      <th>Office Supplies</th>
      <th>Personal Care</th>
      <th>Pet Supplies</th>
      <th>Sea Food</th>
      <th>Spices</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Allen Perl</td>
      <td>Mr.</td>
      <td>4707    Hillcrest Lane</td>
      <td>Abeto</td>
      <td>PG</td>
      <td>IT</td>
      <td>6040</td>
      <td>0</td>
      <td>NaN</td>
      <td>Allen.M.Perl@spambob.com</td>
      <td>...</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Allen Perl</td>
      <td>Mr.</td>
      <td>4707    Hillcrest Lane</td>
      <td>Abeto</td>
      <td>PG</td>
      <td>IT</td>
      <td>6040</td>
      <td>0</td>
      <td>NaN</td>
      <td>Allen.M.Perl@spambob.com</td>
      <td>...</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Allen Perl</td>
      <td>Mr.</td>
      <td>4707    Hillcrest Lane</td>
      <td>Abeto</td>
      <td>PG</td>
      <td>IT</td>
      <td>6040</td>
      <td>0</td>
      <td>NaN</td>
      <td>Allen.M.Perl@spambob.com</td>
      <td>...</td>
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
    </tr>
    <tr>
      <th>3</th>
      <td>Allen Perl</td>
      <td>Mr.</td>
      <td>4707    Hillcrest Lane</td>
      <td>Abeto</td>
      <td>PG</td>
      <td>IT</td>
      <td>6040</td>
      <td>0</td>
      <td>NaN</td>
      <td>Allen.M.Perl@spambob.com</td>
      <td>...</td>
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
    </tr>
    <tr>
      <th>4</th>
      <td>Allen Perl</td>
      <td>Mr.</td>
      <td>4707    Hillcrest Lane</td>
      <td>Abeto</td>
      <td>PG</td>
      <td>IT</td>
      <td>6040</td>
      <td>0</td>
      <td>NaN</td>
      <td>Allen.M.Perl@spambob.com</td>
      <td>...</td>
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
    </tr>
  </tbody>
</table>
<p>5 rows × 62 columns</p>
</div>



# Data Understanding and Preparing


```python
#cleaning data unnecesary columns.

df = df.drop(columns=['ADDRESS1', 'CITY', 'COUNTRY_CODE', 'POSTAL_CODE', 'POSTAL_CODE_PLUS4', 
                      'ADDRESS2', 'EMAIL_ADDRESS', 'PHONE_NUMBER', 'LOCALITY', 'DRIVER_LICENSE', 
                      'NATIONAL_ID', 'ORDER_DATE', 'ORDER_TIME', 'NATIONALITY', 'SALESMAN_ID',
                      'CUST_ID', 'ORDER_ID', 'FREIGHT_CHARGES', 'ORDER_SALESMAN', 'ORDER_POSTED_DATE', 'ORDER_SHIP_DATE', 'AGE',
                       'ORDER_VALUE', 'T_TYPE', 'PURCHASE_STATUS', 'CUSTNAME', 'CREDITCARD_NUMBER'])
```


```python
df.head()
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
      <th>GenderCode</th>
      <th>STATE</th>
      <th>CREDITCARD_TYPE</th>
      <th>PURCHASE_TOUCHPOINT</th>
      <th>ORDER_TYPE</th>
      <th>GENERATION</th>
      <th>Baby Food</th>
      <th>Diapers</th>
      <th>Formula</th>
      <th>Lotion</th>
      <th>...</th>
      <th>Cleaning Products</th>
      <th>Condiments</th>
      <th>Frozen Foods</th>
      <th>Kitchen Items</th>
      <th>Meat</th>
      <th>Office Supplies</th>
      <th>Personal Care</th>
      <th>Pet Supplies</th>
      <th>Sea Food</th>
      <th>Spices</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Mr.</td>
      <td>PG</td>
      <td>Master Card</td>
      <td>Phone</td>
      <td>MediumValue</td>
      <td>Gen_Y</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>...</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Mr.</td>
      <td>PG</td>
      <td>Master Card</td>
      <td>Phone</td>
      <td>MediumValue</td>
      <td>Gen_Y</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>...</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Mr.</td>
      <td>PG</td>
      <td>Master Card</td>
      <td>Desktop</td>
      <td>LowValue</td>
      <td>Gen_Y</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
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
    </tr>
    <tr>
      <th>3</th>
      <td>Mr.</td>
      <td>PG</td>
      <td>Master Card</td>
      <td>Phone</td>
      <td>LowValue</td>
      <td>Gen_Y</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>...</td>
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
    </tr>
    <tr>
      <th>4</th>
      <td>Mr.</td>
      <td>PG</td>
      <td>Master Card</td>
      <td>Phone</td>
      <td>LowValue</td>
      <td>Gen_Y</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
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
    </tr>
  </tbody>
</table>
<p>5 rows × 35 columns</p>
</div>



## Data set Description:

The data set Customer demographics and sales has 13.733 rows and 62 columns, but after cleanned data set has 36 row:


```python
print('Rows and Colums:', df.shape)
```

    Rows and Colums: (13733, 35)



```python
df['STATE'] = df['STATE'].fillna(0) #fill Columns with out date
```


```python
df.isna().sum() 
```




    GenderCode             0
    STATE                  0
    CREDITCARD_TYPE        0
    PURCHASE_TOUCHPOINT    0
    ORDER_TYPE             0
    GENERATION             0
    Baby Food              0
    Diapers                0
    Formula                0
    Lotion                 0
    Baby wash              0
    Wipes                  0
    Fresh Fruits           0
    Fresh Vegetables       0
    Beer                   0
    Wine                   0
    Club Soda              0
    Sports Drink           0
    Chips                  0
    Popcorn                0
    Oatmeal                0
    Medicines              0
    Canned Foods           0
    Cigarettes             0
    Cheese                 0
    Cleaning Products      0
    Condiments             0
    Frozen Foods           0
    Kitchen Items          0
    Meat                   0
    Office Supplies        0
    Personal Care          0
    Pet Supplies           0
    Sea Food               0
    Spices                 0
    dtype: int64




```python
def count(df, spark):
    c=df.count()
    return c
```


```python
count(df, spark) #see the elements in string
```




    GenderCode             13733
    STATE                  13733
    CREDITCARD_TYPE        13733
    PURCHASE_TOUCHPOINT    13733
    ORDER_TYPE             13733
    GENERATION             13733
    Baby Food              13733
    Diapers                13733
    Formula                13733
    Lotion                 13733
    Baby wash              13733
    Wipes                  13733
    Fresh Fruits           13733
    Fresh Vegetables       13733
    Beer                   13733
    Wine                   13733
    Club Soda              13733
    Sports Drink           13733
    Chips                  13733
    Popcorn                13733
    Oatmeal                13733
    Medicines              13733
    Canned Foods           13733
    Cigarettes             13733
    Cheese                 13733
    Cleaning Products      13733
    Condiments             13733
    Frozen Foods           13733
    Kitchen Items          13733
    Meat                   13733
    Office Supplies        13733
    Personal Care          13733
    Pet Supplies           13733
    Sea Food               13733
    Spices                 13733
    dtype: int64




```python
def getNumberOfFields(df, spark):
    c=len(df.columns)
    return c
```


```python
getNumberOfFields(df, spark) #see number of columns in data set
```




    35




```python
def getFieldName(df, spark):
    c=df.columns
    return c
```


```python
print(getFieldName(df, spark)) #Name columns
```

    Index(['GenderCode', 'STATE', 'CREDITCARD_TYPE', 'PURCHASE_TOUCHPOINT',
           'ORDER_TYPE', 'GENERATION', 'Baby Food', 'Diapers', 'Formula', 'Lotion',
           'Baby wash', 'Wipes', 'Fresh Fruits', 'Fresh Vegetables', 'Beer',
           'Wine', 'Club Soda', 'Sports Drink', 'Chips', 'Popcorn', 'Oatmeal',
           'Medicines', 'Canned Foods', 'Cigarettes', 'Cheese',
           'Cleaning Products', 'Condiments', 'Frozen Foods', 'Kitchen Items',
           'Meat', 'Office Supplies', 'Personal Care', 'Pet Supplies', 'Sea Food',
           'Spices'],
          dtype='object')


## Data set Statistic:


```python
df.describe()
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
      <th>Baby Food</th>
      <th>Diapers</th>
      <th>Formula</th>
      <th>Lotion</th>
      <th>Baby wash</th>
      <th>Wipes</th>
      <th>Fresh Fruits</th>
      <th>Fresh Vegetables</th>
      <th>Beer</th>
      <th>Wine</th>
      <th>...</th>
      <th>Cleaning Products</th>
      <th>Condiments</th>
      <th>Frozen Foods</th>
      <th>Kitchen Items</th>
      <th>Meat</th>
      <th>Office Supplies</th>
      <th>Personal Care</th>
      <th>Pet Supplies</th>
      <th>Sea Food</th>
      <th>Spices</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>...</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>0.053375</td>
      <td>0.101289</td>
      <td>0.056142</td>
      <td>0.050681</td>
      <td>0.053594</td>
      <td>0.052647</td>
      <td>0.054977</td>
      <td>0.055487</td>
      <td>0.054540</td>
      <td>0.219835</td>
      <td>...</td>
      <td>0.101362</td>
      <td>0.260176</td>
      <td>0.137698</td>
      <td>0.056797</td>
      <td>0.055196</td>
      <td>0.053739</td>
      <td>0.146072</td>
      <td>0.052501</td>
      <td>0.139809</td>
      <td>0.189835</td>
    </tr>
    <tr>
      <th>std</th>
      <td>0.224788</td>
      <td>0.301722</td>
      <td>0.230204</td>
      <td>0.219353</td>
      <td>0.225222</td>
      <td>0.223336</td>
      <td>0.227944</td>
      <td>0.228936</td>
      <td>0.227089</td>
      <td>0.414150</td>
      <td>...</td>
      <td>0.301818</td>
      <td>0.438747</td>
      <td>0.344595</td>
      <td>0.231464</td>
      <td>0.228370</td>
      <td>0.225510</td>
      <td>0.353191</td>
      <td>0.223044</td>
      <td>0.346802</td>
      <td>0.392185</td>
    </tr>
    <tr>
      <th>min</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>...</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 29 columns</p>
</div>




```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
plt.style.use('ggplot')
%matplotlib inline
import matplotlib
matplotlib.rcParams['figure.figsize'] = (40,5)
import warnings 
warnings.filterwarnings('ignore')
```


```python
df[df.columns[6:-1]].boxplot();
```


![png](output_22_0.png)


## Correlation:

The correlation help to measure linear relationship between two quantitative variables, positive correlation is cause when the variables move in same direction, while negative correlation the variance increases as the other decreases and vice versa. if we analysis the products wine with fresh vegetable the correlation is negative -0.022. the customer buy more win decrease to buy fresh vegetables.


```python
df.corr(method='pearson') #Correlation by products.
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
      <th>Baby Food</th>
      <th>Diapers</th>
      <th>Formula</th>
      <th>Lotion</th>
      <th>Baby wash</th>
      <th>Wipes</th>
      <th>Fresh Fruits</th>
      <th>Fresh Vegetables</th>
      <th>Beer</th>
      <th>Wine</th>
      <th>...</th>
      <th>Cleaning Products</th>
      <th>Condiments</th>
      <th>Frozen Foods</th>
      <th>Kitchen Items</th>
      <th>Meat</th>
      <th>Office Supplies</th>
      <th>Personal Care</th>
      <th>Pet Supplies</th>
      <th>Sea Food</th>
      <th>Spices</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Baby Food</th>
      <td>1.000000</td>
      <td>0.091002</td>
      <td>0.064520</td>
      <td>0.051471</td>
      <td>0.088773</td>
      <td>0.047012</td>
      <td>0.046477</td>
      <td>0.061312</td>
      <td>0.062801</td>
      <td>-0.008714</td>
      <td>...</td>
      <td>0.110236</td>
      <td>-0.036704</td>
      <td>-0.000876</td>
      <td>0.083092</td>
      <td>0.051837</td>
      <td>0.054028</td>
      <td>-0.000982</td>
      <td>0.069016</td>
      <td>-0.033143</td>
      <td>0.018876</td>
    </tr>
    <tr>
      <th>Diapers</th>
      <td>0.091002</td>
      <td>1.000000</td>
      <td>0.081680</td>
      <td>0.078676</td>
      <td>0.090501</td>
      <td>0.075398</td>
      <td>0.096913</td>
      <td>0.110505</td>
      <td>0.715428</td>
      <td>-0.026686</td>
      <td>...</td>
      <td>0.113559</td>
      <td>-0.029103</td>
      <td>-0.013684</td>
      <td>0.083414</td>
      <td>0.099581</td>
      <td>0.096590</td>
      <td>-0.005594</td>
      <td>0.074634</td>
      <td>-0.052527</td>
      <td>0.046119</td>
    </tr>
    <tr>
      <th>Formula</th>
      <td>0.064520</td>
      <td>0.081680</td>
      <td>1.000000</td>
      <td>0.056136</td>
      <td>0.081014</td>
      <td>0.051571</td>
      <td>0.054974</td>
      <td>0.062484</td>
      <td>0.048685</td>
      <td>-0.014889</td>
      <td>...</td>
      <td>0.079499</td>
      <td>-0.022060</td>
      <td>0.006275</td>
      <td>0.063154</td>
      <td>0.068490</td>
      <td>0.084962</td>
      <td>-0.013991</td>
      <td>0.063144</td>
      <td>-0.034473</td>
      <td>0.023906</td>
    </tr>
    <tr>
      <th>Lotion</th>
      <td>0.051471</td>
      <td>0.078676</td>
      <td>0.056136</td>
      <td>1.000000</td>
      <td>0.067362</td>
      <td>0.076343</td>
      <td>0.078264</td>
      <td>0.049857</td>
      <td>0.052688</td>
      <td>-0.014433</td>
      <td>...</td>
      <td>0.102794</td>
      <td>-0.014439</td>
      <td>-0.014295</td>
      <td>0.062347</td>
      <td>0.050276</td>
      <td>0.059766</td>
      <td>-0.016605</td>
      <td>0.072129</td>
      <td>-0.040500</td>
      <td>0.020210</td>
    </tr>
    <tr>
      <th>Baby wash</th>
      <td>0.088773</td>
      <td>0.090501</td>
      <td>0.081014</td>
      <td>0.067362</td>
      <td>1.000000</td>
      <td>0.052484</td>
      <td>0.070268</td>
      <td>0.058135</td>
      <td>0.065295</td>
      <td>-0.015457</td>
      <td>...</td>
      <td>0.089344</td>
      <td>-0.014363</td>
      <td>0.002491</td>
      <td>0.070121</td>
      <td>0.058582</td>
      <td>0.072332</td>
      <td>-0.013282</td>
      <td>0.051259</td>
      <td>-0.027877</td>
      <td>0.025790</td>
    </tr>
    <tr>
      <th>Wipes</th>
      <td>0.047012</td>
      <td>0.075398</td>
      <td>0.051571</td>
      <td>0.076343</td>
      <td>0.052484</td>
      <td>1.000000</td>
      <td>0.081897</td>
      <td>0.059653</td>
      <td>0.052506</td>
      <td>-0.026722</td>
      <td>...</td>
      <td>0.064513</td>
      <td>-0.008255</td>
      <td>-0.008095</td>
      <td>0.067528</td>
      <td>0.060102</td>
      <td>0.052265</td>
      <td>-0.019027</td>
      <td>0.051227</td>
      <td>-0.036746</td>
      <td>0.032217</td>
    </tr>
    <tr>
      <th>Fresh Fruits</th>
      <td>0.046477</td>
      <td>0.096913</td>
      <td>0.054974</td>
      <td>0.078264</td>
      <td>0.070268</td>
      <td>0.081897</td>
      <td>1.000000</td>
      <td>0.055969</td>
      <td>0.068685</td>
      <td>-0.014638</td>
      <td>...</td>
      <td>0.113760</td>
      <td>-0.008325</td>
      <td>0.001890</td>
      <td>0.060893</td>
      <td>0.064809</td>
      <td>0.051605</td>
      <td>-0.000257</td>
      <td>0.083594</td>
      <td>-0.043809</td>
      <td>0.029876</td>
    </tr>
    <tr>
      <th>Fresh Vegetables</th>
      <td>0.061312</td>
      <td>0.110505</td>
      <td>0.062484</td>
      <td>0.049857</td>
      <td>0.058135</td>
      <td>0.059653</td>
      <td>0.055969</td>
      <td>1.000000</td>
      <td>0.084661</td>
      <td>-0.022669</td>
      <td>...</td>
      <td>0.083009</td>
      <td>-0.024834</td>
      <td>-0.009162</td>
      <td>0.032598</td>
      <td>0.055633</td>
      <td>0.049440</td>
      <td>-0.006580</td>
      <td>0.078429</td>
      <td>-0.033510</td>
      <td>0.031913</td>
    </tr>
    <tr>
      <th>Beer</th>
      <td>0.062801</td>
      <td>0.715428</td>
      <td>0.048685</td>
      <td>0.052688</td>
      <td>0.065295</td>
      <td>0.052506</td>
      <td>0.068685</td>
      <td>0.084661</td>
      <td>1.000000</td>
      <td>-0.019866</td>
      <td>...</td>
      <td>0.077647</td>
      <td>-0.026219</td>
      <td>-0.012224</td>
      <td>0.051897</td>
      <td>0.069731</td>
      <td>0.066478</td>
      <td>-0.011265</td>
      <td>0.054169</td>
      <td>-0.039499</td>
      <td>0.031737</td>
    </tr>
    <tr>
      <th>Wine</th>
      <td>-0.008714</td>
      <td>-0.026686</td>
      <td>-0.014889</td>
      <td>-0.014433</td>
      <td>-0.015457</td>
      <td>-0.026722</td>
      <td>-0.014638</td>
      <td>-0.022669</td>
      <td>-0.019866</td>
      <td>1.000000</td>
      <td>...</td>
      <td>-0.028553</td>
      <td>-0.208990</td>
      <td>0.461432</td>
      <td>-0.023148</td>
      <td>-0.015888</td>
      <td>-0.025137</td>
      <td>0.502336</td>
      <td>-0.023257</td>
      <td>0.759477</td>
      <td>0.412433</td>
    </tr>
    <tr>
      <th>Club Soda</th>
      <td>-0.153122</td>
      <td>-0.222118</td>
      <td>-0.154897</td>
      <td>-0.146809</td>
      <td>-0.145717</td>
      <td>-0.154093</td>
      <td>-0.165901</td>
      <td>-0.166365</td>
      <td>-0.171478</td>
      <td>-0.436769</td>
      <td>...</td>
      <td>-0.225196</td>
      <td>0.270144</td>
      <td>-0.328798</td>
      <td>-0.157025</td>
      <td>-0.181326</td>
      <td>-0.150011</td>
      <td>-0.340305</td>
      <td>-0.169062</td>
      <td>-0.331716</td>
      <td>-0.388070</td>
    </tr>
    <tr>
      <th>Sports Drink</th>
      <td>0.068742</td>
      <td>0.084626</td>
      <td>0.055911</td>
      <td>0.058888</td>
      <td>0.083940</td>
      <td>0.068551</td>
      <td>0.064692</td>
      <td>0.041601</td>
      <td>0.061191</td>
      <td>-0.022204</td>
      <td>...</td>
      <td>0.066590</td>
      <td>-0.017776</td>
      <td>-0.012496</td>
      <td>0.081082</td>
      <td>0.062945</td>
      <td>0.072371</td>
      <td>0.001923</td>
      <td>0.043080</td>
      <td>-0.056160</td>
      <td>0.034872</td>
    </tr>
    <tr>
      <th>Chips</th>
      <td>-0.133778</td>
      <td>-0.196960</td>
      <td>-0.136838</td>
      <td>-0.131524</td>
      <td>-0.129842</td>
      <td>-0.135472</td>
      <td>-0.141323</td>
      <td>-0.141416</td>
      <td>-0.148444</td>
      <td>-0.335923</td>
      <td>...</td>
      <td>-0.197050</td>
      <td>0.419934</td>
      <td>-0.252882</td>
      <td>-0.137885</td>
      <td>-0.152956</td>
      <td>-0.133657</td>
      <td>-0.261732</td>
      <td>-0.143906</td>
      <td>-0.255126</td>
      <td>-0.306327</td>
    </tr>
    <tr>
      <th>Popcorn</th>
      <td>-0.114745</td>
      <td>-0.159796</td>
      <td>-0.115222</td>
      <td>-0.112973</td>
      <td>-0.109337</td>
      <td>-0.103266</td>
      <td>-0.121069</td>
      <td>-0.109112</td>
      <td>-0.119620</td>
      <td>-0.327790</td>
      <td>...</td>
      <td>-0.160434</td>
      <td>0.264593</td>
      <td>-0.246759</td>
      <td>-0.108602</td>
      <td>-0.124287</td>
      <td>-0.115374</td>
      <td>-0.255395</td>
      <td>-0.122717</td>
      <td>-0.248949</td>
      <td>-0.284373</td>
    </tr>
    <tr>
      <th>Oatmeal</th>
      <td>0.063455</td>
      <td>0.107358</td>
      <td>0.072803</td>
      <td>0.066572</td>
      <td>0.060282</td>
      <td>0.067499</td>
      <td>0.074769</td>
      <td>0.076672</td>
      <td>0.075519</td>
      <td>-0.026656</td>
      <td>...</td>
      <td>0.081015</td>
      <td>-0.013591</td>
      <td>-0.020924</td>
      <td>0.085410</td>
      <td>0.060519</td>
      <td>0.068480</td>
      <td>-0.028878</td>
      <td>0.073430</td>
      <td>-0.026843</td>
      <td>0.013905</td>
    </tr>
    <tr>
      <th>Medicines</th>
      <td>0.008634</td>
      <td>-0.013891</td>
      <td>0.000844</td>
      <td>0.003289</td>
      <td>-0.008538</td>
      <td>0.003432</td>
      <td>0.000156</td>
      <td>-0.019068</td>
      <td>-0.000914</td>
      <td>0.483587</td>
      <td>...</td>
      <td>-0.019543</td>
      <td>-0.146693</td>
      <td>0.335353</td>
      <td>-0.014803</td>
      <td>-0.002986</td>
      <td>-0.013438</td>
      <td>0.336622</td>
      <td>-0.018869</td>
      <td>0.350719</td>
      <td>0.263979</td>
    </tr>
    <tr>
      <th>Canned Foods</th>
      <td>-0.103344</td>
      <td>-0.149661</td>
      <td>-0.101523</td>
      <td>-0.097792</td>
      <td>-0.095649</td>
      <td>-0.100988</td>
      <td>-0.092117</td>
      <td>-0.104732</td>
      <td>-0.117487</td>
      <td>-0.331489</td>
      <td>...</td>
      <td>-0.155390</td>
      <td>0.592457</td>
      <td>-0.242988</td>
      <td>-0.102338</td>
      <td>-0.128312</td>
      <td>-0.094627</td>
      <td>-0.250169</td>
      <td>-0.112370</td>
      <td>-0.259554</td>
      <td>-0.282232</td>
    </tr>
    <tr>
      <th>Cigarettes</th>
      <td>0.024856</td>
      <td>0.046302</td>
      <td>0.033984</td>
      <td>0.027071</td>
      <td>0.028501</td>
      <td>0.032444</td>
      <td>0.045798</td>
      <td>0.025725</td>
      <td>0.037819</td>
      <td>0.395234</td>
      <td>...</td>
      <td>0.025700</td>
      <td>-0.144976</td>
      <td>0.267735</td>
      <td>0.034064</td>
      <td>0.506041</td>
      <td>0.027326</td>
      <td>0.290184</td>
      <td>0.010971</td>
      <td>0.256104</td>
      <td>0.506903</td>
    </tr>
    <tr>
      <th>Cheese</th>
      <td>0.003846</td>
      <td>-0.013506</td>
      <td>-0.015704</td>
      <td>-0.006477</td>
      <td>-0.009636</td>
      <td>0.002353</td>
      <td>-0.010113</td>
      <td>-0.013722</td>
      <td>-0.012158</td>
      <td>0.476395</td>
      <td>...</td>
      <td>-0.002441</td>
      <td>-0.140892</td>
      <td>0.337873</td>
      <td>-0.011300</td>
      <td>-0.004026</td>
      <td>0.003185</td>
      <td>0.342769</td>
      <td>-0.012481</td>
      <td>0.339953</td>
      <td>0.286928</td>
    </tr>
    <tr>
      <th>Cleaning Products</th>
      <td>0.110236</td>
      <td>0.113559</td>
      <td>0.079499</td>
      <td>0.102794</td>
      <td>0.089344</td>
      <td>0.064513</td>
      <td>0.113760</td>
      <td>0.083009</td>
      <td>0.077647</td>
      <td>-0.028553</td>
      <td>...</td>
      <td>1.000000</td>
      <td>-0.025388</td>
      <td>-0.006774</td>
      <td>0.094794</td>
      <td>0.088926</td>
      <td>0.078313</td>
      <td>-0.002276</td>
      <td>0.700892</td>
      <td>-0.059564</td>
      <td>0.040451</td>
    </tr>
    <tr>
      <th>Condiments</th>
      <td>-0.036704</td>
      <td>-0.029103</td>
      <td>-0.022060</td>
      <td>-0.014439</td>
      <td>-0.014363</td>
      <td>-0.008255</td>
      <td>-0.008325</td>
      <td>-0.024834</td>
      <td>-0.026219</td>
      <td>-0.208990</td>
      <td>...</td>
      <td>-0.025388</td>
      <td>1.000000</td>
      <td>-0.143532</td>
      <td>-0.015731</td>
      <td>-0.036495</td>
      <td>-0.022088</td>
      <td>-0.152220</td>
      <td>-0.020529</td>
      <td>-0.178296</td>
      <td>-0.145281</td>
    </tr>
    <tr>
      <th>Frozen Foods</th>
      <td>-0.000876</td>
      <td>-0.013684</td>
      <td>0.006275</td>
      <td>-0.014295</td>
      <td>0.002491</td>
      <td>-0.008095</td>
      <td>0.001890</td>
      <td>-0.009162</td>
      <td>-0.012224</td>
      <td>0.461432</td>
      <td>...</td>
      <td>-0.006774</td>
      <td>-0.143532</td>
      <td>1.000000</td>
      <td>-0.019542</td>
      <td>-0.004974</td>
      <td>-0.003393</td>
      <td>0.354085</td>
      <td>-0.004055</td>
      <td>0.319685</td>
      <td>0.281830</td>
    </tr>
    <tr>
      <th>Kitchen Items</th>
      <td>0.083092</td>
      <td>0.083414</td>
      <td>0.063154</td>
      <td>0.062347</td>
      <td>0.070121</td>
      <td>0.067528</td>
      <td>0.060893</td>
      <td>0.032598</td>
      <td>0.051897</td>
      <td>-0.023148</td>
      <td>...</td>
      <td>0.094794</td>
      <td>-0.015731</td>
      <td>-0.019542</td>
      <td>1.000000</td>
      <td>0.077077</td>
      <td>0.079639</td>
      <td>-0.005288</td>
      <td>0.077650</td>
      <td>-0.041778</td>
      <td>0.032834</td>
    </tr>
    <tr>
      <th>Meat</th>
      <td>0.051837</td>
      <td>0.099581</td>
      <td>0.068490</td>
      <td>0.050276</td>
      <td>0.058582</td>
      <td>0.060102</td>
      <td>0.064809</td>
      <td>0.055633</td>
      <td>0.069731</td>
      <td>-0.015888</td>
      <td>...</td>
      <td>0.088926</td>
      <td>-0.036495</td>
      <td>-0.004974</td>
      <td>0.077077</td>
      <td>1.000000</td>
      <td>0.076734</td>
      <td>-0.004263</td>
      <td>0.061768</td>
      <td>-0.037676</td>
      <td>0.499321</td>
    </tr>
    <tr>
      <th>Office Supplies</th>
      <td>0.054028</td>
      <td>0.096590</td>
      <td>0.084962</td>
      <td>0.059766</td>
      <td>0.072332</td>
      <td>0.052265</td>
      <td>0.051605</td>
      <td>0.049440</td>
      <td>0.066478</td>
      <td>-0.025137</td>
      <td>...</td>
      <td>0.078313</td>
      <td>-0.022088</td>
      <td>-0.003393</td>
      <td>0.079639</td>
      <td>0.076734</td>
      <td>1.000000</td>
      <td>-0.017190</td>
      <td>0.071310</td>
      <td>-0.037413</td>
      <td>0.031208</td>
    </tr>
    <tr>
      <th>Personal Care</th>
      <td>-0.000982</td>
      <td>-0.005594</td>
      <td>-0.013991</td>
      <td>-0.016605</td>
      <td>-0.013282</td>
      <td>-0.019027</td>
      <td>-0.000257</td>
      <td>-0.006580</td>
      <td>-0.011265</td>
      <td>0.502336</td>
      <td>...</td>
      <td>-0.002276</td>
      <td>-0.152220</td>
      <td>0.354085</td>
      <td>-0.005288</td>
      <td>-0.004263</td>
      <td>-0.017190</td>
      <td>1.000000</td>
      <td>-0.002142</td>
      <td>0.356448</td>
      <td>0.290832</td>
    </tr>
    <tr>
      <th>Pet Supplies</th>
      <td>0.069016</td>
      <td>0.074634</td>
      <td>0.063144</td>
      <td>0.072129</td>
      <td>0.051259</td>
      <td>0.051227</td>
      <td>0.083594</td>
      <td>0.078429</td>
      <td>0.054169</td>
      <td>-0.023257</td>
      <td>...</td>
      <td>0.700892</td>
      <td>-0.020529</td>
      <td>-0.004055</td>
      <td>0.077650</td>
      <td>0.061768</td>
      <td>0.071310</td>
      <td>-0.002142</td>
      <td>1.000000</td>
      <td>-0.038413</td>
      <td>0.023418</td>
    </tr>
    <tr>
      <th>Sea Food</th>
      <td>-0.033143</td>
      <td>-0.052527</td>
      <td>-0.034473</td>
      <td>-0.040500</td>
      <td>-0.027877</td>
      <td>-0.036746</td>
      <td>-0.043809</td>
      <td>-0.033510</td>
      <td>-0.039499</td>
      <td>0.759477</td>
      <td>...</td>
      <td>-0.059564</td>
      <td>-0.178296</td>
      <td>0.319685</td>
      <td>-0.041778</td>
      <td>-0.037676</td>
      <td>-0.037413</td>
      <td>0.356448</td>
      <td>-0.038413</td>
      <td>1.000000</td>
      <td>0.278695</td>
    </tr>
    <tr>
      <th>Spices</th>
      <td>0.018876</td>
      <td>0.046119</td>
      <td>0.023906</td>
      <td>0.020210</td>
      <td>0.025790</td>
      <td>0.032217</td>
      <td>0.029876</td>
      <td>0.031913</td>
      <td>0.031737</td>
      <td>0.412433</td>
      <td>...</td>
      <td>0.040451</td>
      <td>-0.145281</td>
      <td>0.281830</td>
      <td>0.032834</td>
      <td>0.499321</td>
      <td>0.031208</td>
      <td>0.290832</td>
      <td>0.023418</td>
      <td>0.278695</td>
      <td>1.000000</td>
    </tr>
  </tbody>
</table>
<p>29 rows × 29 columns</p>
</div>




```python
corr_matrix = df.corr()
sns.heatmap(corr_matrix)
```




    <matplotlib.axes._subplots.AxesSubplot at 0x7f767c1dd410>




![png](output_26_1.png)


## Covariance:

Large covariance mean a strong relationship between variable, positive covariance mean that the product return move together and the move inverse if the negative covariance. Example the beer with fresh vegetables the return is minimun 0.004401.

### The formula is:

Cov(X,Y) = Σ E((X-μ)E(Y-ν)) / n-1 where:

X is a random variable

E(X) = μ is the expected value (the mean) of the random variable X and

E(Y) = ν is the expected value (the mean) of the random variable Y

n = the number of items in the data set


```python
df.cov() #Covariance by products
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
      <th>Baby Food</th>
      <th>Diapers</th>
      <th>Formula</th>
      <th>Lotion</th>
      <th>Baby wash</th>
      <th>Wipes</th>
      <th>Fresh Fruits</th>
      <th>Fresh Vegetables</th>
      <th>Beer</th>
      <th>Wine</th>
      <th>...</th>
      <th>Cleaning Products</th>
      <th>Condiments</th>
      <th>Frozen Foods</th>
      <th>Kitchen Items</th>
      <th>Meat</th>
      <th>Office Supplies</th>
      <th>Personal Care</th>
      <th>Pet Supplies</th>
      <th>Sea Food</th>
      <th>Spices</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Baby Food</th>
      <td>0.050530</td>
      <td>0.006172</td>
      <td>0.003339</td>
      <td>0.002538</td>
      <td>0.004494</td>
      <td>0.002360</td>
      <td>0.002381</td>
      <td>0.003155</td>
      <td>0.003206</td>
      <td>-0.000811</td>
      <td>...</td>
      <td>0.007479</td>
      <td>-0.003620</td>
      <td>-0.000068</td>
      <td>0.004323</td>
      <td>0.002661</td>
      <td>0.002739</td>
      <td>-0.000078</td>
      <td>0.003460</td>
      <td>-0.002584</td>
      <td>0.001664</td>
    </tr>
    <tr>
      <th>Diapers</th>
      <td>0.006172</td>
      <td>0.091036</td>
      <td>0.005673</td>
      <td>0.005207</td>
      <td>0.006150</td>
      <td>0.005081</td>
      <td>0.006665</td>
      <td>0.007633</td>
      <td>0.049019</td>
      <td>-0.003335</td>
      <td>...</td>
      <td>0.010341</td>
      <td>-0.003853</td>
      <td>-0.001423</td>
      <td>0.005825</td>
      <td>0.006862</td>
      <td>0.006572</td>
      <td>-0.000596</td>
      <td>0.005023</td>
      <td>-0.005496</td>
      <td>0.005457</td>
    </tr>
    <tr>
      <th>Formula</th>
      <td>0.003339</td>
      <td>0.005673</td>
      <td>0.052994</td>
      <td>0.002835</td>
      <td>0.004200</td>
      <td>0.002651</td>
      <td>0.002885</td>
      <td>0.003293</td>
      <td>0.002545</td>
      <td>-0.001420</td>
      <td>...</td>
      <td>0.005524</td>
      <td>-0.002228</td>
      <td>0.000498</td>
      <td>0.003365</td>
      <td>0.003601</td>
      <td>0.004411</td>
      <td>-0.001138</td>
      <td>0.003242</td>
      <td>-0.002752</td>
      <td>0.002158</td>
    </tr>
    <tr>
      <th>Lotion</th>
      <td>0.002538</td>
      <td>0.005207</td>
      <td>0.002835</td>
      <td>0.048116</td>
      <td>0.003328</td>
      <td>0.003740</td>
      <td>0.003913</td>
      <td>0.002504</td>
      <td>0.002625</td>
      <td>-0.001311</td>
      <td>...</td>
      <td>0.006805</td>
      <td>-0.001390</td>
      <td>-0.001081</td>
      <td>0.003166</td>
      <td>0.002518</td>
      <td>0.002956</td>
      <td>-0.001286</td>
      <td>0.003529</td>
      <td>-0.003081</td>
      <td>0.001739</td>
    </tr>
    <tr>
      <th>Baby wash</th>
      <td>0.004494</td>
      <td>0.006150</td>
      <td>0.004200</td>
      <td>0.003328</td>
      <td>0.050725</td>
      <td>0.002640</td>
      <td>0.003607</td>
      <td>0.002998</td>
      <td>0.003340</td>
      <td>-0.001442</td>
      <td>...</td>
      <td>0.006073</td>
      <td>-0.001419</td>
      <td>0.000193</td>
      <td>0.003655</td>
      <td>0.003013</td>
      <td>0.003674</td>
      <td>-0.001057</td>
      <td>0.002575</td>
      <td>-0.002177</td>
      <td>0.002278</td>
    </tr>
    <tr>
      <th>Wipes</th>
      <td>0.002360</td>
      <td>0.005081</td>
      <td>0.002651</td>
      <td>0.003740</td>
      <td>0.002640</td>
      <td>0.049879</td>
      <td>0.004169</td>
      <td>0.003050</td>
      <td>0.002663</td>
      <td>-0.002472</td>
      <td>...</td>
      <td>0.004349</td>
      <td>-0.000809</td>
      <td>-0.000623</td>
      <td>0.003491</td>
      <td>0.003065</td>
      <td>0.002632</td>
      <td>-0.001501</td>
      <td>0.002552</td>
      <td>-0.002846</td>
      <td>0.002822</td>
    </tr>
    <tr>
      <th>Fresh Fruits</th>
      <td>0.002381</td>
      <td>0.006665</td>
      <td>0.002885</td>
      <td>0.003913</td>
      <td>0.003607</td>
      <td>0.004169</td>
      <td>0.051958</td>
      <td>0.002921</td>
      <td>0.003555</td>
      <td>-0.001382</td>
      <td>...</td>
      <td>0.007826</td>
      <td>-0.000833</td>
      <td>0.000148</td>
      <td>0.003213</td>
      <td>0.003374</td>
      <td>0.002653</td>
      <td>-0.000021</td>
      <td>0.004250</td>
      <td>-0.003463</td>
      <td>0.002671</td>
    </tr>
    <tr>
      <th>Fresh Vegetables</th>
      <td>0.003155</td>
      <td>0.007633</td>
      <td>0.003293</td>
      <td>0.002504</td>
      <td>0.002998</td>
      <td>0.003050</td>
      <td>0.002921</td>
      <td>0.052412</td>
      <td>0.004401</td>
      <td>-0.002149</td>
      <td>...</td>
      <td>0.005736</td>
      <td>-0.002494</td>
      <td>-0.000723</td>
      <td>0.001727</td>
      <td>0.002909</td>
      <td>0.002552</td>
      <td>-0.000532</td>
      <td>0.004005</td>
      <td>-0.002661</td>
      <td>0.002865</td>
    </tr>
    <tr>
      <th>Beer</th>
      <td>0.003206</td>
      <td>0.049019</td>
      <td>0.002545</td>
      <td>0.002625</td>
      <td>0.003340</td>
      <td>0.002663</td>
      <td>0.003555</td>
      <td>0.004401</td>
      <td>0.051569</td>
      <td>-0.001868</td>
      <td>...</td>
      <td>0.005322</td>
      <td>-0.002612</td>
      <td>-0.000957</td>
      <td>0.002728</td>
      <td>0.003616</td>
      <td>0.003404</td>
      <td>-0.000904</td>
      <td>0.002744</td>
      <td>-0.003111</td>
      <td>0.002827</td>
    </tr>
    <tr>
      <th>Wine</th>
      <td>-0.000811</td>
      <td>-0.003335</td>
      <td>-0.001420</td>
      <td>-0.001311</td>
      <td>-0.001442</td>
      <td>-0.002472</td>
      <td>-0.001382</td>
      <td>-0.002149</td>
      <td>-0.001868</td>
      <td>0.171520</td>
      <td>...</td>
      <td>-0.003569</td>
      <td>-0.037975</td>
      <td>0.065853</td>
      <td>-0.002219</td>
      <td>-0.001503</td>
      <td>-0.002348</td>
      <td>0.073479</td>
      <td>-0.002148</td>
      <td>0.109082</td>
      <td>0.066989</td>
    </tr>
    <tr>
      <th>Club Soda</th>
      <td>-0.016888</td>
      <td>-0.032883</td>
      <td>-0.017496</td>
      <td>-0.015801</td>
      <td>-0.016103</td>
      <td>-0.016886</td>
      <td>-0.018555</td>
      <td>-0.018688</td>
      <td>-0.019107</td>
      <td>-0.088754</td>
      <td>...</td>
      <td>-0.033349</td>
      <td>0.058155</td>
      <td>-0.055592</td>
      <td>-0.017833</td>
      <td>-0.020318</td>
      <td>-0.016598</td>
      <td>-0.058973</td>
      <td>-0.018502</td>
      <td>-0.056445</td>
      <td>-0.074675</td>
    </tr>
    <tr>
      <th>Sports Drink</th>
      <td>0.003531</td>
      <td>0.005835</td>
      <td>0.002941</td>
      <td>0.002952</td>
      <td>0.004320</td>
      <td>0.003498</td>
      <td>0.003370</td>
      <td>0.002176</td>
      <td>0.003175</td>
      <td>-0.002101</td>
      <td>...</td>
      <td>0.004593</td>
      <td>-0.001782</td>
      <td>-0.000984</td>
      <td>0.004289</td>
      <td>0.003285</td>
      <td>0.003729</td>
      <td>0.000155</td>
      <td>0.002196</td>
      <td>-0.004451</td>
      <td>0.003125</td>
    </tr>
    <tr>
      <th>Chips</th>
      <td>-0.013589</td>
      <td>-0.026854</td>
      <td>-0.014235</td>
      <td>-0.013037</td>
      <td>-0.013215</td>
      <td>-0.013672</td>
      <td>-0.014557</td>
      <td>-0.014630</td>
      <td>-0.015233</td>
      <td>-0.062867</td>
      <td>...</td>
      <td>-0.026875</td>
      <td>0.083257</td>
      <td>-0.039378</td>
      <td>-0.014422</td>
      <td>-0.015785</td>
      <td>-0.013620</td>
      <td>-0.041773</td>
      <td>-0.014504</td>
      <td>-0.039982</td>
      <td>-0.054288</td>
    </tr>
    <tr>
      <th>Popcorn</th>
      <td>-0.011531</td>
      <td>-0.021554</td>
      <td>-0.011858</td>
      <td>-0.011079</td>
      <td>-0.011009</td>
      <td>-0.010311</td>
      <td>-0.012337</td>
      <td>-0.011167</td>
      <td>-0.012144</td>
      <td>-0.060690</td>
      <td>...</td>
      <td>-0.021647</td>
      <td>0.051899</td>
      <td>-0.038014</td>
      <td>-0.011238</td>
      <td>-0.012689</td>
      <td>-0.011632</td>
      <td>-0.040326</td>
      <td>-0.012237</td>
      <td>-0.038597</td>
      <td>-0.049859</td>
    </tr>
    <tr>
      <th>Oatmeal</th>
      <td>0.003278</td>
      <td>0.007443</td>
      <td>0.003851</td>
      <td>0.003355</td>
      <td>0.003120</td>
      <td>0.003464</td>
      <td>0.003916</td>
      <td>0.004033</td>
      <td>0.003941</td>
      <td>-0.002537</td>
      <td>...</td>
      <td>0.005619</td>
      <td>-0.001370</td>
      <td>-0.001657</td>
      <td>0.004543</td>
      <td>0.003176</td>
      <td>0.003549</td>
      <td>-0.002344</td>
      <td>0.003763</td>
      <td>-0.002139</td>
      <td>0.001253</td>
    </tr>
    <tr>
      <th>Medicines</th>
      <td>0.000674</td>
      <td>-0.001455</td>
      <td>0.000067</td>
      <td>0.000250</td>
      <td>-0.000668</td>
      <td>0.000266</td>
      <td>0.000012</td>
      <td>-0.001516</td>
      <td>-0.000072</td>
      <td>0.069532</td>
      <td>...</td>
      <td>-0.002048</td>
      <td>-0.022345</td>
      <td>0.040120</td>
      <td>-0.001190</td>
      <td>-0.000237</td>
      <td>-0.001052</td>
      <td>0.041277</td>
      <td>-0.001461</td>
      <td>0.042227</td>
      <td>0.035943</td>
    </tr>
    <tr>
      <th>Canned Foods</th>
      <td>-0.011004</td>
      <td>-0.021389</td>
      <td>-0.011070</td>
      <td>-0.010161</td>
      <td>-0.010204</td>
      <td>-0.010683</td>
      <td>-0.009946</td>
      <td>-0.011357</td>
      <td>-0.012638</td>
      <td>-0.065029</td>
      <td>...</td>
      <td>-0.022215</td>
      <td>0.123125</td>
      <td>-0.039662</td>
      <td>-0.011220</td>
      <td>-0.013880</td>
      <td>-0.010108</td>
      <td>-0.041852</td>
      <td>-0.011872</td>
      <td>-0.042637</td>
      <td>-0.052429</td>
    </tr>
    <tr>
      <th>Cigarettes</th>
      <td>0.002173</td>
      <td>0.005433</td>
      <td>0.003043</td>
      <td>0.002309</td>
      <td>0.002497</td>
      <td>0.002818</td>
      <td>0.004060</td>
      <td>0.002291</td>
      <td>0.003340</td>
      <td>0.063662</td>
      <td>...</td>
      <td>0.003017</td>
      <td>-0.024739</td>
      <td>0.035882</td>
      <td>0.003067</td>
      <td>0.044946</td>
      <td>0.002397</td>
      <td>0.039861</td>
      <td>0.000952</td>
      <td>0.034543</td>
      <td>0.077318</td>
    </tr>
    <tr>
      <th>Cheese</th>
      <td>0.000299</td>
      <td>-0.001410</td>
      <td>-0.001251</td>
      <td>-0.000492</td>
      <td>-0.000751</td>
      <td>0.000182</td>
      <td>-0.000797</td>
      <td>-0.001087</td>
      <td>-0.000955</td>
      <td>0.068259</td>
      <td>...</td>
      <td>-0.000255</td>
      <td>-0.021386</td>
      <td>0.040281</td>
      <td>-0.000905</td>
      <td>-0.000318</td>
      <td>0.000248</td>
      <td>0.041884</td>
      <td>-0.000963</td>
      <td>0.040788</td>
      <td>0.038931</td>
    </tr>
    <tr>
      <th>Cleaning Products</th>
      <td>0.007479</td>
      <td>0.010341</td>
      <td>0.005524</td>
      <td>0.006805</td>
      <td>0.006073</td>
      <td>0.004349</td>
      <td>0.007826</td>
      <td>0.005736</td>
      <td>0.005322</td>
      <td>-0.003569</td>
      <td>...</td>
      <td>0.091094</td>
      <td>-0.003362</td>
      <td>-0.000705</td>
      <td>0.006622</td>
      <td>0.006129</td>
      <td>0.005330</td>
      <td>-0.000243</td>
      <td>0.047183</td>
      <td>-0.006235</td>
      <td>0.004788</td>
    </tr>
    <tr>
      <th>Condiments</th>
      <td>-0.003620</td>
      <td>-0.003853</td>
      <td>-0.002228</td>
      <td>-0.001390</td>
      <td>-0.001419</td>
      <td>-0.000809</td>
      <td>-0.000833</td>
      <td>-0.002494</td>
      <td>-0.002612</td>
      <td>-0.037975</td>
      <td>...</td>
      <td>-0.003362</td>
      <td>0.192499</td>
      <td>-0.021701</td>
      <td>-0.001598</td>
      <td>-0.003657</td>
      <td>-0.002185</td>
      <td>-0.023588</td>
      <td>-0.002009</td>
      <td>-0.027129</td>
      <td>-0.024998</td>
    </tr>
    <tr>
      <th>Frozen Foods</th>
      <td>-0.000068</td>
      <td>-0.001423</td>
      <td>0.000498</td>
      <td>-0.001081</td>
      <td>0.000193</td>
      <td>-0.000623</td>
      <td>0.000148</td>
      <td>-0.000723</td>
      <td>-0.000957</td>
      <td>0.065853</td>
      <td>...</td>
      <td>-0.000705</td>
      <td>-0.021701</td>
      <td>0.118746</td>
      <td>-0.001559</td>
      <td>-0.000391</td>
      <td>-0.000264</td>
      <td>0.043095</td>
      <td>-0.000312</td>
      <td>0.038204</td>
      <td>0.038088</td>
    </tr>
    <tr>
      <th>Kitchen Items</th>
      <td>0.004323</td>
      <td>0.005825</td>
      <td>0.003365</td>
      <td>0.003166</td>
      <td>0.003655</td>
      <td>0.003491</td>
      <td>0.003213</td>
      <td>0.001727</td>
      <td>0.002728</td>
      <td>-0.002219</td>
      <td>...</td>
      <td>0.006622</td>
      <td>-0.001598</td>
      <td>-0.001559</td>
      <td>0.053575</td>
      <td>0.004074</td>
      <td>0.004157</td>
      <td>-0.000432</td>
      <td>0.004009</td>
      <td>-0.003354</td>
      <td>0.002981</td>
    </tr>
    <tr>
      <th>Meat</th>
      <td>0.002661</td>
      <td>0.006862</td>
      <td>0.003601</td>
      <td>0.002518</td>
      <td>0.003013</td>
      <td>0.003065</td>
      <td>0.003374</td>
      <td>0.002909</td>
      <td>0.003616</td>
      <td>-0.001503</td>
      <td>...</td>
      <td>0.006129</td>
      <td>-0.003657</td>
      <td>-0.000391</td>
      <td>0.004074</td>
      <td>0.052153</td>
      <td>0.003952</td>
      <td>-0.000344</td>
      <td>0.003146</td>
      <td>-0.002984</td>
      <td>0.044721</td>
    </tr>
    <tr>
      <th>Office Supplies</th>
      <td>0.002739</td>
      <td>0.006572</td>
      <td>0.004411</td>
      <td>0.002956</td>
      <td>0.003674</td>
      <td>0.002632</td>
      <td>0.002653</td>
      <td>0.002552</td>
      <td>0.003404</td>
      <td>-0.002348</td>
      <td>...</td>
      <td>0.005330</td>
      <td>-0.002185</td>
      <td>-0.000264</td>
      <td>0.004157</td>
      <td>0.003952</td>
      <td>0.050855</td>
      <td>-0.001369</td>
      <td>0.003587</td>
      <td>-0.002926</td>
      <td>0.002760</td>
    </tr>
    <tr>
      <th>Personal Care</th>
      <td>-0.000078</td>
      <td>-0.000596</td>
      <td>-0.001138</td>
      <td>-0.001286</td>
      <td>-0.001057</td>
      <td>-0.001501</td>
      <td>-0.000021</td>
      <td>-0.000532</td>
      <td>-0.000904</td>
      <td>0.073479</td>
      <td>...</td>
      <td>-0.000243</td>
      <td>-0.023588</td>
      <td>0.043095</td>
      <td>-0.000432</td>
      <td>-0.000344</td>
      <td>-0.001369</td>
      <td>0.124744</td>
      <td>-0.000169</td>
      <td>0.043660</td>
      <td>0.040285</td>
    </tr>
    <tr>
      <th>Pet Supplies</th>
      <td>0.003460</td>
      <td>0.005023</td>
      <td>0.003242</td>
      <td>0.003529</td>
      <td>0.002575</td>
      <td>0.002552</td>
      <td>0.004250</td>
      <td>0.004005</td>
      <td>0.002744</td>
      <td>-0.002148</td>
      <td>...</td>
      <td>0.047183</td>
      <td>-0.002009</td>
      <td>-0.000312</td>
      <td>0.004009</td>
      <td>0.003146</td>
      <td>0.003587</td>
      <td>-0.000169</td>
      <td>0.049749</td>
      <td>-0.002971</td>
      <td>0.002048</td>
    </tr>
    <tr>
      <th>Sea Food</th>
      <td>-0.002584</td>
      <td>-0.005496</td>
      <td>-0.002752</td>
      <td>-0.003081</td>
      <td>-0.002177</td>
      <td>-0.002846</td>
      <td>-0.003463</td>
      <td>-0.002661</td>
      <td>-0.003111</td>
      <td>0.109082</td>
      <td>...</td>
      <td>-0.006235</td>
      <td>-0.027129</td>
      <td>0.038204</td>
      <td>-0.003354</td>
      <td>-0.002984</td>
      <td>-0.002926</td>
      <td>0.043660</td>
      <td>-0.002971</td>
      <td>0.120271</td>
      <td>0.037905</td>
    </tr>
    <tr>
      <th>Spices</th>
      <td>0.001664</td>
      <td>0.005457</td>
      <td>0.002158</td>
      <td>0.001739</td>
      <td>0.002278</td>
      <td>0.002822</td>
      <td>0.002671</td>
      <td>0.002865</td>
      <td>0.002827</td>
      <td>0.066989</td>
      <td>...</td>
      <td>0.004788</td>
      <td>-0.024998</td>
      <td>0.038088</td>
      <td>0.002981</td>
      <td>0.044721</td>
      <td>0.002760</td>
      <td>0.040285</td>
      <td>0.002048</td>
      <td>0.037905</td>
      <td>0.153809</td>
    </tr>
  </tbody>
</table>
<p>29 rows × 29 columns</p>
</div>




```python
cov_matrix = df.cov()
sns.heatmap(cov_matrix);
```


![png](output_31_0.png)


## Skewness and Kurtosis:

Skewness use to measure symmetry of data along with the mean value. In this Data set some products as chips, Club Soda, Canned Foods have 0 in Skewness this mean that the data is symmetric. We need to remember that negative Skewness means more people buy the product.


```python
import pandas as pd

df1 = pd.DataFrame(df)
print('The value of Skewness is:')
print(df1.skew())
```

    The value of Skewness is:
    Baby Food            3.974314
    Diapers              2.643290
    Formula              3.856769
    Lotion               4.097362
    Baby wash            3.964723
    Wipes                4.006688
    Fresh Fruits         3.905241
    Fresh Vegetables     3.883858
    Beer                 3.923794
    Wine                 1.353159
    Club Soda            0.392596
    Sports Drink         3.892988
    Chips                0.947490
    Popcorn              1.002027
    Oatmeal              3.865748
    Medicines            2.073159
    Canned Foods         0.676355
    Cigarettes           1.616194
    Cheese               2.087156
    Cleaning Products    2.641965
    Condiments           1.093382
    Frozen Foods         2.103080
    Kitchen Items        3.830122
    Meat                 3.896043
    Office Supplies      3.958360
    Personal Care        2.004470
    Pet Supplies         4.013239
    Sea Food             2.077518
    Spices               1.581962
    dtype: float64



```python
df1.describe() #Describe statistic information by products.
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
      <th>Baby Food</th>
      <th>Diapers</th>
      <th>Formula</th>
      <th>Lotion</th>
      <th>Baby wash</th>
      <th>Wipes</th>
      <th>Fresh Fruits</th>
      <th>Fresh Vegetables</th>
      <th>Beer</th>
      <th>Wine</th>
      <th>...</th>
      <th>Cleaning Products</th>
      <th>Condiments</th>
      <th>Frozen Foods</th>
      <th>Kitchen Items</th>
      <th>Meat</th>
      <th>Office Supplies</th>
      <th>Personal Care</th>
      <th>Pet Supplies</th>
      <th>Sea Food</th>
      <th>Spices</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>...</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>0.053375</td>
      <td>0.101289</td>
      <td>0.056142</td>
      <td>0.050681</td>
      <td>0.053594</td>
      <td>0.052647</td>
      <td>0.054977</td>
      <td>0.055487</td>
      <td>0.054540</td>
      <td>0.219835</td>
      <td>...</td>
      <td>0.101362</td>
      <td>0.260176</td>
      <td>0.137698</td>
      <td>0.056797</td>
      <td>0.055196</td>
      <td>0.053739</td>
      <td>0.146072</td>
      <td>0.052501</td>
      <td>0.139809</td>
      <td>0.189835</td>
    </tr>
    <tr>
      <th>std</th>
      <td>0.224788</td>
      <td>0.301722</td>
      <td>0.230204</td>
      <td>0.219353</td>
      <td>0.225222</td>
      <td>0.223336</td>
      <td>0.227944</td>
      <td>0.228936</td>
      <td>0.227089</td>
      <td>0.414150</td>
      <td>...</td>
      <td>0.301818</td>
      <td>0.438747</td>
      <td>0.344595</td>
      <td>0.231464</td>
      <td>0.228370</td>
      <td>0.225510</td>
      <td>0.353191</td>
      <td>0.223044</td>
      <td>0.346802</td>
      <td>0.392185</td>
    </tr>
    <tr>
      <th>min</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>...</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 29 columns</p>
</div>




```python
#Graphics compared de correlation by products.

import matplotlib
import matplotlib.pyplot as plt
import pandas as pd

matplotlib.style.use('ggplot')
df1.hist(alpha=0.5, figsize=(16,10))
plt.show()
```


![png](output_36_0.png)


## The Kurtosis 

The Kurtosis products as Cigarettes, Spices has to normal distribution, the products as Wine, Club Soda, Chips, Popcorn, Canned Foods, Condiments have a negative Kurtosis, tha means this products have limited customer to buy. The others products have positive kurtosis.


```python
print('The Value of Kurtosis is:')
print(df1.kurtosis())
```

    The Value of Kurtosis is:
    Baby Food            13.797179
    Diapers               4.987711
    Formula              12.876539
    Lotion               14.790530
    Baby wash            13.721028
    Wipes                14.055594
    Fresh Fruits         13.252841
    Fresh Vegetables     13.086257
    Beer                 13.398114
    Wine                 -0.168987
    Club Soda            -1.846137
    Sports Drink         13.157273
    Chips                -1.102424
    Popcorn              -0.996087
    Oatmeal              12.945897
    Medicines             2.298325
    Canned Foods         -1.542769
    Cigarettes            0.612173
    Cheese                2.356565
    Cleaning Products     4.980706
    Condiments           -0.804634
    Frozen Foods          2.423300
    Kitchen Items        12.671678
    Meat                 13.181070
    Office Supplies      13.670606
    Personal Care         2.018192
    Pet Supplies         14.108140
    Sea Food              2.316417
    Spices                0.502677
    dtype: float64



```python
#Graphic that show dataframe relationship Lotion with the others products.
import seaborn as sns

sns.distplot(df1['Lotion'], hist=True, kde=True)
```




    <matplotlib.axes._subplots.AxesSubplot at 0x7f76344e7ed0>




![png](output_40_1.png)


## Feature Engineering:

The database object of this study presents the features of segmenting the market into two categories, one is by-products and the other by qualities or characterization of the customers, so it will be coded in such a way as to show us the grouped information unifying it to In order to respond to which market segmentation the product should be directed and in which product more emphasis should be placed.

### Categorical Variable:

-GenderCode
     
     * Master
     * Miss
     * Mr.
     * Mrs.

-STATE

     * All state of United States.

-CREDITCARD_TYPE

     * American Express	
     
     * Diners Club	
     
     * Discover	
     
     * JCB	
     
     * Master Card	VISA


-PURCHASE_TOUCHPOINT
      
      * Desktop
      
      * Phone


-ORDER_TYPE

      * High Value		
      
      * Medium Value
      
      * Low Value

-GENERATION:

      * Baby Boomer that represent 76 million people born between 1946 and 1964.
      
      * generation X born between 1965 and 1980.
      
      * generation Z born after 1997.

#### Analysis:

In this dataset the generation Baby Boomer that represent 76 million people born between 1946 and 1964. They expenden more money that generation X, Y and Z, being generation X the ones who spend the least. See Table:


```python
tab = pd.crosstab(df['GenderCode'], df['GENERATION'])
tab
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
      <th>GENERATION</th>
      <th>Baby_Boomers</th>
      <th>Gen_X</th>
      <th>Gen_Y</th>
      <th>Gen_Z</th>
    </tr>
    <tr>
      <th>GenderCode</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Master.</th>
      <td>185</td>
      <td>63</td>
      <td>84</td>
      <td>86</td>
    </tr>
    <tr>
      <th>Miss.</th>
      <td>175</td>
      <td>40</td>
      <td>106</td>
      <td>113</td>
    </tr>
    <tr>
      <th>Mr.</th>
      <td>2232</td>
      <td>784</td>
      <td>1579</td>
      <td>1398</td>
    </tr>
    <tr>
      <th>Mrs.</th>
      <td>2567</td>
      <td>958</td>
      <td>1723</td>
      <td>1640</td>
    </tr>
  </tbody>
</table>
</div>




```python
tab.describe()
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
      <th>GENERATION</th>
      <th>Baby_Boomers</th>
      <th>Gen_X</th>
      <th>Gen_Y</th>
      <th>Gen_Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>4.000000</td>
      <td>4.000000</td>
      <td>4.000000</td>
      <td>4.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1289.750000</td>
      <td>461.250000</td>
      <td>873.000000</td>
      <td>809.250000</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1288.712891</td>
      <td>478.533437</td>
      <td>900.323275</td>
      <td>825.555722</td>
    </tr>
    <tr>
      <th>min</th>
      <td>175.000000</td>
      <td>40.000000</td>
      <td>84.000000</td>
      <td>86.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>182.500000</td>
      <td>57.250000</td>
      <td>100.500000</td>
      <td>106.250000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1208.500000</td>
      <td>423.500000</td>
      <td>842.500000</td>
      <td>755.500000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2315.750000</td>
      <td>827.500000</td>
      <td>1615.000000</td>
      <td>1458.500000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>2567.000000</td>
      <td>958.000000</td>
      <td>1723.000000</td>
      <td>1640.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
tab.plot(kind='box')
```




    <matplotlib.axes._subplots.AxesSubplot at 0x7f763473c650>




![png](output_47_1.png)



```python
tab.plot();
tab
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
      <th>GENERATION</th>
      <th>Baby_Boomers</th>
      <th>Gen_X</th>
      <th>Gen_Y</th>
      <th>Gen_Z</th>
    </tr>
    <tr>
      <th>GenderCode</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Master.</th>
      <td>185</td>
      <td>63</td>
      <td>84</td>
      <td>86</td>
    </tr>
    <tr>
      <th>Miss.</th>
      <td>175</td>
      <td>40</td>
      <td>106</td>
      <td>113</td>
    </tr>
    <tr>
      <th>Mr.</th>
      <td>2232</td>
      <td>784</td>
      <td>1579</td>
      <td>1398</td>
    </tr>
    <tr>
      <th>Mrs.</th>
      <td>2567</td>
      <td>958</td>
      <td>1723</td>
      <td>1640</td>
    </tr>
  </tbody>
</table>
</div>




![png](output_48_1.png)



```python
from scipy.stats import norm, kurtosis
kurtosis(tab)
plt.hist(tab, bins=60)
```




    (array([[1., 2., 0., 1., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
             0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
             0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
             0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.],
            [1., 2., 0., 1., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
             0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
             0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
             0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.],
            [0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
             0., 1., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
             1., 0., 0., 0., 1., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
             0., 0., 0., 0., 1., 0., 0., 0., 0., 0., 0., 0.],
            [0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
             0., 0., 0., 0., 0., 1., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
             0., 0., 0., 0., 0., 1., 0., 1., 0., 0., 0., 0., 0., 0., 0., 0.,
             0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 1.]]),
     array([  40.        ,   82.11666667,  124.23333333,  166.35      ,
             208.46666667,  250.58333333,  292.7       ,  334.81666667,
             376.93333333,  419.05      ,  461.16666667,  503.28333333,
             545.4       ,  587.51666667,  629.63333333,  671.75      ,
             713.86666667,  755.98333333,  798.1       ,  840.21666667,
             882.33333333,  924.45      ,  966.56666667, 1008.68333333,
            1050.8       , 1092.91666667, 1135.03333333, 1177.15      ,
            1219.26666667, 1261.38333333, 1303.5       , 1345.61666667,
            1387.73333333, 1429.85      , 1471.96666667, 1514.08333333,
            1556.2       , 1598.31666667, 1640.43333333, 1682.55      ,
            1724.66666667, 1766.78333333, 1808.9       , 1851.01666667,
            1893.13333333, 1935.25      , 1977.36666667, 2019.48333333,
            2061.6       , 2103.71666667, 2145.83333333, 2187.95      ,
            2230.06666667, 2272.18333333, 2314.3       , 2356.41666667,
            2398.53333333, 2440.65      , 2482.76666667, 2524.88333333,
            2567.        ]),
     <a list of 4 Lists of Patches objects>)




![png](output_49_1.png)


## Analysis Cross table by category

The trend in the use of Credit card the generation Boomers continue to predominate, followed by generation Z (born after 1997)


```python
tab2 = pd.crosstab(df['GENERATION'], df['CREDITCARD_TYPE']) #A crosstable is a common type of table featuring a matrix of values between two or more orthogonal lists of header data
tab2
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
      <th>CREDITCARD_TYPE</th>
      <th>American Express</th>
      <th>Diners Club</th>
      <th>Discover</th>
      <th>JCB</th>
      <th>Master Card</th>
      <th>VISA</th>
    </tr>
    <tr>
      <th>GENERATION</th>
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
      <th>Baby_Boomers</th>
      <td>992</td>
      <td>1052</td>
      <td>896</td>
      <td>886</td>
      <td>440</td>
      <td>893</td>
    </tr>
    <tr>
      <th>Gen_X</th>
      <td>369</td>
      <td>282</td>
      <td>360</td>
      <td>344</td>
      <td>148</td>
      <td>342</td>
    </tr>
    <tr>
      <th>Gen_Y</th>
      <td>665</td>
      <td>649</td>
      <td>615</td>
      <td>604</td>
      <td>291</td>
      <td>668</td>
    </tr>
    <tr>
      <th>Gen_Z</th>
      <td>669</td>
      <td>592</td>
      <td>591</td>
      <td>610</td>
      <td>273</td>
      <td>502</td>
    </tr>
  </tbody>
</table>
</div>




```python
tab2.describe() #Statistic categorical compared the use of different credit card by generations.
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
      <th>CREDITCARD_TYPE</th>
      <th>American Express</th>
      <th>Diners Club</th>
      <th>Discover</th>
      <th>JCB</th>
      <th>Master Card</th>
      <th>VISA</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>4.000000</td>
      <td>4.00000</td>
      <td>4.000000</td>
      <td>4.000000</td>
      <td>4.000000</td>
      <td>4.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>673.750000</td>
      <td>643.75000</td>
      <td>615.500000</td>
      <td>611.000000</td>
      <td>288.000000</td>
      <td>601.250000</td>
    </tr>
    <tr>
      <th>std</th>
      <td>254.463324</td>
      <td>316.35252</td>
      <td>219.515375</td>
      <td>221.332329</td>
      <td>119.635558</td>
      <td>235.679691</td>
    </tr>
    <tr>
      <th>min</th>
      <td>369.000000</td>
      <td>282.00000</td>
      <td>360.000000</td>
      <td>344.000000</td>
      <td>148.000000</td>
      <td>342.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>591.000000</td>
      <td>514.50000</td>
      <td>533.250000</td>
      <td>539.000000</td>
      <td>241.750000</td>
      <td>462.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>667.000000</td>
      <td>620.50000</td>
      <td>603.000000</td>
      <td>607.000000</td>
      <td>282.000000</td>
      <td>585.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>749.750000</td>
      <td>749.75000</td>
      <td>685.250000</td>
      <td>679.000000</td>
      <td>328.250000</td>
      <td>724.250000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>992.000000</td>
      <td>1052.00000</td>
      <td>896.000000</td>
      <td>886.000000</td>
      <td>440.000000</td>
      <td>893.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
tab2.plot(); #Graphic used credit card type by generation.
```


![png](output_54_0.png)


## Statistic categorical compared the use of different credit card by gender.


```python
tab3 = pd.crosstab(df['CREDITCARD_TYPE'], df['GenderCode']) #American express is the prefer by MR and MRS.
tab3
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
      <th>GenderCode</th>
      <th>Master.</th>
      <th>Miss.</th>
      <th>Mr.</th>
      <th>Mrs.</th>
    </tr>
    <tr>
      <th>CREDITCARD_TYPE</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>American Express</th>
      <td>80</td>
      <td>70</td>
      <td>1229</td>
      <td>1316</td>
    </tr>
    <tr>
      <th>Diners Club</th>
      <td>72</td>
      <td>83</td>
      <td>1078</td>
      <td>1342</td>
    </tr>
    <tr>
      <th>Discover</th>
      <td>77</td>
      <td>89</td>
      <td>1077</td>
      <td>1219</td>
    </tr>
    <tr>
      <th>JCB</th>
      <td>77</td>
      <td>72</td>
      <td>1068</td>
      <td>1227</td>
    </tr>
    <tr>
      <th>Master Card</th>
      <td>24</td>
      <td>51</td>
      <td>510</td>
      <td>567</td>
    </tr>
    <tr>
      <th>VISA</th>
      <td>88</td>
      <td>69</td>
      <td>1031</td>
      <td>1217</td>
    </tr>
  </tbody>
</table>
</div>




```python
tab3.describe()
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
      <th>GenderCode</th>
      <th>Master.</th>
      <th>Miss.</th>
      <th>Mr.</th>
      <th>Mrs.</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>6.000000</td>
      <td>6.000000</td>
      <td>6.000000</td>
      <td>6.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>69.666667</td>
      <td>72.333333</td>
      <td>998.833333</td>
      <td>1148.000000</td>
    </tr>
    <tr>
      <th>std</th>
      <td>22.984052</td>
      <td>13.140269</td>
      <td>249.050530</td>
      <td>289.642538</td>
    </tr>
    <tr>
      <th>min</th>
      <td>24.000000</td>
      <td>51.000000</td>
      <td>510.000000</td>
      <td>567.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>73.250000</td>
      <td>69.250000</td>
      <td>1040.250000</td>
      <td>1217.500000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>77.000000</td>
      <td>71.000000</td>
      <td>1072.500000</td>
      <td>1223.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>79.250000</td>
      <td>80.250000</td>
      <td>1077.750000</td>
      <td>1293.750000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>88.000000</td>
      <td>89.000000</td>
      <td>1229.000000</td>
      <td>1342.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
tab3.plot(); #Graphic to analysis the correlation into gender and credit card type.
```


![png](output_58_0.png)


## Statistic categorical compared the use of different Value by gender.


```python
tab4 = pd.crosstab(df['GenderCode'], df['ORDER_TYPE']) #this crosstable and statistic description tell us that the mayority people expend in low value, fallowed by high value, for the Baby_Boomers and Gen_Y
tab4
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
      <th>ORDER_TYPE</th>
      <th>HighValue</th>
      <th>LowValue</th>
      <th>MediumValue</th>
    </tr>
    <tr>
      <th>GenderCode</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Master.</th>
      <td>102</td>
      <td>259</td>
      <td>57</td>
    </tr>
    <tr>
      <th>Miss.</th>
      <td>106</td>
      <td>262</td>
      <td>66</td>
    </tr>
    <tr>
      <th>Mr.</th>
      <td>1696</td>
      <td>3507</td>
      <td>790</td>
    </tr>
    <tr>
      <th>Mrs.</th>
      <td>1939</td>
      <td>4012</td>
      <td>937</td>
    </tr>
  </tbody>
</table>
</div>




```python
tab4.describe()
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
      <th>ORDER_TYPE</th>
      <th>HighValue</th>
      <th>LowValue</th>
      <th>MediumValue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>4.000000</td>
      <td>4.00000</td>
      <td>4.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>960.750000</td>
      <td>2010.00000</td>
      <td>462.500000</td>
    </tr>
    <tr>
      <th>std</th>
      <td>994.252609</td>
      <td>2030.64177</td>
      <td>466.922192</td>
    </tr>
    <tr>
      <th>min</th>
      <td>102.000000</td>
      <td>259.00000</td>
      <td>57.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>105.000000</td>
      <td>261.25000</td>
      <td>63.750000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>901.000000</td>
      <td>1884.50000</td>
      <td>428.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>1756.750000</td>
      <td>3633.25000</td>
      <td>826.750000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>1939.000000</td>
      <td>4012.00000</td>
      <td>937.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
tab4.plot(kind='density')
```




    <matplotlib.axes._subplots.AxesSubplot at 0x7f75f061aa90>




![png](output_62_1.png)



```python
import seaborn as sns

sns.set(style="ticks", color_codes=True)
pair = sns.pairplot(tab4)
```


![png](output_63_0.png)



```python
tab5 = pd.crosstab(df['ORDER_TYPE'], df['GENERATION'])
tab5
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
      <th>GENERATION</th>
      <th>Baby_Boomers</th>
      <th>Gen_X</th>
      <th>Gen_Y</th>
      <th>Gen_Z</th>
    </tr>
    <tr>
      <th>ORDER_TYPE</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>HighValue</th>
      <td>2280</td>
      <td>0</td>
      <td>452</td>
      <td>1111</td>
    </tr>
    <tr>
      <th>LowValue</th>
      <td>2411</td>
      <td>1845</td>
      <td>2660</td>
      <td>1124</td>
    </tr>
    <tr>
      <th>MediumValue</th>
      <td>468</td>
      <td>0</td>
      <td>380</td>
      <td>1002</td>
    </tr>
  </tbody>
</table>
</div>




```python
tab5.describe()
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
      <th>GENERATION</th>
      <th>Baby_Boomers</th>
      <th>Gen_X</th>
      <th>Gen_Y</th>
      <th>Gen_Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>3.000000</td>
      <td>3.000000</td>
      <td>3.000000</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1719.666667</td>
      <td>615.000000</td>
      <td>1164.000000</td>
      <td>1079.0</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1085.952270</td>
      <td>1065.211247</td>
      <td>1296.074072</td>
      <td>67.0</td>
    </tr>
    <tr>
      <th>min</th>
      <td>468.000000</td>
      <td>0.000000</td>
      <td>380.000000</td>
      <td>1002.0</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>1374.000000</td>
      <td>0.000000</td>
      <td>416.000000</td>
      <td>1056.5</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>2280.000000</td>
      <td>0.000000</td>
      <td>452.000000</td>
      <td>1111.0</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2345.500000</td>
      <td>922.500000</td>
      <td>1556.000000</td>
      <td>1117.5</td>
    </tr>
    <tr>
      <th>max</th>
      <td>2411.000000</td>
      <td>1845.000000</td>
      <td>2660.000000</td>
      <td>1124.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
tab5.plot();
```


![png](output_66_0.png)


## Statistic categorical compared the use of different Purchase touch point by gender.

Shopping continues with the trend towards online or telephone purchases, being men and women parents the ones who currently use this system the most.


```python
tab6 = pd.crosstab(df['GenderCode'], df['PURCHASE_TOUCHPOINT'])
tab6
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
      <th>PURCHASE_TOUCHPOINT</th>
      <th>Desktop</th>
      <th>Phone</th>
    </tr>
    <tr>
      <th>GenderCode</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Master.</th>
      <td>106</td>
      <td>312</td>
    </tr>
    <tr>
      <th>Miss.</th>
      <td>111</td>
      <td>323</td>
    </tr>
    <tr>
      <th>Mr.</th>
      <td>1608</td>
      <td>4385</td>
    </tr>
    <tr>
      <th>Mrs.</th>
      <td>1827</td>
      <td>5061</td>
    </tr>
  </tbody>
</table>
</div>




```python
tab6.describe()
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
      <th>PURCHASE_TOUCHPOINT</th>
      <th>Desktop</th>
      <th>Phone</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>4.000000</td>
      <td>4.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>913.000000</td>
      <td>2520.250000</td>
    </tr>
    <tr>
      <th>std</th>
      <td>933.251306</td>
      <td>2558.448667</td>
    </tr>
    <tr>
      <th>min</th>
      <td>106.000000</td>
      <td>312.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>109.750000</td>
      <td>320.250000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>859.500000</td>
      <td>2354.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>1662.750000</td>
      <td>4554.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>1827.000000</td>
      <td>5061.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
import matplotlib
%matplotlib inline
matplotlib.use('Agg')

plt.figure()
sns.boxplot('Desktop', 'Phone', data = tab6)
plt.show()
```


![png](output_71_0.png)



```python
import seaborn as sns

sns.catplot(x='Desktop', y='Phone', kind='bar', data=tab6, height=7);
```


![png](output_72_0.png)


## Statistic categorical compared the use of different Purchase touch point by generation.

Generation Z is the principal used the shopping online or phone, Baby Boomers the most used purchase direct in the store and Phone.


```python
tab7 = pd.crosstab(df['PURCHASE_TOUCHPOINT'], df['GENERATION'])
tab7
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
      <th>GENERATION</th>
      <th>Baby_Boomers</th>
      <th>Gen_X</th>
      <th>Gen_Y</th>
      <th>Gen_Z</th>
    </tr>
    <tr>
      <th>PURCHASE_TOUCHPOINT</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Desktop</th>
      <td>2717</td>
      <td>0</td>
      <td>262</td>
      <td>673</td>
    </tr>
    <tr>
      <th>Phone</th>
      <td>2442</td>
      <td>1845</td>
      <td>3230</td>
      <td>2564</td>
    </tr>
  </tbody>
</table>
</div>




```python
tab7.describe()
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
      <th>GENERATION</th>
      <th>Baby_Boomers</th>
      <th>Gen_X</th>
      <th>Gen_Y</th>
      <th>Gen_Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>2579.500000</td>
      <td>922.500000</td>
      <td>1746.000000</td>
      <td>1618.500000</td>
    </tr>
    <tr>
      <th>std</th>
      <td>194.454365</td>
      <td>1304.612011</td>
      <td>2098.692927</td>
      <td>1337.138923</td>
    </tr>
    <tr>
      <th>min</th>
      <td>2442.000000</td>
      <td>0.000000</td>
      <td>262.000000</td>
      <td>673.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2510.750000</td>
      <td>461.250000</td>
      <td>1004.000000</td>
      <td>1145.750000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>2579.500000</td>
      <td>922.500000</td>
      <td>1746.000000</td>
      <td>1618.500000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2648.250000</td>
      <td>1383.750000</td>
      <td>2488.000000</td>
      <td>2091.250000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>2717.000000</td>
      <td>1845.000000</td>
      <td>3230.000000</td>
      <td>2564.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
tab7.plot(kind = 'density')
```




    <matplotlib.axes._subplots.AxesSubplot at 0x7f75f07f2b90>




![png](output_77_1.png)


## Statistic categorical compared the use of different State by generation.


```python
tab8 = pd.crosstab(df['GENERATION'], df['STATE'])
tab8
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
      <th>STATE</th>
      <th>0</th>
      <th>AB</th>
      <th>ACT</th>
      <th>AG</th>
      <th>AK</th>
      <th>AL</th>
      <th>AN</th>
      <th>AO</th>
      <th>AP</th>
      <th>AQ</th>
      <th>...</th>
      <th>VE</th>
      <th>VI</th>
      <th>VIC</th>
      <th>VR</th>
      <th>VT</th>
      <th>VV</th>
      <th>WA</th>
      <th>WI</th>
      <th>WV</th>
      <th>WY</th>
    </tr>
    <tr>
      <th>GENERATION</th>
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
      <th>Baby_Boomers</th>
      <td>629</td>
      <td>5</td>
      <td>0</td>
      <td>3</td>
      <td>1</td>
      <td>19</td>
      <td>2</td>
      <td>0</td>
      <td>7</td>
      <td>17</td>
      <td>...</td>
      <td>11</td>
      <td>2</td>
      <td>82</td>
      <td>9</td>
      <td>19</td>
      <td>1</td>
      <td>35</td>
      <td>38</td>
      <td>6</td>
      <td>1</td>
    </tr>
    <tr>
      <th>Gen_X</th>
      <td>192</td>
      <td>5</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>8</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>7</td>
      <td>10</td>
      <td>30</td>
      <td>1</td>
      <td>5</td>
      <td>6</td>
      <td>9</td>
      <td>6</td>
      <td>0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>Gen_Y</th>
      <td>398</td>
      <td>9</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>18</td>
      <td>7</td>
      <td>3</td>
      <td>9</td>
      <td>6</td>
      <td>...</td>
      <td>4</td>
      <td>1</td>
      <td>55</td>
      <td>5</td>
      <td>2</td>
      <td>14</td>
      <td>29</td>
      <td>26</td>
      <td>8</td>
      <td>8</td>
    </tr>
    <tr>
      <th>Gen_Z</th>
      <td>368</td>
      <td>6</td>
      <td>5</td>
      <td>0</td>
      <td>9</td>
      <td>15</td>
      <td>7</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>...</td>
      <td>9</td>
      <td>11</td>
      <td>43</td>
      <td>0</td>
      <td>3</td>
      <td>7</td>
      <td>29</td>
      <td>34</td>
      <td>8</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
<p>4 rows × 146 columns</p>
</div>




```python
tab8.describe()
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
      <th>STATE</th>
      <th>0</th>
      <th>AB</th>
      <th>ACT</th>
      <th>AG</th>
      <th>AK</th>
      <th>AL</th>
      <th>AN</th>
      <th>AO</th>
      <th>AP</th>
      <th>AQ</th>
      <th>...</th>
      <th>VE</th>
      <th>VI</th>
      <th>VIC</th>
      <th>VR</th>
      <th>VT</th>
      <th>VV</th>
      <th>WA</th>
      <th>WI</th>
      <th>WV</th>
      <th>WY</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>4.000000</td>
      <td>4.000000</td>
      <td>4.00</td>
      <td>4.000000</td>
      <td>4.000000</td>
      <td>4.000000</td>
      <td>4.000000</td>
      <td>4.00</td>
      <td>4.000000</td>
      <td>4.00000</td>
      <td>...</td>
      <td>4.000000</td>
      <td>4.000000</td>
      <td>4.00000</td>
      <td>4.000000</td>
      <td>4.000000</td>
      <td>4.000000</td>
      <td>4.000000</td>
      <td>4.000000</td>
      <td>4.000000</td>
      <td>4.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>396.750000</td>
      <td>6.250000</td>
      <td>1.25</td>
      <td>1.000000</td>
      <td>2.750000</td>
      <td>15.000000</td>
      <td>4.000000</td>
      <td>0.75</td>
      <td>4.250000</td>
      <td>5.75000</td>
      <td>...</td>
      <td>7.750000</td>
      <td>6.000000</td>
      <td>52.50000</td>
      <td>3.750000</td>
      <td>7.250000</td>
      <td>7.000000</td>
      <td>25.500000</td>
      <td>26.000000</td>
      <td>5.500000</td>
      <td>3.750000</td>
    </tr>
    <tr>
      <th>std</th>
      <td>179.527853</td>
      <td>1.892969</td>
      <td>2.50</td>
      <td>1.414214</td>
      <td>4.193249</td>
      <td>4.966555</td>
      <td>3.559026</td>
      <td>1.50</td>
      <td>4.425306</td>
      <td>8.01561</td>
      <td>...</td>
      <td>2.986079</td>
      <td>5.228129</td>
      <td>22.15852</td>
      <td>4.112988</td>
      <td>7.932003</td>
      <td>5.354126</td>
      <td>11.357817</td>
      <td>14.236104</td>
      <td>3.785939</td>
      <td>3.095696</td>
    </tr>
    <tr>
      <th>min</th>
      <td>192.000000</td>
      <td>5.000000</td>
      <td>0.00</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>8.000000</td>
      <td>0.000000</td>
      <td>0.00</td>
      <td>0.000000</td>
      <td>0.00000</td>
      <td>...</td>
      <td>4.000000</td>
      <td>1.000000</td>
      <td>30.00000</td>
      <td>0.000000</td>
      <td>2.000000</td>
      <td>1.000000</td>
      <td>9.000000</td>
      <td>6.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>324.000000</td>
      <td>5.000000</td>
      <td>0.00</td>
      <td>0.000000</td>
      <td>0.750000</td>
      <td>13.250000</td>
      <td>1.500000</td>
      <td>0.00</td>
      <td>0.750000</td>
      <td>0.00000</td>
      <td>...</td>
      <td>6.250000</td>
      <td>1.750000</td>
      <td>39.75000</td>
      <td>0.750000</td>
      <td>2.750000</td>
      <td>4.750000</td>
      <td>24.000000</td>
      <td>21.000000</td>
      <td>4.500000</td>
      <td>1.750000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>383.000000</td>
      <td>5.500000</td>
      <td>0.00</td>
      <td>0.500000</td>
      <td>1.000000</td>
      <td>16.500000</td>
      <td>4.500000</td>
      <td>0.00</td>
      <td>4.000000</td>
      <td>3.00000</td>
      <td>...</td>
      <td>8.000000</td>
      <td>6.000000</td>
      <td>49.00000</td>
      <td>3.000000</td>
      <td>4.000000</td>
      <td>6.500000</td>
      <td>29.000000</td>
      <td>30.000000</td>
      <td>7.000000</td>
      <td>3.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>455.750000</td>
      <td>6.750000</td>
      <td>1.25</td>
      <td>1.500000</td>
      <td>3.000000</td>
      <td>18.250000</td>
      <td>7.000000</td>
      <td>0.75</td>
      <td>7.500000</td>
      <td>8.75000</td>
      <td>...</td>
      <td>9.500000</td>
      <td>10.250000</td>
      <td>61.75000</td>
      <td>6.000000</td>
      <td>8.500000</td>
      <td>8.750000</td>
      <td>30.500000</td>
      <td>35.000000</td>
      <td>8.000000</td>
      <td>5.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>629.000000</td>
      <td>9.000000</td>
      <td>5.00</td>
      <td>3.000000</td>
      <td>9.000000</td>
      <td>19.000000</td>
      <td>7.000000</td>
      <td>3.00</td>
      <td>9.000000</td>
      <td>17.00000</td>
      <td>...</td>
      <td>11.000000</td>
      <td>11.000000</td>
      <td>82.00000</td>
      <td>9.000000</td>
      <td>19.000000</td>
      <td>14.000000</td>
      <td>35.000000</td>
      <td>38.000000</td>
      <td>8.000000</td>
      <td>8.000000</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 146 columns</p>
</div>



## Categorical Analysis by Products:

The analysis of the products we can see how the first 3 products that are bought the most are Lotions, wipes and cleaning products. See Table.


```python
product = pd.crosstab(df['Baby wash'], df['STATE'])
product
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
      <th>STATE</th>
      <th>0</th>
      <th>AB</th>
      <th>ACT</th>
      <th>AG</th>
      <th>AK</th>
      <th>AL</th>
      <th>AN</th>
      <th>AO</th>
      <th>AP</th>
      <th>AQ</th>
      <th>...</th>
      <th>VE</th>
      <th>VI</th>
      <th>VIC</th>
      <th>VR</th>
      <th>VT</th>
      <th>VV</th>
      <th>WA</th>
      <th>WI</th>
      <th>WV</th>
      <th>WY</th>
    </tr>
    <tr>
      <th>Baby wash</th>
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
      <th>0</th>
      <td>1511</td>
      <td>24</td>
      <td>4</td>
      <td>4</td>
      <td>11</td>
      <td>58</td>
      <td>15</td>
      <td>3</td>
      <td>15</td>
      <td>22</td>
      <td>...</td>
      <td>29</td>
      <td>24</td>
      <td>198</td>
      <td>15</td>
      <td>29</td>
      <td>28</td>
      <td>98</td>
      <td>92</td>
      <td>22</td>
      <td>13</td>
    </tr>
    <tr>
      <th>1</th>
      <td>76</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>2</td>
      <td>1</td>
      <td>0</td>
      <td>2</td>
      <td>1</td>
      <td>...</td>
      <td>2</td>
      <td>0</td>
      <td>12</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>4</td>
      <td>12</td>
      <td>0</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>2 rows × 146 columns</p>
</div>




```python
df.groupby(by="STATE").sum()
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
      <th>Baby Food</th>
      <th>Diapers</th>
      <th>Formula</th>
      <th>Lotion</th>
      <th>Baby wash</th>
      <th>Wipes</th>
      <th>Fresh Fruits</th>
      <th>Fresh Vegetables</th>
      <th>Beer</th>
      <th>Wine</th>
      <th>...</th>
      <th>Cleaning Products</th>
      <th>Condiments</th>
      <th>Frozen Foods</th>
      <th>Kitchen Items</th>
      <th>Meat</th>
      <th>Office Supplies</th>
      <th>Personal Care</th>
      <th>Pet Supplies</th>
      <th>Sea Food</th>
      <th>Spices</th>
    </tr>
    <tr>
      <th>STATE</th>
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
      <th>0</th>
      <td>96</td>
      <td>173</td>
      <td>91</td>
      <td>96</td>
      <td>76</td>
      <td>84</td>
      <td>68</td>
      <td>90</td>
      <td>95</td>
      <td>395</td>
      <td>...</td>
      <td>165</td>
      <td>408</td>
      <td>244</td>
      <td>113</td>
      <td>109</td>
      <td>103</td>
      <td>271</td>
      <td>83</td>
      <td>259</td>
      <td>352</td>
    </tr>
    <tr>
      <th>AB</th>
      <td>1</td>
      <td>2</td>
      <td>1</td>
      <td>3</td>
      <td>1</td>
      <td>2</td>
      <td>2</td>
      <td>3</td>
      <td>0</td>
      <td>7</td>
      <td>...</td>
      <td>5</td>
      <td>6</td>
      <td>3</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>5</td>
      <td>3</td>
      <td>3</td>
      <td>6</td>
    </tr>
    <tr>
      <th>ACT</th>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>1</td>
      <td>0</td>
      <td>2</td>
      <td>...</td>
      <td>1</td>
      <td>2</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>2</td>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>1</td>
    </tr>
    <tr>
      <th>AG</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>...</td>
      <td>2</td>
      <td>2</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>AK</th>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>1</td>
      <td>0</td>
      <td>4</td>
      <td>...</td>
      <td>2</td>
      <td>5</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>2</td>
      <td>4</td>
      <td>0</td>
      <td>2</td>
      <td>3</td>
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
      <th>VV</th>
      <td>3</td>
      <td>6</td>
      <td>1</td>
      <td>2</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>3</td>
      <td>7</td>
      <td>...</td>
      <td>7</td>
      <td>8</td>
      <td>4</td>
      <td>2</td>
      <td>1</td>
      <td>2</td>
      <td>4</td>
      <td>3</td>
      <td>5</td>
      <td>4</td>
    </tr>
    <tr>
      <th>WA</th>
      <td>9</td>
      <td>16</td>
      <td>6</td>
      <td>4</td>
      <td>4</td>
      <td>5</td>
      <td>6</td>
      <td>6</td>
      <td>9</td>
      <td>27</td>
      <td>...</td>
      <td>8</td>
      <td>23</td>
      <td>21</td>
      <td>3</td>
      <td>7</td>
      <td>3</td>
      <td>17</td>
      <td>4</td>
      <td>17</td>
      <td>24</td>
    </tr>
    <tr>
      <th>WI</th>
      <td>7</td>
      <td>11</td>
      <td>5</td>
      <td>7</td>
      <td>12</td>
      <td>1</td>
      <td>8</td>
      <td>6</td>
      <td>7</td>
      <td>22</td>
      <td>...</td>
      <td>10</td>
      <td>21</td>
      <td>13</td>
      <td>4</td>
      <td>9</td>
      <td>7</td>
      <td>17</td>
      <td>4</td>
      <td>14</td>
      <td>21</td>
    </tr>
    <tr>
      <th>WV</th>
      <td>1</td>
      <td>3</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>2</td>
      <td>1</td>
      <td>2</td>
      <td>1</td>
      <td>3</td>
      <td>...</td>
      <td>3</td>
      <td>7</td>
      <td>0</td>
      <td>2</td>
      <td>3</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <th>WY</th>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>...</td>
      <td>2</td>
      <td>3</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>3</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
<p>146 rows × 29 columns</p>
</div>




```python
product.describe()
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
      <th>STATE</th>
      <th>0</th>
      <th>AB</th>
      <th>ACT</th>
      <th>AG</th>
      <th>AK</th>
      <th>AL</th>
      <th>AN</th>
      <th>AO</th>
      <th>AP</th>
      <th>AQ</th>
      <th>...</th>
      <th>VE</th>
      <th>VI</th>
      <th>VIC</th>
      <th>VR</th>
      <th>VT</th>
      <th>VV</th>
      <th>WA</th>
      <th>WI</th>
      <th>WV</th>
      <th>WY</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.00000</td>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.00000</td>
      <td>2.000000</td>
      <td>2.00000</td>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>...</td>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.00000</td>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>793.500000</td>
      <td>12.500000</td>
      <td>2.50000</td>
      <td>2.000000</td>
      <td>5.500000</td>
      <td>30.00000</td>
      <td>8.000000</td>
      <td>1.50000</td>
      <td>8.500000</td>
      <td>11.500000</td>
      <td>...</td>
      <td>15.500000</td>
      <td>12.000000</td>
      <td>105.000000</td>
      <td>7.500000</td>
      <td>14.500000</td>
      <td>14.00000</td>
      <td>51.000000</td>
      <td>52.000000</td>
      <td>11.000000</td>
      <td>7.500000</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1014.698231</td>
      <td>16.263456</td>
      <td>2.12132</td>
      <td>2.828427</td>
      <td>7.778175</td>
      <td>39.59798</td>
      <td>9.899495</td>
      <td>2.12132</td>
      <td>9.192388</td>
      <td>14.849242</td>
      <td>...</td>
      <td>19.091883</td>
      <td>16.970563</td>
      <td>131.521861</td>
      <td>10.606602</td>
      <td>20.506097</td>
      <td>19.79899</td>
      <td>66.468037</td>
      <td>56.568542</td>
      <td>15.556349</td>
      <td>7.778175</td>
    </tr>
    <tr>
      <th>min</th>
      <td>76.000000</td>
      <td>1.000000</td>
      <td>1.00000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>2.00000</td>
      <td>1.000000</td>
      <td>0.00000</td>
      <td>2.000000</td>
      <td>1.000000</td>
      <td>...</td>
      <td>2.000000</td>
      <td>0.000000</td>
      <td>12.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.00000</td>
      <td>4.000000</td>
      <td>12.000000</td>
      <td>0.000000</td>
      <td>2.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>434.750000</td>
      <td>6.750000</td>
      <td>1.75000</td>
      <td>1.000000</td>
      <td>2.750000</td>
      <td>16.00000</td>
      <td>4.500000</td>
      <td>0.75000</td>
      <td>5.250000</td>
      <td>6.250000</td>
      <td>...</td>
      <td>8.750000</td>
      <td>6.000000</td>
      <td>58.500000</td>
      <td>3.750000</td>
      <td>7.250000</td>
      <td>7.00000</td>
      <td>27.500000</td>
      <td>32.000000</td>
      <td>5.500000</td>
      <td>4.750000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>793.500000</td>
      <td>12.500000</td>
      <td>2.50000</td>
      <td>2.000000</td>
      <td>5.500000</td>
      <td>30.00000</td>
      <td>8.000000</td>
      <td>1.50000</td>
      <td>8.500000</td>
      <td>11.500000</td>
      <td>...</td>
      <td>15.500000</td>
      <td>12.000000</td>
      <td>105.000000</td>
      <td>7.500000</td>
      <td>14.500000</td>
      <td>14.00000</td>
      <td>51.000000</td>
      <td>52.000000</td>
      <td>11.000000</td>
      <td>7.500000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>1152.250000</td>
      <td>18.250000</td>
      <td>3.25000</td>
      <td>3.000000</td>
      <td>8.250000</td>
      <td>44.00000</td>
      <td>11.500000</td>
      <td>2.25000</td>
      <td>11.750000</td>
      <td>16.750000</td>
      <td>...</td>
      <td>22.250000</td>
      <td>18.000000</td>
      <td>151.500000</td>
      <td>11.250000</td>
      <td>21.750000</td>
      <td>21.00000</td>
      <td>74.500000</td>
      <td>72.000000</td>
      <td>16.500000</td>
      <td>10.250000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>1511.000000</td>
      <td>24.000000</td>
      <td>4.00000</td>
      <td>4.000000</td>
      <td>11.000000</td>
      <td>58.00000</td>
      <td>15.000000</td>
      <td>3.00000</td>
      <td>15.000000</td>
      <td>22.000000</td>
      <td>...</td>
      <td>29.000000</td>
      <td>24.000000</td>
      <td>198.000000</td>
      <td>15.000000</td>
      <td>29.000000</td>
      <td>28.00000</td>
      <td>98.000000</td>
      <td>92.000000</td>
      <td>22.000000</td>
      <td>13.000000</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 146 columns</p>
</div>




```python
product0 = pd.crosstab(df['Office Supplies'], df['ORDER_TYPE']) 
product0
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
      <th>ORDER_TYPE</th>
      <th>HighValue</th>
      <th>LowValue</th>
      <th>MediumValue</th>
    </tr>
    <tr>
      <th>Office Supplies</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3661</td>
      <td>7901</td>
      <td>1433</td>
    </tr>
    <tr>
      <th>1</th>
      <td>182</td>
      <td>139</td>
      <td>417</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby(by="ORDER_TYPE").sum()
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
      <th>Baby Food</th>
      <th>Diapers</th>
      <th>Formula</th>
      <th>Lotion</th>
      <th>Baby wash</th>
      <th>Wipes</th>
      <th>Fresh Fruits</th>
      <th>Fresh Vegetables</th>
      <th>Beer</th>
      <th>Wine</th>
      <th>...</th>
      <th>Cleaning Products</th>
      <th>Condiments</th>
      <th>Frozen Foods</th>
      <th>Kitchen Items</th>
      <th>Meat</th>
      <th>Office Supplies</th>
      <th>Personal Care</th>
      <th>Pet Supplies</th>
      <th>Sea Food</th>
      <th>Spices</th>
    </tr>
    <tr>
      <th>ORDER_TYPE</th>
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
      <th>HighValue</th>
      <td>204</td>
      <td>357</td>
      <td>201</td>
      <td>179</td>
      <td>194</td>
      <td>190</td>
      <td>205</td>
      <td>194</td>
      <td>193</td>
      <td>3019</td>
      <td>...</td>
      <td>355</td>
      <td>385</td>
      <td>1891</td>
      <td>192</td>
      <td>201</td>
      <td>182</td>
      <td>2006</td>
      <td>174</td>
      <td>1920</td>
      <td>2050</td>
    </tr>
    <tr>
      <th>LowValue</th>
      <td>134</td>
      <td>288</td>
      <td>156</td>
      <td>127</td>
      <td>127</td>
      <td>145</td>
      <td>130</td>
      <td>170</td>
      <td>153</td>
      <td>0</td>
      <td>...</td>
      <td>301</td>
      <td>2430</td>
      <td>0</td>
      <td>149</td>
      <td>155</td>
      <td>139</td>
      <td>0</td>
      <td>137</td>
      <td>0</td>
      <td>155</td>
    </tr>
    <tr>
      <th>MediumValue</th>
      <td>395</td>
      <td>746</td>
      <td>414</td>
      <td>390</td>
      <td>415</td>
      <td>388</td>
      <td>420</td>
      <td>398</td>
      <td>403</td>
      <td>0</td>
      <td>...</td>
      <td>736</td>
      <td>758</td>
      <td>0</td>
      <td>439</td>
      <td>402</td>
      <td>417</td>
      <td>0</td>
      <td>410</td>
      <td>0</td>
      <td>402</td>
    </tr>
  </tbody>
</table>
<p>3 rows × 29 columns</p>
</div>




```python
product0.describe()
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
      <th>ORDER_TYPE</th>
      <th>HighValue</th>
      <th>LowValue</th>
      <th>MediumValue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.00000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1921.500000</td>
      <td>4020.000000</td>
      <td>925.00000</td>
    </tr>
    <tr>
      <th>std</th>
      <td>2460.024492</td>
      <td>5488.562836</td>
      <td>718.42049</td>
    </tr>
    <tr>
      <th>min</th>
      <td>182.000000</td>
      <td>139.000000</td>
      <td>417.00000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>1051.750000</td>
      <td>2079.500000</td>
      <td>671.00000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1921.500000</td>
      <td>4020.000000</td>
      <td>925.00000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2791.250000</td>
      <td>5960.500000</td>
      <td>1179.00000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>3661.000000</td>
      <td>7901.000000</td>
      <td>1433.00000</td>
    </tr>
  </tbody>
</table>
</div>




```python
product1 = pd.crosstab(df['Pet Supplies'], df['PURCHASE_TOUCHPOINT'])
product1
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
      <th>PURCHASE_TOUCHPOINT</th>
      <th>Desktop</th>
      <th>Phone</th>
    </tr>
    <tr>
      <th>Pet Supplies</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3370</td>
      <td>9642</td>
    </tr>
    <tr>
      <th>1</th>
      <td>282</td>
      <td>439</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby(by="PURCHASE_TOUCHPOINT").sum()
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
      <th>Baby Food</th>
      <th>Diapers</th>
      <th>Formula</th>
      <th>Lotion</th>
      <th>Baby wash</th>
      <th>Wipes</th>
      <th>Fresh Fruits</th>
      <th>Fresh Vegetables</th>
      <th>Beer</th>
      <th>Wine</th>
      <th>...</th>
      <th>Cleaning Products</th>
      <th>Condiments</th>
      <th>Frozen Foods</th>
      <th>Kitchen Items</th>
      <th>Meat</th>
      <th>Office Supplies</th>
      <th>Personal Care</th>
      <th>Pet Supplies</th>
      <th>Sea Food</th>
      <th>Spices</th>
    </tr>
    <tr>
      <th>PURCHASE_TOUCHPOINT</th>
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
      <th>Desktop</th>
      <td>306</td>
      <td>515</td>
      <td>284</td>
      <td>272</td>
      <td>275</td>
      <td>285</td>
      <td>302</td>
      <td>304</td>
      <td>285</td>
      <td>1933</td>
      <td>...</td>
      <td>536</td>
      <td>697</td>
      <td>1236</td>
      <td>322</td>
      <td>293</td>
      <td>265</td>
      <td>1269</td>
      <td>282</td>
      <td>1224</td>
      <td>1505</td>
    </tr>
    <tr>
      <th>Phone</th>
      <td>427</td>
      <td>876</td>
      <td>487</td>
      <td>424</td>
      <td>461</td>
      <td>438</td>
      <td>453</td>
      <td>458</td>
      <td>464</td>
      <td>1086</td>
      <td>...</td>
      <td>856</td>
      <td>2876</td>
      <td>655</td>
      <td>458</td>
      <td>465</td>
      <td>473</td>
      <td>737</td>
      <td>439</td>
      <td>696</td>
      <td>1102</td>
    </tr>
  </tbody>
</table>
<p>2 rows × 29 columns</p>
</div>




```python
product1.describe()
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
      <th>PURCHASE_TOUCHPOINT</th>
      <th>Desktop</th>
      <th>Phone</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>2.00000</td>
      <td>2.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1826.00000</td>
      <td>5040.500000</td>
    </tr>
    <tr>
      <th>std</th>
      <td>2183.54574</td>
      <td>6507.503707</td>
    </tr>
    <tr>
      <th>min</th>
      <td>282.00000</td>
      <td>439.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>1054.00000</td>
      <td>2739.750000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1826.00000</td>
      <td>5040.500000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2598.00000</td>
      <td>7341.250000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>3370.00000</td>
      <td>9642.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
product2 = pd.crosstab(df['Pet Supplies'], df['CREDITCARD_TYPE'])
product2
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
      <th>CREDITCARD_TYPE</th>
      <th>American Express</th>
      <th>Diners Club</th>
      <th>Discover</th>
      <th>JCB</th>
      <th>Master Card</th>
      <th>VISA</th>
    </tr>
    <tr>
      <th>Pet Supplies</th>
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
      <th>0</th>
      <td>2559</td>
      <td>2442</td>
      <td>2339</td>
      <td>2313</td>
      <td>1096</td>
      <td>2263</td>
    </tr>
    <tr>
      <th>1</th>
      <td>136</td>
      <td>133</td>
      <td>123</td>
      <td>131</td>
      <td>56</td>
      <td>142</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby(by="CREDITCARD_TYPE").sum()
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
      <th>Baby Food</th>
      <th>Diapers</th>
      <th>Formula</th>
      <th>Lotion</th>
      <th>Baby wash</th>
      <th>Wipes</th>
      <th>Fresh Fruits</th>
      <th>Fresh Vegetables</th>
      <th>Beer</th>
      <th>Wine</th>
      <th>...</th>
      <th>Cleaning Products</th>
      <th>Condiments</th>
      <th>Frozen Foods</th>
      <th>Kitchen Items</th>
      <th>Meat</th>
      <th>Office Supplies</th>
      <th>Personal Care</th>
      <th>Pet Supplies</th>
      <th>Sea Food</th>
      <th>Spices</th>
    </tr>
    <tr>
      <th>CREDITCARD_TYPE</th>
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
      <th>American Express</th>
      <td>132</td>
      <td>281</td>
      <td>139</td>
      <td>141</td>
      <td>148</td>
      <td>139</td>
      <td>146</td>
      <td>158</td>
      <td>154</td>
      <td>576</td>
      <td>...</td>
      <td>255</td>
      <td>669</td>
      <td>353</td>
      <td>155</td>
      <td>162</td>
      <td>161</td>
      <td>418</td>
      <td>136</td>
      <td>368</td>
      <td>509</td>
    </tr>
    <tr>
      <th>Diners Club</th>
      <td>155</td>
      <td>258</td>
      <td>158</td>
      <td>145</td>
      <td>125</td>
      <td>121</td>
      <td>140</td>
      <td>143</td>
      <td>141</td>
      <td>633</td>
      <td>...</td>
      <td>255</td>
      <td>693</td>
      <td>363</td>
      <td>138</td>
      <td>147</td>
      <td>138</td>
      <td>389</td>
      <td>133</td>
      <td>400</td>
      <td>544</td>
    </tr>
    <tr>
      <th>Discover</th>
      <td>117</td>
      <td>243</td>
      <td>154</td>
      <td>122</td>
      <td>145</td>
      <td>140</td>
      <td>132</td>
      <td>120</td>
      <td>132</td>
      <td>567</td>
      <td>...</td>
      <td>256</td>
      <td>656</td>
      <td>334</td>
      <td>126</td>
      <td>111</td>
      <td>137</td>
      <td>339</td>
      <td>123</td>
      <td>361</td>
      <td>433</td>
    </tr>
    <tr>
      <th>JCB</th>
      <td>134</td>
      <td>245</td>
      <td>141</td>
      <td>130</td>
      <td>116</td>
      <td>127</td>
      <td>141</td>
      <td>130</td>
      <td>122</td>
      <td>480</td>
      <td>...</td>
      <td>244</td>
      <td>630</td>
      <td>330</td>
      <td>137</td>
      <td>125</td>
      <td>122</td>
      <td>354</td>
      <td>131</td>
      <td>312</td>
      <td>431</td>
    </tr>
    <tr>
      <th>Master Card</th>
      <td>66</td>
      <td>120</td>
      <td>55</td>
      <td>48</td>
      <td>86</td>
      <td>52</td>
      <td>81</td>
      <td>68</td>
      <td>68</td>
      <td>244</td>
      <td>...</td>
      <td>107</td>
      <td>310</td>
      <td>171</td>
      <td>58</td>
      <td>62</td>
      <td>58</td>
      <td>181</td>
      <td>56</td>
      <td>151</td>
      <td>228</td>
    </tr>
    <tr>
      <th>VISA</th>
      <td>129</td>
      <td>244</td>
      <td>124</td>
      <td>110</td>
      <td>116</td>
      <td>144</td>
      <td>115</td>
      <td>143</td>
      <td>132</td>
      <td>519</td>
      <td>...</td>
      <td>275</td>
      <td>615</td>
      <td>340</td>
      <td>166</td>
      <td>151</td>
      <td>122</td>
      <td>325</td>
      <td>142</td>
      <td>328</td>
      <td>462</td>
    </tr>
  </tbody>
</table>
<p>6 rows × 29 columns</p>
</div>




```python
product2.describe()
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
      <th>CREDITCARD_TYPE</th>
      <th>American Express</th>
      <th>Diners Club</th>
      <th>Discover</th>
      <th>JCB</th>
      <th>Master Card</th>
      <th>VISA</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1347.500000</td>
      <td>1287.500000</td>
      <td>1231.000000</td>
      <td>1222.000000</td>
      <td>576.000000</td>
      <td>1202.500000</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1713.319731</td>
      <td>1632.709558</td>
      <td>1566.948627</td>
      <td>1542.906997</td>
      <td>735.391052</td>
      <td>1499.773483</td>
    </tr>
    <tr>
      <th>min</th>
      <td>136.000000</td>
      <td>133.000000</td>
      <td>123.000000</td>
      <td>131.000000</td>
      <td>56.000000</td>
      <td>142.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>741.750000</td>
      <td>710.250000</td>
      <td>677.000000</td>
      <td>676.500000</td>
      <td>316.000000</td>
      <td>672.250000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1347.500000</td>
      <td>1287.500000</td>
      <td>1231.000000</td>
      <td>1222.000000</td>
      <td>576.000000</td>
      <td>1202.500000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>1953.250000</td>
      <td>1864.750000</td>
      <td>1785.000000</td>
      <td>1767.500000</td>
      <td>836.000000</td>
      <td>1732.750000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>2559.000000</td>
      <td>2442.000000</td>
      <td>2339.000000</td>
      <td>2313.000000</td>
      <td>1096.000000</td>
      <td>2263.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
product3 = pd.crosstab(df['Beer'], df['GenderCode'])
product3
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
      <th>GenderCode</th>
      <th>Master.</th>
      <th>Miss.</th>
      <th>Mr.</th>
      <th>Mrs.</th>
    </tr>
    <tr>
      <th>Beer</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>403</td>
      <td>410</td>
      <td>5656</td>
      <td>6515</td>
    </tr>
    <tr>
      <th>1</th>
      <td>15</td>
      <td>24</td>
      <td>337</td>
      <td>373</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby(by="GenderCode").sum()
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
      <th>Baby Food</th>
      <th>Diapers</th>
      <th>Formula</th>
      <th>Lotion</th>
      <th>Baby wash</th>
      <th>Wipes</th>
      <th>Fresh Fruits</th>
      <th>Fresh Vegetables</th>
      <th>Beer</th>
      <th>Wine</th>
      <th>...</th>
      <th>Cleaning Products</th>
      <th>Condiments</th>
      <th>Frozen Foods</th>
      <th>Kitchen Items</th>
      <th>Meat</th>
      <th>Office Supplies</th>
      <th>Personal Care</th>
      <th>Pet Supplies</th>
      <th>Sea Food</th>
      <th>Spices</th>
    </tr>
    <tr>
      <th>GenderCode</th>
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
      <th>Master.</th>
      <td>22</td>
      <td>37</td>
      <td>25</td>
      <td>19</td>
      <td>19</td>
      <td>27</td>
      <td>26</td>
      <td>20</td>
      <td>15</td>
      <td>79</td>
      <td>...</td>
      <td>42</td>
      <td>137</td>
      <td>45</td>
      <td>32</td>
      <td>20</td>
      <td>18</td>
      <td>48</td>
      <td>18</td>
      <td>45</td>
      <td>68</td>
    </tr>
    <tr>
      <th>Miss.</th>
      <td>20</td>
      <td>42</td>
      <td>29</td>
      <td>30</td>
      <td>26</td>
      <td>18</td>
      <td>28</td>
      <td>29</td>
      <td>24</td>
      <td>89</td>
      <td>...</td>
      <td>43</td>
      <td>122</td>
      <td>53</td>
      <td>28</td>
      <td>17</td>
      <td>25</td>
      <td>51</td>
      <td>23</td>
      <td>53</td>
      <td>61</td>
    </tr>
    <tr>
      <th>Mr.</th>
      <td>319</td>
      <td>610</td>
      <td>339</td>
      <td>318</td>
      <td>320</td>
      <td>294</td>
      <td>317</td>
      <td>316</td>
      <td>337</td>
      <td>1326</td>
      <td>...</td>
      <td>634</td>
      <td>1508</td>
      <td>840</td>
      <td>322</td>
      <td>328</td>
      <td>318</td>
      <td>898</td>
      <td>314</td>
      <td>836</td>
      <td>1152</td>
    </tr>
    <tr>
      <th>Mrs.</th>
      <td>372</td>
      <td>702</td>
      <td>378</td>
      <td>329</td>
      <td>371</td>
      <td>384</td>
      <td>384</td>
      <td>397</td>
      <td>373</td>
      <td>1525</td>
      <td>...</td>
      <td>673</td>
      <td>1806</td>
      <td>953</td>
      <td>398</td>
      <td>393</td>
      <td>377</td>
      <td>1009</td>
      <td>366</td>
      <td>986</td>
      <td>1326</td>
    </tr>
  </tbody>
</table>
<p>4 rows × 29 columns</p>
</div>




```python
product3.describe()
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
      <th>GenderCode</th>
      <th>Master.</th>
      <th>Miss.</th>
      <th>Mr.</th>
      <th>Mrs.</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.00000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>209.000000</td>
      <td>217.000000</td>
      <td>2996.500000</td>
      <td>3444.00000</td>
    </tr>
    <tr>
      <th>std</th>
      <td>274.357431</td>
      <td>272.943218</td>
      <td>3761.100969</td>
      <td>4343.04985</td>
    </tr>
    <tr>
      <th>min</th>
      <td>15.000000</td>
      <td>24.000000</td>
      <td>337.000000</td>
      <td>373.00000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>112.000000</td>
      <td>120.500000</td>
      <td>1666.750000</td>
      <td>1908.50000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>209.000000</td>
      <td>217.000000</td>
      <td>2996.500000</td>
      <td>3444.00000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>306.000000</td>
      <td>313.500000</td>
      <td>4326.250000</td>
      <td>4979.50000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>403.000000</td>
      <td>410.000000</td>
      <td>5656.000000</td>
      <td>6515.00000</td>
    </tr>
  </tbody>
</table>
</div>




```python
product4 = pd.crosstab(df['Lotion'], df['GENERATION'])
product4
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
      <th>GENERATION</th>
      <th>Baby_Boomers</th>
      <th>Gen_X</th>
      <th>Gen_Y</th>
      <th>Gen_Z</th>
    </tr>
    <tr>
      <th>Lotion</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>4933</td>
      <td>1815</td>
      <td>3343</td>
      <td>2946</td>
    </tr>
    <tr>
      <th>1</th>
      <td>226</td>
      <td>30</td>
      <td>149</td>
      <td>291</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby(by="GENERATION").sum()
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
      <th>Baby Food</th>
      <th>Diapers</th>
      <th>Formula</th>
      <th>Lotion</th>
      <th>Baby wash</th>
      <th>Wipes</th>
      <th>Fresh Fruits</th>
      <th>Fresh Vegetables</th>
      <th>Beer</th>
      <th>Wine</th>
      <th>...</th>
      <th>Cleaning Products</th>
      <th>Condiments</th>
      <th>Frozen Foods</th>
      <th>Kitchen Items</th>
      <th>Meat</th>
      <th>Office Supplies</th>
      <th>Personal Care</th>
      <th>Pet Supplies</th>
      <th>Sea Food</th>
      <th>Spices</th>
    </tr>
    <tr>
      <th>GENERATION</th>
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
      <th>Baby_Boomers</th>
      <td>272</td>
      <td>479</td>
      <td>254</td>
      <td>226</td>
      <td>237</td>
      <td>233</td>
      <td>260</td>
      <td>265</td>
      <td>261</td>
      <td>1789</td>
      <td>...</td>
      <td>482</td>
      <td>1213</td>
      <td>1131</td>
      <td>286</td>
      <td>276</td>
      <td>254</td>
      <td>1189</td>
      <td>240</td>
      <td>1120</td>
      <td>1383</td>
    </tr>
    <tr>
      <th>Gen_X</th>
      <td>23</td>
      <td>63</td>
      <td>45</td>
      <td>30</td>
      <td>31</td>
      <td>35</td>
      <td>31</td>
      <td>32</td>
      <td>34</td>
      <td>0</td>
      <td>...</td>
      <td>81</td>
      <td>549</td>
      <td>0</td>
      <td>31</td>
      <td>30</td>
      <td>25</td>
      <td>0</td>
      <td>37</td>
      <td>0</td>
      <td>30</td>
    </tr>
    <tr>
      <th>Gen_Y</th>
      <td>164</td>
      <td>312</td>
      <td>151</td>
      <td>149</td>
      <td>165</td>
      <td>142</td>
      <td>148</td>
      <td>158</td>
      <td>155</td>
      <td>352</td>
      <td>...</td>
      <td>284</td>
      <td>987</td>
      <td>227</td>
      <td>165</td>
      <td>159</td>
      <td>156</td>
      <td>235</td>
      <td>146</td>
      <td>234</td>
      <td>371</td>
    </tr>
    <tr>
      <th>Gen_Z</th>
      <td>274</td>
      <td>537</td>
      <td>321</td>
      <td>291</td>
      <td>303</td>
      <td>313</td>
      <td>316</td>
      <td>307</td>
      <td>299</td>
      <td>878</td>
      <td>...</td>
      <td>545</td>
      <td>824</td>
      <td>533</td>
      <td>298</td>
      <td>293</td>
      <td>303</td>
      <td>582</td>
      <td>298</td>
      <td>566</td>
      <td>823</td>
    </tr>
  </tbody>
</table>
<p>4 rows × 29 columns</p>
</div>




```python
product4.describe()
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
      <th>GENERATION</th>
      <th>Baby_Boomers</th>
      <th>Gen_X</th>
      <th>Gen_Y</th>
      <th>Gen_Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.000000</td>
      <td>2.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>2579.500000</td>
      <td>922.500000</td>
      <td>1746.000000</td>
      <td>1618.500000</td>
    </tr>
    <tr>
      <th>std</th>
      <td>3328.351619</td>
      <td>1262.185604</td>
      <td>2258.499059</td>
      <td>1877.368504</td>
    </tr>
    <tr>
      <th>min</th>
      <td>226.000000</td>
      <td>30.000000</td>
      <td>149.000000</td>
      <td>291.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>1402.750000</td>
      <td>476.250000</td>
      <td>947.500000</td>
      <td>954.750000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>2579.500000</td>
      <td>922.500000</td>
      <td>1746.000000</td>
      <td>1618.500000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>3756.250000</td>
      <td>1368.750000</td>
      <td>2544.500000</td>
      <td>2282.250000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>4933.000000</td>
      <td>1815.000000</td>
      <td>3343.000000</td>
      <td>2946.000000</td>
    </tr>
  </tbody>
</table>
</div>



# Model


Regression analysis is supervised machine learning, this model helps to see the relationship between a certain number of features and target variable. Also,  Logistic Regression the probability of some events is represented as a linear function of combination of predictor variables, but no required linear relationship between dependent and independent variables. These variables can be represented in the binary values (0 0r one, False or True). With sigmoid function we can do the value of range 0 to 1.



Prepared categorical data:

Normalize is the process creating tables and establishing relationships between those tables according to rules designed both to protect the data and to make the database more flexible by eliminating redundancy and inconsistent dependency.

Train dataset that use samples to create the model, and validation that is used to qualify performance.

Features and target 

steps to create the model, in case I did Logistic Regression.


```python
df['GenderCode'].value_counts(normalize=True) #Normalize the dataset.
df['GenderCode'].describe()
```




    count     13733
    unique        4
    top        Mrs.
    freq       6888
    Name: GenderCode, dtype: object




```python
product_df = df.copy() #Prepared the dataset to partition.
train_set = product_df.sample(frac=0.75, random_state=0)
test_set  = product_df.drop(train_set.index)

print('training set')
print(train_set)
print('\nOriginal DataFrame')
```

    training set
          GenderCode STATE   CREDITCARD_TYPE PURCHASE_TOUCHPOINT   ORDER_TYPE  \
    3569        Mrs.     0          Discover               Phone  MediumValue   
    12654        Mr.    CA          Discover               Phone     LowValue   
    5455        Mrs.    PG  American Express               Phone  MediumValue   
    13037        Mr.    CA       Diners Club             Desktop     LowValue   
    7628         Mr.     0               JCB               Phone  MediumValue   
    ...          ...   ...               ...                 ...          ...   
    9280        Mrs.    CA          Discover               Phone    HighValue   
    12280       Mrs.    CA  American Express             Desktop  MediumValue   
    8524        Mrs.    CA          Discover               Phone     LowValue   
    4646         Mr.     0               JCB             Desktop  MediumValue   
    4569        Mrs.    MO       Diners Club               Phone     LowValue   
    
             GENERATION  Baby Food  Diapers  Formula  Lotion  ...  \
    3569          Gen_Y          0        0        0       0  ...   
    12654         Gen_X          0        0        0       0  ...   
    5455          Gen_Z          0        0        0       0  ...   
    13037         Gen_Z          0        0        0       0  ...   
    7628          Gen_Y          0        1        0       0  ...   
    ...             ...        ...      ...      ...     ...  ...   
    9280          Gen_Z          0        0        0       0  ...   
    12280  Baby_Boomers          0        1        0       1  ...   
    8524          Gen_Y          0        0        0       0  ...   
    4646          Gen_Z          1        0        0       0  ...   
    4569   Baby_Boomers          0        0        0       0  ...   
    
           Cleaning Products  Condiments  Frozen Foods  Kitchen Items  Meat  \
    3569                   0           0             0              1     0   
    12654                  0           0             0              0     1   
    5455                   1           0             0              1     1   
    13037                  0           1             0              0     0   
    7628                   1           1             0              0     0   
    ...                  ...         ...           ...            ...   ...   
    9280                   0           0             0              0     0   
    12280                  1           0             0              0     0   
    8524                   0           1             0              0     0   
    4646                   0           1             0              0     0   
    4569                   0           0             0              0     0   
    
           Office Supplies  Personal Care  Pet Supplies  Sea Food  Spices  
    3569                 0              0             0         0       0  
    12654                0              0             0         0       1  
    5455                 0              0             1         0       1  
    13037                0              0             0         0       0  
    7628                 0              0             1         0       0  
    ...                ...            ...           ...       ...     ...  
    9280                 0              1             0         1       0  
    12280                1              0             0         0       0  
    8524                 0              0             0         0       0  
    4646                 0              0             0         0       0  
    4569                 0              0             0         0       0  
    
    [10300 rows x 35 columns]
    
    Original DataFrame



```python
target = 'Lotion'  #create the target and train set.
y_train = train_set[target]
y_train.value_counts(normalize=True)
```




    0    0.950485
    1    0.049515
    Name: Lotion, dtype: float64




```python
from sklearn.linear_model import LogisticRegressionCV
from sklearn.model_selection import train_test_split

linear_reg = LogisticRegressionCV() #create the model.
train_set, val = train_test_split(train_set, random_state=42)
train_set.shape, val.shape
```




    ((7725, 35), (2575, 35))




```python
#create the features by products.
features = ['Baby Food', 'Diapers', 'Formula', 
       'Baby wash', 'Wipes', 'Fresh Fruits', 'Fresh Vegetables', 'Beer',
       'Wine', 'Club Soda', 'Sports Drink', 'Chips', 'Popcorn', 'Oatmeal',
       'Medicines', 'Canned Foods', 'Cigarettes', 'Cheese',
       'Cleaning Products', 'Condiments', 'Frozen Foods', 'Kitchen Items',
       'Meat', 'Office Supplies', 'Personal Care', 'Pet Supplies', 'Sea Food',
       'Spices']
```


```python
X_train = train_set[features] #create train set ann validation.
y_train = train_set[target]
X_val = val[features]
y_val = val[target]
```

## Logistic Regression Model

To Analysis the model, we use Logistic Regression that is a linear model where Y is the dependent variable, X represents the independent variables, B is the regression coefficients to be estimated, and e represents the errors are residuals. 


```python
from sklearn.impute import SimpleImputer
from sklearn.linear_model import LogisticRegressionCV
from sklearn.preprocessing import StandardScaler

imputer = SimpleImputer () #impute missiing values
X_train_imputed = imputer.fit_transform(X_train)
X_val_imputed = imputer.transform(X_val)

scaler = StandardScaler() #Scaler and  fit
X_train_scaled = scaler.fit_transform(X_train_imputed)
X_val_scaled = scaler.transform(X_val_imputed)

model = LogisticRegressionCV(cv=5, n_jobs=1, random_state=42) #Fit the Model
model.fit(X_train_scaled, y_train)
print('Validation Accuracy', model.score(X_val_scaled, y_val)) #Model performance indicators that is not overfitting. 
```

    Validation Accuracy 0.9518446601941748



```python
sns.lmplot(x='Beer', y=target, data=df, scatter_kws={'alpha':0.05}); #Graphic compared two products Lotions and beer: in all this products the lotion has high preference in the customers.
```


![png](output_112_0.png)



```python
from sklearn.preprocessing import MinMaxScaler
scaler = MinMaxScaler()

df_scaler = df[df.columns[6:]].copy()
```


```python
df_scaled = pd.DataFrame(data=scaler.fit_transform(df_scaler), columns=df_scaler.columns)
```


```python
df_scaled.describe()
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
      <th>Baby Food</th>
      <th>Diapers</th>
      <th>Formula</th>
      <th>Lotion</th>
      <th>Baby wash</th>
      <th>Wipes</th>
      <th>Fresh Fruits</th>
      <th>Fresh Vegetables</th>
      <th>Beer</th>
      <th>Wine</th>
      <th>...</th>
      <th>Cleaning Products</th>
      <th>Condiments</th>
      <th>Frozen Foods</th>
      <th>Kitchen Items</th>
      <th>Meat</th>
      <th>Office Supplies</th>
      <th>Personal Care</th>
      <th>Pet Supplies</th>
      <th>Sea Food</th>
      <th>Spices</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>...</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
      <td>13733.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>0.053375</td>
      <td>0.101289</td>
      <td>0.056142</td>
      <td>0.050681</td>
      <td>0.053594</td>
      <td>0.052647</td>
      <td>0.054977</td>
      <td>0.055487</td>
      <td>0.054540</td>
      <td>0.219835</td>
      <td>...</td>
      <td>0.101362</td>
      <td>0.260176</td>
      <td>0.137698</td>
      <td>0.056797</td>
      <td>0.055196</td>
      <td>0.053739</td>
      <td>0.146072</td>
      <td>0.052501</td>
      <td>0.139809</td>
      <td>0.189835</td>
    </tr>
    <tr>
      <th>std</th>
      <td>0.224788</td>
      <td>0.301722</td>
      <td>0.230204</td>
      <td>0.219353</td>
      <td>0.225222</td>
      <td>0.223336</td>
      <td>0.227944</td>
      <td>0.228936</td>
      <td>0.227089</td>
      <td>0.414150</td>
      <td>...</td>
      <td>0.301818</td>
      <td>0.438747</td>
      <td>0.344595</td>
      <td>0.231464</td>
      <td>0.228370</td>
      <td>0.225510</td>
      <td>0.353191</td>
      <td>0.223044</td>
      <td>0.346802</td>
      <td>0.392185</td>
    </tr>
    <tr>
      <th>min</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>...</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 29 columns</p>
</div>




```python
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import plot_confusion_matrix

X_train, X_test, y_train, y_test = train_test_split(df_scaled.iloc[:,:-1], df_scaled.iloc[:,-1:], test_size=0.2, random_state=0)
clf = LogisticRegression(C=10).fit(X_train, y_train)
```


```python
clf.score(X_test, y_test)
```




    0.8248998907899526




```python
from sklearn.metrics import balanced_accuracy_score


y_pred = clf.predict(X_test)
balanced_accuracy_score(y_test, y_pred)
```




    0.658039950062422




```python
def conf_matrix(clf):
    disp = plot_confusion_matrix(clf, X_test, y_test,
                                display_labels= ['Spend', 'Saved'],
                                cmap=plt.cm.Blues,
                                normalize='true')
    disp.ax_.set_title('Normalized Confusion Matrix');
    disp.ax_.grid()
conf_matrix(clf)
```


![png](output_119_0.png)



```python
from sklearn.model_selection import GridSearchCV
from sklearn.metrics import roc_auc_score

grid_values = {'C': [10, 100, 1000, 5000, 10000, 12000, 16000, 20000]}
grid_clf = LogisticRegression()

grid_clf = GridSearchCV(grid_clf, param_grid = grid_values, scoring= 'balanced_accuracy')
grid_clf.fit(X_train, y_train)
y_pred = grid_clf.predict(X_test)
print('Grid Best Parameter(max. balanced_accurracy):', grid_clf.best_params_)
print('Grid Best Score(balanced_accuracy)', grid_clf.best_score_)
```

    Grid Best Parameter(max. balanced_accurracy): {'C': 10}
    Grid Best Score(balanced_accuracy) 0.662179770545524



```python
conf_matrix(grid_clf)
```


![png](output_121_0.png)


# EVALUATION

# Report validation MAE and R2
# MAE = (1/n) * Σ|yi – xi|


```python
!pip install category_encoders
```

    Collecting category_encoders
      Using cached category_encoders-2.2.2-py2.py3-none-any.whl (80 kB)
    Collecting pandas>=0.21.1
      Using cached pandas-1.2.3-cp37-cp37m-manylinux1_x86_64.whl (9.9 MB)
    Collecting numpy>=1.14.0
      Using cached numpy-1.20.2-cp37-cp37m-manylinux2010_x86_64.whl (15.3 MB)
    Collecting scikit-learn>=0.20.0
      Using cached scikit_learn-0.24.1-cp37-cp37m-manylinux2010_x86_64.whl (22.3 MB)
    Collecting statsmodels>=0.9.0
      Using cached statsmodels-0.12.2-cp37-cp37m-manylinux1_x86_64.whl (9.5 MB)
    Collecting patsy>=0.5.1
      Using cached patsy-0.5.1-py2.py3-none-any.whl (231 kB)
    Collecting scipy>=1.0.0
      Using cached scipy-1.6.2-cp37-cp37m-manylinux1_x86_64.whl (27.4 MB)
    Collecting python-dateutil>=2.7.3
      Using cached python_dateutil-2.8.1-py2.py3-none-any.whl (227 kB)
    Collecting pytz>=2017.3
      Using cached pytz-2021.1-py2.py3-none-any.whl (510 kB)
    Collecting threadpoolctl>=2.0.0
      Using cached threadpoolctl-2.1.0-py3-none-any.whl (12 kB)
    Collecting joblib>=0.11
      Using cached joblib-1.0.1-py3-none-any.whl (303 kB)
    Collecting six
      Using cached six-1.15.0-py2.py3-none-any.whl (10 kB)
    [31mERROR: tensorflow 2.1.0 has requirement scipy==1.4.1; python_version >= "3", but you'll have scipy 1.6.2 which is incompatible.[0m
    [31mERROR: ibm-watson-machine-learning 1.0.38 has requirement pandas<=1.0.5, but you'll have pandas 1.2.3 which is incompatible.[0m
    Installing collected packages: six, python-dateutil, pytz, numpy, pandas, threadpoolctl, scipy, joblib, scikit-learn, patsy, statsmodels, category-encoders
    Successfully installed category-encoders-2.2.2 joblib-1.0.1 numpy-1.20.2 pandas-1.2.3 patsy-0.5.1 python-dateutil-2.8.1 pytz-2021.1 scikit-learn-0.24.1 scipy-1.6.2 six-1.15.0 statsmodels-0.12.2 threadpoolctl-2.1.0
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/patsy-0.5.1.dist-info already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/pytz-2021.1.dist-info already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/threadpoolctl.py already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/scikit_learn-0.24.1.dist-info already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/category_encoders-2.2.2.dist-info already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/pandas already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/dateutil already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/category_encoders already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/statsmodels already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/threadpoolctl-2.1.0.dist-info already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/scipy-1.6.2.dist-info already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/pytz already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/pandas-1.2.3.dist-info already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/statsmodels-0.12.2.dist-info already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/joblib already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/scipy already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/six.py already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/scikit_learn.libs already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/sklearn already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/numpy-1.20.2.dist-info already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/patsy already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/__pycache__ already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/six-1.15.0.dist-info already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/examples already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/python_dateutil-2.8.1.dist-info already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/numpy.libs already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/scipy.libs already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/joblib-1.0.1.dist-info already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/numpy already exists. Specify --upgrade to force replacement.[0m
    [33mWARNING: Target directory /home/spark/shared/user-libs/python3.7/bin already exists. Specify --upgrade to force replacement.[0m



```python
import category_encoders as ce
from sklearn.metrics import r2_score

encoder = ce.OneHotEncoder(use_cat_names=True) #Encoder and fit transform method with train set/val
X_train_encoded = encoder.fit_transform(X_train)
X_val_encoded = encoder.transform(X_val)

linear = LogisticRegressionCV() #Logistic Regression 
linear.fit(X_train_encoded, y_train)
```




    LogisticRegressionCV()




```python
import numpy as np
from sklearn.metrics import mean_squared_error
from sklearn.metrics import mean_absolute_error

y_pred_train = model.predict(X_train_encoded)
y_pred_val = model.predict(X_val_encoded)

print(f'Logistic Regression with {len(features)} features: {features}')
print('______________________________________________')
print('Train Root Mean Squared Error:', 
    np.sqrt(mean_squared_error(y_train, y_pred_train)))
print('Validation Root Mean Square Error:', 
    np.sqrt(mean_squared_error(y_val, y_pred_val)))
print('Train Mean Absolute Error:', 
    mean_absolute_error(y_train, y_pred_train))
print('Validation Mean Absolute Error:', 
    mean_absolute_error(y_val, y_pred_val))
print('Train R^2 Score:', 
    r2_score(y_train, y_pred_train))
print('Validation R^2 Score:', 
    r2_score(y_val, y_pred_val))
```

    Logistic Regression with 28 features: ['Baby Food', 'Diapers', 'Formula', 'Baby wash', 'Wipes', 'Fresh Fruits', 'Fresh Vegetables', 'Beer', 'Wine', 'Club Soda', 'Sports Drink', 'Chips', 'Popcorn', 'Oatmeal', 'Medicines', 'Canned Foods', 'Cigarettes', 'Cheese', 'Cleaning Products', 'Condiments', 'Frozen Foods', 'Kitchen Items', 'Meat', 'Office Supplies', 'Personal Care', 'Pet Supplies', 'Sea Food', 'Spices']
    ______________________________________________
    Train Root Mean Squared Error: 0.4356454999635012
    Validation Root Mean Square Error: 0.21944324962464726
    Train Mean Absolute Error: 0.18978700163844894
    Validation Mean Absolute Error: 0.048155339805825245
    Train R^2 Score: -0.23424334344455722
    Validation R^2 Score: -0.05059159526723778



```python
%matplotlib inline
import matplotlib.pyplot as plt
import seaborn as sns

for col in sorted(df.columns):
    if df[col].nunique() <= 20:
        sns.catplot(x=col, y='Lotion', data=df, kind='bar', color='yellow')
        plt.xticks(rotation=45)
        plt.show() #Graphic analysis the principal product lotioon compared with the other products and differents variance.
```


![png](output_127_0.png)



![png](output_127_1.png)



![png](output_127_2.png)



![png](output_127_3.png)



![png](output_127_4.png)



![png](output_127_5.png)



![png](output_127_6.png)



![png](output_127_7.png)



![png](output_127_8.png)



![png](output_127_9.png)



![png](output_127_10.png)



![png](output_127_11.png)



![png](output_127_12.png)



![png](output_127_13.png)



![png](output_127_14.png)



![png](output_127_15.png)



![png](output_127_16.png)



![png](output_127_17.png)



![png](output_127_18.png)



![png](output_127_19.png)



![png](output_127_20.png)



![png](output_127_21.png)



![png](output_127_22.png)



![png](output_127_23.png)



![png](output_127_24.png)



![png](output_127_25.png)



![png](output_127_26.png)



![png](output_127_27.png)



![png](output_127_28.png)



![png](output_127_29.png)



![png](output_127_30.png)



![png](output_127_31.png)



![png](output_127_32.png)



![png](output_127_33.png)


### Analysis:

Logistic regression we analysis differents features in this dataset, the principal product the customer expense their money are the lotions, even in comparison that beer, cigarettes, and medicine if went be compared way to pay,  we can see that Diners Club is the credit card with the principal move in sales of Lotions,  followed by American Express.

Compared the Lotion versus Cheese the customers have the same level to buy of preference at the time acquire this product.

If we Compared the Lotion by generations, and see who the expense more in these items, and is the generation Z(born after 1997) -that will be the most target to sale this type of products-.

The genders are Miss and Mr. 

In the order type medium value is the quantity of money the customer expend. the preference most representative to buy Lotion is directly in the stores (desktop).


# Calculate Negative Mean Absolute Error


```python
import category_encoders as ce
from sklearn.feature_selection import f_regression, SelectKBest
from sklearn.linear_model import Ridge
from scipy.stats import randint, uniform
from sklearn.pipeline import make_pipeline
from sklearn.model_selection import cross_val_score

pipeline = make_pipeline(
    ce.OneHotEncoder(use_cat_names=True), 
    SimpleImputer(strategy='mean'), 
    StandardScaler(), 
    SelectKBest(f_regression, k=20), 
    Ridge(alpha=1.0)
)
```


```python
k = 3
scores = cross_val_score(pipeline, X_train, y_train, cv=k, 
                         scoring='neg_mean_absolute_error')
```


```python
print(f'MAE for {k} folds:', -scores)
```

    MAE for 3 folds: [0.17884946 0.17892547 0.18024867]



```python
-scores.mean()
```




    0.17934119691805192




```python
plt.figure(figsize=(8,12)) #the customer that expend more money in beer are who used Master card following by American Express.
df.groupby('CREDITCARD_TYPE')['Beer'].mean().sort_values().plot.barh();
```


![png](output_134_0.png)



```python
%matplotlib inline
coefficients = pd.Series(model.coef_[0], features)
coefficients.sort_values().plot.barh();
```


![png](output_135_0.png)



```python
%matplotlib inline
coefficients.sort_values().plot.barh(color='magenta', figsize=(7,20));
```


![png](output_136_0.png)


### Analysis:

if we remove the Lotion the model show us that the product where customer expend more money are cleaning products.

# Conclusion:

For market segmentation, this study represents a decision-making tool, market niche and characterization of the target market. The model showed a precision of 0.95, which shows the shareholders of the company that the actions to be taken can be supported by the best-selling products, the community to which it will be offered, and the age range.We can conclude that the baby boomers generation continues to be in force since they exceed the other generations in quantity, who when buying do not repair how much to spend or what they spend, that hygiene products and fragrances are a market to enter. On the other hand, generation Z has changed the way of acquiring products and this leads to not depending on physical locations for the sale of products, but when it comes to lotions and everything in this category, physical facilities are required.
