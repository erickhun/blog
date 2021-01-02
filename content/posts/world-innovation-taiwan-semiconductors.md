+++
categories = ["taiwan"]
date = "2020-12-31T12:39:00+01:00"
description = ""
draft = false
image = "/img/tsmc/boston-dynamics.jpg"
og_image = "/img/tsmc/boston-dynamics.jpg"
title = "The world next innovations depend on a single country, Taiwan"
+++

The world's current and next innovations depend on a single country: Taiwan. It's probably one country you might never hear about, or perhaps confuse with its neighbor, Thailand, or even think it's a part of [China](https://en.wikipedia.org/wiki/Political_status_of_Taiwan). 

I've been living in Taiwan for 3+ years, and am baffled that I never pay attention to semiconductors. I'm a software engineer but didn't think much more about the importance of them. As far as my laptop can change code to real things and doesn't lag when I have constantly [hundred tabs open](/img/tsmc/tabs.jpg), I was satisfied.
At a recent [Taiwan Gold Card](https://taiwangoldcard.com) dinner, one of the speakers introduced himself as someone with 30+ years of experience at IBM, who moved to Taiwan for [TSMC](https://en.wikipedia.org/wiki/TSMC). It piqued my curiosity and I started to investigate, to realize how **the world depends on a TSMC for the past decades of innovation, and still be dependant for the next decade**.

## The world needs (and want) better semiconductors

Semiconductors have and had a significant impact on our society. They're everywhere, and essential to any electrical object, from a simple [led](https://en.wikipedia.org/wiki/Light-emitting_diode) to a [shuttle that can send humanity to Mars](https://www.analog.com/en/technical-articles/challenges-for-electronic-circuits-in-space-applications.html#).  Without them, you couldn't read this article, we couldn't drive cars, and wouldn't be able to call your family. They are needed to build any electronic devices. TV's, computers, medical equipment. 

We can illustrate with the COVID19 vaccine that was created in less than 6 months, from research to mass production. This would have been impossible a decade ago. Zoom calls over the internet were made to connect researchers. Any new research papers were instantly available to researchers to make progress. Machine Learning was used to sequence the virus DNA. Cutting edge machines were used to prototype any new potential vaccines. Thousands of volunteers were reached instantly to test the vaccines. Then [millions of vaccines were being manufactured at scale](https://www.labiotech.eu/medical/covid-19-vaccine-manufacture/). And this happened in less than 6 months what would have probably taken years a decade ago.

Making those tiny things might sound easy, but making them better, more efficient, and smaller is the real challenge. Without the progress the semiconductor industry has made, we wouldn't have been where the world is today.  Even if [software](https://a16z.com/2011/08/20/why-software-is-eating-the-world/) or bigger hardware are the final mean, semiconductors do the real works to enable them to run. 

And the future needs semiconductors to be better. We want electronic devices consuming less electricity to save the planet. We want [clean energy](https://repositories.lib.utexas.edu/handle/2152/47379#:~:text=Semiconductors%20play%20a%20key%20role,for%20solar%20electric%20energy%20systems.) (solar panels & co) and replace fossil energy. We want [unlimited battery life for our phone or computer](https://medium.com/pcmag-access/apple-our-new-arm-based-macs-offer-epic-cpu-performance-and-battery-life-3ccda5e1da11). We want a tinier camera with a higher resolution to [spy](https://en.wikipedia.org/wiki/Mass_surveillance_in_China) on citizens of [every country](https://californiaglobe.com/section-2/city-of-san-diego-awarded-ge-mass-surveillance-contract-without-oversight/). We want better computer to run IA, to run your [next domestic helper (or terminator?)](https://youtube.com/watch?v=fn3KWM1kuAw) or [less resourceful bitcoin miners](https://www.bbc.com/news/technology-48853230). We want to space travel. We want [...]

_**The one company that changed the game and enabled that technology to progress, and will help everyone's dream is called TSMC, and they are based in Taiwan**_


{{< youtube fn3KWM1kuAw >}}


## Isn't it just "chips"? It's everywhere it must be simple to do
Not that simple. To understand why TSMC is so essential we should understand first the supply-chain for any end-user electronic devices. 

### The supply chain
Historically, all electronic selling electronic hardware had a small business unit manufacturing the Integrated Circuit (ICs, or chips). It cost money and time to create them. However those companies didn't want to waste time to do those chips, so they ask to other big names such as Texas Instrument, or Samsung to help them do them. 
But those don't necessarily have the capacity or willingness to do chips for those competitors. If so, they were often  asking big bucks to design/manufacture them. 

This when we started to see the born of semiconductors focused company, only designing/manufacturing those chips. Some of those companies only designed them for the end product company. They're called Fabless Company. You'll just need to tell them what you want. TSMC is a bit diffferent. They only manufacture those chips, and you'll need to give them the design of the chip you want. It is called a "Pure Play Foundry". 

To visualize better and understand who is who, let's put some names into players of the supply chain: 
- End product company: Amazon (Cloud servers), Sony (Console), Apple (Phones), Tesla (cars), Samsung*, etc...
- [IDMs](https://en.wikipedia.org/wiki/Integrated_device_manufacturer) (design and manufacture the ICs): Samsung*, Intel
- Fabless (only design chips the ICs and gives to the pure-play foundry for manufacturing): Nvidia, AMD, Qualcomm, Broadcom
- Pure Play (only manufacture the ICs): TSMC, GlobalFoundry

_*You can notice here that Samsung has the End product, ICs design, and manufacturing abilities_

Designing a chip has its own quirks, and burden. You can see it could cost [up to $1.5 billions dollars](https://semiengineering.com/big-trouble-at-3nm/
) to design one: 
![ semiconductor fab breakeven](/img/tsmc/design-chips-nano3-ibs.png)

Again, TSMC only manufactures chips and avoid the design cost. So just manufacturing  must be easy, isn’t it?  This is what I was also thinking, until I dig deeper into the subject.  *The hardest part is actually to manufacture the Integrated Circuit (ICs, or chips)*. Today only 2 companies doing it at the state of the art: TSMC and Samsung. 

### Why is it so hard?

To create smaller and smaller chips, TSMC uses today an extremely difficult process called [Extreme ultraviolet lithography](https://en.wikipedia.org/wiki/Extreme_ultraviolet_lithography) (or EUV). The machine enabling this litography process is provided by a company called [ASML](https://www.asml.com/). The machine has to basically create a new way to make light. The process is to drip molten tin into a chamber, and hit it with a laser to create a bright light/plasma that can make it through the series of mirrors and masks to the wafers (chips). And it happens 50,000 times a minute. Some agree that this machine might probably be the most complicated machine humankind has ever engineered - more difficult than putting a man on the moon. This kind of machine costs itself $120 million US dollar. 1 machine weight 180 tonnes, with the size of a double-decker bus. A  mindblowing part is that [ASML sources from 5000 vendors to make its EUV machines](https://www.economist.com/business/2020/02/29/how-asml-became-chipmakings-biggest-monopoly).

{{< youtube Gqu0L5oVatk >}}

So wouldn't just getting the ASML machine enough to take over TSMC? Not that easy. It's not only ASML lithography machines, but other types of equipment that come into play that come into play. ASML's lithography is only 10% of the manufacturing process (but 20% of the total costs). TSMC needs to learn how to operate each equipment together, and every single equipment has their own quirks, faults, and tolerances. Having to chain all the equipment together, into a high volume manufacturing process, is a problem of itself.

Put simply is ASML sells the pots and TSMC sells the cooking. Cooking is very hard. Each takes a lifetime of specialty to get to the top of the field, it's hard to be good at both. And everything is done with an army of people. People who make chef knives are probably not Michelin star chefs. The machines that ASML builds as simply a tool to which they are the only ones who have been able to solve a specific set of problems. A nice hammer still needs a skilled craftsman to use it.

### The importance of minimizing faults, and Research & Development

Getting the fewest "defects" as possible is the biggest challenge for the manufacturer. This is probably the main focus for the chips manufacturers, and where TSMC excels. The percent of chips found to perform properly is referred to as the yield. If you manufacture chips, but more than 60% of the chips are faulty, this wouldn't be great when you'll need to scale. Those failures can be caused for multiple reasons. Some because of tiny imperfections, others caused of alignment and patterning issues.

The yield is why so much money is poured by the manufacturers into Research and Development. You want to get the highest yield possible, to be able to scale to [billions of chips](https://www.tsmc.com/english/news-events/blog-article-20200801) to satisfy your customers. Each year,  TMSC's customers ask for smaller, and better chips (especially Apple). The process to make them needs to be refined, and new equipments to support those new process are constantly needed. [TSMC invested in 2019 3 billions dollar](https://www.taiwannews.com.tw/en/news/3954592) into R&D, and plan to invest more in 2020.  Would any other company would have the budget to do that? 

Today's TSMC's monopoly is probably the result of a 40 years relationships with partners, with tight relationship and trust between each others. 

{{< youtube SP7PMmetpyw >}}

### Why companies prefer to use TSMC over others?
**It's all about trust**. TSMC and its founder [Morris Chang](https://www.youtube.com/watch?v=wEh3ZgbvBrE) is well respected for [its integrity](https://www.tsmc.com/english/aboutTSMC/values) and being impeccable about it. Companies trust them, and they have a well known clause of non-competitivity with anyone choosing them. When hearing about customers, you’ll likely to hear love stories about people having the chance to work with them and how awesome is TSMC.

Trust that the foundry will not compete unfairly with you. Trust that the foundry will deliver the PPA (power/performance/area). TSMC was impeccable on those 2 points since it was created. [Apple had legal issues with Samsung](https://en.wikipedia.org/wiki/Apple_Inc._v._Samsung_Electronics_Co ) when Apple asked them to manufacture their chips. They won't likely get back to them for this reason.

The other strength of TSMC is probably their inner circle of partners. They a massive ecosystem of partners and customers who together spend trillions of dollars on research and development for the greater good of the fabless semiconductor ecosystem. There is also an inner circle of partners and customers that TSMC intimately collaborates with on new process development and deployment. Including Apple, AMD, ARM or ASML. Sourcing the right partners that will help with the correct equipment for making. They work closely  to improve everyone's process and together partners together spend trillions of dollars on R&D.

Trust toward TSMC is proably the main reason why companies that needs chips will prefer TSMC over others. 

## Why not just do an other TSMC? 
It is not as simple. Every year, billions of US dollars are poured into R&D to keep their advantages. Then production facilities costs billions to build: 
- TSMC last production facility (Fab18) to manufacture [the newest technology 5nm chips cost 17billion USD](https://www.eteknix.com/tsmc-building-fab-18-5nm-production/) (excluding R&D) 
- The next TSMC's fab for [3nm (more advanced) chips with cost 19.6 billion USD](https://www.taiwannews.com.tw/en/news/3805032)

And those production facilities would take up to 5 years to make profit in a best case scenario. Companies must thoroughly investigate product demand, including possible long-term shifts, before beginning fab construction. What seems [not to be a problem for TSMC](https://www.extremetech.com/computing/315186-apple-books-tsmcs-entire-5nm-production-capability) that have more demand than supply. 

![ semiconductor fab breakeven](/img/tsmc/rANDd-breaakeven.jpg)

The most serious competitor to TSMC today is probably Samsung. As explained, some trust or Intellectual Property issues might surface since Samsung is not only doing chips, but also end products for their users. Many countries are trying hard, but they’re not quite there:

- The US has [tried decades ago with Sematech](https://www.technologyreview.com/2011/07/25/192832/lessons-from-sematech/) but failed. 
- Intel (US) today is losing the race. Even with production facilities, and decades of experience, Intel fell years behind Samsung and TSMC. [Their stackholders are also asking to consider outsourcing the manufacturing to their competitors (TSMC or Samsung?)](https://in.reuters.com/article/us-intel-thirdpoint-exclusive/exclusive-hedge-fund-third-point-urges-intel-to-explore-deal-options-idINKBN2931PS). 
- China is trying to catch up, and has already [invested more than $150 billion (!!) in chip manufacturing since 2014](https://thediplomat.com/2020/09/can-china-become-the-world-leader-in-semiconductors/), and about to [pour more](https://www.ft.com/content/46edd2b2-1734-47da-8e77-21854ca5b212). SMIC seems to have the leadership there, with a [few questionable](https://asia.nikkei.com/Business/China-tech/China-hires-over-100-TSMC-engineers-in-push-for-chip-leadership) - [tactics](https://www.eetimes.com/smic-to-pay-175-million-to-tsmc-in-suit-settlement/). But China is still [years (maybe decades?) behind TSMC](https://www.eetimes.com/smic-advanced-process-technologies-and-govt-funding/), even with such a large amount of money invested.
- Europe [will try to join forces](https://www.reuters.com/article/eu-tech-semiconductor-idUSKBN28H1HV) with 10+ countries to try to compete with TSMC by [investing 145 billions Euros](https://www.eetimes.eu/eu-signs-e145bn-declaration-to-develop-next-gen-processors-and-2nm-technology/)

It’s also not only money, it’s semiconductor physics. Intel is not having the issues they have today because they lack time or money. They probably lack of better experts than could help them improve their technology and scale to mass productions.  The number of engineers that has the knowledge on how to put together the chips is so small, compared to the majority of software or hardware engineers on the planet. It isn’t a big field for [Electric Engineer graduates](https://datausa.io/profile/cip/electrical-engineering#:~:text=The%20number%20of%20Engineering%20graduates,to%204.48M%20in%202018.). The problem is [finding and hiring them](https://asia.nikkei.com/Business/China-tech/China-hires-over-100-TSMC-engineers-in-push-for-chip-leadership), and you want the best ones.

Barriers to entry are extremely high for chip manufacturing. One would argue that there are few, if any, other industries that requires as much investment and expertise as semiconductor manufacturing. Apple, is well aware of that and certainly [thought about having their own manufacturing facilities](https://mule.substack.com/p/the-tech-monopolies-go-vertical). It has the cash in bank ($200 billions!), but doesn't have any guarantee that such an investment will results into creating the same quality of chips that TSMC can give them.  

## Conclusion

The cutting edge semiconductor chip manufacturing is (and was) done in Taiwan by TSMC. The island has acquired strategic significance, with partners all over the world depending on them. The chips they make are essentials to any of today's and future hardware: (flying) electrical cars, space ships, servers, 5G, machine to discover new drugs or vaccines, and any military equipments.

Taiwan is now [Arrakis](https://www.epsilontheory.com/taiwan-is-now-arrakis/). If you want to control the empire, you have to control the supply of spice. And if you want to control the supply of spice, you have to control Arrakis. It’s now the most important country on earth. And [we will fight over it...](https://steveblank.com/2020/06/18/the-coming-chip-wars-of-the-21st-century/)




[Comment on Hacker News](https://news.ycombinator.com/item?id=25603340)



#### Next reads:

🚲 [Taiwan's amazing bike sharing system](https://erickhun.com/posts/taiwan-youbike-bike-sharing/)

📚 [Why you should have a side project](https://erickhun.com/posts/why-you-should-have-a-side-project/)

🤸🏻‍♂️ [How to keep working out while travelling](https://erickhun.com/posts/traveling-and-working-out/)



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
