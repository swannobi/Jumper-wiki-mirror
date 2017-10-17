# Casino Plugin Wiki

## Table of Contents

 - [Overview](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#overview)
 - [Features](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#features)
 - [Command List](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#command-list)
 - [Games](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#games)
     - [All-In](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#all-in)
     - [Coin](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#coin)
     - [Cups](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#cups)
     - [Dice](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#dice)
     - [Hi-Lo](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#hi-lo)
     - [War](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#war)
     - [Blackjack](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#blackjack)
 - [User Commands](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#user-commands)
     - [Balance](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#balance)
     - [Exchange](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#exchange)
     - [Info](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#info)
     - [Join](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#join)
     - [Leaderboard](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#leaderboard)
     - [Payday](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#payday)
     - [Stats](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#stats)
     - [Transfer](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#transfer)
 - [Admin Commands](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#admin-commands)
 - [Logging](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#logging)
 - [Membership Auto System](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#membership-auto-system)
 - [FAQ](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#faq)
 - [Credits](https://github.com/Redjumpman/Jumper-Cogs/wiki/Casino/#credits)
 

## Overview
I am Redjumpman and I developed Casino for Red Bot. Casino started out as a remake of a modded economy made by Spriter. I didn't like that users were unable to update a core function of Red Bot. Thus casino was born. It started out with only 4 games, and has grown to 7! The original code started out at about 300 lines, and has grown to over 2000. I hope that you enjoy using Casino as much as I have enjoyed making it for the community. My plugins will always be free and open source, so please don't hesitate to fork and make it better. All that I ask is that you credit me.

## Features
* Comes with different casino games. Blackjack, Dice, Coin, Cups, Hi-Lo, War, and All-in
* Leaderboard System
* Stats system. Track your wins/losses and more
* Customizable game settings. Change payout multipliers, min/max bets, cooldowns, and access levels
* Casino name and chip name changeable
* Membership system. Add memberships that provide player benefits to the casino and set requirements like Days on server.
* Membership auto-assign. No worries about adding memberships to players. Happens automatically and picks the best one.
* Threshold system. Set a win threshold amount that withholds the winnings if amount exceeded until you approve it.
* Logging system. Rotates to a new file every 10mb. Logs every administrative action and threshold exceed
* built-in hooks to allow you to integrate other cogs with casino!


## Command List

### Requires casino prefix
   
| Commands         	| Description                                           	| Commands         	| Description                                            	|
|------------------	|-------------------------------------------------------	|------------------	|--------------------------------------------------------	|
| approve          	| Approve a user's pending chips                        	| payday           	| Gives you some chips                                   	|
| balance          	| Shows your number of chips                            	| removemembership 	| Remove a casino membership                             	|
| createmembership 	| Add a casino membership to reward that gives benefits 	| removeuser       	| Remove a user from casino                              	|
| exchange         	| Exchange chips for credits and credits for chips      	| reset            	| Resets casino to default settings. Keeps user data     	|
| info             	| Shows information about the server casino             	| stats            	| Shows your casino play stats                           	|
| join             	| Grants you general access to the casino               	| toggle           	| Opens and closes the casino                            	|
| leaderboard      	| Displays Casino Leaderboard                           	| acctransfer      	| Transfers account data from old json. Limit 1 per user 	|
| wipe             	| Wipe casino server data                               	| version          	| Shows current Casino version                           	|
| transfer         	| Transfer chips to another user                        	| forceupdate      	| Force applies older patches                            	|
| memberships      	| Shows all memberships on the server                   	|                  	|                                                        	|

***

### Requires the setcasino prefix
   
| Commands   | Description                                    | Commands        | Description                                         |
|------------|------------------------------------------------|-----------------|-----------------------------------------------------|
| access     | Set the access level for a game. Default is 0. | name            | Sets the name of the Casino.                        |
| balance    | Sets a Casino member's chip balance            | payday          | Set the default payday amount with no membership    |
| chipname   | Sets the name of your Casino chips.            | paydaytimer     | Set the cooldown on payday                          |
| cooldown   | Set the cooldown period for casino games       | reqadd          | Add a requirement to a membership                   |
| exchange   | Sets the exchange rate for chips or credits    | reqremove       | Remove a requirement to a membership                |
| max        | Set the maximum bet to play a game             | threshold       | Sets a win amount that requires an admin to approve |
| min        | Set the minimum bet to play a game             | thresholdtoggle | Turns on a chip win limit                           |
| multiplier | Sets the payout multiplier for casino games    | transferlimit   | Limit amount of chips a user can transfer
| transfercd | Set the cooldown for transferring chips.

***

### Game Commands
   
| Commands  | Description                                                    |
|-----------|----------------------------------------------------------------|
| coin      | Bet on heads or tails                                          |
| cups      | Pick a cup that is holding the gold coin. Choose 1, 2, 3, or 4 |
| blackjack | Modified Blackjack Game                                        |
| dice      | Roll 2, 7, 11, or 12 to win                                    |
| allin     | It's all or nothing. Bets everything you have.                 |
| hilo      | Pick High, Low, Seven. Lo is < 7 Hi is > 7. 12x payout on 7    |
| war       | Modified War Card Game.                                        |

## Games

### All-In
`[p]allin <multiplier>`

All-In is an All-or-Nothing gamble. It wagers your entire chip balance. The higher the multiplier the lower your chance for success. If you use a 2 as your multiplier than your chances for success will be 1 in 4. The logic for this is a random number from 0 to multiplier + 1. If a 0 is picked then you win. Yes, the random number generating can pick 0. No this game is not rigged. This game has cannot have a threshold requirement.

### Coin
`[p]coin <choice> <bet>`

Coin is a simple coin flip game. You must pick either heads or tails as your choice. This isn't case sensitive. The outcome will randomly pick heads or tails as an outcome. This game can have a threshold requirement.

### Cups
`[p]cups <cup> <bet>`

This was modeled after a street game. There is a gold coin hiding under one of four cups. The cups are shuffled and the player may pick one. Only integers(1, 2, 3, 4) are accepted. Cannot use One or four. This game can have a threshold requirement.

### Dice
`[p]dice <bet>`

Automatically rolls the dice for you. Produces a number from a random number generator(1-12). If a 2, 7, 11, or 12 is produced the player will win.


### Hi-Lo
`[p]hilo <choice> <bet>`  
**Aliases:** hl, hi-lo  
**Choice Aliases:** High, Hi, Low, Lo, Seven, 7

Player has three choices. Pick **High** (8, 9, 10, 11, 12), **Low** (1, 2, 3, 4, 5, 6), or **Seven** (7). If the player
picks 7 and wins, they will receive their bet * multiplier * 12. The 12 is hard coded into hi-lo because I feel this is fair. There is a 1/12 chance that a seven will show up, and a player will most likely not choose 7 because the odds are low. Thus the high payout. The multiplier can still be changed, but will also affects high and Low wins.

### War
`[p]war <bet>`

War is based on the real life casino version of war. The dealer shuffles the deck and draws to cards face down. One for the player, and one for the dealer. The cards are then flipped. The higher card wins. In the result of a tie, the player has the option of going to war by typing war. 

If the player decides to go to war his/her bet is doubled and three cards are burned(discarded) from the deck. Then, two more cards are drawn. If the player's hand is greater than **or equal** then the player wins. This is important difference, because the player must be higher on the first draw, but during war they only need to equal. The player wins the war, he/she only receives a multiplier for half the bet. The rest is pushed(returned) to the player. 

If the player does not have enough credits to go to war, a player gives no response, or the player types surrender or ffs, then the player only loses half of their original bet.

### Blackjack
`[p]blackjack <bet>`  
**Aliases:** bj, 21

Originally when I created blackjack I borrowed some old code I found on the web. It didn't work properly and was super basic. After tons of modifications, and optimizations I think that it is in a good place. 

Blackjack draws 1 card face up for the dealer, and two cards face up for the player. The player may choose hit, stay, or double on their first turn. Doubling down when you do not have enough credits forces you to hit or stay. Double will double your bet, draw one card, and end the game. Choosing the stay will end the game. Choosing to hit will deal you another card face up, until you choose stay or have 21 or greater.

When the game concludes the dealer will draw cards face up until it beats your score or busts. If the outcome results in a tie the bet will be pushed (returned).

## User Commands
### Balance
`[p]casino balance`

This command shows the number of chips you have in your account. Not to be confused with the setcasino balance command that is used to set a user's chip balance.

### Exchange
`[p]casino exchange <currency> <amount>`  
_Currency must be Chips or Credits_    
_Amount must be an integer_  

Allows you exchange chips for credits and vice versa. The server default is set to a 1:1 ratio but may be changed. If an admin changed to a 13:1 ratio for chips, for example, then you will need to exchange credits in multiples of 13.

### Info
`[p]casino info`

This command will show you all the relevant user information about casino on your current server. It will show you the min/max bets for games, multipliers, their cooldowns, and access levels. Additionally, it will display the credit and chip exchange rates, and the number of people who have joined casino on that server.

### Join
`[p]casino join`

This command is required be ran by the user before participating in any of the features of casino. It will register your information into the system. If you attempt to register again, it will throw a registration error, telling you that you have already registered. By default you will receive 100 chips, all stats and cooldowns start at 0, and you start with no membership.

### Leaderboard
`[p]casino leaderboard sort=top`

Sort may be Top, Bottom, or Place.

This command displays by default the top users on the server based on chip balance. You have 3 sorting options, top, bottom, or place. Bottom will reverse the list and starts at the bottom with the least amount of chips. Place will find your place in the list and mark you in blue with brackets. When searching for your place in the leaderboard it will look like this:

![Leaderboard Place](https://i.gyazo.com/f76d309334abd9c612c74cd70ecc3668.png)

### Memberships
`[p]casino memberships`

Displays the list of memberships on the server. Will likely be expanded in a future update.

### Payday
`[p]casino payday`

Will give you a lump sum of chips, in the same way that payday works in Economy. The default amount is set to 100 and has a 1200 second cooldown. These can be changed through `setcasino` commands. A user will always receive the the default amount, unless they have a membership. Memberships can change the payday amount, but will not change the cooldown for payday. 

### Stats
`[p]casino stats`

Displays membership, chip balance, benefits from your current membership, any pending chips from games you exceeded the payout threshold on, your play/win stats for each game, and your current remaining cooldown for each game. The output will look like this:

![Casino Stats](https://i.gyazo.com/42194361fcff4cf7b0a0141226790d8d.png)

### Transfer
`[p]casino transfer <user> <amount>`

Allows you to transfer chips to another user. You can set a transfer limit by using the command `>setcasino transferlimit <amount>`. 

## Admin Commands

### Access
`[p]setcasino access <game> <access>`

The default access level for every game is set to 0. A casino user with no membership will be able to access everything by default. Optionally, you can change a game's access level with this command. Remember to set a membership with a access level high enough to access anything you may have set. If you forget what you set the access level for, simply type `[p]casino info` which will display all the access levels for games.

### Approve
`[p]casino approve <user>`

Will approve any pending chips a user has. You can review the logs to receive more details about what happened when their chips became pending. This command will fail if the user is no longer on the server.

### Balance
`[p]setcasino balance <user> <chips>`

This command will set a users balance to the number of chips specified. If the user is no longer on your server this command will not work.

### Chip Name
`[p]setcasino chipname <name>`

Will change the name of your chips. This affects most outputs that talk about chips. Default is Jump chips. Just because.

### Create Membership
`[p]casino createmembership`

***
   
**Name:**  
The name of the membership  
**Cooldown Reduction:**
  Reduces any cooldown set for games. Uses seconds, and does not affect payday timers.  
**Access Level:**  
You can set an access level will grant the ability to play a game with an access level = or less  
**Color:**   
 embed color when the player uses stats when they have this membership  
**Requirement:**   
One of four different requirements(Credits, Chips, DoS, or role) required to get this membership 

***

This command will walk you through the process of creating a membership. During this process you will create a name, payday amount, cooldown reduction, access level, color, and a requirement. You can only set one requirement during the creation process, but later you can add more using the reqadd command. Once a membership is created it will automatically be added to the list, and the auto updater will start assigning it to users who qualify. You can cancel the process any time by using your prefix + cancel. Example: `>cancel`. *Note* The auto updater is on a 5 minute rotation, so if a membership doesn't show up automagically, just give it some time to start the next cycle.

### Set Game Cooldowns
`[p]setcasino cooldown <game> <seconds>`

Game accepts any of the games: Allin, Coin, Dice, Cups, Blackjack, Hi-Lo, or War.  
The time is set in seconds, but converts to hours, minutes, and seconds respectively. This will be how long between plays a user has before they can play again.

### Exchange
`[p]setcasino exchange <rate> <currency>`  
Accepted Rate inputs: floats  **Note** This floating number will be turned into a fraction for the rate.  
Accepted currency inputs: Chips, Credits  

Sets the exchange rate for chips or credits. By default everything is set to one. It accepts floating numbers, IE 2.5, 13.2, etc. The decimal number will be converted in a fraction to show the ratio when a user initiates an exchange. Be careful when using this command. You do not want users to artificially create credits or chips on your server by washing their chips or credits back and forth.

### Force Update
`[p]casino forceupdate`

The purpose of this command is to prevent any issues that might have arose when updating to a version of casino
when a patch fails. If a patch fails to run completely, it may still report that you are using the latest version.
This could be the result of any number of factors. This command will allow you to run all of the relevant patches
to force update your JSON to match the latest version. This command does not update your casino to the latest version
on github, but applies the older patches. This command may **only** be used by the bot owner. 


### Max
`[p]setcasino max <game> <maxbet>`

Set the maximum bet for game. Works for all games except All-In. You cannot set a maximum bet that is lower than the minimum bet for the game.

### Min
`[p]setcasino min <game> <minbet>`

Set the minimum bet for game. Works for all games except All-In. Cannot set a minimum bet higher than the maximum bet for a game.

### Multiplier
`[p]setcasino multiplier <game> <multiplier>`

Sets the payout multiplier for a game, excluding All-In. The multiplier accepts floats, such as 2.5 for example.

### Name
`[p]setcasino name <name>`

Changes the default name of casino to your input.

### Payday
`[p]setcasino payday <amount>`

You can change the default amount received from a payday using this command. This will not affect memberships. If you want to change the amount someone with a membership receives from payday you will need to re-create the membership.

### Payday Timer
`[p]setcasino paydaytimer <seconds>`

Set how long a user must wait before they can receive a chip payday. This will affect users with memberships, as the cooldown reduction from a membership will not affect paydays.

### Remove Membership
`[p]casino removemembership <membership>`

This will remove a membership from the list of memberships on your server. When the auto updater function triggers (runs every 5 minutes) It will remove the membership from anyone who currently has it and award them with the next best thing, or none if they no longer qualify for any memberships.

### Remove User
`[p]casino removeuser <user>`

Will remove a user entirely from casino. This will delete all of their data. This command will prompt you to confirm before executing the command. Once deleted their data cannot be recovered!

### Requirement Add
`[p]setcasino reqadd <membership>`

This allows you to set an additional requirement for a membership. You can have one of each type: Role, DoS, Credits, and Chips. If you use this command to add the same requirement twice, it will override the previous. Please wait for the auto updater to cycle through for these changes to take affect.

### Requirement Remove
`[p]setcasino reqremove <membership>`

This removes a requirement from a membership. Please wait for the auto updater to cycle through for these changes to take affect.

### Reset
`[p]>casino reset`

Resets casino back to it's default settings without removing the users data. You will be asked to confirm that you want to perform this action before it executes.

### Threshold
`[p]setcasino threshold <threshold>`

This command will set a payout threshold. For example, if an admin sets a payout threshold of 5000 chips, than any win that exceeds 5000 chips will be with-held until an admin approves the amount. The details of the game and the pending amount can be found in the logs. The user is prompt a message letting them know that their winnings have been kept aside and that an admin will be required to release the chips. This can be done with the `[p]casino approve` command. Users should not attempt to place a bet that would yield over the threshold when an amount is still pending or their pending amount will be overridden. You can only have **ONE** set of  pending chips. 

Thresholds affect all games except All-In. This is because All-In is already an all or nothing gamble and would be extremely discouraging if a threshold was set. Thresholds do not affect win/played stats.

### Threshold Toggle
`[p]setcasino thresholdtoggle`

Toggles thresholding on/off . Make sure you set a threshold amount using `[p]setcasino threshold` before turning this feature on or else it will trigger on the default amount.

### Toggle
`[p]casino toggle`

This will open and close the casino. When the casino is closed no games can be played.

### Transfer Cooldown
`[p]setcasino transfercd <seconds>`

Set the cooldown (in Seconds) for transfer. This is used to prevent spams and scripts. There is a mandatory five second
cooldown that is set on top of any cooldown you set. This will work in-conjunction with transfer limits so you can better
moderate your server. Default is 30 seconds (+5).

### Transfer Limit
`[p]setcasino transferlimit <limit>`

Set a limit to the amount that can be transferred. This will prevent anyone who may have manipulated the system from transferring large sums at once. Set the limit with respect to those instances. Default is 1000 chips.

### Version
`[p]casino version`

Shows the current running version of casino. If you have a bug, please make sure you update casino first to make sure you are running on the current version. If the bug persists, then report it to me on my support channel or post an issue on Github.

### Wipe
`[p]casino wipe <servername>`

This will wipe a server's casino data. You can specify which server by name. You will be prompted to confirm the server you wish to delete by retyping in the server name. This data will be gone forever, so please think carefully before using this command.

## Logging
Casino supports logging administrative actions. All commands that are performed by an admin and any threshold that is exceeded will be logged. The log file will continue to grow until it reaches 10mb. It will rotate to a new file, up to 5 times, before it will stop logging. The log is saved as a .txt file and is located in the data/JumperCogs/casino folder. This cannot be turned off.

## Membership Auto System
I created an event loop which will process all users, across all servers which have casino, to determine if a user meets the requirements for the memberships on that server. It will auto-assign the membership with the highest access level to the user. If a user met all requirements for a membership previously, but doesn't when the updater runs again, it will assign them to the next highest membership or None if they don't meet any.

## FAQ
**Q: Sometimes when I try to play a game, it doesn't do anything, but eventually it works. Why?**

_A: Good question. The reason is that all games have a built-in, mandatory cooldown of five seconds. This prevents spamming and overloading the bot. This cooldown is applied before any cooldowns you set administratively._

**Q: Hey RJM, feature X in casino is not working for me. What do I do?**

_A: First start by updating casino to ensure you are on the most current version. I try to release fixes as soon as they are reported to me. You can check your version by typing `[p]casino version`. If this still doesn't resolve your issue please post an issue on github. This helps to give me a reminder that I need to work on it._

**Q: I really want to have feature X in casino. How can I get you to make it?**

_A: I am always welcome to accepting new ideas for casino. If you have a new idea post it in my support channel on the Red Cog Support server. This doesn't guarantee that I'll implement it, but if I really like it, and depending on size and scope, I'll add it._

**Q: I used casino back in the day, and I recently updated. All of my server memberships are gone!**

_A: During the localization update I implemented a breaking change. But have no fear! I made it so that people could transfer their old account to **ONE** server. Before you could access casino from any server the bot was on, now it is localized to prevent cheating, and other people messing with the settings. Once an account is transfered to a server the old data is gone. So choose which server you want to be located on wisely._

**Q: Can you add Poker?**

_A: No. Poker involves a lot of player interaction and activity which might cause some rate limitations. The best thing to do is to find a bot that only does poker._

**Q: Can you make casino global again?**

_A: No. Stop asking._

**Q: All of my users say that All-In is rigged. Is it?**

_A: OMG. No it is not rigged. It uses Linear congruential generation to determine a number from 0 to your multiplier + 1. this is expressed as X<sub>n+1</sub> = (aX<sub>n</sub> + b)mod m_

**Q: Can you make all the admin commands owner commands?**

_A: No. You can do this yourself. Casino is general purpose. Feel free to edit it, but I will not explain how to, or fix it when you mess it up._

**Q: Can I modify casino?**

_A: Yes! Fork it, twerk it, and reverse it. Build on it, PR to me if you want. All of my stuff is open source, and I encourage you to transform it into whatever you wish. Don't expect me to help you when you mess it up. I only ask that you credit me as the original author._

**Q: Will you make X output and embed?**

_A: Not everything has to be an embed. If you can code, make it an embed and show me what you got! If it looks cool I'll add it in and credit you._

**Q: Do you have any plans to translate your cogs?**

_A: I would love to have my cogs translated to a few different languages. With that said, I have never done a translation before. I have some idea of how to do it, but I'm just not there yet. In the mean time, if you are fluent in a language other than English, and would be willing to translate please send me a DM. Let me know what language you speak, and I will contact you when I begin adding in the language packs. I will make sure to credit you as the translator._

**Q: Hey RJM! How do I support you?**

_A: I love getting stars for my repo, but if you wish to contribute to me my homepage has a link to my paypal, and I'll be eternally gracious :D Keep spreading the word about Redbot with RJM's casino plugin and thank you for using it. :D_

## Credits
Special thanks to Aikaterna for always helping with tests before I deploy, without him there would be many more bugs than usual. Special thanks to Spriter for the original concept on a modded economy and a special thanks to everyone in the community who uses this cog, I really never expected so many people to use and enjoy something I wrote in my spare time. Thank you all!