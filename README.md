# Swiss Federal Chancellery News portal
The Swiss Federal Chancellery (Bern, Switzerland) manages a news portal at the address https://www.news.admin.ch. Here we present and update on a regular schedule all the data available on the news portal.

## Changes with respect to the original data
- XML objects are prettified in order to eventually take advantage of git to track changes.
- A ``/updated_at.json`` file is preriodically generated, this helps to keep the dataset up to date without having to scrape the whole website. 
- In order to keep directories reasonably small, file names use the following notation ``/#{pubdate.year}/#{id}.#{pubdate}.xml``

## Feedbacks
Feedbacks are welcome. For missing or incorrect data open an issue. 

## References
- https://www.news.admin.ch
- https://www.news.admin.ch/NSBSubscriber/feeds/rss (RSS Feed)
