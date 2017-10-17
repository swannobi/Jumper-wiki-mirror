## Table of Contents

 - [Overview](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#overview)
 - [Features](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#features)
 - [Command List](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#command-list)
 - [Lottery Commands](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#lottery-commands)
     - [Delete](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#delete)
     - [Edit](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#edit)
     - [End](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#end)
     - [Enter](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#enter)
     - [Reset](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#reset)
     - [Setup](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#setup)
     - [Signup](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#signup)
     - [Start](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#start)
     - [Stats](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#stats)
     - [Status](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#status)
     - [Version](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#version)
     - [View Loadout](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#view-loadout)

 - [Set Lottery Commands](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#set-lottery-commands)
     - [Default](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#default)
     - [Role](https://github.com/Redjumpman/Jumper-Cogs/wiki/Lottery/#role)
---
## Command List

**Lottery Commands**  
*These commands require the lottery prefix*

| Commands | Description                                    | Commands    | Description                                   |
|----------|------------------------------------------------|-------------|-----------------------------------------------|
| Delete   | Deletes a lottery loadout                      | Setup       | Allows you to create custom a lottery loadout |
| Edit     | Edits a lottery loadout                        | Signup      | Signs you up to track lottery stats           |
| End      | Manually ends a lottery                        | Start       | Starts a lottery.                             |
| Enter    | Enters you into an active lottery              | Stats       | Shows your tracked lottery stats              |
| Reset    | Force resets the lottery system                | Status      | Check if a lottery is active                  |
| Version  | Shows the current installed version of lottery | Viewloadout | View the parameters set for a loadout         |
---

**Set Lottery Commands**  
*These commands require the setlottery prefix*

| Commands | Description                                         | Commands | Description                                     |
|----------|-----------------------------------------------------|----------|-------------------------------------------------|
| Default  | Changes the default loadout when starting a lottery | Role     | Sets the role required to track and view stats. |

---
## Overview
This cog was originally designed to run simple lotteries on a server. Overtime it has grown to include features such as stat tracking, a loadout system, tons of different requirements, and timers. I wanted to bridge the gap between simplicity and complexity to allow you to run quick and easy lotteries, but also offer customization options.

## Features
* Stat tracking. Track your entries and wins.
* Loadout system, create up to 5 custom tailored lotteries.
* Quickly launch any custom lottery with ease.
* Create optional timers for your lotteries to end.
* Allow for multiple winners
* Set a multitude of entry requirements such as days on server, roles, and entry limits.
* Integrates with economy so you can set a credit prize or just say what your giving away

## Lottery Commands

### Delete
`[p]lottery delete <loadout>`

Deletes a lottery loadout
This command will completely remove a lottery loadout slot.
You cannot delete the default lottery slot, 0.
This comand cannot delete a loadout being used in an active lottery.

### Edit
`[p]lottery edit <loadout>`

Edits a lottery loadout
Will allow you to edit any of the parameters attached to a
lottery loadout. Editing this loadout while it is being used
for an on-going lottery will affect the process.

![](https://i.gyazo.com/b65f331dd5d67812e7f1b443891f9067.gif)

### End
`[p]lottery end`

Manually ends a lottery. Use help on end lottery for more info
This command must be used on an active lottery that does not have a timer set 
or you will be unable to start a new lottery. This command may also be used
to end a lottery which has a timer, early using this command.     

### Enter
`[p]lottery enter`

Enters you into an active lottery
This command will attempt to add a user to a lottery.
It will fail if the there isn't a lottery on-going.
If a user enters the lottery and the entry limit is met
The lottery will begin to end in the next 10 seconds or sooner
based on timer conditions.

### Reset
`[p]lottery reset`

Force resets the lottery system.
This command does not wipe data, and should only be used if the
system is experiencing a hang.

### Setup
`[p]lottery setup`

Allows you to create custom a lottery loadout
This command allows you create a customized lottery which
you can save and launch using the lottery start command.
You can have up to five custom lottery loadouts per server.
The standard lottery is permenantly saved to slot 0.

### Signup
`[p]lottery signup`

Signs you up to track lottery stats.
You must have the required role to sign-up for stat tracking.
If you lose the role, or it changes your stats will still be tracked
and the information can be viewed when you get the role again.
By default, anyone can sign up.

### Start
`[p]lottery start [loadout]`

Starts a lottery. Use help on lottery start for more info
This command defaults to the standard lottery loadout in slot 0.
If you wish to use another loadout, specify it when calling the command.
Additionally, you may change the default loadout using the [p]setlottery default command.

Starting the lottery will apply all parameters set in the creation
process.

### Stats
`[p]lottery stats`

Shows your lottery stats. Displays the number of times you have entered
a lottery and the number of times you have won a lottery.

![](https://i.gyazo.com/dd023ad083d2efb9962d8d4d89c0c917.png)

### Status
`[p]lottery status`

Checks to see if a lottery is active and displays information about the 
current lottery prize and requirements.

### Version
`[p]lottery version`

Shows the currently running version of lottery.

### View Loadout
`[p]lottery viewloadout <loadout>`

View the parameters set for a loadout

![](https://i.gyazo.com/850bd0da2aaa9b8c756460485cf29f9b.png)



---

## Set Lottery Commands

### Default
`[p]setlottery default <loadout>`

Changes the default loadout when starting a lottery
This loadout will run when no other loadout has been specified.
In addition, this loadout will run if an invalid loadout is chosen.

If you have not setup up a loadout, use the command lottery setup.
You cannot set a loadout as a default if it has not been setup.
The factory default is 0.

### Role
`[p]setlottery role <role>`

Sets the role required to track and view stats.
Must be a role that exists on your server. If you delete this role
you will need to update lottery with this command to the new role.
Otherwise, no one will be able to view their stats, but it will still
track if they were able to signup.
        
By default this command is set to @everyone, and anyone can join.

