+++
categories = ["dev", "snipset"]
date = "2025-02-04T12:50:00+08:00"
modified_date = "2024-05-05T11:15:30+08:00"
description = ""
draft = false
images = ["/img/ubike/youbike-yearly-rental.png"]
title = "Previous version of hugo on Mac"
+++

Unfortunately, there is no way to set up versions older than 5 previous versions with brew. Here's a quick workaround:

0. `brew uninstall hugo`
1. Head to [github.com/gohugoio/hugo/tags](https://github.com/gohugoio/hugo/tags) and navigate the version you need
    - The Mac versions are the `hugo_*_darwin-*.tar.gz` ones
      - darwin = macOS
      - universal = works on both Intel and Apple Silicon Macs
      - extended version includes additional features like SASS/SCSS support
2. Download and extract the tar file
3. Move the binary to `/usr/local/bin`
4. When starting the Hugo binary for the first time, your Mac will show a security warning
  - Don't delete the binary
  - Go to System Settings (or System Preferences)
  - Privacy & Security
  - Click "Install app anyway"

Voila!

purists will yell at you to make it work with the latest version for whatever reasons, but who cares for a static website 

<!--

#### Next reads:


🇹🇼 [The world next innovations depend on a single country, Taiwan](/posts/world-innovation-taiwan-semiconductors/) 

🇹🇼 [Why Taiwan?](/posts/why-taiwan/) 

🌱 [How to Invest in Stocks and ETFs from Taiwan](/posts/investing-from-taiwan/) 


 🤖 [How to build a chat bot with Google's Sentence Encoder Model and Google Spreadsheet as a database](https://jonathanbgn.com/nlp/2020/09/29/chatbot-universal-sentence-encoder.html) -->

<!-- 🇹🇼 Living in Taiwan? I've recently built [a chat bot](https://m.me/thetaiwanbot) giving you currated recommendations in Taiwan! Where to find the best value cheese? Where is the best pizza? etc...  [Here the details on how it works](https://jonathanbgn.com/nlp/2020/09/29/chatbot-universal-sentence-encoder.html) -->

<!-- 🌏 Interested in living and working in Taiwan? Have you checked the [Gold Card program](https://taiwangoldcard.com/application-faq/)?  -->

<!-- 📚 [Why you should have a side project](/posts/why-you-should-have-a-side-project/) -->


