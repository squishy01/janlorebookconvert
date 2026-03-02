ok first of all let me say if the code looks like crap i dident writee it, i spent a day with an ai and we ran a ton of updates and we all know how good ai codecan be.

i have at the time of this writing used silly tavern, it should as far as wat im understanding be compatiable with world info.
due to the original process of talking through the bot it put in some quirky text on like field prefills and sch, most of those should be removed but if there not and theconverted jsons dont work on silly tavern i apologize
if it dosent work on your desired platform and you think it mmight be just data not being or thats not suposed to be included
i thought that might eventually be an issue as well so i had a few things put in to save time on that front whcih i will mention later

this has only been tested against standard lorebooks on Janitor.AI, i have not tried it against any of there "advanced" guided setup templates where they claim you have full javascript control, if it does not work against theese i apologize again this was standard lorebook tested only.

ok this all started because i had been thinking of moving over to sillyatavern for just ease of use, consolidated character card, and to break free form api restrictions as well as access to better models. now chubs great its so easy one or 2 clicks depending on what it is and it works with everything.
now janitor on the other hand thats a fight. and i get why becuase they want to protect a creators content if the creator wants it. but they also have there own systems for things and it can be a real pain in the ass. anywayone of my favorite spent the most time on bots was actually all public definitions (i been avoiding prompt engenering to byepass hidden ones)
Lorebook was also public so i went in and looked and it thoughtthis looks nothing like what i was told a lorebook looked like. i knew if i was going to start using local systems to rp i was goign to change afew things in the backstory, a few kinks and start to build a lorebook for this character, so i woul need to figuew this out
so i took it and uploaded or rather tried to upload it to chub as i figured that would be more a reflection of universal layouts. chub straigt up refused to load it, yverns card editor did as well.
but chubs templates worked evrywhere even suprise suprise janitor so i thought ok im sure this wont help but lets compare the code.

## What i found ##
well first thing i saw was chubs condenses its entie script into one line, so that pretty much made side by side comparisons impossible. but what i did find was Janitor immdeiatly cuts every sincle character prior to the first keys entry.
now i had prior to this been looking at another sites character templates and had seen just how picky some platforms are when it comes to either missing json pairings or adding ones. some sites dony content, some just come up blank.
anyways i saw them chopping off everything prior to the keys and i figured oh look if thats not whats messing things up i bet they have a ton of other formattingand such to just trip the other platforms sensors. 
decided i would let chatgpt look at it because well as i mentioned chubs is a single line making this hard to look at plus ai is good at this kinda repetion.and i had intended to learn then have ti build but hey it overachieved.

## How the AI developed its COnversion method ##
ok so this is what we did, i took a prompt from chubs which tbh anybody whos run anything from chubs in chat gpt is not easy to do without getting called a sick weirdo and things getting redacted.
anyways i took a prompt from chub, and imported into janitor and let it do tis thing. this gave me two records of the same data, one with and one without janitors formatting quirks and alterations.
i took the data back to chat gpt and said ok so whats different about these and whats the deveations from a more standard sillytavern protocol, i use silly tavern since its normally a pretty universal standard
the long answer it gave me i wish i had read the entire thing of as well as savedit. i had the idea to just try and make a tool but was skepitcal after the fight me and it had to initialy get a working solution to port and seperate out a character card from a site that used there own kinda methods vs a standard v2
but i thought hey you never know so i put both copies of the chub prompt in asked it to make the janitor prompt conform to the style of the chub one, and to retain all sillytavern required tags as well as give me fields i can manually rebuild the section it cut off
we went back an fourth a few times as it kept not giving me everything but eventually wehad an upload as well as a json section to copy and paste the data in. and ran it in both, and what do you know it now all of a sudden isent getting kicked back by things. we got a working skeleton.

## Fleshing it out ##
i put it into wyverns character card editor just so i can see what kinda fields its pulling and are they coming right. well chatgpt initially missed carying over alot of things
so me and the bot took a day and chatted, we slowly identiied whhat was missing and if it was needed and blah blah blah until i had pretty much alll of wyverns areas filling, i dident give hot if it wasent janitor cmplient, i knew as long as it worked eerywhere else all i ahd to do was import it into janitor to get it to work there.
so we got down to the last one, hich was token budget and man what a nightmare, but hey we got our first feature.

## live view of token budget ##
so as i was initially building out and finding what tags actually where needed i saw it change token budgeta few times, so when we finally got it here i just asked, whats the budget supposed to be
initially it told me average token usage is this and this for large small and medium scripts. so i said ok put those in and also put in one option where they can put whatever they want. 
then i got cute and asked it since we know all the words cant you just do the math on tokens, andits like no cause there can be variances but i can make educated guesses based on wordcount and a buffer
so i daid let they will be doneand it shot back some code to update it that dident really have alot of info presented, and i like info and i lik knowing if i cant to mess with the buffer i can gauge it off this info
so i made a HUGE mistake and asked it to give the data to me in a realtime displaay showign totals and what that total actually contained. and man me and this bot we went back and fourth forever.
also the bot has a habit of misunderstanding sometimes an overfocusing on an area essentially tanking the entre site, and everytime it happeens and i have toask it to revert it builds this live preview section back ddifferent and we have to argue to get it working right again.
but hey now you can select a bunch of flat rate, a user defined amount or a estimated guess weiting each word as 1.33 tokens as ewell as a 15% buffer which i find funny because i asked it to do this and it told me my best option was a flate rate buffer.
then the entire thing broke and it rebuilt it with yea a percentage based model and when i aksked it why said alot of words that rldr came outt to its just better. but hey thats down (until it breaks) we can move on

## Converted entry preview ##
next problem on the docket, what happens when you like i get lazy and dont have more distinct names for your exports? you open a bunch of wrong ones. so i asked it hey can you just like show me a snippit ofsomething in the file after conversion but before i actually hit the button
and it did and that expanded to just show me all the lore entries, that way not ony will i know what file it is but i can also check to make sure its bringing over all the lore, i thought about having it do the other tags as well but its just to cluttered. another feature down.

## side by side comparison of json ##
now pretty much all the things that can really help functionality with this single case use had been done, i mean what else are ou going to do r converting templates thats not going to just be a part of a larger more grand suite of tools
