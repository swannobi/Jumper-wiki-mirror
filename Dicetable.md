### Command List

| Commands 	| Description                                	|
|----------	|--------------------------------------------	|
| d20      	| Rolls a number of d20's plus your modifier 	|
| d12      	| Rolls a number of d12's plus your modifier 	|
| d10      	| Rolls a number of d10's plus your modifier 	|
| d8       	| Rolls a number of d8's plus your modifier  	|
| d6       	| Rolls a number of d6's plus your modifier  	|
| d4       	| Rolls a number of d4's plus your modifier  	|

_Commands should start with the prefix **dicetable**_

---
####*Exceptions*
You can only roll up to 20 dice at one time. Additionally only the following can be rolled:
- d20
- d12
- d10
- d8
- d6
- d4

###Examples
**(p)dicetable (type of die) (How many dice to roll) (modifier added)**  

```<p>dicetable d20 5 1```  
**Sample Output**

    Roll #      Results    Modifier    Totals
    --------  ---------  ----------  --------
    Roll 1           14          +1        15
    Roll 2           16          +1        17
    Roll 3           20          +1        21
    Roll 4            7          +1         8
    Roll 5            4          +1         5

```<p>dicetable d12 4 0```  
**Sample Output**  

    Roll #      Results    Modifier    Totals
    --------  ---------  ----------  --------
    Roll 1            8          +0         8
    Roll 2           11          +0        11
    Roll 3            1          +0         1
    Roll 4            2          +0         2
