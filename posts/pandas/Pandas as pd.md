# Introdução

O pacote pandas é considerado por muitos o melhor pacote da linguagem de programação `python` para trabalhar com dataframes. Nesse post iremos explorar melhor o que esse pacote traz de facilidade na hora de analisarmos dados. A base de dados utilizada é disponibilizada pelo kaggle e nela temos informações sobre vacinação em diversos países.

# Desenvolvimento

Começamos importando o pacote pandas e informando como iremos chamar o pacote no decorrer do nosso código (`pd`).


```python
import pandas as pd
```

Após importação do pacote iremos fazer importação da base de dados utilizando a função `read_csv` e iremos atribuir a base de dados para o objeto `df`.


```python
df = pd.read_csv("C:/Users/Lucas/Downloads/country_vaccinations.csv")
```

Para ver se deu tudo certo na importação da base de dados podemos visualizar o começo da nossa base de dados com a função base do `python` chamada `head`. Por default vemos as primeiras 4 observações da base, mas podemos alterar o argumento de quantas obserações queremos ter como output.


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
      <th>country</th>
      <th>iso_code</th>
      <th>date</th>
      <th>total_vaccinations</th>
      <th>people_vaccinated</th>
      <th>people_fully_vaccinated</th>
      <th>daily_vaccinations_raw</th>
      <th>daily_vaccinations</th>
      <th>total_vaccinations_per_hundred</th>
      <th>people_vaccinated_per_hundred</th>
      <th>people_fully_vaccinated_per_hundred</th>
      <th>daily_vaccinations_per_million</th>
      <th>vaccines</th>
      <th>source_name</th>
      <th>source_website</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-10</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-11</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>64.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>22.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-12</td>
      <td>128.0</td>
      <td>128.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>64.0</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>NaN</td>
      <td>22.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-13</td>
      <td>188.0</td>
      <td>188.0</td>
      <td>NaN</td>
      <td>60.0</td>
      <td>63.0</td>
      <td>0.01</td>
      <td>0.01</td>
      <td>NaN</td>
      <td>22.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-14</td>
      <td>266.0</td>
      <td>266.0</td>
      <td>NaN</td>
      <td>78.0</td>
      <td>66.0</td>
      <td>0.01</td>
      <td>0.01</td>
      <td>NaN</td>
      <td>23.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
  </tbody>
</table>
</div>



Para obter informações gerais sobre a base de dados podemos utilizar a função `info` que nos retorna as informações sobre o preenchimento e a classe de cada uma das variáveis.


```python
df.info() # informações sobre a base de dados
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 3396 entries, 0 to 3395
    Data columns (total 15 columns):
     #   Column                               Non-Null Count  Dtype  
    ---  ------                               --------------  -----  
     0   country                              3396 non-null   object 
     1   iso_code                             3132 non-null   object 
     2   date                                 3396 non-null   object 
     3   total_vaccinations                   2225 non-null   float64
     4   people_vaccinated                    1833 non-null   float64
     5   people_fully_vaccinated              1186 non-null   float64
     6   daily_vaccinations_raw               1861 non-null   float64
     7   daily_vaccinations                   3264 non-null   float64
     8   total_vaccinations_per_hundred       2225 non-null   float64
     9   people_vaccinated_per_hundred        1833 non-null   float64
     10  people_fully_vaccinated_per_hundred  1186 non-null   float64
     11  daily_vaccinations_per_million       3264 non-null   float64
     12  vaccines                             3396 non-null   object 
     13  source_name                          3396 non-null   object 
     14  source_website                       3396 non-null   object 
    dtypes: float64(9), object(6)
    memory usage: 398.1+ KB
    

Se o objetivo for somente ver como as variáveis do dataframe estão nomeadas podemos chamar `df.columns` e obter essa informação.


```python
df.columns # colunas no df 
```




    Index(['country', 'iso_code', 'date', 'total_vaccinations',
           'people_vaccinated', 'people_fully_vaccinated',
           'daily_vaccinations_raw', 'daily_vaccinations',
           'total_vaccinations_per_hundred', 'people_vaccinated_per_hundred',
           'people_fully_vaccinated_per_hundred', 'daily_vaccinations_per_million',
           'vaccines', 'source_name', 'source_website'],
          dtype='object')



Quando queremos acessar a base as observações da base de dados uma a uma em uma lista podemos utilizar chamar `df.values` e obtemos uma lista com cada uma das observações separadas.


```python
df.values # mostra todas as observações 
```




    array([['Albania', 'ALB', '2021-01-10', ..., 'Pfizer/BioNTech',
            'Ministry of Health',
            'https://shendetesia.gov.al/vaksinimi-anticovid-kryhen-424-vaksinime-ne-dy-qendrat-e-vaksinimit-ne-shkoder-dhe-tirane/'],
           ['Albania', 'ALB', '2021-01-11', ..., 'Pfizer/BioNTech',
            'Ministry of Health',
            'https://shendetesia.gov.al/vaksinimi-anticovid-kryhen-424-vaksinime-ne-dy-qendrat-e-vaksinimit-ne-shkoder-dhe-tirane/'],
           ['Albania', 'ALB', '2021-01-12', ..., 'Pfizer/BioNTech',
            'Ministry of Health',
            'https://shendetesia.gov.al/vaksinimi-anticovid-kryhen-424-vaksinime-ne-dy-qendrat-e-vaksinimit-ne-shkoder-dhe-tirane/'],
           ...,
           ['Wales', nan, '2021-02-14', ...,
            'Oxford/AstraZeneca, Pfizer/BioNTech',
            'Government of the United Kingdom',
            'https://coronavirus.data.gov.uk/details/healthcare'],
           ['Wales', nan, '2021-02-15', ...,
            'Oxford/AstraZeneca, Pfizer/BioNTech',
            'Government of the United Kingdom',
            'https://coronavirus.data.gov.uk/details/healthcare'],
           ['Wales', nan, '2021-02-16', ...,
            'Oxford/AstraZeneca, Pfizer/BioNTech',
            'Government of the United Kingdom',
            'https://coronavirus.data.gov.uk/details/healthcare']],
          dtype=object)



A função `loc` é bastante útil se quisermos ter uma saída mais organizada de uma informação específica como podemos ver abaixo.


```python
df.loc[1] # um jeito mais organizado de ver uma observação 
```




    country                                                                          Albania
    iso_code                                                                             ALB
    date                                                                          2021-01-11
    total_vaccinations                                                                   NaN
    people_vaccinated                                                                    NaN
    people_fully_vaccinated                                                              NaN
    daily_vaccinations_raw                                                               NaN
    daily_vaccinations                                                                    64
    total_vaccinations_per_hundred                                                       NaN
    people_vaccinated_per_hundred                                                        NaN
    people_fully_vaccinated_per_hundred                                                  NaN
    daily_vaccinations_per_million                                                        22
    vaccines                                                                 Pfizer/BioNTech
    source_name                                                           Ministry of Health
    source_website                         https://shendetesia.gov.al/vaksinimi-anticovid...
    Name: 1, dtype: object




```python
df.loc[[1,2,3]] # pra mais de uma observação 
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
      <th>country</th>
      <th>iso_code</th>
      <th>date</th>
      <th>total_vaccinations</th>
      <th>people_vaccinated</th>
      <th>people_fully_vaccinated</th>
      <th>daily_vaccinations_raw</th>
      <th>daily_vaccinations</th>
      <th>total_vaccinations_per_hundred</th>
      <th>people_vaccinated_per_hundred</th>
      <th>people_fully_vaccinated_per_hundred</th>
      <th>daily_vaccinations_per_million</th>
      <th>vaccines</th>
      <th>source_name</th>
      <th>source_website</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-11</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>64.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>22.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-12</td>
      <td>128.0</td>
      <td>128.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>64.0</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>NaN</td>
      <td>22.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-13</td>
      <td>188.0</td>
      <td>188.0</td>
      <td>NaN</td>
      <td>60.0</td>
      <td>63.0</td>
      <td>0.01</td>
      <td>0.01</td>
      <td>NaN</td>
      <td>22.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.loc[[1,2,3],["country", "daily_vaccinations"]] # selecionando as observações e também as variáveis 
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
      <th>country</th>
      <th>daily_vaccinations</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Albania</td>
      <td>64.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Albania</td>
      <td>64.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Albania</td>
      <td>63.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.loc[1:3]
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
      <th>country</th>
      <th>iso_code</th>
      <th>date</th>
      <th>total_vaccinations</th>
      <th>people_vaccinated</th>
      <th>people_fully_vaccinated</th>
      <th>daily_vaccinations_raw</th>
      <th>daily_vaccinations</th>
      <th>total_vaccinations_per_hundred</th>
      <th>people_vaccinated_per_hundred</th>
      <th>people_fully_vaccinated_per_hundred</th>
      <th>daily_vaccinations_per_million</th>
      <th>vaccines</th>
      <th>source_name</th>
      <th>source_website</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-11</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>64.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>22.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-12</td>
      <td>128.0</td>
      <td>128.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>64.0</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>NaN</td>
      <td>22.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-13</td>
      <td>188.0</td>
      <td>188.0</td>
      <td>NaN</td>
      <td>60.0</td>
      <td>63.0</td>
      <td>0.01</td>
      <td>0.01</td>
      <td>NaN</td>
      <td>22.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.loc[1:5:2] # selecionando observações 2 a 2 
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
      <th>country</th>
      <th>iso_code</th>
      <th>date</th>
      <th>total_vaccinations</th>
      <th>people_vaccinated</th>
      <th>people_fully_vaccinated</th>
      <th>daily_vaccinations_raw</th>
      <th>daily_vaccinations</th>
      <th>total_vaccinations_per_hundred</th>
      <th>people_vaccinated_per_hundred</th>
      <th>people_fully_vaccinated_per_hundred</th>
      <th>daily_vaccinations_per_million</th>
      <th>vaccines</th>
      <th>source_name</th>
      <th>source_website</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-11</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>64.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>22.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-13</td>
      <td>188.0</td>
      <td>188.0</td>
      <td>NaN</td>
      <td>60.0</td>
      <td>63.0</td>
      <td>0.01</td>
      <td>0.01</td>
      <td>NaN</td>
      <td>22.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-15</td>
      <td>308.0</td>
      <td>308.0</td>
      <td>NaN</td>
      <td>42.0</td>
      <td>62.0</td>
      <td>0.01</td>
      <td>0.01</td>
      <td>NaN</td>
      <td>22.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
  </tbody>
</table>
</div>



Para filtramos a base de dados podemos utilizar a função `query` em que o argumento recebido por ela será uma condição de alguma das variáveis existentes no dataframe.


```python
df.query('total_vaccinations >= 1000'). head() # filtra os dados 
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
      <th>country</th>
      <th>iso_code</th>
      <th>date</th>
      <th>total_vaccinations</th>
      <th>people_vaccinated</th>
      <th>people_fully_vaccinated</th>
      <th>daily_vaccinations_raw</th>
      <th>daily_vaccinations</th>
      <th>total_vaccinations_per_hundred</th>
      <th>people_vaccinated_per_hundred</th>
      <th>people_fully_vaccinated_per_hundred</th>
      <th>daily_vaccinations_per_million</th>
      <th>vaccines</th>
      <th>source_name</th>
      <th>source_website</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>30</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-02-09</td>
      <td>1127.0</td>
      <td>689.0</td>
      <td>438.0</td>
      <td>NaN</td>
      <td>82.0</td>
      <td>0.04</td>
      <td>0.02</td>
      <td>0.02</td>
      <td>28.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
    <tr>
      <th>38</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-02-17</td>
      <td>1701.0</td>
      <td>1090.0</td>
      <td>611.0</td>
      <td>NaN</td>
      <td>72.0</td>
      <td>0.06</td>
      <td>0.04</td>
      <td>0.02</td>
      <td>25.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
    <tr>
      <th>48</th>
      <td>Andorra</td>
      <td>AND</td>
      <td>2021-02-01</td>
      <td>1036.0</td>
      <td>1036.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>66.0</td>
      <td>1.34</td>
      <td>1.34</td>
      <td>NaN</td>
      <td>854.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Government of Andorra</td>
      <td>https://www.govern.ad/comunicats/item/12423-el...</td>
    </tr>
    <tr>
      <th>57</th>
      <td>Andorra</td>
      <td>AND</td>
      <td>2021-02-10</td>
      <td>1291.0</td>
      <td>1291.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>28.0</td>
      <td>1.67</td>
      <td>1.67</td>
      <td>NaN</td>
      <td>362.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Government of Andorra</td>
      <td>https://www.govern.ad/comunicats/item/12423-el...</td>
    </tr>
    <tr>
      <th>59</th>
      <td>Andorra</td>
      <td>AND</td>
      <td>2021-02-12</td>
      <td>1622.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>68.0</td>
      <td>2.10</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>880.0</td>
      <td>Pfizer/BioNTech</td>
      <td>Government of Andorra</td>
      <td>https://www.govern.ad/comunicats/item/12423-el...</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.query('total_vaccinations >= 100000') # filtra os dados 
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
      <th>country</th>
      <th>iso_code</th>
      <th>date</th>
      <th>total_vaccinations</th>
      <th>people_vaccinated</th>
      <th>people_fully_vaccinated</th>
      <th>daily_vaccinations_raw</th>
      <th>daily_vaccinations</th>
      <th>total_vaccinations_per_hundred</th>
      <th>people_vaccinated_per_hundred</th>
      <th>people_fully_vaccinated_per_hundred</th>
      <th>daily_vaccinations_per_million</th>
      <th>vaccines</th>
      <th>source_name</th>
      <th>source_website</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>80</th>
      <td>Argentina</td>
      <td>ARG</td>
      <td>2021-01-08</td>
      <td>107542.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>10519.0</td>
      <td>0.24</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>233.0</td>
      <td>Sputnik V</td>
      <td>Ministry of Health</td>
      <td>http://datos.salud.gob.ar/dataset/vacunas-cont...</td>
    </tr>
    <tr>
      <th>85</th>
      <td>Argentina</td>
      <td>ARG</td>
      <td>2021-01-13</td>
      <td>166833.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>13323.0</td>
      <td>0.37</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>295.0</td>
      <td>Sputnik V</td>
      <td>Ministry of Health</td>
      <td>http://datos.salud.gob.ar/dataset/vacunas-cont...</td>
    </tr>
    <tr>
      <th>87</th>
      <td>Argentina</td>
      <td>ARG</td>
      <td>2021-01-15</td>
      <td>200759.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>13317.0</td>
      <td>0.44</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>295.0</td>
      <td>Sputnik V</td>
      <td>Ministry of Health</td>
      <td>http://datos.salud.gob.ar/dataset/vacunas-cont...</td>
    </tr>
    <tr>
      <th>92</th>
      <td>Argentina</td>
      <td>ARG</td>
      <td>2021-01-20</td>
      <td>247933.0</td>
      <td>243539.0</td>
      <td>4394.0</td>
      <td>NaN</td>
      <td>11586.0</td>
      <td>0.55</td>
      <td>0.54</td>
      <td>0.01</td>
      <td>256.0</td>
      <td>Sputnik V</td>
      <td>Ministry of Health</td>
      <td>http://datos.salud.gob.ar/dataset/vacunas-cont...</td>
    </tr>
    <tr>
      <th>93</th>
      <td>Argentina</td>
      <td>ARG</td>
      <td>2021-01-21</td>
      <td>265724.0</td>
      <td>249372.0</td>
      <td>16352.0</td>
      <td>17791.0</td>
      <td>11704.0</td>
      <td>0.59</td>
      <td>0.55</td>
      <td>0.04</td>
      <td>259.0</td>
      <td>Sputnik V</td>
      <td>Ministry of Health</td>
      <td>http://datos.salud.gob.ar/dataset/vacunas-cont...</td>
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
    </tr>
    <tr>
      <th>3391</th>
      <td>Wales</td>
      <td>NaN</td>
      <td>2021-02-12</td>
      <td>753669.0</td>
      <td>749445.0</td>
      <td>4224.0</td>
      <td>33715.0</td>
      <td>27743.0</td>
      <td>23.90</td>
      <td>23.77</td>
      <td>0.13</td>
      <td>8799.0</td>
      <td>Oxford/AstraZeneca, Pfizer/BioNTech</td>
      <td>Government of the United Kingdom</td>
      <td>https://coronavirus.data.gov.uk/details/health...</td>
    </tr>
    <tr>
      <th>3392</th>
      <td>Wales</td>
      <td>NaN</td>
      <td>2021-02-13</td>
      <td>776224.0</td>
      <td>771651.0</td>
      <td>4573.0</td>
      <td>22555.0</td>
      <td>26285.0</td>
      <td>24.62</td>
      <td>24.47</td>
      <td>0.15</td>
      <td>8337.0</td>
      <td>Oxford/AstraZeneca, Pfizer/BioNTech</td>
      <td>Government of the United Kingdom</td>
      <td>https://coronavirus.data.gov.uk/details/health...</td>
    </tr>
    <tr>
      <th>3393</th>
      <td>Wales</td>
      <td>NaN</td>
      <td>2021-02-14</td>
      <td>790211.0</td>
      <td>784809.0</td>
      <td>5402.0</td>
      <td>13987.0</td>
      <td>26206.0</td>
      <td>25.06</td>
      <td>24.89</td>
      <td>0.17</td>
      <td>8312.0</td>
      <td>Oxford/AstraZeneca, Pfizer/BioNTech</td>
      <td>Government of the United Kingdom</td>
      <td>https://coronavirus.data.gov.uk/details/health...</td>
    </tr>
    <tr>
      <th>3394</th>
      <td>Wales</td>
      <td>NaN</td>
      <td>2021-02-15</td>
      <td>803178.0</td>
      <td>795927.0</td>
      <td>7251.0</td>
      <td>12967.0</td>
      <td>24418.0</td>
      <td>25.47</td>
      <td>25.24</td>
      <td>0.23</td>
      <td>7745.0</td>
      <td>Oxford/AstraZeneca, Pfizer/BioNTech</td>
      <td>Government of the United Kingdom</td>
      <td>https://coronavirus.data.gov.uk/details/health...</td>
    </tr>
    <tr>
      <th>3395</th>
      <td>Wales</td>
      <td>NaN</td>
      <td>2021-02-16</td>
      <td>820339.0</td>
      <td>807351.0</td>
      <td>12988.0</td>
      <td>17161.0</td>
      <td>23033.0</td>
      <td>26.02</td>
      <td>25.61</td>
      <td>0.41</td>
      <td>7305.0</td>
      <td>Oxford/AstraZeneca, Pfizer/BioNTech</td>
      <td>Government of the United Kingdom</td>
      <td>https://coronavirus.data.gov.uk/details/health...</td>
    </tr>
  </tbody>
</table>
<p>1305 rows × 15 columns</p>
</div>



Outra funçao interessante é a `select_dtypes` em que podemos utilizá-la para fazermos uma seleção de variáveis de um único tipo de classe.


```python
df.select_dtypes(include='object') # seleciona uma classe específica das variáveis do df 
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
      <th>country</th>
      <th>iso_code</th>
      <th>date</th>
      <th>vaccines</th>
      <th>source_name</th>
      <th>source_website</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-10</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-11</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-12</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-13</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Albania</td>
      <td>ALB</td>
      <td>2021-01-14</td>
      <td>Pfizer/BioNTech</td>
      <td>Ministry of Health</td>
      <td>https://shendetesia.gov.al/vaksinimi-anticovid...</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>3391</th>
      <td>Wales</td>
      <td>NaN</td>
      <td>2021-02-12</td>
      <td>Oxford/AstraZeneca, Pfizer/BioNTech</td>
      <td>Government of the United Kingdom</td>
      <td>https://coronavirus.data.gov.uk/details/health...</td>
    </tr>
    <tr>
      <th>3392</th>
      <td>Wales</td>
      <td>NaN</td>
      <td>2021-02-13</td>
      <td>Oxford/AstraZeneca, Pfizer/BioNTech</td>
      <td>Government of the United Kingdom</td>
      <td>https://coronavirus.data.gov.uk/details/health...</td>
    </tr>
    <tr>
      <th>3393</th>
      <td>Wales</td>
      <td>NaN</td>
      <td>2021-02-14</td>
      <td>Oxford/AstraZeneca, Pfizer/BioNTech</td>
      <td>Government of the United Kingdom</td>
      <td>https://coronavirus.data.gov.uk/details/health...</td>
    </tr>
    <tr>
      <th>3394</th>
      <td>Wales</td>
      <td>NaN</td>
      <td>2021-02-15</td>
      <td>Oxford/AstraZeneca, Pfizer/BioNTech</td>
      <td>Government of the United Kingdom</td>
      <td>https://coronavirus.data.gov.uk/details/health...</td>
    </tr>
    <tr>
      <th>3395</th>
      <td>Wales</td>
      <td>NaN</td>
      <td>2021-02-16</td>
      <td>Oxford/AstraZeneca, Pfizer/BioNTech</td>
      <td>Government of the United Kingdom</td>
      <td>https://coronavirus.data.gov.uk/details/health...</td>
    </tr>
  </tbody>
</table>
<p>3396 rows × 6 columns</p>
</div>




```python
df.select_dtypes(include='float') # seleciona uma classe específica das variáveis do df 
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
      <th>total_vaccinations</th>
      <th>people_vaccinated</th>
      <th>people_fully_vaccinated</th>
      <th>daily_vaccinations_raw</th>
      <th>daily_vaccinations</th>
      <th>total_vaccinations_per_hundred</th>
      <th>people_vaccinated_per_hundred</th>
      <th>people_fully_vaccinated_per_hundred</th>
      <th>daily_vaccinations_per_million</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>64.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>22.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>128.0</td>
      <td>128.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>64.0</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>NaN</td>
      <td>22.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>188.0</td>
      <td>188.0</td>
      <td>NaN</td>
      <td>60.0</td>
      <td>63.0</td>
      <td>0.01</td>
      <td>0.01</td>
      <td>NaN</td>
      <td>22.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>266.0</td>
      <td>266.0</td>
      <td>NaN</td>
      <td>78.0</td>
      <td>66.0</td>
      <td>0.01</td>
      <td>0.01</td>
      <td>NaN</td>
      <td>23.0</td>
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
    </tr>
    <tr>
      <th>3391</th>
      <td>753669.0</td>
      <td>749445.0</td>
      <td>4224.0</td>
      <td>33715.0</td>
      <td>27743.0</td>
      <td>23.90</td>
      <td>23.77</td>
      <td>0.13</td>
      <td>8799.0</td>
    </tr>
    <tr>
      <th>3392</th>
      <td>776224.0</td>
      <td>771651.0</td>
      <td>4573.0</td>
      <td>22555.0</td>
      <td>26285.0</td>
      <td>24.62</td>
      <td>24.47</td>
      <td>0.15</td>
      <td>8337.0</td>
    </tr>
    <tr>
      <th>3393</th>
      <td>790211.0</td>
      <td>784809.0</td>
      <td>5402.0</td>
      <td>13987.0</td>
      <td>26206.0</td>
      <td>25.06</td>
      <td>24.89</td>
      <td>0.17</td>
      <td>8312.0</td>
    </tr>
    <tr>
      <th>3394</th>
      <td>803178.0</td>
      <td>795927.0</td>
      <td>7251.0</td>
      <td>12967.0</td>
      <td>24418.0</td>
      <td>25.47</td>
      <td>25.24</td>
      <td>0.23</td>
      <td>7745.0</td>
    </tr>
    <tr>
      <th>3395</th>
      <td>820339.0</td>
      <td>807351.0</td>
      <td>12988.0</td>
      <td>17161.0</td>
      <td>23033.0</td>
      <td>26.02</td>
      <td>25.61</td>
      <td>0.41</td>
      <td>7305.0</td>
    </tr>
  </tbody>
</table>
<p>3396 rows × 9 columns</p>
</div>



Uma das funções que considero mais importantes de saber utilizar na análise de dados é o `groupby` e abaixo podemos ver como é fácil a sua utilização no `python`.


```python
df.groupby(by='country').size() # agrupamento 
```




    country
    Albania                     39
    Algeria                      2
    Andorra                     19
    Anguilla                    10
    Argentina                   51
                                ..
    Turks and Caicos Islands    30
    United Arab Emirates        44
    United Kingdom              66
    United States               60
    Wales                       66
    Length: 94, dtype: int64




```python
df.groupby(by='country')['total_vaccinations_per_hundred'].mean() # agrupamento com seleção de "coluna resposta"
```




    country
    Albania                      0.017857
    Algeria                      0.000000
    Andorra                      1.465000
    Anguilla                     4.470000
    Argentina                    0.818750
                                  ...    
    Turks and Caicos Islands     8.310000
    United Arab Emirates        29.550488
    United Kingdom              12.176429
    United States                7.026304
    Wales                       11.999250
    Name: total_vaccinations_per_hundred, Length: 94, dtype: float64



Contrário ao que vemos com a função `info` que nos retorna os dados válidos, abaixo podemos ver como saber a quantidade de dados *nulos* em nosso dataframe.


```python
df.isnull().sum() # mostra a quantidade de valores ausentes por variável 
```




    country                                   0
    iso_code                                264
    date                                      0
    total_vaccinations                     1171
    people_vaccinated                      1563
    people_fully_vaccinated                2210
    daily_vaccinations_raw                 1535
    daily_vaccinations                      132
    total_vaccinations_per_hundred         1171
    people_vaccinated_per_hundred          1563
    people_fully_vaccinated_per_hundred    2210
    daily_vaccinations_per_million          132
    vaccines                                  0
    source_name                               0
    source_website                            0
    dtype: int64



Por fim, abaixo podemos ver a utilização das funções `upper` e `lower` que transforma todos os caracters de uma string para maiúsculo e tranforma todos os caracters de uma string para minúsculo, respectivamente. 


```python
df.country.str.upper().head()
```




    0    ALBANIA
    1    ALBANIA
    2    ALBANIA
    3    ALBANIA
    4    ALBANIA
    Name: country, dtype: object




```python
df.country.str.lower().head()
```




    0    albania
    1    albania
    2    albania
    3    albania
    4    albania
    Name: country, dtype: object


