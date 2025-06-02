# Rabi Ribi Randomizer Guide: New Player
This guide is broken up into 3 understanding sections, with each section being tied to the general knowledge 
needed for some particular challenge. Generally, if you have beaten the challenge associated with a given section,
then it's probably safe to skip the given section. It is highly recommended that you finish at least either Section 1 or
Section 2 before attempting to play the randomizer

## Section 1: 0% run

Rabi Ribi can be completed up to Irisu without picking up any items except for the Bunny Amulet, however 
there is two particular techniques required in order to get past certain jumps and a large number of 
hidden pathways that need to be revealed by ribbon in order to "cheat" through some areas. Luckily, if 
you do not feel like completing the entire 0% run to find out where all of the passageways are then you 
can enable "apply beginner mod" in your YAML to reveal where they are. Furthermore, the two techniques required 
are covered in the next section, so you may want to play with the beginner mod on and proceed to the next section. 
If you are interested in how to complete the 0% run yourself, there is a [guide](https://steamcommunity.com/sharedfiles/filedetails/?id=612667311) 
which has images on how to go about doing this.

## Section 2: Rabi Ribi Platforming Tricks (Steam workshop map) up to intermediate

A lot of the Rabi Ribi Randomizer uses the Platforming Tricks map in order to determine what knowledge level 
is required to perform each trick. For example, the lowest difficulty of the randomizer (`Knowledge: Basic`, 
`Trick difficulty: Normal`) still requires you to complete the very first set of tricks in the map. If you ever 
feel stuck, there is [a full video playthrough](https://www.youtube.com/watch?v=T5utNIiCHcs) available which shows
off each trick. While the most basic settings only require clearing the easy door of the map, it is advised to do the 
second door to prepare for some of the "tight" tricks in the randomizer, including bunstrike jumps and whirl bonks. 
The itermediate section also introduces the main methods to perform a "zip" which are in logic if you enable their 
respective settings. If you are up for a challenge, try the Advanced tricks; some of these tricks are used in the 
randomizer, generally if you play on `Knowledge: advanced` and `Trick difficulty: Very Hard`.  
As a final note, if you ever feel like playing on `Knowledge: Obscure`, you will likely find that the tricks are not covered 
in this map. You will almost certainly need to look through either the AP discord channel, or the speedrunning discord in order 
to find examples of each trick being performed. You also will probably need to have a firm grasp at how to read the constraints 
of the base randomizer.

## Section 3: Completed the Randomizer a couple of times

This last section is mostly an explanation what settings are recommended, as well as how to figure out what to do for a given obstacle. 

Below is settings that would be considered "Standard" once you have completed all of the prior two sections:
 - `Knowledge: Intermediate` is a solid starting point, as most of the tricks are somewhat obvious.
 - `Trick Difficulty: Hard` Allows for some tricks that might require a few tries. 
 - `Event Warps In Logic: True` Generally allows for some interesting routing to get to certain places.
 - `Attack Mode: Super or Hyper` This really helps in preventing getting stuck on bosses early.
 - `Enable Map Constraints: True` Make sure to set the number of constraints to around 30 or so. This helps preventing a massive sphere 1.
 - `Shuffle Map Transitions: True` in conjuction with above, helps prevent a massive sphere 1, although headache inducing at times.
 - `Open mode: True` Removes some of the early game friction
 - `Shuffle Start Locations: True` Adds some good variety to the game.

Finally, if using the built in command `/get_logical_path [LOCATION]` doesn't really explain how to get to a destination, you may want to look at (existing_randomizer/)
constraints_graph.txt to get a sense of what items are used to get from one location to the next. There is three operations that you have to understand to figure out 
what possible ways you have to traverse a given obstacle:
 - `|` Represents a logical OR, meaning if an edge has a prerequisite of `SLIDE_POWDER | RABI_SLIPPERS`, then either item provides you the ability to pass the obstacle.
 - `&` Respresents a logical AND, meaning if an edge has a prerequisite of `SLIDE_POWDER & RABI_SLIPPERS`, then both items are required to pass the obstacle.
 - `()` Brackets behave as they do with regular logic, meaning you should evaluate what is inside before applying it outwards. 
 For example `CHAPTER_1 & (SLIDE_POWDER | RABI_SLIPPERS)` means that you must first either have slide or slippers, and then also be able to access Chapter 1.  
Most of the requirements are self explanatory, below are some of the trickier ones to understand
 - `ADV_VHARD, ADV_EXTREME, OBS_VHARD...` refer to the knowledge and difficulty (in that order) combined to pass the obstacle using the given items.
 - `XXXX_ZIP` requires the option associated with the zip to be enabled to be in logic
 - `DARKNESS` requires light orb to traverse, or `darkness without light orb: True` to traverse without
 - `UNDERWATER` requires water orb to traverse, or `underwater without water orb: True` to traverse without. Not to be confused with...
 - `WATER_ORB` requires water orb to traverse, regardless of `underwater without water orb`
 - `SPEEDX` requires a combination of speed boost + speedy to perform the trick. Note that the number is the upgrade level of Speed boost, plus two if you have access to speedy

Congratulations on getting to the end! You should now be well prepared to play with most of the settings in the randomizer, with the exception of `Knowledge: Obscure` and 
`Trick Difficulty: Very hard, Extreme, stupid`, though only a select few have the skill to play on these settings. This guide does leave out contraints, however most are 
obvious when you see them. If there is any particular trick that you don't understand, try checking the specific area guide or asking in the discord channel.