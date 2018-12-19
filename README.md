# Regular Expression
## Part 1. Objective
Purchasing unit defined in the Order Report is ***Box*** and the aim is to identify how many ***Pieces*** were purchased during a specific period of time.
> **_Point 1:_** Measurement of per unit volume purchased is specified in Column ***Fruit_Name*** and denoted with parentheses.

> **_Point 2:_** People who are responsible for maintaining the Order Report may have different preferences when creating units of measure. 

| Fruit_Name_ID | Fruit_Name        | Qty_Piece |
| :---          | :---              | ---:      |
| APPL001	      | Red Delicious     |	9,600     |
| APPL002	      | Royal Gala	      | 10,080    |
| APPL003	      | Fuji	            | 15,840    |
| GRAP001	      | Golden Muscat	    | 9,000     |
| GRAP002	      | Red Globe         |	16,000    |
| KIWI001	      | Sungold Kiwifruit |	16,000    |


## Part 2. Data
### 2.1. Background Information
> ***Hierarchy of Measuring Units***

| High    | Middle   | Low                 |
| :---:   | :---:    | :---:               |
| *Box*   | *Set*    | *Piece*             |
| Qty_Box | 盒<br>組 | 顆<br>粒<br>個<br>串 |

### 2.2. Original Data
| Index  | Store   | Order | Fruit_Name_ID | Fruit_Name                     | Qty_Box |  
| :---:  | ---     | :---: | :---          | :---                           | ---:    | 
|      1 | Store 1 |     1 | APPL001       | Red Delicious (8顆 x 3)        |  100    | 
|      2 | Store 1 |     2 | APPL002       | Royal Gala (12粒 X 12盒)       |   50    |  
|      3 | Store 1 |     3 | GRAP001       | Golden Muscat (30串 * 10盒)    |   30    |  
|      4 | Store 2 |     1 | KIWI001       | Sungold Kiwifruit (4粒 x 20)   |  200    |  
|      5 | Store 3 |     1 | APPL003       | Fuji (8粒12盒)                 |  150    | 
|      6 | Store 3 |     2 | GRAP002       | Red Globe (20串 * 10組)        |   80    |  
|      7 | Store 4 |     1 | APPL002       | Royal Gala (12粒 x 12)         |   20    |  
|      8 | Store 4 |     2 | APPL003       | Fuji (6個 X 8盒)               |   30    | 
## Part 3. Outline
### 3.1. Clean Dataset
> **Data Type Conversion**
- Records in Column ***Qty_Box*** turned out to be string objects rather than numeric values because data was exported as text format in the first place. It is necessary to convert strings to numbers before proceeding further calculation.
- Tool: Python ```astype```

### 3.2. Select Data
### 3.3. Define Function
#### 3.3.1. Extract Substrings by Regular Expression 
#### 3.3.2. Convert Strings to Numeric Values
#### 3.3.3. Multiplication

### 3.3. Calculate 


## Part 4. Steps
