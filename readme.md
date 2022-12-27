# Ulduar PTR Data

MORE Text will go here eventually.

The main purpose of this data is to:

(1) Identify which parts of each boss encounter raids were having the most trouble with.

(2) Obtain a rough estimate of kill times.

Based on the bias the data has (coming from PTR) it would be bold to assume the kill:wipe rates in PTR will be the same in live servers once Ulduar goes out. You can check more details regarding the "limitations" of this data at the bottom.

# Table of Contents
1. [Hardmodes](#hardmodes-wipes-and-kills-) <br>
        1.2. [Iron Council HM](#iron-council-hm-)<br>
        1.3. [Freya HM](#freya-hm-)<br>
        1.4. [Hodir](#hodir-)<br>
        1.5. [Mimiron HM](#mimiron-hm-)<br>
        1.6. [Thorim HM](#thorim-hm-)<br>
        1.7. [General Vezax HM](#general-vezax-hm-)<br>
        1.8. [Algalon](#algalon-)<br>
        1.9. [Yogg-0](#yogg-0-)<br>
2. [Overrall Tables](#overall-tables---boss-encounters-)<br>
3. [Methodology](#methodology-)<br>
        3.1 [Limitations](#limitations-)<br>

## Hardmodes Wipes and Kills <a name="Hardmodes"></a>

### Iron Council HM <a name="Boss1"></a>

Most of the wipes happen close to the dead of the 2nd add (right before or right after). Likely related to tanks (not) surviving Steelbreaker Fusion Punch or increased damage of Phase 3 in general.

  <img src="img/Iron Council.png" />
 
  <img src="img/Council Table 1.png" />
  
  <img src="img/Council Table 2.png" />

### Freya HM <a name="Boss2"></a>

Wipes happen mostly early in the fight, during the first 3 sets of adds spawning.

  <img src="img/Freya HM plot1.png"/>
  
  <img src="img/Freya Table 1.png" />
  
  <img src="img/Freya Table 2.png" />

### Hodir <a name="Boss3"></a>

Lots of wipes right after the 2 minutes mark (required for it to be "hardmode"). Likely intentional, but very few were able to make it.

 <img src="img/Hodir plot1.png" />


### Mimiron HM <a name="Boss4"></a>

 <img src="img/mimiron_plot.png" />
  
  <img src="img/Mimiron table 1.png" />
  
  <img src="img/Mimiron table 2.png" />

### Thorim HM <a name="Boss4"></a>

 <img src="img/Thor_Plot.png" />
 
### General Vezax HM <a name="Boss5"></a>

 <img src="img/vez_plot.png" />
 
### Algalon <a name="Boss6"></a>

 <img src="img/Alga_plot.png" />
 
### Yogg-0 <a name="Boss7"></a>

Wipes on phase 1, 2 and 3

 <img src="img/Yogg 0 HM plot1.png" />
 Less than 1% of attempts on Yogg-0 resulted in a kill.
 <img src="img/Yogg Table1.png" />


## Overall Tables - Boss Encounters <a name="Tables1"></a>

DISCLAIMER: Data in the following tables are for BOTH hardmodes AND normal modes.For now.
Blame Blizzard/WCL

Tables originally posted (by me) in this reddit post:
https://www.reddit.com/r/classicwow/comments/zob655/5_of_yogg_25m_attempts_were_a_kill_ulduar_ptr/

 <img src="img/Table1.png" />
 <img src="img/Table2.png" />

## Methodology <a name="Methodology"></a>

More text will go here

All the data was collected using the WCL API and processed with R v.4.1 (R Development Core Team).

Ideally this repository should eventually have both the aggregated data used and all the code made to generate both the tables and the graphics.

### Hardmode classification

At the moment of this analysis being done, there is no "Hardmode/Normal" category for Ulduar Bosses data. 

In order to classify a wipe or kill as "hardmode" the following criteria was used:

- Iron Council: 
            - "Steelbreaker" has to be alive (no death for "Steelbreaker" in the logs)
            - "Steelbreaker" has to die 3rd (after both "Runemaster Molgeim" and "Stormcaller Brundir" have died, doesn't matter the order of these 2).

- Freya: Any attempt were Freya had either Brightleaf's Essence (ability.id = 62385) or Stonebark's Essence (ability.id = 62386) was considered a "HM" attempt.

- Hodir: All attempts are presented in the graphics, since the only condition for it to be "HM" is killing Hodir sub 2 minutes.

- Mimiron:
            - The Emergency Mode (ability.id = 64582) is present on Enemies (only detectable in P2 onwards).
            - Damage from Flames (ability.id = 64566) is present on Friendlies (detectable if someone gets hit by it, which is almost always at least 1 person. If you aren't getting hit by Flames, you are likely making it to P2 therefore being detected through Emergency Mode)
            
- Thorim:
            - The wipe happens before 3 minutes
            - Thorim does NOT gain the buff Touch of Dominion (ability.id = 62565), which he can only get it if he loses Touch of Dominion (ability.id = 62507) after 3 minutes have passed.
            
- General Vezax: Friendlies have NOT received damage from Saronite Vaporsfrom (ability.id = 63338)

- Yogg-0: None of the following buffs can be present on friendlie units:
            - Speed of Invention (ability.id = 62671)
            - Resilience of Nature (ability.id = 62670) 
            - Fury of the Storm (ability.id = 62702) 
            - Fortitude of Frost (ability.id = 62650)

### LIMITATIONS <a name="Limitations"></a>

a.k.a. Things to consider when interpreting this as "information"


- Not all logs are public. Given it is on the interest of some guilds to make their logs private on PTR due to the competitive nature of "progression" rewards (lumberjack rankings, in-game title, larping), this statistics are more biased towards a more casual playerbase. (I.E. less kills, more wipes, longer kill times).


- Not everyone has logs of their runs. Probably a minority, if you think most players are in a somewhat well-informed communities. Or it could be a great majority of players not logging their runs if you think most of the playerbase is "casual" and doesn't care about logging.


- PTR  means a portion of the players have either incomplete or scuffed UIs/macros/addons, making the overrall performance of the average player worse than what it actually is in live servers. Another group of the PTR players could also be testing specs and gear.

- Raids in general are mostly testing the content, sometimes wiping on purpose or doing quick pulls "just to see the boss". 


![Flowchart of data](img/flowchart.jpeg)
