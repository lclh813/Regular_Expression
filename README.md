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

| High  | Middle   | Low |
| :---: | :---:  | :---: |
| *Box* | *Set* | *Piece* |
| Box   | 盒<br>組 | 顆<br>粒<br>個<br>串 |

### 2.2. Original Data
| Index  | Store   | Order | Fruit_Name_ID | Fruit_Name                   | Qty_Box |  
| :---:  | ---     | :---: | :---          | :---                         | ---:    | 
|      1 | Store 1 |     1 | APPL001       | Red Delicious（8顆＊3盒）     |  100    | 
|      2 | Store 1 |     2 | APPL002       | Royal Gala（12粒＊12盒）      |   50    |  
|      3 | Store 1 |     3 | GRAP001       | Golden Muscat（30串＊10盒）   |   30    |  
|      4 | Store 2 |     1 | KIWI001       | Sungold Kiwifruit（4粒＊20組）|  200    |  
|      5 | Store 3 |     1 | APPL003       | Fuji（8粒＊12盒）             |  150    | 
|      6 | Store 3 |     2 | GRAP002       | Red Globe（20串＊10組）       |   80    |  
|      7 | Store 4 |     1 | APPL002       | Royal Gala（12粒＊12組）      |   20    |  
|      8 | Store 4 |     2 | APPL003       | Fuji（6個＊8盒）              |   30    | 
## Part 3. Outline
## Part 4. Steps
