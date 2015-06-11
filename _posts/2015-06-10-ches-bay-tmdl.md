---
layout:     post
title:      The Chesapeake Bay TMDL
date:       2015-06-10 19:19:00
summary:    My attempt to explain the effort to save the Bay. 
categories: blog
---

One of the biggest issues in the US environmental / water field over the past several decades has been deciding what to do about the Chesapeake Bay. 

The Chesapeake is the largest estuary in the US. The Bay is huge, shallow, and brackish, and its watershed is massive - over 64,000 square miles. It drains Virginia, West Virginia, Maryland, Delaware, Pennsylvania, New York, and Washington, DC. 

[map]

The Chesapeake Bay has been in a pretty sorry state for a long time. Historically the Bay was a very important fishery, but not so much these days. Supposedly the Bay was once crystal clear and so packed with oysters that ships had a difficult time navigating the shoals. Now the water is generally a nice brownish green, and you would be lucky to spot a crab or two on a nice day. 

More scientifically speaking, the Bay is clogged with excessive sediment (or "suspended solids") and nutrients (nitrogen and phosphorus). 

Excessive sediment is a pretty straightforward thing to understand. As erosion occurs, soil and other particles eventually make their way toward a water body. The really small particles tend to remain suspended in the water, making it brown and gross, and blocking light from aquatic plants. Some amount of erosion is natural, but the Bay is having particularly bad sediment problems because of erosion caused by farming and high-energy stormwater runoff from urban areas. 

But excessive nutrients? Is that even a thing? Like, taking too many vitamins?

Well, yes. Sort of. The growth of an ecosystem is controlled by what's called a "limiting nutrient." Limiting nutrients are elements essential to life, and they govern ecosystem growth simply because they're  difficult to come by. For example, elements like carbon, oxygen, and hydrogen are really easy to find on Earth, and ecosystems basically never run out of them. Limiting nutrients, however, are the hardest building blocks to find. Often the only source of limiting nutrients is within the ecosystem itself - from other organisms. The nutrients get caught up in the cycle of life very quickly and are constantly recycled. Life has evolved to make very efficient use of scarce limiting nutrients. Phosphorus is typically the limiting nutrient in freshwater systems, and nitrogen is typically the limiting nutrient in saltwater systems. 

If you add too much nitrogen or phosphorus to an aquatic system, this is what happens - a process called *eutrophication*:
1. Nurtient-hungry cynaobacteria sucks up the N and P
2. Cynaobacteria multiply like crazy, forming "algae blooms." 
2a. Cyanobacteria release toxic compounds, killing fish
2b. Algae blooms block sunlight from aquatic plants, reducing available oxygen
3. Algae bloom eventually dies and falls to the bottom
4. Other organisms feed on the dead algae mass, consuming oxygen in the process
5. Fish die due to the lack of oxygen
6. Many other things

Basically, too much nitrogen or too much phosphorus = gross water and dead fish. 

Nitrogen and phosphorus are in fertilizers, human/pet/livestock waste, food and yard waste, and nitrogen even falls directly from the sky (atmospheric deposition). Human sources include farms, lawns, sewer/septic systems, and urban stormwater runoff. 

So, back to the Chesapeake Bay - how do we control nitrogen, phosphorus, and sediment pollution coming from six different states and the captiol? EPA's answer: a Chesapeake Bay *TMDL*. 

TMDL stands for Total Maximum Daily Load. It's term from the EPA lexicon. EPA likes to explain TMDLs as "pollution diets." Essentially, a TMDL is the maximum amount of pollution a water body can receive and still remain healthy. To fix the Bay, the EPA has established target pollution levels for nitrogen, phosphorus, and sediment throughout the Bay watershed. The "Chesapeake Bay TMDL" actually refers to a group of 92 inidividual TMDLs for sub-watersheds throughout the Chesapeake Bay watershed. 

The scientific process of establishing a TMDL is, in a word, difficult. Water samples are taken, pollution levels are measured, and a computer model is developed to simulate water flow and pollution concentrations. Then the model is used to figure out what needs to be done in order to reduce pollution concentrations below a particular level. Maybe that sounds straightforward, but it's not. 

First of all, simply measuring and modeling water flow in an aquatic system is difficult. Unlike a manmade system, the natural world isn't made out of perfect circles and lines and right-angles - it's a weird, blobby, irregular mess. The natural landscape is constantly shifting, and it doesn't come with design specs. Measuring the flow in pipe is easy; measuring the flow in a river is really hard. Variations in river channel shape and water velocity cause complex flow patterns. The USGS has an entire department dedicated to measuring river flows across the US. But even then, they're only able to scratch the surface. There are roughly 10,000 active stream gages throughout the US, but there are over XXX miles of rivers and streams. There are some gigantic gaps in our river data.   

But rivers aren't even the half of it - there's also groundwater flow, which I won't get into because I don't completely understand it myself. If measuring river flows accurately is difficult, measuring groundwater flow accurately is nearly impossible. I mean... you can't even see it. 

Measuing pollution concentrations in the aquatic environment is also difficult. Engineers and scientists physically visit a site, collect water samples, and bring them back to a lab for analysis. Some kinds of measurements can be taken remotely with automated equipment, but generally speaking you need field staff to get the right data. This gets expensive very quickly, and samples can be easily contaminated or taken at non-ideal times or locations. Much like river and ground water flow data, getting good water quality data is difficult. 

Getting back to our TMDL computer model, we basically use landuse, soils, and rainfall data to build a hydrologic simulation of our watershed. Then, if it's even available, we use flow and water quality data to calibrate our model and bring it more in line with real-world conditions. I'd like to point out here - if it wasn't obvious already - that hydrologic models are fickle things. One-hundred percent accuracy is impossible; 90% accuracy would be like running a three-minute mile. Generally speaking, the bar for accuracy in hydrologic modeling is absurdly low. That's not a criticism of the engineers and scientists in the field - it's just the nature of the problem. Measuring and simulating natural systems is just really, really, really hard.

The Chesapeake Bay TMDL is backed by the Chesapeake Bay Model. The CBM is a highly customized system developed by the Chesapeake Bay Program - a group of really smart people at EPA. You can actually download the source code / data and run the model yourself. 

Regarding the CBM, I'm going to go out on a limb here and guess that fewer than two dozen people *really* understand it. Some staff at the Bay Program, a handful of academic researchers, maybe one or two consultants, one or two state or federal employees, and that's it. Why? Well, just download it yourself and get try to get it running. 

Oh, did I mention that you'll need to install Linux first? Yeah, you'll need to install Linux first. Then you'll probably need to compile some Fortran77 code. Have you ever extracted a tar.gz file? Are you comfortable at a Unix command line? Knowing Bash would definitely be helpful. 

Aaaand that's why so few people understand it. Computers are hard! The CBM is very computer-y. Environmental professionals get worked up about Excel formulas and ArcGIS Model Builder, but the CBM is on a whole other level. 

So, the environmental community as a whole has basically put complete trust in the Chesapeake Bay Program to build a good-enough model for the Bay TMDL. And maybe that's okay. Understandable or not, the CBM is a monumental undertaking and a giant accomplishment. The Bay program staff is apparently a super-qualified team of eco-geniuses. Maybe the labyrinthe structure of the CBM helps keep out the lesser-qualified trolls and nitpickers who would slow down the process. 
