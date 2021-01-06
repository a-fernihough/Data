# HISCO Data for Ireland

I use the 1911 and 1901 (mainly 1911) Irish Census in my research.
The beauty of this dataset is that it contains the entire population of Ireland. The downside is that the data was entered in text and needs to be “cleaned” before you can use it in any statistical applications.
The file “hiscoireland.csv” is a concordance file that links the textual information completed by individuals in the 1911 census to a HISCO occupational code. I have also linked these codes to both the HISCLASS and HISCLASS-5 schemes. Additionally, I have also included a column showing the Connor (2019) occupational stratification. 

Variable Name  | Description 
------------- | ------------- 
occ_plain	    | Character entry for occupation
n	            | Number of people with this occupation in 1911
HISCO	        | HISCO code      
hisclass	    | HISCLASS code	
hisclass5	    | HISCLASS-5 code	
occ_group	    | Connor (2019) schema

The "occ_plain" variable in the above is the occupation entry from 1911 converted to lower case with all spaces and punctuation removed. The code is below where `occupation` is a character vector of original occupations.

```
occ_plain = gsub("[[:punct:]]", "", occupation)
occ_plain = gsub(" ", "", occ_plain)
occ_plain = tolower(occ_plain)
```


***

### References
Connor, D. (2019). The Cream of the Crop? Geography, Networks, and Irish Migrant Selection in the Age of Mass Migration. The Journal of Economic History, 79(1), 139-175. doi:10.1017/S0022050718000682

HISCO Codes: https://historyofwork.iisg.nl/index.php

HISCO to HISCLASS Conversion: https://rdrr.io/github/cedarfoundation/hisco/
