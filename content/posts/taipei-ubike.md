+++
categories = ["taiwan", "taipei"]
date = "2020-09-27T22:50:00+08:00"
description = ""
draft = false
image = "/img/about-bg.jpg"
title = "Taiwan amazing bike-sharing system"
+++
[YouBike](https://taipei.youbike.com.tw/home) (or Ubike) is my first choice of transportation when it comes to move around the city of Taipei. I largely prefer it over taking the subway, bus or taxi. It is affordable, well maintained, comfortable, at waking distance reach from anywhere, and the cities has built great biking paths in the major cities. 

## A high quality infrastructure 

YouBikes are [everywhere](https://taipei.youbike.com.tw/station/map) in Taipei and New Taipei City . As for October 2020, over [42000 YouBikes are deployed](https://gist.github.com/erickhun/f0d3e8f3c3c4f70dc521c2abb43bb8a0), with over 1000 stations. Stations [get added every few weeks](https://taipei.youbike.com.tw/news/list?5cb582c1060db454916c643c).

Since the first time I arrive in Taipei (2016), I am pleasantely  suprised that I rarely got a broken bike. [Giant](https://en.wikipedia.org/wiki/Giant_Bicycles) is actually the (local) company that provides them. The bikes feels durable, lightweight, and really well maintained. Each bike is bought by the city for around [9200 TWD (~USD 300)](https://disp.cc/b/163-6PkZ), and comes with a 7 years maintenance. 

To make it really convenient, the city has organized each station   [from 200 to 600 meters](https://english.gov.taipei/News_Content.aspx?n=A11F01CFC9F58C83&s=5888478293ADD1A8) from each others. What make you within 5 to 10 minutes walk from wherever you are in the city.


![](https://i.imgur.com/F5HWa3v.jpg)


## Data driven decisions

I've noticed that station are also rarely empty. From time to time, I've noticed some employees "reloading" or "deloading" stations that are full or empty. Who are they? Where do they take those bikes?  I've discussed with [Alex Garcia](https://twitter.com/TaipeiUrbanism) and [Tim Cho](https://www.linkedin.com/in/timcho-giser), two urbanisms specialist of the city of Taipei. 

1 or 2 employees are reponsible for a given area to "unload" or "refill" the stations. But how do they decide if some station should be "refilled" or not? Is a single empty station enough to make the employee move to the station? Not necessarly. To make an employee to go to "refill" a station, an area of few stations being almost empty will trigger that. This is called "[cluster analysis](https://en.wikipedia.org/wiki/Cluster_analysis)". Alex mentioned me they probably have "re-balancing" trucks equiped with an application with a smart algorithm telling them where to unload full station and reload empty ones. 

To make their work easier, historical is  used to predict the flow-in & flow out for each station. They've noticed some patterns on which area will be empty and will need the refill. Those stations often have a "buffer" of bikes nearby locked with together in bulk. When the station is about to get empty (and they've predicted it, the employee responsible for this area will drive their and simply refill the empty station the the buffer of bikes. 

Tim explained to decide where to add new stations, they use [GIS spatial analysis](https://en.wikipedia.org/wiki/Geographic_information_system),  to realize uncovered area (population density, schools, presence of metro station, POIs, etc...) to make the decision to add or not a new YouBike station. 


### Open data
Taipei city (and [Taiwan in general](https://data.gov.tw)) makes an amazing job at [opening data](https://data.taipei/). It provides [real time data](https://tcgbusfs.blob.core.windows.net/blobyoubike/YouBikeTP.json) showing each Youbike station status. Any developer can offer their own application to help users to find bikes avaibility. This is how [I've calculated the number](https://gist.github.com/erickhun/f0d3e8f3c3c4f70dc521c2abb43bb8a0) of YouBikes in Taipei. [Brandon](http://bdon.org/about/) also created this really [interesting visual map](http://bdon.org/youbike-forecast/) showing detailed usage of each station with cool animations: 

![](/img/ubike/youbike-realtime.gif)


Google recently took advantage of it, and made a really nice implemention when users are looking for directions in Google Maps. The app will [show you nearest departure/arrival Youbike station](https://twitter.com/eric_khun/status/1291567323510317057) and its avaibility: 

![](/img/ubike/GoogleMaps-Youbike.jpg)

## An universal and simple payment system

One of my favorite this about Taiwan is probably the EasyCard payment system. With a single card you can use in metro, convenient store, supermarkets and YouBike. Probably the best thing is that you can use that card everywhere in Taiwan.

Banks with their debit/credit cards, and phones (via NFC?) have the Easycard payment system integrated. All those following card/debit card integrate the EasyCard payment chip. 


![Easy Card solution integrated in every card payment](/img/ubike/easy_cards-back-front.jpg)


A single chip to rule them all. 

## The right pricing

The Youbike rental system is a pay as you go model. It [costs](https://taipei.youbike.com.tw/use/rates?5cc2971d083e7b55e32b8172)  **5 NTD (usd0,17) the first 30 minutes**, then 10NTD (usd0.35) per 30 minute. The city also encourage the usage youbike with taking 5NTD on the first 30 minutes on them. To compare the rate with other city in the world: 

- Lyon ([1usd/ 45 minute](https://velov.grandlyon.com/en/offers/groups/list#190) per rental)
- Paris is 1EUR / 30 minute (~ usd1,20)
- Germany has a [3euros per 30 minutes](https://www.callabike.de/en) rate (~ usd3,50)


## Great Bike paths

The inner city has spent lot of effort building large and safe bike path. It is really pleasant to go from A to B. 

![](https://i.imgur.com/5sv48SJ.jpg)


The riverside bike-path is [more than 100 kilometers](https://www.travel.taipei/en/must-visit/riverside-bikeway) long! And they [are planning to extends those biking paths](https://english.gov.taipei/News_Content.aspx?n=A11F01CFC9F58C83&sms=DFFA119D1FD5602C&s=C8487022F5E63064)  to expand bicycle trails in the city in the near future. 




## Bike usage: 

The number of YouBike rides keeps increasing steadily:

- There was 170 millions rides since it was introduced in 2012
- In August 2020, there was ~3 millions rides in Taipei . 
- You can check the number of rides since 2012 in this graph ([source](https://taipei.youbike.com.tw/news/content?5ee1e4b61b994541c0690826)): 

![Youbike usage statistics](/img/ubike/youbike-monthly-rental.jpg)


## Major cities have YouBike
An other great thing is that  all the biggest cities in Taiwan (Taichung, New Tapei City, Kaoshuing) have YouBike. No matter [great or bad](https://www.economicshelp.org/blog/265/economics/are-monopolies-always-bad/), it makes the discovery of a new city frictioneless. You don't have to subscribe for an other services and worrying about 


Taipei has made an amazing job at encouraging. The number or rides talks by itself. They're doign a great by listening citizen and making the . They're now transitionning to the Youbike 2.0


#### Next reads:
🇹🇼 Living in Taiwan? I've recently built [a chat bot](https://www.facebook.com/thetaiwanbot) to help you with all sorts of questions in Taiwan!
📚 [Why you should have a side project](https://erickhun.com/posts/why-you-should-have-a-side-project/)

<!-- ### TODO

- [ ] New youbike 2.0 : https://english.gov.taipei/News_Content.aspx?n=A11F01CFC9F58C83&s=5888478293ADD1A8
Gradually changing from 1.0 to 2.0 bikes : https://www.ettoday.net/news/20200421/1696594.htm
- [ ] Kaoshuing, and other city in Taiwan, has Youbike 2.0 : https://www.twreporter.org/a/opinion-youbike-2-0-plot , can mention a single system https://www.taiwannews.com.tw/en/news/3938326
- [ ] Paris sharing bike [Velib' usage is decreasing](https://www.icmrindia.org/casestudies/catalogue/Operations/V%C3%A9lib_%202.0-Case.htm
) 
- [ ] Cool Timeline of station https://bikesharemap.com/taipei/timeline/#/13/121.5317/25.0358/



Taiwan also recently stopped the ["dockless bikes" company Ofo to operate](https://www.gvm.com.tw/article/66450). What I think is a great thing, when we [hear stories on crazy it can become](https://www.scmp.com/abacus/tech/article/3028722/hundreds-rental-bikes-dumped-dallas-ofo-opts-out), and avoid situations like [this](https://twitter.com/BradfordPearson/status/973630266584510464).  -->