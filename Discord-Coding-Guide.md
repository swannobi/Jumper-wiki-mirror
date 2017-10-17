# Coding FAQ Guide

The purpose of this guide is **not** to teach you Python, but to help you better understand how red interacts discord API wrapper, and to answer common questions. If you have something you think I should add to this guide, let me know. Remember, there is always more than one way to skin a cat. Not all of the examples below are the best, or the only way to achieve the end result, but they will work.

If you find these examples helpful star my repo above and let me know what I might be able to add to help in the future.

# Table of Contents
- [Say](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-you-make-the-bot-say-something-in-chat)    
- [Whisper](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-you-make-the-bot-whisper--dm--pm-)
- [Upload Image](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-you-make-the-bot-send-a-file--show-an-image-without-a-link)  
- [Make commands usable in DMs](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-i-make-a-command-usable-in-a-pmdmwhisper)       
- [Integration](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-i-integrate-my-cog-with-another-cog)
- [Permissions](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-i-make-a-command-usable-by-owneradminmod) 
- [Group Commands](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-i-make-a-group-command--make-commands-start-with-the-same-pre-command) 
- [Multi Word Arguments](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-i-capture-more-than-one-word-as-an-argument)
- [Handling 3rd Party Requirements](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-i-make-sure-someone-has-my-library-requirement-installed)
- [Command Aliases](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-i-make-a-command-have-different-names--how-do-i-make-a-command-have-an-aliases)
- [Code Blocks](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-i-make-my-output-in-a-code-block)
- [Colored Text](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-i-make-my-output-have-colors)
- [Saving Data](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-i-save-information--how-do-i-use-dataio--how-do-i-use-json)
- [Get User Info](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-i-return-a-member-object-from-a-user-id)
- [Non-Blocking Code](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-i-make-my-code-non-blocking-)
- [Formatted Strings](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-i-use-variables-in-my-strings---how-do-i-use-formatted-string-literals)
- [Convert User ID to User Object](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-i-return-a-member-object-from-a-user-id)
- [Targeted Messaging](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-i-pmdmwhisper-everyone-with-a-certain-role)
- [Embeds](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-i-make-an-output-a-cool-embed)
- [Logging](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-i-add-logging-to-my-cog)
- [Custom Exceptions](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-can-i-add-custom-exceptions)
- [Editing Messages](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide#how-do-I-get-the-bot-to-edit-a-message)

***

### How do you make the bot say something in chat?

```Python
@commands.command()
async def test(self, *, message):
    await self.bot.say(message)
```

### How do you make the bot whisper / DM / PM ?

**Method 1** (Whispering the person who used the command)  
  
```Python
@commands.command()
async def test(self, *, message):
    await self.bot.whisper(message)
```  

**Method 2** (Whispering a specific user)

```Python
import discord   # We need this because we will use it in the command
@commands.command() # Here we are getting the member object
async def commandname(self, ctx, user: discord.Member):
    await self.bot.send_message(user, message)
```

### How do you make the bot send a file / show an image without a link  

```Python
@commands.command()
async def commandname(self, ctx):
    channel = ctx.message.channel
    with open('data/cogfolder/imagename.png', 'rb') as f:
        await self.bot.send_file(channel, f)
```

### How do I make a command usable in a PM/DM/Whisper?

```Python
@commands.command(no_pm=True)  # Default is True, and you can just omit it from the arguments as well.
```

### How do I integrate my cog with another cog?

When using another cog for "integration" you are essentially calling the functions that were defined in that cog and executing them. This ensures you do not alter or corrupt anything if the cog changes. I use economy as an example here, because it will be the most common that is integrated with cogs. For a full list of economy bank functions check the code [here](https://github.com/Twentysix26/Red-DiscordBot/blob/develop/cogs/economy.py)

**Example**

```Python
@commands.command(pass_context=True)
async def commandname(self, ctx):
    user = ctx.message.author # Member object of command issuer, required argument in the economy function.
    bank = self.bot.get_cog("Economy").bank # we use .bank at the end to specify we want to use the bank class
    bank.withdraw_credits(user, credits) # This function requires two arguments: Member object, and an integer/float
```


### How do I make a command usable by Owner/Admin/Mod

Redbot is packaged with some nice helper functions that allow us to perform a variety of checks to authorize
the execution of a command.

```Python
from .utils import checks

@commands.command()
# This under a command will check if the user is an admin or it has the manage server permission
@checks.admin_or_permissions(manage_server=True)
```
Other examples:  
`@checks.mod_or_permissions()`  
`@checks.is_owner()  
`serverowner_or_permissions()`

In server settings on your discord server, look in Roles.  
You will see on the right: "GENERAL PERMISSIONS"  
These can be used to pass as keyword arguments.
For more information look at checks.py in your utils folder located in cogs/utils

### How do I make a group command / make commands start with the same 'pre-command'

**Method 1**

```Python
@commands.group(name="example", pass_context=True)
    async def _example(self, ctx):
        """Tell users what your group command is all about here"""
        
        if ctx.invoked_subcommand is None:
            await send_cmd_help(ctx)

@_example.command()
async def poop(self, ctx):
    # Put what your command does here
    # This command executes as !example poop
```

**Method 2**

```Python
@commands.group(pass_context=True)
    async def example2(self, ctx):
        """Example2 group command is all about stuff"""

        if ctx.invoked_subcommand is None:
            await send_cmd_help(ctx)

@example2.command(name="poop", pass_context=False)
async def _poop_example2(self):
 # Put what your command does here
 # This command executes as !example2 poop
```

### How do I capture more than one word as an argument?

```Python
async def commandname(self, *, text) # text can be poop. I use text cause it makes sense. You don't have to make sense.
```

### How do I make a command have different names / How do I make a command have an alias(es)?

```Python
@command.commands(name="poop", aliases=["poo", "number2", "duty"]) # these aliases cant be used as other command names
```
### How do I make sure someone has my library requirement installed?

The best way to ensure that your third-party requirements are installed by the user is to put the information in your info.json file. The libraries needed will be listed in the requirements parameter. If you want to add an additional check in your code, you can do the following:  

_Example using BeautifulSoup4_
```Python 
try:   # check if BeautifulSoup4 is installed
    from bs4 import BeautifulSoup
    soupAvailable = True # This is like using a flag or a switch that we use later
except ImportError:
    soupAvailable = False

# at the very bottom in your setup...

def setup(bot):
    if soupAvailable: # This is our "switch" when it is on (meaning they have bs4 installed) it will try to load.
        n = Pokedex(bot)
        bot.add_cog(n)
    else:
        raise RuntimeError("You need to run 'pip3 install beautifulsoup4'") # This should be the instructions they need.
```

### How do I make my output in a code block?

```Python
message = "```Hello World```"
await self.bot.say(message)

# OR when you are going to cram a bunch of other stuff in there you can use multiple assignment

message = "```"
message += "Hello World"
message += "```"
await self.bot.say(message)
```

### How do I make my output have colors?

_This is kind of misleading, because the colors are from syntax highlighting._
_Syntax highlighting is used to help programmers read code easier, so it highlights functions, classes, sometimes numbers_
_Different languages highlight different things. You can experiment to find which works for you._
_The example below uses the programming language Ruby_

```Python
message = "```Ruby" + "\n"   # \n is a line break, and forces the following text to go to the next line
message += "Ruby will Highlight words that are Capitalized"
message += "```"
await self.bot.say(message)
```
**Sample Output**
```Ruby
Ruby will Highlight words that are Capitalized
```

### How do I save information / How do I use dataIO / How do I use JSON

_JSON is a file type which allows you to store key, value pairs and can be deeply nested._ The data must be serialiazable in order for the data to be saved to JSON. Please use this table for reference when loading and unloading data:

| JSON          	| Python 	|
|---------------	|--------	|
| object        	| dict   	|
| array         	| list   	|
| string        	| str    	|
| number (int)  	| int    	|
| number (real) 	| float  	|
| true          	| True   	|
| false         	| False  	|
| null          	| None   	|

_Using DataIO you can read and write to these files. This is extremely useful when you have data that needs to persist through crashes or restarts. You should always inform the user that your cog will create one of these files. Here is an example of a JSON file created from my cog Russian Roulette:_

```JSON
{
    "Config" : {
        "Min Bet" : 50
    },
    "Players" : {},
    "System" : {
        "Active" : false,
        "Player Count" : 0,
        "Pot" : 0,
        "Roulette Initial" : false,
        "Start Bet" : 0
    }
}
```

There are a lot of steps to this process, but here are the minimum you would need:
(note everything should go under you main class)

```Python
import os # This is required because you will be creating folders/files
from .utils.dataIO import dataIO  # This is pulled from Red's utils

def __init__(self, bot):
        self.bot = bot
        self.file_path = "data/cogfolder/filename.json"
        self.json_data = dataIO.load_json(self.file_path) 

# all your commands and code
# would be the meat in this sandwich
# Right here. MMmmm. Tasty

# Substitute cogfolder with the name of the folder you want created  
def check_folders(): # This is how you make your folder that will hold your data for your cog
    if not os.path.exists("data/cogfolder"): # Checks if it exists first, if it does, then nothing executes
        print("Creating data/cogfolder folder...")  # You can put what you want here. Prints in console for the owner
        os.makedirs("data/cogfolder") # This makes the directory


def check_files(): # This is how you check if your file exists and let's you create it
    system = {"System": {"Pot": 0,            # system is only used when you want your JSON to have a default structure
                         "Active": False,
                         "Start Bet": 0,
                         "Roulette Initial": False,
                         "Player Count": 0},
              "Players": {},
              "Config": {"Min Bet": 50}}

    f = "data/cogfolder/filename.json" # f is the path to the file
    if not dataIO.is_valid_json(f): # Checks if file in the specified path exists
        print("Creating default filename.json...") # Prints in console to let the user know we are making this file
        dataIO.save_json(f, system) # If you didn't use a default structure you could type: dataIO.save_json(f, {})


def setup(bot):
    check_folders() # runs the folder check on setup that way it exists before running the cog
    check_files() # runs the check files function to make sure the files you have exists
    n = Russianroulette(bot)
    bot.add_cog(n)
```

### How do I get a user's id / name

_see more on this_ [here](https://twentysix26.github.io/Red-Docs/red_guide_command_args/)

In this example we set a variable "author" as the author object. We obtain this through passing
ctx and accessing that information. ctx must always be the first argument when passed (after self).
We set user to be the user object for the discord member. 
```Python
@commands.command(pass_context=True)
async def mycommand(self, ctx, user: discord.Member):
    author = ctx.message.author
    author.id # This is your author id number
    user.id # This is the user's id
    author.name # This is the author's id
    user.name # This is the user's name
```

### How do I use variables in my strings  / How do I use formatted string literals

```Python
color = "Red"
animal = "Tiger"
output = "I have a {} shirt, with a huge {} on the back".format(color, animal)
await self.bot.say(output)
```

### How do I make my code 'non-blocking' ?

_Something that is 'blocking' means that the bot will stop functioning until it completes that task._
_Two good examples are requests and time.sleep(). If you use time.sleep(5) to wait for 5 seconds, the bot_
_will be unable to perform other tasks while it is waiting. instead use this:_

```Python
import asyncio

await asyncio.sleep(5) # forces only the code for the command to yield until it is finished executing
``` 

_In place of requests use aiohttp_

### How do I return a member object from a user id?

```Python

@commands.command(pass_context=True)
async def mycommand(self, ctx):
    server = ctx.message.server
    user = ctx.message.author
    member_object = server.get_member(user.id)
```

### How do I PM/DM/Whisper everyone with a certain role?

```Python
import discord
from discord.ext import commands


@commands.command(pass_context=True)
async def mycommand(self, ctx, role: discord.Member):
    destinations = [m for m in ctx.message.server.members if role in m.roles] # list comprehension to filter members
    for destination in destinations: # Loop through our list of objects, to send a message one by one
        await self.bot.send_message(destination, message)
```

### How do I make an output a cool embed?

**Example:**

```Python
@commands.command(pass_context=True)
    async def excom(self, ctx):
        """CTX example command"""
        author = ctx.message.author
        description = ("Short little description with a link to "
                       "the [guide](https://github.com/Redjumpman/Jumper-Cogs/wiki/Discord-Coding-Guide)")
        field_name = "Generic Name"
        field_contents = "Example contents for this field"
        footer_text = "Hi. I am a footer text. I look small when displayed."

        embed = discord.Embed(colour=0xFF0000, description=description)  # Can use discord.Colour()
        embed.title = "Cool title for my embed"
        embed.set_author(name=str(author.name), icon_url=author.avatar_url)
        embed.add_field(name=field_name, value=field_contents)  # Can add multiple fields.
        embed.set_footer(text=footer_text)

        await self.bot.say(embed=embed)
```

### How do I add logging to my cog?

There are many ways in which to implement logging. For the full details and options at your disposal please check out the docs [here](https://docs.python.org/3.5/library/logging.html).

**Your setup should look something like this:**
```Python
def setup(bot):
    global logger  # Set logger as a global var
    logger = logging.getLogger("red.cog_name")
    if logger.level == 0:  # Prevents the logger from being loaded again
        logger.setLevel(logging.INFO)
        handler = logging.handlers.FileHandler(filename='data/cog_name/cog_name.log', encoding='utf-8', mode='a')
        handler.setFormatter(logging.Formatter('%(asctime)s %(name)-12s %(message)s',
                                               datefmt="[%d/%m/%Y %H:%M]"))
        logger.addHandler(handler)
    # Make sure this is outside the if statement!
    bot.add_cog(CogName(bot))
```

**Example of adding logging to a command:**
```Python
@commands.command(pass_context=True)
async def mycommand(self, ctx):
	author = ctx.message.author
    await self.bot.say("Hello World")
    # Will the users name and the message in a text file for later review
    logger.info("{} used the hello world command.".format(author.name))
    
```
### How can I add custom exceptions?

Custom exceptions are great for cogs that have integration or are very complex and need to provide additional context to the user for why something did not return what they expected. Here is one way you can implement this feature in your cogs. For more information please refer to [User-defined Exceptions](https://docs.python.org/3/tutorial/errors.html#user-defined-exceptions) section in the Python docs

**Here is an extremely basic example:**
```Python
# This will be passed into all of your specific exceptions
class MyCogError(Exception):
    pass


class InvalidPassword(MyCogError):
    pass


class MyCog:

    def __init__(self, bot):
        self.bot = bot
    
    @commands.command()
    async def mycommand(self, password):
        try:
            self.pass_checker(password)
        except InvalidPassword:  # When our custom exception is raised, we can catch it here
            return await self.bot.say("Password was invalid, must be integers.")
        # Rest of your password code here
    
    def pass_checker(self, password):
    # some cool pasword checking code here
    try:
        int(password)
    except ValueError:
         # Instead of raising a value error, we can raise our custom error
        raise InvalidPassword()
```       

### How do I get the bot to edit a message?

Here is one example to do it all within the same command
```Python

@commands.command()
async def mycommand(self, password):
    # Assign the message to a variable
    hello = await self.bot.say("Hello World")
    # Optional wait 5 seconds
    asyncio.sleep(5)
    # The first argument must be the message object you wish to edit
    edit_message(hello, new_content="Goodbye World")
```
    

For more information on embeded messages, please check out this [page](http://discordpy.readthedocs.io/en/latest/api.html#embed) on the discord py docs.
