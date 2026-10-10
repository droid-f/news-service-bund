# News Service Bund, the Swiss Government News portal
The Swiss Federal Chancellery manages the Swiss Government News portal[^1]. This repository contains the XML version of all the ~50'000 press releases available on the news portal since 1997 and, since 14 April 2025, also their JSON version.

## Changes with respect to the original data
Data is provided _as is_, XML are crawled and committed to this repository at least once per day.

It is important to note that press releases are not always translated into all languages. When not fully translated, editors often copy the text or a portion of the text in one language into the space intended for other languages. In the ``/updates.json`` file, you can find a guess of the languages available in the press release. In case the guess is not good enough, ``languages`` is left empty ``[]``.

Moreover: 
- XML objects are prettified in order to take advantage of git in case of changes or revisions.
- An ``/updates.json`` file is generated after each update and include the last ``xml`` change and the guessed languages present in the press release. 
- In order to keep directories reasonably small, file names use the following notation ``/xml/#{pubdate.year}/#{pubdate.year}-#{pubdate.month}/#{pubdate}.#{msg-id}.xml`` (and the same under ``/json/`` with ``.json``)

## Two formats

Since 2026-10-10 this repository holds the press releases in two formats, side by side:

- ``xml/YYYY/YYYY-MM/<date>.<id>.xml``: the XML of the legacy News Service Bund interface, as published here since 2021. Until 2026-10-10 these files were at the root of the repository (``YYYY/YYYY-MM/...``). They were moved unchanged: ``git log --follow`` shows their history, and the tag ``layout-v1`` marks the last commit of the old layout.
- ``json/YYYY/YYYY-MM/<date>.<id>.json``: the newsd REST API (https://www.newsd.admin.ch), which replaced the News Service Bund on 2025-04-14. ``json/`` starts with that day. One file per press release; each language version is the API's item, unchanged, under ``languages.<locale>``, in the envelope ``{id, date, publishers, topics, tags, languages}`` (publishers, topics and tags are the union over the language versions). Keys are sorted at every level and indented by two spaces, so a file changes only when its content does.

<!-- XML available up to <date>. -->

A press release has the same ``<date>.<id>`` in both trees. ``<date>`` is the XML's ``pubdate`` when the XML has the message, else the Swiss calendar date of the German version's ``publishDate``, else of the earliest version's; this matches the XML's date for every press release checked. Example: ``xml/2026/2026-09/2026-09-09.ViFgmTTmBF9M.xml`` and ``json/2026/2026-09/2026-09-09.ViFgmTTmBF9M.json``.

Press releases get corrected after publication. Both sources are fetched again for the last month every night and for the last twelve months every Sunday, so a correction appears as a change of the file in a daily commit ("Update <date>").

``/updates.json`` has one entry per press release in either format (numeric ids first, in numeric order, then the string ids). Besides ``id``, ``languages`` and ``updated_at`` it carries ``formats`` (``["xml"]``, ``["json"]`` or ``["xml", "json"]``), ``languages_source`` (``"api"`` when ``languages`` comes from the API, ``"guess"`` when it was detected in the XML text), and, where the JSON exists, ``json_updated_at`` and the API's ``publishers`` and ``topics`` codes. Publisher names are available from https://www.newsd.admin.ch/v1/organisations; the API does not publish topic names.

## Message ids
Up to April 2025 message ids are numbers (e.g. ``103839``). Since the Federal Chancellery replaced the News Service Bund on 14 April 2025, ids are opaque strings (e.g. ``sWl2llfFOn3r``). The XML format itself did not change (for the moment).

## Feedbacks
Feedbacks are welcome [@gamba](https://github.com/gamba). For suggestions, missing or incorrect data open an issue. 

## Resources
- https://www.admin.ch/de/newnsb

## Licence
Swiss Federal Chancellery generic _Terms and Conditions_ are available [here](https://www.admin.ch/gov/en/start/terms-and-conditions.html). This repository is licensed under the [CC BY-NC-SA 4.0 licence](https://creativecommons.org/licenses/by-nc-sa/4.0/) and cannot be used for commercial purposes. 

Droid Factory.

[^1]: News Service Bund, NSB: https://www.admin.ch/de/newnsb
