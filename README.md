# Lynchian wind

## Goal
Explore the nature of wind through David Lynch's [Weather Reports](https://www.youtube.com/playlist?list=PLTPQcjlcvvXExy6Ti4TccyRvwntL00b2w).

From [IMdb](https://www.imdb.com/title/tt12313750/trivia/?ref_=tt_trv_trv):
> David Lynch first started reporting weather on Los Angeles indie radio 103.1, via telephone. He then moved practice as a web-series to his official website in 2006, where it continued until 2010. The series suddenly returned on YouTube in 2020, during the COVID-19 pandemic quarantine.

## Research quesitons
1. How does Lynch describe the weather?
2. What sort of weather is prominent?
3. Is Lynch describing the weather or climate of Los Angeles?
4. Is the influence of the pandemic and its lockdowns noticeable? 

## Steps
1. Install [videogrep](https://github.com/antiboredom/videogrep).
2. Download all of Lynch's Weather Reports using [yt-dlp](https://github.com/yt-dlp/yt-dlp).
3. Exlopre the corpus using
```
videogrep -i *.webm --ngrams 1
```
4. Generate a list of synonyms for wind using ChatGPT:
> Breeze, gust, draft, zephyr, gale, airflow, current, blast, squall, air, hurricane, tempest, air current, cyclone, whirlwind, puff, waft, sirocco, typhoon, chinook, airstream, flutter, blow, bluster, breath, flurry, airstream, windstorm, draught, puff, crosswind, headwind, tailwind, updraft, downdraft, eddy, tornado, storm, twister, funnel, williwaw, mistral, monsoon, nor'easter, samiel, tradewind, airstream, breeze, southerly, northerly, easterly, westerly, Santa Ana.
5. Run search based on this list
```
videogrep --input *.webm --search 'Breeze|gust|draft|zephyr|gale|airflow|current|blast|squall|air|hurricane|tempest|aircurrent|cyclone|whirlwind|puff|waft|sirocco|typhoon|chinook|airstream|flutter|blow|bluster|breath|flurry|airstream|windstorm|draught|puff|crosswind|headwind|tailwind|updraft|downdraft|eddy|tornado|storm|twister|funnel|williwaw|mistral|monsoon|nor'easter|samiel|tradewind|airstream|breeze|southerly|northerly|easterly|westerly|SantaAna' --search-type fragment --demo
```
6. Find further wind-related words based on exploring ngrams and manual review of the videos:
> still
7. New command including added words:
```
videogrep --input *.webm --search 'Breeze|gust|draft|zephyr|gale|airflow|current|blast|squall|air|hurricane|tempest|aircurrent|cyclone|whirlwind|puff|waft|sirocco|typhoon|chinook|airstream|flutter|blow|bluster|breath|flurry|airstream|windstorm|draught|puff|crosswind|headwind|tailwind|updraft|downdraft|eddy|tornado|storm|twister|funnel|williwaw|mistral|monsoon|nor'easter|samiel|tradewind|airstream|breeze|southerly|northerly|easterly|westerly|SantaAna|still' --search-type fragment --demo
```

## Notes during research
- you have to get a feel for someone's specific speaking patterns
