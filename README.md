![](http://cdn.akamai.steamstatic.com/steam/apps/447530/header.jpg)

# NOTE: THIS IS NOT A BOT. It's a cog, or extention, for discord.py using the ext.commands

## NOTE 2: This Cog is a work-in-progress, this means it isn't finished and means that bugs may arise and cause problems.

# Bartender (AKA. Jill)
### About
Jill is the playable bartender on the game known as VA-11 Hall-A, pronounced as Vall-Halla, which is also the name of the bar she works at. More info on the [steam page](http://store.steampowered.com/app/447530/ "VA-11 Hall-A")
### Why?
Well, because why not? It was a learning experience. When you're 18 years old and just starting college for programming, wouldn't you code for no reason too?
### How?
Magic \**sparkles**

# Information
Info about the cog and how it currently works. (WIP)

## First time set-up
When a member first uses any command, it generates a file for them. If a member uses the main bar command, `<prefix>bar`, Jill will greet them and talk about how ordering works. You can get this help screen back by issuing `<prefix>bar help`

Each Member first starts with $1000 and can start working right away.

## Ordering
Ordering is quite simple.  
You can order:
- From the name of the drink
 - `<prefix>bar order Brandtini`
- A random flavored drink
 - `<prefix>bar order Sweet`
- A random type of drink
 - `<prefix>bar order Classy`
- Or a random drink in general
 - `<prefix>bar order`

When you order the drink, Jill will ask if you want to purchased the drink, along with info about the drink.  
Apon answering 'Yes', Jill will give you the drink and money will be deducted.  
Apon answering 'No', the order will be cancelled.  
Not answering will cause Jill to cancel the order. (Timeout is 8 seconds)
 
## Getting Info on a drink
Using the same parameters as ordering, it just shows you info without buying the drink.

## Working
Working allows for the member to gain money from doing jobs for Dana Zane, AKA Boss. Her command is `<prefix>bar work`. She will also talk about working on your first visit. `<prefix>bar work help` for getting the help back.

When you issue `<prefix>bar work` Boss will tell you about the jobs you can currently do.  
To work, you issue `<prefix>bar work (type)` (without parentheses)
- `type` being the name of the job  

## Tab
Tbh I really didn't know what to call the account. ¯\\\_(ツ)\_/¯

To get your tab, or account, balance, issue `<prefix>bar tab`

You can also send other members money, using `<prefix>bar tab transfer (amount) (member)` (Again, without parentheses)  
- `amount` is the amount of money to transfer.
- `member` is the member to transfer to, which could be their name, nickname, or mention.

# Folder Locations
Like most bots, there are configs locations.
FYI: ROOT means the location of the bot script.
### Configs
 - ROOT/data/bartender/drinks.json
 - ROOT/data/bartender/quotes.json
 - ROOT/data/bartender/work.json   

### Member Configs
In the cog, I made a money system. These configs generate when a member uses any command. (And will only generate when they are not present)
- ROOT/data/bartender/customers/{member id}/data.json  

The reason I made {member id} a folder rather than just the file is because later I'm thinking of meeting other characters and I want seperate files for each character, *data.json* being the main

# Custom Drinks, Quotes, Jobs
### Drinks
Within the cog, I made it dynamic. So you can add custom drinks and it'll automatically add to the list of drinks, flavors, and types.  
When you open *drinks.json*, it's fairly simple to understand but I'll explain anyway:
```json
"Piano Woman":{
 "Description":"It was originally called Pretty Woman, but too many people complained there should be a Piano Woman if there was a Piano Man.",
 "Flavor":"Sweet",
 "Type":"Promo",
 "Techniques":["Mixed"],
 "Ingredients":{"Adelhyde":5,"Bronson Extract":5,"Powdered Delta":2,"Flanergide":3,"Karmotrine":3},
 "Price":"320",
 "custom_icon":"<url to icon>" (OPTIONAL)
}
```  
- `Piano Woman` is obviously the name of the drink. (Make sure the first letter of EACH word is capitalized)
- `Description` is a description of the drink, this could be also lore. What ever you want.
- `Flavor` is what flavor the drink is (Make sure the first letter is capitalized)
- `Type` is what type of drink it is. (Again first letter capitalized)
- `Techniques` are if the drink has certain ways to make them. Drinks can either be `Mixed` or `Blended`, and could also have `Iced` and/or `Aged` (First Letter Capitalized. Also Unused atm.)
- `Ingredients` are unused and most likely wont be. They are used within VA-11 Hall-A to make the drinks.
- `Price` is how much is drink.  
- `custom_icon` is purely optional and is for only custom drinks. No url means No Icon. (OPTIONAL)

### Quotes
Quotes are what Jill says in the footer of most embeds with her picture.
Also, fairly simple to understand. (P.S. I haven't really finished this so it's gonna be mostly blank)
```json
{
 "greetings":["Hello!","Welcome!"],
 "drinks":{
  "<Flavor>":["That <Flavor> is amazing!"],
  "General":["I really like that drink!"]
 },
 "amount":["Need money? We're Hiring!"]
}
```
- `greetings` is when using the main command, Jill will randomly say what is in the list.
- `drinks` is when a member buys a drink
 - `<Flavor>` it's not actually `<Flavor>` but instead the name of a flavor (With first letter of each work capitalized)
 - `General` is when `<Flavor>` is not defined, it defaults to this.
- `amount` is when the command, `<prefix>bar tab` is issued

### Jobs/Work
Jobs, or Work, is currently the only way to gain money.
Again, simple to understand.
```json
 "cleaning":{
  "desc":"Easiest, fastest, and less paying job. Good for a quick buck.",
  "minhours":"1",
  "maxhours":"2",
  "minwage":"200"
 }
```
- `cleaning` is the name of said job (Lowercase)
- `desc` is the description of the job.
- `minhours` is the minimum amount the randomizer uses
- `maxhours` is the maximum amount
- `minwage` is the minimum wage per hour for the member (Keep in mind that most of the drinks are $50-$300)

FYI: The more hours you add, the longer the member has to wait before working again. (Which is a full 24 hours plus the amount of hours they worked)

# Extra Info
### Usage
I here by allow for the use of this cog within discord bots, and only discord bots. I am not resposible for this cog causing problems on your computer, internet, or the bot itself. If said bot is a self-bot, the commands are only allowed to be used by the owner, and only the owner. If said bot is a public bot, the bot must be a bot account using [Discord's API](https://discordapp.com/developers). I will not allow and tell anyone to make their self-bot public or semi-public. (If I do, slap me)

### Requirments
This cog uses:
- [discord.py](https://github.com/Rapptz/discord.py)
 - discord.ext.commands
- asyncio
- json
- random
- os (for folder creation and checking)
- datetime
- time.sleep
- [BeautifulSoup4](https://www.crummy.com/software/BeautifulSoup/)
- [requests](http://docs.python-requests.org/en/master/)

### Checklist
- ~~Make the basic system~~
- ~~Add the drinks~~
- ~~Overinflated Currency~~
- ~~Jobs so that people dont collect massive debt~~
- Add some beats

### Sources
All VA-11 Hall-A Information is from [Wikia](http://va11halla.wikia.com/wiki/VA-11_HALL-A_Wikia)  

I do not own VA-11 Hall-A, I do not and will not tell anyone that I made it. It was made by [Sukeban Games](https://sukebangames.itch.io/) and published by [Ysbryd Games](http://www.ysbryd.net/)

The Idea came from a friend of mine on Discord who is working on his own version on his own bot.

### Support
If any problems show up, either write an issue on github, or join [Neku's Discord Server](https://www.nekku.me/) and PM me.

### Thanks
Of course, Thanks [Era The Monologuer (09eragera09)](https://github.com/09eragera09) for the Idea.  
Thanks [Neku](https://github.com/NekuNeku) ([website](https://www.nekku.me/)) for allowing me to use his server for testing.  
And anyone else who helped me along the journey (I talk like it took forever, it was only 2 days xD)
