# Swiss Government News portal
The Swiss Federal Chancellery manages the Swiss Government News portal[^1]. This repository contains the XML version of all the ~40'000 press releases available on the news portal since 1997.

## Changes with respect to the original data
Data is provided _as is_, XML are crawled and committed to this repository at least once per day.
- XML objects are prettified in order to take advantage of git in case of changes or revisions.
- An ``/updates.json`` file is generated after each update. 
- In order to keep directories reasonably small, file names use the following notation ``/#{pubdate.year}/#{pubdate.year}-#{pubdate.month}/#{pubdate}.#{msg-id}.xml``

## Feedbacks
Feedbacks are welcome. For suggestions, missing or incorrect data open an issue. 

## Resources
- https://www.news.admin.ch/NSBSubscriber/feeds/rss
- https://www.news.admin.ch/NSBSubscriber/messages

## Licence
Swiss Federal Chancellery generic _Terms and Conditions_ are available [here](https://www.admin.ch/gov/en/start/terms-and-conditions.html). This repository is licensed under the [CC BY-NC-SA 4.0 licence](https://creativecommons.org/licenses/by-nc-sa/4.0/) and cannot be used for commercial purposes. 

Droid Factory.

[^1]: News Service Bund, NSB: www.news.admin.ch
