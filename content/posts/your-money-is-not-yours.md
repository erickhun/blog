+++ 
draft = false
date = 2023-04-28T15:32:58+08:00
title = "Money in your Bank Account is not yours"
description = ""
slug = "" 
tags = []
categories = []
externalLink = ""
series = []
+++

When depositing money in a bank, we usually forget that money you deposit in the bank isn't ours anymore. We are essentially _giving the bank temporary custody of our money in exchange for **a promise** that they will give us back the same amount (and sometimes more)_.

Over the past decade, I have encountered numerous challenges dealing with banks across various countries, which made me realize that **the promise to return your money isn't always as straightforward as it seems**. There are often fine prints subtilities that you may only discover the hard way 🥲. This made me felt like the **cash I deposit in the bank didn't really felt like mine**.

So what are the situations when banks could potentially make you hard time to get back that money, or worst, don't give it back? 

### Banks can fail, and your money could evaporate

A "run on the bank" is a situation where a large number of depositors try to withdraw their money from a bank all at once and the bank don't have enough cash in hands. This is not a hypothetical scenario and it has happened many times in history.  Historically, there were many bank runs:

- [In 2020, the banking system in Cyprus faced a bank run](https://en.wikipedia.org/wiki/2012%E2%80%932013_Cypriot_financial_crisis). All depositors feared for their cash, and tried to withdraw their money. The European Union bailed them out, but only for account with cash under €100,000 per depositor.  **If you had more than over €100,000, you'd have lost anything over 100k**, and it represented  [€38 billion](https://www.reuters.com/article/us-cyprus-parliament/cyprus-closes-in-on-eu-bailout-u-turn-on-levy-idUSBRE92G03I20130322) overall 😳.
- In 2017 in Spain, customers with deposits over 100,000 euros in Banco Popular, were wiped out as part of the resolution process, and they received shares in the new entity as compensation. 
- More recently [Silicon Valley Bank (SVB)](https://en.wikipedia.org/wiki/Silicon_Valley_Bank#Collapse) faced a bank run. But this time, depositor were made whole .

Why would banks not having enough money you'd ask? An interesting finding I came accros is that banks aren't required to the full amount of cash you've deposit. 

However, since 2008, banks have to [follow stricter regulations](https://en.wikipedia.org/wiki/Basel_Accords#Basel_III:_responding_to_the_financial_crisis) to make sure to endure bank runs:

- In the US, before 2020, the Federal Reserve asked banks to keep 10% of customers' deposits at all times. However, [since 2020](https://www.federalreserve.gov/monetarypolicy/reservereq.htm), due to the economic impact of the COVID-19 pandemic, the Fed eliminated all reserve requirements for depository institutions. They, however, have to follow the LCR rules, like the US and Asia (cf next paragraph).
- In Europe and Asia, banks need to follow the LCR (Liquidity Coverage Ratio) rules. It is a regulatory standard asking banks to hold sufficient HQLAs (cash or any assets that can be quickly converted to cash) to cover net cash outflows over a 30-day stress period. The value they have to keep against the deposited money is [clearly defined](https://www.eba.europa.eu/sites/default/documents/files/documents/10180/2751085/c465a8e4-a8a6-407b-9ca7-d9e1572c922e/Annex%20VI%20%28Annex%2025%20%28LCR%29%29.pdf).

The LCR is defined with a score in %, 100% meaning they could endure an "outflow of cash" of 30 days. The more, the better. [The world average score](https://www.bis.org/bcbs/dashboards.htm) is 138%. Europe being first with 150%, the rest of the world (144%), and the US 120%:

![LCR world average, US, Europe graph](/img/bank-money-is-not-your-money/LCR-average-europe-us.png)

What is interesting to note is that [Silicon Valley Bank had an LCR score of 70%](https://som.yale.edu/story/2023/lessons-applying-liquidity-coverage-ratio-silicon-valley-bank), which is far from the recommended 100%.

This is when you should probably check the current (and historical) level of LCR of the bank where you hold your money 😜. The LCR  should be publicaly available in their financial statements.


### Banks can freeze or seize your cash, for any reason

There can also be several other reasons that a bank can freeze or, worse, seize your cash. Depending on local laws, your bank account can be frozen for any kind of reasons. These are mainly due to some anti-money laundering processes that were set up by the bank, but they can also be triggered by "external" factors.

- **International Wires**: When sending money from one country to another. This can easily trigger alerts within banks, and that money is frozen until you prove the source of it.
- **Deposit cash money in the ATM**: This can freeze the money in the account. I've experienced this several times in France. The resolution was showing my work contract and a translated document of the withdrawal.
- **In Taiwan, when your ARC permit (resident card) expires**: Your bank account [can be restricted](https://tw.forumosa.com/t/cannot-get-an-online-banking-account-if-arc-expires-in-less-than-a-year/216192).
- **Tax authorities** can take money from your bank account:
    - In the US, the IRS can seize the money in your account after a [levy](https://www.irs.gov/businesses/small-businesses-self-employed/what-is-a-levy) has been issued.
    - In Europe, tax authorities [can seize unsettled tax debts](https://www.impots.gouv.fr/particulier/questions/mon-compte-bancaire-fait-lobjet-dun-avis-tiers-detenteur-la-banque-peut-elle).
- **Department of Justice** can seize or freeze your bank account:
    - Assets that have been seized by law enforcement as part of a criminal investigation or forfeiture proceeding, even before a final judgment has been made.
    - Divorce: Half of your money is given away.


## Then... what should I do?

- Don't put all your eggs in the same basket:
    - Usually banks have insurances that can protect you up to €100,000. In the US, it's up to $250,000. Make sure not to have more than that. Even though you are under this threshold, banks can "freeze" your cash if they're facing a difficult time or any other reasons. It's why it's always a good practices to split your cash accross various banks.
    - Some friends I know keep several bank accounts across several countries to mitigate those risks.
- Have you heard of [Bitcoin](/posts/explaining-blockchains-to-developers/)? It allows you to transfer value and is a permisionless, meaning it allows anyone to participate without needing approval or permission from a central authority - such as a bank or governement . Just don't keep [them on exchanges](https://en.wikipedia.org/wiki/FTX), and use a cold wallet).