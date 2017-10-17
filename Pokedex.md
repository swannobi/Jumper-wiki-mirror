# Pokedex Plugin Wiki

# Special Thanks
Special thanks to Claire on discord for their hard work and dedication. Claire searched through over 800 Pokémon + forms/colors/megas/variants. Without their help and passion, tons and tons of bugs would have taken forever to fix and the pokedex cog would have stayed in the mess of regex hell. Thank you!

## Table of Contents
 - [Overview](https://github.com/Redjumpman/Jumper-Cogs/wiki/Pokedex/#overview)
 - [Features](https://github.com/Redjumpman/Jumper-Cogs/wiki/Pokedex/#features)
 - [Command List](https://github.com/Redjumpman/Jumper-Cogs/wiki/Pokedex/#command-list)
 - [Commands](https://github.com/Redjumpman/Jumper-Cogs/wiki/Pokedex/#commands)
     - [Pokedex](https://github.com/Redjumpman/Jumper-Cogs/wiki/Pokedex/#pokedex)
     - [Move Set](https://github.com/Redjumpman/Jumper-Cogs/wiki/Pokedex/#move-set)
     - [TM Set](https://github.com/Redjumpman/Jumper-Cogs/wiki/Pokedex/#tm-set)
     - [Item](https://github.com/Redjumpman/Jumper-Cogs/wiki/Pokedex/#item)
     - [Location](https://github.com/Redjumpman/Jumper-Cogs/wiki/Pokedex/#location)
 - [FAQ](https://github.com/Redjumpman/Jumper-Cogs/wiki/Pokedex/#faq)
 - [Credits](https://github.com/Redjumpman/Jumper-Cogs/wiki/Pokedex/#credits)
 

## Overview
Pokedex provides important and crucial information about Pokémon to your discord server. A pokedex search will give you base stats, resistances/weaknesses, abilities, and more. Important information, such as abilities, are hyperlinked to take you to Bulbapedia for more information. This cog also provides information on move sets, TM learn sets, item information, and where to catch specific Pokémon.

Pokedex was the first plugin I worked on for Red bot. It has gone through many iterations since it was first written and holds a special place in my heart. Without this cog, I may not have learned Python or made anything else for Red.

## Features
* Pokedex information
* Pokedex supports Aolola, Forms, Megas, Colors, and Variants  
* TM Learn Set Searches
* Search For Items
* Catch Locations
* Move Set Information

## Command List

| Commands         | Description                                          |
|------------------|------------------------------------------------------|
| pokedex          | Search for information on a Pokémon                  |
| pokemon item     | Get a description of an item in the Pokémon universe |
| pokemon location | Get a Pokémon's catch location                       |
| pokemon moves    | Search for a Pokémon's move set                      |
| pokemon tmset    | Search for a Pokémon's learn set                     |
| pokemon version  | Display the Pokedex cog's version                    |

## Commands

### Pokedex
`[p]pokedex <pokemon>`

**NOTE: The bot must have permission to send embedded text for this command to function.**
This command uses a custom csv file included in your data/pokedex/ folder to output this data.
The file, pokemon.csv, MUST be in the folder for this command to work properly.
A dash should be used when denoting a mega, alola, form, color, or variant.
This commmand is not case sensitive. All hyperlinks will take you to Bulbapedia for the 
appropriate information. A Pokémon's primary type will determine the embed's color. This command also has
a built in alias set to dex.

Finally, the stats displayed are based on the generation it was introduced. The stats of many older Pokémon,
such as Alakazam, have received multiple stat adjustments over the course of several generations. Please
refer to their respective Bulbapedia page for more information.
 
**Examples:**    
Regular:    [p]pokedex pikachu  
Megas:      [p]pokedex charizard-mega y  
Alola:      [p]pokedex geodude-alola  
Forms:      [p]pokedex hoopa-unbound  
Variants:   [p]pokedex floette-orange  

Displays the following information in an embed:  
* Name, ID  
* Japanese Name  
* Species  
* Stats  
* Types  
* Resistances/Weaknesses  
* Abilities  
* Flavor Text  
* Pokémon Image  

![](https://i.gyazo.com/9ae575866b0e4ed4eabdfc8ee621a95f.png)

### Move Set
`[p]pokemon moves <pokemon>`

Returns the set of moves a Pokémon learns as it levels up. Also displays the versions corresponding to that generation. generation should be expressed in dash number notation. For example, `[p]pokemon moves entei-4`. When a generation is not specified, the output will display the first generation that Pokémon appeared.

![](https://i.gyazo.com/b828b3e1135f3505a29c53c9f0f5421a.png)

### TM Set
`[p]pokemon tmset <generation> <pokemon>`

This is a list of TMs a Pokémon can learn, based on generation. The generation must be specified as a digit
1-7 or expressed as a roman numeral I-VII. If an incorrect generation is provided it will default to
generation VII. The data outputs into a markdown table.

![](https://i.gyazo.com/7843cf731fc988ee2023973d697a30c4.png)

### Item
`[p]pokemon item <pokemon>`

Retrieves the cost, item-type, effect, and image of an item. The display will result
in an embed.

![](https://i.gyazo.com/8a69320b76d44063fc9e91b5a02e8bdc.png)

### Location
`[p]pokemon location <pokemon>`

Displays the catch location/receipt of a Pokémon based on game version.
Some Pokémon, such as starters, will only display the town they are received in.
![](https://i.gyazo.com/3450fea6d461acbe46baf79fc1942977.png)

## FAQ

**Q: Why did you change the group command from pokedex to pokemon?**

_A: Typing something like `[p]pokedex pokemon charizard-mega y' is so wordy. Sure you can make an alias, but not everyone who uses my cogs understand how to make an alias. Additionally, a command is probably too wordy if you feel like it needs an alias in the first place._

**Q: Hey. Why do Pokémon like Geodude have gen I stats? Aren't we on Gen VII now?**

_A: Pokedex will display the stats based on the generation it was introduced. See [pokedex](https://github.com/Redjumpman/Jumper-Cogs/wiki/Pokedex/#pokedex)_

**Q: What do I do if I find a bug-type Pokémon in your code?**

_A: Let me know in my support channel. If you are tech savvy enough to fix it on your own, then shoot me a PR on github._

**Q: Some of the other searches kinda suck.**

_A: That's not a question! The truth hurts though. I'm working on upgrading the other features of pokedex to become more aligned with how I refactored the pokedex search. Hang in there!_

**Q: Why did it take you so long to switch to csv?**

_A: Good question. This was my first cog, and when I first started writing it the poke api was trash. Once the api became stable, it didn't quite have the information I wanted within one query. The other side of the coin is that if you had asked me 2 years ago to use csv I would not have known how to do it._

**Q: Will you be moving other searches to csv?**

_A: Yes! There is really not a good reason to be webscraping static information. If information never changes (Only need bits added every gen) csv or some other reliable storage will be preferred. Expect an upgrade in the future._

**Q: How can I help?**

_A: Report bugs, submit prs, help others, and work to help improve the experience in my support channel [here](https://discord.gg/c6HQUb7)._


## Credits
Claire - Tester  
Aikaterna - Tester  
Bulbapedia - Resource  
Pokemondb - Resource  
All information provided by this cog, within the Pokémon universe, is the intellectual property of Nintendo Co., Ltd., Creatures Inc., and Game Freak Inc.
