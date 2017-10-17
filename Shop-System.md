### Command List

**Shop Commands**  
_These commands require the **shop** prefix_

| Commands | Description                                                             |
|----------|-------------------------------------------------------------------------|
| toggle   | Opens and closes the shop                                               |
| name     | Renames the shop                                                        |
| join     | Adds you to the shop. Only need to do this once.                        |
| add      | Adds an item to the shop list. Max 100 items                            |
| buy      | Buy an item from the store list                                         |
| notify   | PM's all users with Shopkeeper role. Add this role if it does not exist |
| remove   | Removes an item from the shop list                                      |
| gift     | Send a gift in your inventory to another member                         |
| redeem   | Sends a request to redeem an item                                       |

**Pending List Commands**  
_These commands require the **pending** prefix_

| Commands  | Description                                  |
|-----------|----------------------------------------------|
| show      | Shows a list of items waiting to be redeemed |
| clear     | clear one single item from the pending list  |
| clearall  | clears all items from the pending list       |

**Individual Commands**  
_These commands do not require the shop or pending prefix_  

| Commands  | Description                             |
|-----------|-----------------------------------------|
| inventory | Shows a list of items in your inventory |
| store     | Shows a list of items for sale          |





### Introduction
This shop was designed to assist server owners who are running a game server. This system allows them to add items purchasable by points earned in Economy.py (I.E. slot games). This items can then be purchased by players, and redeemed at their leisure. What these items do, are up to the admins in their game. In a future update I may add some fun items that interact with discord, but that is not currently in development 

### Explanation
---
####Inventory
Will display any items that you are currently holding in your inventory.  

    <p>Inventory

**Sample Output:**  

    Void Staff: 
        Item Quantity: 0
        Item Name: Void Staff
    
    Frost Potion: 
        Item Quantity: 3
        Item Name: Frost Potion

####Store
Shows all the items for sale in the store

    <p>store  
  
**Sample Output:**
  
    Void Staff: 
        Item Cost: 20
        Item Name: Void Staff
    
    Frost Potion: 
        Item Cost: 10
        Item Name: Frost Potion
####Pending Show
Shows a list of pending items. Items are added to this list when a player redeems an item.  
It will include the item being redeemed and a time-stamp of when the user tried to redeem it.  
**Example:**  
If a user buys an item called "Name Change Voucher" and redeems that item, he/she will    
need to wait until an admin clears it from the list before they can redeem another.    
**Note:**   
Multiple items of the same name, cannot be redeemed at the same time.  

```<p>pending show```  

**Sample Output:**  

     <Player's User Id Here>: 
      Redjumpman: 
       Frost Potion: 
        Item Name: Frost Potion
        Time Requested: 2016-05-07 22:27:43

####Pending Clear
This should be used when you need to clear exactly one item from the pending list. If you want to 
clear all items from the pending list you should use the clear all command

```<p>pending clear Redjumpman Frost Potion```

**Sample Output**   

    Frost Potion has been cleared from pending, for Redjumpman's redeem request.

####Pending Clear All
Used when you want to clear the entire pending list. Make sure you that you are ready to use this command, because
once the pending list has been cleared, it cannot be reversed.

```<p>pending clearall```

**Sample Output**   

    Pending list now cleared.

####Shop Add
This adds an item to the shop. It is restricted to admins who have manage server rights. The syntax is <p>shop add <price> <Item Name>  

```<p>shop add <100> <Jump Potion>```

**Sample Output**   

    Red Potion has been added to the shop for purchase.

####Shop Remove
This will remove an item that was added to the shop. It is restricted to admins who have manage server rights.

```<p>shop remove <100> <Jump Potion>```

**Sample Output**  

    Jump Potion has been removed from the shop.

####Shop Buy
Allows users to buy items that were created for the shop

```<p>shop buy <Jump Potion>```

**Sample Output** 

    Jump Potion has been added to your inventory

####Shop Join
All users are required to use this command at least once. This is used to create their inventory

```<p>shop join```

**Sample Output** 

    You have joined the shop shop. You can now buy items with points.

####Shop Gift
Items that are purchased can be gifted to another user. This process cannot be reversed.

```<p>shop gift <Redjumpman> <Jump Potion> ```

**Sample Output** 

    I have gifted Jump Potion to Redjumpman's inventory

####Shop Redeem
When a user is ready to redeem an item, this will add it to the pending list

```<p>shop redeem <Jump Potion>```

**Sample Output** 

    Jump Potion has been added to pending list. Please wait for
    approval before adding more of the same item.



