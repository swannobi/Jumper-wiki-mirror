# Introduction
These are some useful aliases that do not require you to download a cog to utilize. Credit to irdumbs for creating the majority of these aliases, and to Aikaterna for compiling them all into a list. To add these aliases simply copy and paste the code into your discord chat, with your command prefix. You can call it by using the name of the alias created.


***

# Tutorial
This is irdumb's tutorial section on making your own alias!

***

#Useful Aliases

### TODO
Lets the user create a todo list.

**Code**  
`alias add todo debug (lambda n1=-1, n2=0, fg=0: (lambda res: res[:1900]+'...\n\nThere\'s still more.. Holy Crap, do some of the things on your todo list man!' if len(res)>1980 else res)((lambda n1=n1, n2=n2, fg=fg: (lambda ld:'@Deleting these todo items:\n'+''.join(ld[1])+'\n#'+str((lambda: open('data/todo.txt', 'w'))().write(''.join(ld[0])))+' Bytes left in todo.txt')((lambda f, b, e: [f[1:],f[:1]] if b<0 else [f[:b]+f[e+1:],f[b:e+1]] if e>b else [f[:b]+f[b+1:],f[b:b+1]])(list(open('data/todo.txt')), n2, fg)) if n1=='del' and type(n2) is int else (lambda y: str((lambda y: (lambda: open('data/todo.txt', 'a'))().write(datetime.datetime.now().strftime('%m-%d(%a) %I%p')+': '+y+'\n'))(y)) + ' Bytes added to todo.txt:\n@: '+y[:21]+'...')(n1) if type(n1) is str else ''.join(['{}: {}'.format(i,line) if fg else '{}: {}'.format(i,line[17:]) for i, line in enumerate(open('data/todo.txt')) if n1 == -1 or (i >= n1 and (i <= n2 or n2 == 0))]))()))`

| Command                          	| Description                                             	|
|----------------------------------	|---------------------------------------------------------	|
| !todo ('add this to a list')     	| add an item to your list                                	|
| !todo ('del', 0,1) or ('de1', 2) 	| delete a numbered item on your list (two at a time max) 	|
| !todo ()                         	| display list                                            	|

***

### Bots
Prints out how many bots are on your server.

**Code**  
`alias add bots debug "Bots up in here: " + str(len([m for m in ctx.message.server.members if 'Bots' in [r.name for r in m.roles]]))+ "\nOnline: "+ str(len([m for m in ctx.message.server.members if 'Bots' in [r.name for r in m.roles] and m.status.name == 'online'])) + '\n\nPeeps with bot tags: '+str(len([m.name for m in ctx.message.server.members if m.bot])) + '\nBot tags online: ' + str(len([m.name for m in ctx.message.server.members if m.bot and m.status.name == 'online']))`

**Example**  

Bots up in here: 0  
Online: 0

Peeps with bot tags: 3  
Bot tags online: 3

***

### Cogs
Prints out a list of cogs. Indicates whether the cog is loaded or not.

**Code**  
`alias add cogs debug "+ enabled cogs\n- disabled cogs"+"\n"+"diff\n"+"\n".join([('+ ' if file[:-3] in [cog.__module__[5:] for cog in bot.cogs.values()] else '- ') + file[:-3] for file in os.listdir('cogs') if file.endswith('.py')])`

***

### Days
Prints out how many days a user has been on the server. Username only, not a mention.

**Code**  
`alias add days debug (lambda name, ctx=ctx: "\n".join(["{0.name}#{0.discriminator} has wasted {1.days} days here.".format(m, ctx.message.timestamp -m.joined_at) for m in ctx.message.server.members if m.name.startswith(name)]))`

**Example**  

!days ('username')

***

### Exec
Executes something.

**Code**  
`alias add exec debug (lambda cmd, ctx=ctx, bot=bot: (lambda op, bot=bot, cmd=cmd.replace('\\','\\\\'): os.getcwd()[os.getcwd().index('/Red'):]+'$ '+cmd if op is None else op)(bot.loop.run_in_executor(None,(lambda: os.popen(cmd).read())).add_done_callback((lambda op, ctx=ctx, bot=bot: bot.loop.create_task(    bot.send_message(ctx.message.channel, "`"+"``\n"+( op.result() if len(op.result())<1980 else (lambda op: op if os.popen('subl data/alias_exec.txt') else op[-1980:] + "\n\nSubl open failed")("Output too long! Opening in a file." if (lambda: open('data/alias_exec.txt', 'w'))().write(op.result()) else op.result()[-1950:] + "`"+"``diff\n- Too long. Failed to save output.`"+"``") )+"`"+"``")) ))))`

Executes something.

**Example Table:**   

| Command                        	| OS      	|
|--------------------------------	|---------	|
| !exec ('ping -c 4 google.com') 	| Windows 	|
| !exec ('ping -n 4 google.com') 	| Linux   	|


***

### Idchar
Identifies a username based on input. Requires proper case, works for the beginning of the user's name.

**Code**  
`alias add idchar debug (lambda name=ctx.message.author.name, ctx=ctx: "\n".join(["{0.name} {1:c}".format(m, int(m.id)%11000) for m in ctx.message.server.members if m.name.startswith(name)]))`

**Example**  
!idchar ('user')		Bot prints: `username`

***

### Pg
Looks at the first bit of a file in Red's directory structure.

**Code**  
`alias add pg debug (lambda fn, pg=0, sz=3, spg=1, max=1980: fn+('\nResult #'+str(spg)+' for '+pg if type(pg) is str else '')+'``'+'`\n`'+'``py\n'+(lambda f, fn=fn, p=pg, s=sz, sp=spg, m=int(max*(sz/10))-(len(str(pg)+fn)): [f[i:i+m] for i in range(0,len(f),m) if p.lower() in f[i:i+m].lower()][sp-1] if type(p) is str else f[int(p*m):] if (p+1)*m > len(f) else f[int(p*m):int((p+1)*m)])(''.join(list(open(fn)))))`


**Example**

!pg ('data/red/red.log')

!pg ('data/red/red.log','last')		Searches for the first result of 'last' in red.log


***

### Pgc
Looks at a cog in Red's files.

**Code**  
`alias add pgc debug (lambda fn, pg=0, sz=3, spg=1, max=1980: fn+('\nResult #'+str(spg)+' for '+pg if type(pg) is str else '')+'``'+'`\n`'+'``py\n'+(lambda f, fn=fn, p=pg, s=sz, sp=spg, m=int(max*(sz/10))-(len(str(pg)+fn)): [f[i:i+m] for i in range(0,len(f),m) if p.lower() in f[i:i+m].lower()][sp-1] if type(p) is str else f[int(p*m):] if (p+1)*m > len(f) else f[int(p*m):int((p+1)*m)])(''.join(list(open('cogs/'+fn+'.py')))))`


**Example**  
!pgc ('economy')

!pgc ('snacktime', 'plox')			Searches for the first result of 'plox' in snacktime.py

***

### Role
Displays all users in a role and whether they are online or offline.

**Code**  
`alias add role debug  (lambda role, ctx=ctx: '@online:\n\n'+'\n'.join([m.name for m in ctx.message.server.members if role.lower() in [str(r).lower() for r in m.roles] and str(m.status)!='offline'])+'\n\n@offline:\n\n'+'\n'.join([m.name for m in ctx.message.server.members if role.lower() in [str(r).lower() for r in m.roles] and str(m.status)=='offline']))`

**Example**  
!role ('Member')

***

### Transfer Aliases
Copies all aliases from the server you are on to the target server. Can be a partial name.

**Code**  
`alias add transfer_aliases debug (lambda server_name, ow='', ctx=ctx, bot=bot: (lambda servers: ('More than 1 server starts with '+server_name if servers else 'Could not find any servers that begin with '+server_name) if len(servers)!=1 else (lambda io, s, tsid, overwrite=(True if ow.lower()=='overwrite' else False): ("You can't transfer aliases to the same server!\nsilly buns...") if s.id == tsid else (lambda data: (lambda save: ((lambda msg: msg if bot.loop.create_task(bot.process_commands([ctx.message for ctx.message.content in [ctx.prefix+'reload alias']][0])) else 'Error reloading alias. You must [p]reload alias\nfor changes to take effect')(('@ Aliases transfered! @\n'+ctx.message.server.name+' --> '+s.name+('\n\nany aliases already in target server have been overwritten!')*overwrite)) if io.save_json('data/alias/aliases.json',data) is None else 'Error saving aliases.json') if data[s.id].update(save) is None else 'Error transfering aliases')({**data[s.id], **data[tsid]} if overwrite else {**data[tsid], **data[s.id]}))(io.load_json('data/alias/aliases.json')))(__import__('cogs').utils.dataIO.dataIO, servers[0], ctx.message.server.id))([s for s in bot.servers if s.name.lower().startswith(server_name.lower())]))`

**Example**  
!transfer_aliases ('Red')

Bot responds: 
```py
@ Aliases transfered! @
Test Server --> Red - Discord Bot
```

***

### Update Discord.py
Updates discord.py. Change the command as the value for discord.py changes with future updates.

**Code**  

`alias add update_discordpy debug (lambda op: "Updating..." if op is None else op)(bot.loop.run_in_executor(None,(lambda: os.popen(r'pip3 install -U git+https://github.com/Rapptz/discord.py@master#egg=discord.py[voice]').read())).add_done_callback((lambda op, ctx=ctx, bot=bot: bot.loop.create_task(bot.send_message(ctx.message.channel, "`"+"``"+(op.result()[op.result().index("Successfully installed discord.py",-250):] if "finished with status 'done'" in op.result()[-250:] and "Successfully installed discord.py" in op.result()[-250:] else op.result()[-1500:] + "``"+"`\n`"+"``diff\n- Failed to update discord.py.. probably..")+"`"+"``")) )))`

***

### Install
From Kowlin's https://twentysix26.github.io/Red-Docs/red_guide_aliases/  
Instructions online. Requires editing red.py (not recommended).

**Code**  
`alias add install debug (lambda fn_or_url, core_cog=0: 'Installed. Make sure to (re)load the cog.'*int(0==(lambda url: subprocess.call(['wget', '-P', 'cogs', '-N', url]))((lambda c=fn_or_url, co=core_cog: (c.replace('https://github.com/','https://raw.githubusercontent.com/')).replace('/blob','') if '.' in c or '/' in c else 'https://raw.githubusercontent.com/Twentysix26/Red-DiscordBot/develop/cogs/' +c+'.py' if bool(co) else 'https://raw.githubusercontent.com/Twentysix26/Red-Cogs/master/cogs'+('/'+c)*2+'.py')())))`

***

### pplsince (Kowlin)
Prints who has joined the server in the last X hours.

**Code**  
`alias add pplsince debug (lambda h, ctx=ctx: "# Unassigned members that have joined since "+str(h)+" hrs ago\n\n"+"\n".join([m.name for m in ctx.message.server.members if len(m.roles) == 1 and m.joined_at > ctx.message.timestamp - datetime.timedelta(hours=h)]))`

**Example**  
!pplsince (300)

***

### freshmeat
Prints who has joined the server in the last 24 hours.

**Code**  
`alias add freshmeat debug (lambda h, ctx=ctx: "Jenn's fresh meat of the day\n\n"+"\n".join([m.name for m in ctx.message.server.members if len(m.roles) == 1 and m.joined_at > ctx.message.timestamp - datetime.timedelta(hours=h)]))(24)`

**Example**  
!freshmeat

***

### rolerace
Add your own friends' ids to track role accrual, leaderboard-style.

**Code**  
`alias add rolerace debug  (lambda sv, ppl: "@@@ Role Race! @@@\n"+"\n".join(["{0.name}: {1}".format(sv.get_member(m),len(sv.get_member(m).roles)-1) for m in ppl]))(ctx.message.server, ["00000000000000001","00000000000000001","00000000000000001","00000000000000001"])`

***

### score
Will display a score when a trivia match is active.

`alias add score debug (lambda li, ctx=ctx, bot=bot: "\nTrivia Current Score:\n"+"\n".join(['%s %d' % (k.ljust(24), v) for k,v in sorted(li.items() ,key=lambda x:x[1], reverse=True)]))((lambda ctx=ctx, bot=bot:[x.score_list for x in bot.get_cog("Trivia").trivia_sessions if x.channel == ctx.message.channel][0])())`

***

### tag_leave
Leaves a server, including with a partial name lookup in the query. No confirmation in the dialog - be sure you want to use this.

**Code**
`!alias add tag_leave debug (lambda sname, bot=bot: "There are more than one servers with that name" if len([s for s in bot.servers if sname.lower() in s.name.lower()]) > 1 else bot.leave_server([s for s in bot.servers if sname.lower() in s.name.lower()][0]))`

**Example**  
!tag_leave ('Red')		Leaves the Red-DiscordBot server.

***

### Google Search
Google search query for mac and linux users

**Code** (Linux Only)  
`alias add g? debug (lambda st, i=0: (lambda url,st=st,i=i: (['@ ','# ','\"\"\" ',''][int(datetime.datetime.now().strftime('%f'))%4]+['ʕ •ᴥ•ʔ < {1} you say? ','ʕ •ᴥ•ʔ < You wanna know about {1}s?','ʕ •ᴥ•ʔ < '+'{1} '*(int(datetime.datetime.now().strftime('%f'))%7+1),'ʕ •ᴥ•ʔ < Wow, you don\'t know what that is?','ʕ •ᴥ•ʔ < Bahahaha! You have to Google that?!','ʕ •ᴥ•ʔ < Woah! What\'s a {1}?!','ʕ •ᴥ•ʔ < wow.. Don\'t you feel embarrassed searching for that?','ʕ •ᴥ•ʔ < I hear Bing gives better results for that sort of thing, but ok.'][int(datetime.datetime.now().strftime('%f'))%8]+'`'*3+'{0}').format(url,st)+''*subprocess.call(['open',url]))((lambda st=st,i=i: 'https://www.google.com/'+ ['search?q=','search?tbm=isch&q='][i] + '+'.join(st.split()))()))`



**Code** (Mac Only)  
`alias add g? debug (lambda s, i=0: (lambda url: (lambda sp: 'Popen Sesame!``'+'`\n'+url+'\n\n`'+'``' if sp else 'Popen Sesame!``'+'`\n'+url+'\n\n`'+'``\nWhy no open?')(__import__('subprocess').Popen(['open', url])))('https://www.google.com/search?'+__import__('urllib').parse.urlencode({'q':s})+('&tbm=isch' if i else '')))`

**Example**  
g?  

