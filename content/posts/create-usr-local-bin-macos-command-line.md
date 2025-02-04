+++
categories = ["dev", "snipset"]
date = "2025-02-04T12:50:00+08:00"
modified_date = "2024-05-05T11:15:30+08:00"
description = ""
draft = false
images = ["/img/ubike/youbike-yearly-rental.png"]
title = "Create /usr/local/bin in macOS"
+++


It's 2025, and `/usr/local/bin` still not a directory in MacOS (15.1) 🤦‍♂️ . Programs you download (via Homebrew or online) are usually set inside this folder. 

Here the correct way to create it: 

```bash
sudo mkdir -p /usr/local/bin
sudo chmod 755 /usr/local/bin
```

Why `755`?. It follows the principle of least privilege while still allowing the necessary functionality - anyone can use the programs, but only root can modify them:

- Owner as `root` with `rwx` permissions is standard because the system (root) needs full control to manage executables
- Group as `wheel` with `r-x`, `wheel` is traditionally the admin group on Unix systems
- Others with `r-x` because:
  - Everyone needs to be able to read (`r`) and execute (`x`) programs in this directory
  - They shouldn't be able to write (`w`) to it, which prevents regular users from modifying system binaries

Hope this helps.


#### Next reads:

🇹🇼 [The world next innovations depend on a single country, Taiwan](/posts/world-innovation-taiwan-semiconductors/) 

<!--
🇹🇼 [Why Taiwan?](/posts/why-taiwan/) 

🌱 [How to Invest in Stocks and ETFs from Taiwan](/posts/investing-from-taiwan/) 


 🤖 [How to build a chat bot with Google's Sentence Encoder Model and Google Spreadsheet as a database](https://jonathanbgn.com/nlp/2020/09/29/chatbot-universal-sentence-encoder.html) -->

<!-- 🇹🇼 Living in Taiwan? I've recently built [a chat bot](https://m.me/thetaiwanbot) giving you currated recommendations in Taiwan! Where to find the best value cheese? Where is the best pizza? etc...  [Here the details on how it works](https://jonathanbgn.com/nlp/2020/09/29/chatbot-universal-sentence-encoder.html) -->

<!-- 🌏 Interested in living and working in Taiwan? Have you checked the [Gold Card program](https://taiwangoldcard.com/application-faq/)?  -->

<!-- 📚 [Why you should have a side project](/posts/why-you-should-have-a-side-project/) -->


