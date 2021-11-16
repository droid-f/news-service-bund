# Swiss Federal Chancellery News portal
The Swiss Federal Chancellery manages the Swiss Government news portal[^1] at the address https://www.news.admin.ch (now integrated in www.admin.ch CMS). This repository contains the XML version of all the ~40'000 press releases available on the news portal since 1997.

## Changes with respect to the original data
Data is provided _as is_, XML are crawled and committed to this repository at least once per day.
- XML objects are prettified in order to take advantage of git in case of changes or revisions.
- A ``/updated_at.json`` file is preriodically generated, this helps to keep the dataset up to date without having to scrape the whole website. 
- In order to keep directories reasonably small, file names use the following notation ``/#{pubdate.year}/#{msg-id}.#{pubdate}.xml``

## Feedbacks
Feedbacks are welcome. For missing or incorrect data open an issue. 

## Resources
- https://www.news.admin.ch
- https://www.news.admin.ch/NSBSubscriber/feeds/rss (RSS Feed)

## Licence
Swiss Federal Chancellery generic _terms and conditions_ are available (here)[https://www.admin.ch/gov/en/start/terms-and-conditions.html]. This repository is licensed under the CC BY-NC-SA 4.0 licence and cannot be used for commercial purposes.

[^1]: News Service Bund, NSB
