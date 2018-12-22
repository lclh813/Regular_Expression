# Regular Expression
## Notice
It is possible that GitHub fails to display Jupyter Notebooks. Should such circumstances arise, please refer to ***Part 4. Steps*** listed below for code samples.

## Part 1. Objective
Purchasing unit defined in the Order Report is ***Box*** and the aim is to identify how many ***Pieces*** were purchased during a specific period of time.
> **_Point 1:_** Measurement of per unit volume purchased is specified in Column ***Fruit_Name*** and denoted with parentheses.

> **_Point 2:_** People who are responsible for maintaining the Order Report may have different preferences when creating units of measure or may include irrelevant information by accident.   

| Fruit_Name_ID | Fruit_Name        | Qty_Box       | Set/Box  | Piece/Set | Qty_Piece   |
| :---          | :---              | ---:          | ---:     | ---:      | ---:        |
| APPL001	      | Red Delicious     |	**100**       | 12       | 8         | **9,600**   |
| APPL002	      | Royal Gala	      | **50<br>20**  | 12<br>12 | 12<br>12  | **10,080**  |
| APPL003	      | Fuji	            | **150<br>30** | 12<br>8  | 8<br>6    | **15,840**  |
| GRAP001	      | Golden Muscat	    | **30**        | 10       | 30        | **9,000**   |
| GRAP002	      | Red Globe         |	**80**        | 10       | 20        | **16,000**  |
| KIWI001	      | Sungold Kiwifruit |	**200**       | 20       | 4         | **16,000**  |

## Part 2. Data
### 2.1. Background Information
> ***Info 1. Hierarchy of Measuring Units***

| High    | Middle   | Low                 |
| :---:   | :---:    | :---:               |
| *Box*   | *Set*    | *Piece*             |
| Qty_Box | 盒<br>組 | 顆<br>粒<br>個<br>串 |

> ***Info 2. Conversion Table of Chinese Numerals to Arabic***

| Arabic  | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Chinese** | **一** | **二** | **三** | **四** | **五** | **六** | **七** | **八** | **九** | **十** |

### 2.2. Original Data
> ***Data 1. Order Report***

| Index  | Store   | Order | Fruit_Name_ID | Fruit_Name                      | Qty_Box |  
| :---:  | ---     | :---: | :---          | :---                            | ---:    | 
|      1 | Store 1 |     1 | APPL001       | Red D e liciou s (八顆 x 3)      |  100    | 
|      2 | Store 1 |     2 | APPL002       | Royal Gala (12粒 X 12盒)         |   50    |
|      3 | Store 1 |     3 | APPL          | iPad Mi n i 4                   |   2     | 
|      4 | Store 1 |     4 | GRAP001       | Golden Muscat (30串 * 十盒)      |   30    | 
|      5 | Store 2 |     1 | KIWI001       | Sungold Kiwifru i t (4粒 x 20)   |  200    |  
|      6 | Store 3 |     1 | APPL003       | Fuj i (8粒十二盒)                |  150    | 
|      7 | Store 3 |     2 | GRAP002       | Red Globe (二十串 * 10 組)       |   80    | 
|      8 | Store 4 |     1 | APPL002       | Royal Gala (12  粒 x 12)         |   20    |  
|      9 | Store 4 |     2 | APPL003       | Fuji (6個 X 8 盒)                |   30    |
|     10 | Store 4 |     3 | APPL          | iPhone 8 32GB                    |   1     | 

> ***Data 2. Fruit Type and ID***

| Index  | Fruit_Type_ID  | Fruit_Type | 
| :---:  | :---           | :---       | 
|      1 | APPL           | Apple      |
|      2 | GRAP           | Grape      |
|      3 | KIWI           | Kiwifruit  |

## Part 3. Outline
### 3.1. Clean Dataset
- Select columns that are essential to further analysis and remove spaces from dataframe strings.
- Tool: Python ```replace```
### 3.2. Define Function
#### 3.2.1. Extract Substrings by Regular Expression 
- Extract numbers ***before*** units of measure or ***after*** multiplication signs.
- Tool: Python ```re.findall```
#### 3.2.2. Convert Strings to Numeric Values
- Convert strings that are Arabic numerals to integers by ```int``` and those that are Chinese numerals by adopting the concept of base-10 positional numeral system.
- Tool: Python ```int``` ```if```
#### 3.2.3. Multiplication
- Multiply values in specific columns to get the number of pieces purchased.
- Tool: Python ```lambda```

## Part 4. Steps
> [***Complete Code***](https://nbviewer.jupyter.org/github/lclh813/Regular_Expression/blob/master/6_CompleteCode.ipynb)
#### [Step 1. Import Library](https://nbviewer.jupyter.org/github/lclh813/Regular_Expression/blob/master/1_ImportLibrary.ipynb)
#### [Step 2. Import Data](https://nbviewer.jupyter.org/github/lclh813/Regular_Expression/blob/master/2_ImportData.ipynb)
#### [Step 3. Clean Datset](https://nbviewer.jupyter.org/github/lclh813/Regular_Expression/blob/master/3_CleanDataset.ipynb)
#### [Step 4. Define Function](https://nbviewer.jupyter.org/github/lclh813/Regular_Expression/blob/master/4_DefineFunction.ipynb)
#### [Step 5. Data Analysis](https://nbviewer.jupyter.org/github/lclh813/Regular_Expression/blob/master/5_DataAnalysis.ipynb)
