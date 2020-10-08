+++
categories = ["taiwan", "taipei"]
date = "2020-09-30T22:50:00+08:00"
description = ""
draft = false
image = "/img/about-bg.jpg"
title = "Taiwan's amazing bike-sharing system"
+++

[YouBike](https://taipei.youbike.com.tw/home) (or Ubike) is my first choice of transportation when it comes to moving around the city of Taipei. I largely prefer it over taking the subway, bus, or taxi. It is affordable, well maintained, comfortable, at waking distance reach from anywhere, and the cities have built great biking paths in the major cities. 

The number of YouBike rides keeps increasing steadily since it was launched in 2012. There were 170 million rides since it was introduced in 2012, and [last month it reached  ~3 million rides](https://taipei.youbike.com.tw/news/content?5ee1e4b61b994541c0690826) in Taipei: 

![Youbike usage statistics](/img/ubike/youbike-monthly-rental.jpg)

## A high-quality infrastructure 

YouBikes are [everywhere](https://taipei.youbike.com.tw/station/map) in Taipei and New Taipei City. As for October 2020, over [42000 YouBikes are deployed](https://gist.github.com/erickhun/f0d3e8f3c3c4f70dc521c2abb43bb8a0), with over 1000 stations. Stations [get added every few weeks](https://taipei.youbike.com.tw/news/list?5cb582c1060db454916c643c).

Since the first time I arrive in Taipei (2016), I am pleasantly surprised that I rarely got a broken bike. [Giant](https://en.wikipedia.org/wiki/Giant_Bicycles) is actually the (local) company that provides them. The bikes feel durable, lightweight, and really well maintained. Each bike is bought by the city for around [9200 TWD (~USD 300)](https://disp.cc/b/163-6PkZ), and comes with a 7 years maintenance. 

To make it really convenient, the city has organized each station  [from 200 to 600 meters](https://english.gov.taipei/News_Content.aspx?n=A11F01CFC9F58C83&s=5888478293ADD1A8) from each other. What makes you within 5 to 10 minutes walk from wherever you are in the city.


![](https://i.imgur.com/F5HWa3v.jpg)


## Data-driven decisions

I've noticed that the stations are also rarely empty. From time to time, I've spotted some employees "reloading" or "deloading" stations that are full or empty. Who are they? Where do they take those bikes? I've discussed with [Alex Garcia](https://twitter.com/TaipeiUrbanism) and [Tim Cho](https://www.linkedin.com/in/timcho-giser), two urbanism specialists of the city of Taipei. 

1 or 2 employees are responsible for a given area to "unload" or "refill" the stations. But how do they decide if some station should be "refilled" or not? Is a single empty station enough to make an employee move to the station? Not necessarily. Most of the time, an area of few stations being almost empty will make it worthwhile to move. This is a "[cluster analysis](https://en.wikipedia.org/wiki/Cluster_analysis)". Alex mentioned me they also have "re-balancing" trucks equipped with an application with a smart algorithm telling them where which full stations to unload, and which empty ones need a refill. 

To make their work easier, historical data are used to predict the flow-in & flow out for each station. They know the patterns on which stations will be empty and which one will need a refill. Those stations often have a "buffer" of bikes nearby locked together in bulk. When the station is about to get empty, the employee responsible for this area will drive there and refill the empty station with the buffer of bikes already present. 

To make the decisions to add new stations, [Tim](https://www.linkedin.com/in/timcho-giser) explained they use [GIS spatial analysis](https://en.wikipedia.org/wiki/Geographic_information_system),  to realize uncovered area (population density, schools, presence of metro station, POIs, etc...) to make the decision to add or not a new YouBike station. 


### Open data
Taipei City (and [Taiwan in general](https://data.gov.tw)) makes an amazing job at [opening their data](https://data.taipei/). It provides [real time data](https://tcgbusfs.blob.core.windows.net/blobyoubike/YouBikeTP.json) showing each Youbike station status. Any developer can offer their own application to help users to find bikes availability or making the service more useful. This open data is how [I've calculated the number](https://gist.github.com/erickhun/f0d3e8f3c3c4f70dc521c2abb43bb8a0) of YouBikes in Taipei.

[Jakub told me](https://twitter.com/jakubsvehla/status/1311345837952434176) he used this open data to help him stop being late at class. He depended on the YouBike to go to NTUST but ended up always late because his nearest station was empty. He started recording the patterns/waves of bikes coming and leaving the stations to know the time to go to the station. 

[Brandon](http://bdon.org/about/) created this really [interesting visual map](http://bdon.org/youbike-forecast/) showing detailed usage of each station with cool animations. If you live in Taiwan, click on your station, and you'll see when bikes are more likely to be available! 

![](/img/ubike/youbike-realtime.gif)


Google recently took advantage of it and made a really nice implementation when users are looking for directions in Google Maps. The app will [show you nearest departure/arrival Youbike station](https://twitter.com/eric_khun/status/1291567323510317057) and its availability: 

![](/img/ubike/GoogleMaps-Youbike.jpg)

## An universal and simple payment system

One of my favorite this about Taiwan is probably the EasyCard payment system. With a single card, you can use it in the metro, convenient store, supermarkets, and YouBike. Probably the best thing is that you can use that card everywhere in Taiwan.

Banks with their debit/credit cards and phones (via NFC?) have the Easycard payment system integrated. All those following card/debit cards integrate the EasyCard payment chip. Any convenient store will sell you one of those cards, without any requirements.


![Easy Card solution integrated into every card payment](/img/ubike/easy_cards-back-front.jpg)


A single chip to rule them all. 

## The right pricing

The Youbike rental system is a pay as you go model. It [costs](https://taipei.youbike.com.tw/use/rates?5cc2971d083e7b55e32b8172)  **5 NTD (usd0,17) the first 30 minutes**, then 10NTD (usd0.35) per 30 minute. The city also encourages the usage of YoubBke by taking 5NTD on the first 30 minutes on them. To compare the rate with other cities in the world: 

- Lyon (France) ([1usd/ 45 minute](https://velov.grandlyon.com/en/offers/groups/list#190) per rental)
- Paris is 1EUR / 30 minute (~ usd1,20)
- Germany has a [3euros per 30 minutes](https://www.callabike.de/en) rate (~ usd3,50)



## Impressive dedicated bike paths infrastructure

Taiwan is famously known for being a paradise for Bike lovers, from the urban city bikers the [most courageous professional bikers](https://youtu.be/Sxfd2xzlM6k). Did you know that Taiwan had more than 4500km of dedicated bike path? The longest one measuring [968km long](http://edition.cnn.com/travel/article/taiwan-cycle-tour/index.html). Taipei alone has 500+ km of dedicated biking path. The city has spent a lot of effort into building a large and safe bike path. It is really pleasant to move around the city: 

![](https://i.imgur.com/5sv48SJ.jpg)

The riverside bike-path is [more than 100 kilometers](https://www.travel.taipei/en/must-visit/riverside-bikeway) long! And they [are planning to extends those biking paths](https://english.gov.taipei/News_Content.aspx?n=A11F01CFC9F58C83&sms=DFFA119D1FD5602C&s=C8487022F5E63064) to expand bicycle trails in the city soon. 


## An unified bike-sharing system in all cities

Another great thing is that all the biggest cities in Taiwan (Taichung, New Tapei City, Kaoshuing) have YouBike. No matter [great or bad](https://www.economicshelp.org/blog/265/economics/are-monopolies-always-bad/), it makes the discovery of a new city frictionless. You don't have to subscribe to other services and worry about getting back a deposit.


## Conclusion

Taipei has made a great job of implementing an amazing infrastructure bike-sharing infrastructure. With open data, the incentive to use bikes, maintaining a low price, and keeping bikes in great shape. The steady increases in the number of rides in Taipei talks by itself, while [other countries see their usage decreasing](https://www.icmrindia.org/casestudies/catalogue/Operations/V%C3%A9lib_%202.0-Case.htm) over years. They're today transitioning to a second generation of [Youbike 2.0](https://english.gov.taipei/News_Content.aspx?n=A11F01CFC9F58C83&s=5888478293ADD1A8), better, lighter, and with docks taking less space.


<!-- Taiwan also recently stopped the ["dockless bikes" company Ofo to operate](https://www.gvm.com.tw/article/66450) -->


#### Next reads:

🤖 [How to build a chat bot with Google's Sentence Encoder Model and Google Spreadsheet as a database](https://jonathanbgn.com/nlp/2020/09/29/chatbot-universal-sentence-encoder.html)

<!-- 🇹🇼 Living in Taiwan? I've recently built [a chat bot](https://m.me/thetaiwanbot) giving you currated recommendations in Taiwan! Where to find the best value cheese? Where is the best pizza? etc...  [Here the details on how it works](https://jonathanbgn.com/nlp/2020/09/29/chatbot-universal-sentence-encoder.html) -->

<!-- 🌏 Interested in living and working in Taiwan? Have you checked the [Gold Card program](https://taiwangoldcard.com/application-faq/)?  -->

📚 [Why you should have a side project](https://erickhun.com/posts/why-you-should-have-a-side-project/)

🤸🏻‍♂️ [How to keep working out while travelling](https://erickhun.com/posts/traveling-and-working-out/)

