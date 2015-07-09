---
layout:     post
title:      The Chesapeake Bay TMDL - Part 1 of Many
date:       2015-07-08 21:26:00
summary:    The effort to save the Bay. 
categories: blog
---

##Foreword##

This post will probably be one of several discussing the Chesapeake Bay TMDL, which is EPA's attempt to save the Bay. The Bay TMDL is a big part of the work I've been doing day-to-day as an engineer for the past six years. It's a huge regulatory driver in the civil / environmental field, and massive amounts of money will be spent on compliance. There's a lot going on but you don't see it in the news too often, perhaps due to the complexity of the situation. Seems worthy of a few blog posts.

##The Chesapeake Bay##

One of the biggest issues in the US environmental field over the past several decades has been figuring out how to fix the Chesapeake Bay. 

The Chesapeake is the largest estuary in the US. The Bay is huge, shallow, and brackish, and its watershed is massive - over 64,000 square miles. It drains six states (Virginia, West Virginia, Maryland, Delaware, Pennsylvania, New York) and Washington, DC before flowing into the Atlantic Ocean. 

![The Chesapeake Bay Watershed]({{site.images}}/cbp_17024.jpg)
*Source:* [*Chesapeake Bay Program*](http://www.chesapeakebay.net/)

The Chesapeake Bay has been in a pretty sorry state for a long time. Historically it was a very important fishery. Supposedly the water was once crystal clear and so densely packed with oysters that ships had a difficult time navigating the shoals. Now the water is generally a nice brownish green, and you'd would be lucky to spot a crab or two on a nice day. 

##What's wrong with the Chesapeake Bay?##

The Bay is clogged with excessive sediment (or "suspended solids") and nutrients (nitrogen and phosphorus). 

Excessive sediment is a pretty straightforward thing to understand. As erosion occurs, soil and other particles make their way downhill toward the water. The really small particles tend to remain suspended in the water, making it brown and gross and blocking light from aquatic plants. Some amount of erosion is natural, but the Bay is having particularly bad sediment problems because of erosion caused by farming and high-energy stormwater runoff from urban areas. 

But wait - excessive nutrients? How does that even happen? Is the Chesapeake Bay taking too many vitamins?

Well, yes. Sort of. The growth of an ecosystem is controlled by what's called a "limiting nutrient." Limiting nutrients are elements essential to life, and they govern ecosystem growth simply because they're difficult to come by. Elements like carbon, oxygen, and hydrogen are really easy to find on Earth, and ecosystems basically never run out of them. They're always in abundance. Limiting nutrients, however, are more scarce, and life has evolved to make very efficient use of them. Nitrogen is the limiting nutrient in saltwater ecosystems, and phosphorus is the limiting nutrient in freshwater ecosystems.

If you add too much nitrogen or phosphorus to an aquatic ecosystem, this is what happens - a process called [eutrophication](https://en.wikipedia.org/wiki/Eutrophication):

1.  Nurtient-hungry cynaobacteria sucks up the nitrogen and phosphorus.
2.  Cynaobacteria multiply like crazy, forming "algae blooms." 
4.  Algae blooms block sunlight from aquatic plants, reducing available oxygen
5.  Algae bloom eventually dies and drifts to the bottom
6.  Microorganisms feed on the dead algae mass, consuming dissolved oxygen in the process
7.  Fish die due to lack of dissolved oxygen
8.  Other bad things

Basically, too much nitrogen and phosphorus means gross water and dead fish. 

Nitrogen and phosphorus are in fertilizers, human/pet/livestock waste, food waste, and yard waste. Human sources include farms, lawns, sewer/septic systems, and urban stormwater runoff. Nurtients have always cycled through the environment naturally, but we're overloading the system.

##The Chesapeake Bay TMDL##

So, back to the Chesapeake Bay - how do we control nitrogen, phosphorus, and sediment pollution coming from six different states and the captiol? 

EPA's answer: *The Chesapeake Bay TMDL*. 

TMDL stands for Total Maximum Daily Load. EPA likes to explain that TMDLs are "pollution diets." A TMDL is the maximum amount of pollution a water body can receive and still remain healthy. To fix the Bay, the EPA has established target pollution levels for nitrogen, phosphorus, and sediment throughout the Bay watershed. 

The scientific process of establishing a TMDL is, in a word, difficult. Water samples are taken, pollution levels are measured, and a computer model is developed to simulate water flow and pollution concentrations. Then the model is used to figure out what needs to be done in order to reduce pollution concentrations below the critical level. 

Maybe that sounds straightforward, but it isn't. 

##Modeling the Chesapeake Bay##

First of all, simply measuring water flow in an aquatic system is difficult. Unlike a manmade system, the natural world isn't made out of perfect circles and lines and right-angles - it's a squiggly, blobby, irregular mess with rough edges and weeds everywhere. The natural landscape is constantly shifting, and it doesn't come with design specs. Measuring flow in pipe is easy; measuring the flow in a river is really hard. Variations in a river's shape and water velocity cause can complex flow patterns, and one good storm can completely change a river channel. The USGS has an entire department dedicated to measuring river flows across the US, but they're only able to scratch the surface. There are roughly 10,000 active stream gages throughout the US, but there are over XXX miles of rivers and streams. There are some gaping holes in our river data.   

But rivers aren't even the half of it. There's also groundwater flow, which I won't get into because I don't completely understand it myself. Just like a river, groundwater also moves. It tends to move slowly and in weird, counterintutive patterns. If measuring river flows is difficult, measuring groundwater flow...well...you can't even see it, for starters. 

Measuing pollution concentrations is also easier said than done. Engineers and scientists physically visit a site, collect water samples, and bring them back to a lab for analysis. Some types of measurements can be taken remotely with automated equipment, but generally speaking you need dedicated field staff. This gets expensive very quickly. Samples can easily get contaminated or taken at non-ideal times or locations. 

Getting back to our TMDL computer model, we use landuse, soils, and rainfall data to build a hydrologic simulation of our watershed. Then - *if it's even available* - we use real-world flow data and water quality data to calibrate our model. 

I'd like to point out here - if it wasn't obvious already - that hydrologic models are fickle things. One-hundred percent accuracy is impossible; 90% accuracy would be like running a three-minute mile. Generally speaking, the bar for accuracy in hydrologic modeling is absurdly low. That's not a criticism of the engineers and scientists in the field - it's just the nature of the problem. Measuring and simulating natural systems is really, really, really hard.

The Chesapeake Bay TMDL is backed by the Chesapeake Bay Model. The CBM is a highly customized system developed by the Chesapeake Bay Program - a group of really smart people at EPA. 

But regarding the CBM, I'm going to go out on a limb here and guess that fewer than two dozen people *really* understand it. Some staff at the Bay Program, a handful of academic researchers, maybe a few consultants, a couple state or federal employees, and that's it. Why so few? Well, just [download](http://ches.communitymodeling.org/models/CBPhase5/) it yourself and get try to get it running. 

Oh, did I mention that you'll need to install Linux first? Yeah, you'll need to install Linux first. Then you'll probably need to compile some Fortran77 code. Have you ever extracted a tar.gz file? Are you comfortable at a Unix command line? Knowing Bash would definitely be helpful. 

Computers are hard! The CBM is very computer-y. Environmental professionals get worked up about nested Excel functions and ArcGIS Model Builder. The CBM is on a whole other level. 

##Some Closing Thoughts (For Now)##

The environmental community as a whole has essentially put complete trust in the Chesapeake Bay Program to build a model for the Bay TMDL. And maybe that's actually okay. Understandable or not, the CBM is a monumental undertaking and a huge accomplishment. The Bay program staff is likely more qualified than anyone else to take it on. Maybe the labyrinthe structure of the CBM helps keep out the lesser-qualified trolls and nitpickers who would slow down the process. The Bay really does need saving, after all.
