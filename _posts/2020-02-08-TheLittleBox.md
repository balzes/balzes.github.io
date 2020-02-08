---
layout: post
title:  "The Little Box"
#date:   2020-01-31 22:26:23 +0200
# categories:  [electronics]
tags: [electronics]
---


In 2014-2016 Google held a contest named "Little Box Challenge" with a $1 Million prize. The winner should create the smallest power inverter (DC to AC e.g. solar panels to AC mains line) capable to supply 2kW.

Recently, I wanted to re-read some of the ideas that were published on the ~~[LittleBoxChallenge.com](https://www.littleboxchallenge.com/)~~, but the site is dead as Google decided to keep it alive only till the end of 2017 (see their post at [googleblog.com](https://ai.googleblog.com/2016/02/and-winner-of-1-million-little-box.html). It is a little surprising after giving away $1M, a lot of time and effort spent to define and judge the contest, and the final results are thrown away, instead of shared with others. For comparison, Google stores 90 GB (!) of my private data but didn't do the same for <1GB of something more valuable for society. (You can check how much of your data Google has by going to your Google account => Data & personalization => Download your data)

### The clone
After spending an evening of googling, I found some interesting reads about this competition (see below) and weeks later, by chance, the archived version with all the data. My huge thanks for this goes to [Archive.Org](archive.org):  
**[Archived version of LittleBoxChallenge.com](https://web.archive.org/web/20171006105655/https://littleboxchallenge.com/)**

### "The winner takes it all..."
<iframe width="560" height="315" src="https://www.youtube.com/embed/bSrHXpK338k" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
The winners, [CE+T](https://www.cet-power.com), created a neat but mainly advertising one-pager (they also haven't expected that google will close the site so the link to their technical document isn't working):  
[LittleBoxChallengeCETpower.com](http://www.littleboxchallengecetpower.com)  
[The tech doc from the archived site](https://web.archive.org/web/20171006105655/https://littleboxchallenge.com/pdf/finalists/56568-Tech.pdf)

### The 2nd place: Schneider Electric France
![Schneider Electric's Little Box](/assets/images/littlebox_schneider.png)  
Some pic from their [site](https://www.se.com/fr/fr/about-us/newsroom/actualites/little-box-challenge-schneider-electric-developpe-un-prototype-d-onduleur-d-une-puissance-de-2kw-de-la-taille-d-un-appareil-photo-compact-d31c-636ff.html).  
Their technical approach in [the tech doc](https://web.archive.org/web/20171006105655/https://littleboxchallenge.com/pdf/finalists/57137-Tech.pdf).

### The 3rd place: VirginiaTech
[VirginiaTech approach](https://web.archive.org/web/20160603203640/https://www.littleboxchallenge.com/pdf/finalists/59316-Tech.pdf)  
[Additional thoughts](https://gansystems.com/wp-content/uploads/2018/01/A-look-at-virginia-techs-little-box-challenge-design.pdf)


### ETH [!verter](https://pes.ee.ethz.ch/)
The team "!verter" from Albert Einstein's alma mater [ETHZ - Eidgenössische Technische Hochschule Zürich (Swiss Federal Institute of Technology in Zurich )](https://en.wikipedia.org/wiki/ETH_Zurich) published some papers and the analysis of different approaches:   
[!verter approach](https://web.archive.org/web/20160603175437/https://www.littleboxchallenge.com/pdf/finalists/56618-Tech.pdf)   
Nice overview keynotes from conferences (there are a lot of [power publications available](https://www.pes-publications.ee.ethz.ch/publications/conferences/?no_cache=1)):  
[Google Little-Box Reloaded (CIPS 2018)](https://www.pes-publications.ee.ethz.ch/uploads/tx_ethpublications/__CIPS_18_Keynote_FINALFINAL_270318.pdf)  
[ηρ-Pareto Optimization and Comparative Evaluation of Inverter Concepts considered for the GOOGLE Little Box Challenge (COMPEL 2016)](https://www.pes-publications.ee.ethz.ch/uploads/tx_ethpublications/20_np-Pareto_Optimization_and_Comparative_Evaluation_of_Inverter_COMPEL_Bortis_02.pdf)  
[GOOGLE/IEEE Little-Box Challenge (CIPS 2016)](https://www.pes-publications.ee.ethz.ch/uploads/tx_ethpublications/__CIPS_16_Keynote_Presentation_FINAL_as_published_090316.pdf)  
[Approaches to Overcome the Google/IEEE Little-Box Challenges (INTELEC 2015)](https://www.pes-publications.ee.ethz.ch/uploads/tx_ethpublications/Keynote_Presentation_ITELEC_15_FINALFINAL_as_published_251015.pdf)  

### Some other related publications
[Opening the Box](http://ieeexplore.ieee.org/document/8008942/) - published on IEEE but with free open access!




### Capacitor assemblies by TDK
![TDK capacitor assemblies](/assets/images/tdk-caps.png)  
Some interesting findings for myself from the ETH team about ceramic caps assemblies. During my power electronics thesis, I was soldering ceramic capacitors into blocks to reduce ESR and increase allowable peak current, and it is cool that now such assemblies are available of the shelf for commercial usage (although ETH mentioned that single chips X6S MLCC are better):  
[TDK CeraLink Capacitors](https://www.tdk-electronics.tdk.com/en/1195576/products/ceralink-presentation---overview)