# News Service Bund, the Swiss Government News portal
The Swiss Federal Chancellery manages the Swiss Government News portal[^1]. This repository contains the XML version of all the ~50'000 press releases available on the news portal since 1997.

## Changes with respect to the original data
Data is provided _as is_, XML are crawled and committed to this repository at least once per day.

It is important to note that press releases are not always translated into all languages. When not fully translated, editors often copy the text or a portion of the text in one language into the space intended for other languages. In the ``/updates.json`` file, you can find a guess of the languages available in the press release. In case the guess is not good enough, ``languages`` is left empty ``[]``.

Moreover: 
- XML objects are prettified in order to take advantage of git in case of changes or revisions.
- An ``/updates.json`` file is generated after each update and include the last ``xml`` change and the guessed languages present in the press release. 
- In order to keep directories reasonably small, file names use the following notation ``/#{pubdate.year}/#{pubdate.year}-#{pubdate.month}/#{pubdate}.#{msg-id}.xml``

## Message ids
Up to April 2025 message ids are numbers (e.g. ``103839``). Since the Federal Chancellery replaced the News Service Bund on 14 April 2025, ids are opaque strings (e.g. ``sWl2llfFOn3r``). Both appear as they come from the source, in file names (``/2026/2026-10/2026-10-08.sWl2llfFOn3r.xml``) and in ``/updates.json``, where numeric ids come first and string ids follow. The XML format itself did not change.

## Feedbacks
Feedbacks are welcome [@gamba](https://github.com/gamba). For suggestions, missing or incorrect data open an issue. 

## Resources
- https://www.admin.ch/de/newnsb

## Licence
Swiss Federal Chancellery generic _Terms and Conditions_ are available [here](https://www.admin.ch/gov/en/start/terms-and-conditions.html). This repository is licensed under the [CC BY-NC-SA 4.0 licence](https://creativecommons.org/licenses/by-nc-sa/4.0/) and cannot be used for commercial purposes. 

Droid Factory.

[^1]: News Service Bund, NSB: https://www.admin.ch/de/newnsb
