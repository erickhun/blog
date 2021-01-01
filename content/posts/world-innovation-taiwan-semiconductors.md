+++
categories = ["taiwan"]
date = "2020-12-31T12:39:00+01:00"
description = ""
draft = false
image = "/img/about-bg.jpg"
title = "The world's innovation depends on a single country: Taiwan"
+++

The world's next innovations depends on a single country: Taiwan. It's probably one country you might never heard about, or perhaps confuse with it neighbor, Thailand, or even think it's a part of [China](https://en.wikipedia.org/wiki/Political_status_of_Taiwan). 

I've been living in Taiwan for  3+ years, and baffled that I never pay attention to semiconductors. I'm a software engineer, but didn't think much more about the importance of them. As far as my laptop can change code to real things and doesn't lag when I have constantly [hundred tabs open](/img/tsmc/tabs.jpg), I was satisfied.
At a recent [Taiwan Gold Card](https://taiwangoldcard.com) dinner, one of the speakers introduced himself as someone with 30+ years experience at IBM, who moved to Taiwan for [TSMC](https://en.wikipedia.org/wiki/TSMC). It picked my curiosity, and started to investigate, to realize how **the world depends on a TSMC for the past decades of innovation, and still be for the next ones**.


## The world needs (and want) better semiconductors

Semiconductors has and had a significant impact on our society. They're everywhere, and essential to any electrical object, from a simple [led](https://en.wikipedia.org/wiki/Light-emitting_diode) to a [shuttle that can send the humanity to Mars](https://www.analog.com/en/technical-articles/challenges-for-electronic-circuits-in-space-applications.html#).  Without them, you couldn't read this article, we couldn't drive cars , and wouldn't be able to call your family. They are needed to build any electronic devices. TV's, computers, medical equipment. 

We can illustrate with the COVID19 vaccine that was created in less than 6 months, from research to mass production. This would have been impossible a decade ago. Zoom calls over internet were made to connect researchers. Any new reasearch papers were instantly available to researchers to make progress. Machine Learning was used to sequence the virus DNA. Cutting edges machines were used to prototype any new potential vaccines. Thousansands of volunteers were reached instantly to test the vaccines. Then [millions of vaccines were be manufactured at scale](https://www.labiotech.eu/medical/covid-19-vaccine-manufacture/). And this happened in less than 6 months what would have probably take years a decade ago.

Making those tiny things might sound like an easy, but making them better, more efficient, and smaller is the real challenge. Without the progress the semiconductor industry has made, we wouldn't have been where the world is today.  Even if [software](https://a16z.com/2011/08/20/why-software-is-eating-the-world/) or bigger hardware are the final mean, semicondutors do the real works to enable them to run. 

And our future needs needs semiconductors to be better. We want electronic devices consuming less electricity to save the planet. We want [clean energy](https://repositories.lib.utexas.edu/handle/2152/47379#:~:text=Semiconductors%20play%20a%20key%20role,for%20solar%20electric%20energy%20systems.) (solar panels & co) and replace fossil energy. We want [unlimited battery life for our phone of computer](https://medium.com/pcmag-access/apple-our-new-arm-based-macs-offer-epic-cpu-performance-and-battery-life-3ccda5e1da11). We want tinier camera with higher resolution to [spy](https://en.wikipedia.org/wiki/Mass_surveillance_in_China) citizens of [every country](https://californiaglobe.com/section-2/city-of-san-diego-awarded-ge-mass-surveillance-contract-without-oversight/).  We want better computers to run IA and run your [next domestic helper (or terminator?)](https://youtube.com/watch?v=fn3KWM1kuAw). We want to space travel. We want [...]

_**The one company that changed the game, enabled those technology to progress, and will help everyone's dream is called TSMC.**_


{{< youtube fn3KWM1kuAw >}}


## Isn't it just "chips"? It's everywhere it must be simple to do
Not that simple. To understand why TSMC is so essential we should understand first the supply-chain for any end user electronic devices. 

### The supply chain
Historically, all electronic selling electronic hardware had a small business unit manufacturing the Integrated Circuit (ICs, or chips). It cost money and time to create them. However those companies didn't want to waste time to do those chips, so they ask to other big names such as Texas Instrument, or Samsung to help them do them. 
But those doesn't necessarly have capacity or willingness to do chips for those competitors. If so, they were often  asking big bucks to design/manufacture them. 

This is wheen we start seeing the born of semiconductors that we only designing/manufacturing those the chips. Some of those companies only designed them for the end product company. They're called Fabless Company. You'll just need to tell them what you want. TSMC is a bit diffferent. They only manufacture those chips, and you'll need to give them the design of the chip you want. It is called a "Pure Play Foundry". 

To vizualize better and understand who is who, let's put some names into players of the supply chain: 
- End product company: Canon (Camera), Sony (Console), Apple, Tesla (cars) Samsung*, etc...
- [IDMs](https://en.wikipedia.org/wiki/Integrated_device_manufacturer) (design and manufacture the ICs): Samsung*, Intel
- Fabless (only design chips the ICs and give to pure play foundry for manufacturing): Nvidia, AMD, Qualcomm, Broadcom
- Pure Play (only manufacture the ICs): TSMC, GlobalFoundry, 

_*You can notice here that Samsung has the End product, ICs design, and manufacturing abilities_

Designing a chip has its own quirks, and burden. You can see it it could cost [up to $1.5 billons dollars](https://semiengineering.com/big-trouble-at-3nm/
) to design one: 
![ semiconductor fab breakeven](/img/tsmc/design-chips-nano3-ibs.png)

Again, TSMC only manufactures chips and avoid the design cost. So just manufacturing  must be easy isn't it? This is what I was also thinking, until I dig deeper into the subject.  *The hardest part is actually to manufacture the Integrated Circuit (ICs, or chips)*. Today only 2 companies doing it at the state of the art: TSMC and Samsung. 

### Why is it so hard?

To create smaller and smaller chips, TSMC uses today a proces called [Extreme ultraviolet lithography](https://en.wikipedia.org/wiki/Extreme_ultraviolet_lithography) (or EUV). The machine enabling this litography process is provided by a company called [ASML](https://www.asml.com/). The machine has to basically create a new way to make light. Extreme difficult process called [Immersion Litography](https://en.wikipedia.org/wiki/Immersion_lithography). The process is to drip molten tin into a chamber, and hit it with a laser to create a bright light / plasma that can make it through the series of mirrors and masks to the wafers (chips). And it happens 50,000 times a minute. Some agrees that this machine might probably be the most complicated machine human kind has ever engineered - more difficult than putting a man on the moon. This kind of machine costs itself $120 million US dollar. 1 machine weight 180 tonnes, with the size of a double-decker bus. A  mindblowing part is that [ASML sources from 5000 vendors to make its EUV machines](https://www.economist.com/business/2020/02/29/how-asml-became-chipmakings-biggest-monopoly).

{{< youtube Gqu0L5oVatk >}}

So wouldn't just getting the ASML machine enough to take over TSMC? Not that easy. It's not only ASML lithography machines, but other equipments that come into play. ASML's lithography is only 10% of the manufacturing process (but 20% of the total costs). TSMC needs to learn how to operate each equipment together, and every single equipment has their own quirks, faults and tolerances. Having to chain all the equipment together, into a high volume manufacturing process, is a problem of itself.

Put simply is ASML sells the pots and TSMC sells the cooking. Cooking is very hard. Each takes a lifetime of specialty to get to the top of the field, it's hard to be good at both. And everything is done with an army of people. People who make chef knives are probably not michellin star chefs. The machines that ASML builds as simply a tool to which they are the only ones who have been able to solve a specific set of problems. A nice hammer still needs a skilled craftsman to use it.

### The importance of minimizing faults, and Research & Development

Getting the fewer "defects" as possible is the biggest challenge for manufacturer. This is probably the main focus for the chips manufacturers, and where TSMC excels. The percent of chips found to perform properly is referred to as the yield. If you manufacture chips, but more than 60% of the chips are faulty, this wouldn't be great when you'll need to scale. Those failure can be caused for multiple reasons. Some because of tiny imperfections, others caused of alignment and patterning issues.

The yield this is why so much money are poured by the manufacturers into Research and Development. You want to get the highest yield as possible, to be able to scale to [billons of chips](https://www.tsmc.com/english/news-events/blog-article-20200801) to satisfy your customers. Each year,  TMSC's customers ask for smaller, and better chips (especially Apple). The process to make them needs to be refined, and new equipments to support those new process are constantly needed. [TSMC invested in 2019 3 billons dollar](https://www.taiwannews.com.tw/en/news/3954592) into R&D, and plan to invest more in 2020.  Would any other other company would have the budget to do that? 

Today's TSMC's monopoly is is probably the results of a 40 years relationships with partners working wit each other, creating tight relationship and trust between each other. 

{{< youtube SP7PMmetpyw >}}

### Why companies prefer to use TSMC over others?
**It's all about trust**. TSMC and its founder [Morris Chang](https://www.youtube.com/watch?v=wEh3ZgbvBrE) is well respected for [its integrity](https://www.tsmc.com/english/aboutTSMC/values) and being impecable about it. Companies trust them, and they have a well known clause of non-competitivity with anyone chosing them. When hearing about customers, you'll likely to hear love story with peolpe having the chance to work with them and how awesome is TSMC. 

Trust that the foundry will not compete unfairly with you. Trust that the foundry will deliver the PPA (power/performance/area). TSMC was impeccable on those 2 points since it was created. [Apple had legal issues with Samsung](https://en.wikipedia.org/wiki/Apple_Inc._v._Samsung_Electronics_Co ) when Apple asked them to manufacture their chips. They won't likely get back to them for this reason.

The other strength of TSMC are probably their inner circle of partners. They a massive ecosystem of partners and customers who together spend trillions of dollars on research and development for the greater good of the fabless semiconductor ecosystem. There is also an inner circle of partners and customers that TSMC intimately collaborates with on new process development and deployment. Including Apple, AMD, ARM or ASML. Sourcing the right partners that will helps into the correct equipment for making. They work closely  to improve everyone's process and together partners together spend trillions of dollars on R&D.

Trust toward TSMC is proably the main reason why companies that needs chips will prefer TSMC over others. 

## Why not just do an other TSMC? 
It is not as simple. Every year, billons of US dollars are poured into R&D to keep their advantages. Then production facilities costs billons to build: 
- TSMC last production facility (Fab18) to manufacture [the newest technology 5nm chips cost 17billion USD](https://www.eteknix.com/tsmc-building-fab-18-5nm-production/) (excluding R&D) 
- The next TSMC's fab for [3nm (more advanced) chips with cost 19.6 billion USD](https://www.taiwannews.com.tw/en/news/3805032)

And those production facilities would take up to 5 years to make profit in a best case scenario. Companies must thoroughly investigate product demand, including possible long-term shifts, before beginning fab construction. What seems [not be a problem for TSMC](https://www.extremetech.com/computing/315186-apple-books-tsmcs-entire-5nm-production-capability) that have more demand than supply . 

![ semiconductor fab breakeven](/img/tsmc/rANDd-breaakeven.jpg)

The most serious competitor to TSMC today is probably Samsung. As explained, some trust or Intellectual Propery issues might surfaced since Samsung is not only doing chips, but also end products for their users. Many countries are trying hard, but they're not quite there: 

- The US has [tried decades ago with Sematech](https://www.technologyreview.com/2011/07/25/192832/lessons-from-sematech/) but failed. 
- Intel (US) today is losing the race. Even with production facilities, and decades of experience, Intel fell years behind Samsung and TSMC. [Their stackholders are also asking to consider outsourcing the manufacturing to their competitors (TSMC or Samsung?)](https://in.reuters.com/article/us-intel-thirdpoint-exclusive/exclusive-hedge-fund-third-point-urges-intel-to-explore-deal-options-idINKBN2931PS). 
- China is trying to catchup with their with [multibillion-dollar government plan](https://www.ft.com/content/46edd2b2-1734-47da-8e77-21854ca5b212) SMIC with [multiple tactics](https://www.eetimes.com/smic-to-pay-175-million-to-tsmc-in-suit-settlement/). But they're still [years (decades?) behind TSMC](https://www.eetimes.com/smic-advanced-process-technologies-and-govt-funding/). 
- Europe [will try to join force](https://www.reuters.com/article/eu-tech-semiconductor-idUSKBN28H1HV) with 10+ countries to try to compete with TSMC. 

## Conclusion

The cutting edge semiconductor chip manufacturing is (and was) done in Taiwan. The island has acquired strategic significance, with partners all over the world.  Those chips helps every new products to progress: (flying) electrical cars, space ships, Phones, 5G , new drugs to progress. It became a key technology , but also in any world military forces.  
Creating an other is not that simple as pouring money . 

<!-- ### Cost of creating an other TSMC


Morris Chang had the idea to create a new model, where all those companie would , and they'll only focus . Pretty simple isn't it? Wrong. 
It might have been simple, but the more you want, the more research you'll need to invest. In human ressource.


Apple knows how hard it is to create. It is simpler for them to let, and focusing on products people want. iPhones, macbook, and cars ;) . They gave to build a new plant in the south only to build the. Who else could do that? 

Trust between vendors and TSMC: https://www.youtube.com/watch?v=wEh3ZgbvBrE

TSMC : never compete with our customers
Because trust ans integrity. they don't do product, they enable other companies tondo products


Make their partner better and better

To compare, Apple invested 9B to build a fab for APple produt, while the biggest raised . 

TSMC make better progress with less risks. progress are .
They work closely with all their partner to make sure progress are made. 
All those parameter compound over time, and result in better performance, better technlogy 


For its 7nm processor, they've announced 1b chips made https://www.tsmc.com/english/news-events/blog-article-20200801

Apple also want that innovation, and ready to pay more to TSMC for them to innovate and do more reasearch. They don't mind pouring 
from R&D to 2 years to chip 1B chips is amazing. and no one can compete today. 

 
Apple already booked https://wccftech.com/apple-secured-80-tsmc-5nm-production-capacity-2021/





It is not because you have a recipe that your food will be great.
You'll need a good recipe, some great ustensile, and someone who can put it together to make it work.


## Geopolicatcal status quo
Cold war between China 
China is now . but don't have access to the best chips to create new products
It settled with an other company, but 

https://thediplomat.com/2020/12/taiwan-chips-and-geopolitics-part-1/


## So why don't we derisk it?
Europe is edging with this new
USA tried to edge in the past but failed
Barrier to entry:
McKinsey report -->
