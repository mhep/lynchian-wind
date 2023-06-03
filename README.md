# Lynchian wind

## Goal
Explore the nature of wind through David Lynch's [Weather Reports](https://www.youtube.com/playlist?list=PLTPQcjlcvvXExy6Ti4TccyRvwntL00b2w).

From [IMdb](https://www.imdb.com/title/tt12313750/trivia/?ref_=tt_trv_trv):
> David Lynch first started reporting weather on Los Angeles indie radio 103.1, via telephone. He then moved practice as a web-series to his official website in 2006, where it continued until 2010. The series suddenly returned on YouTube in 2020, during the COVID-19 pandemic quarantine.

## Research questions
1. How does Lynch describe the weather?
2. What sort of weather is prominent?
3. Is Lynch describing the weather or climate of Los Angeles?
4. Is the influence of the pandemic and its lockdowns noticeable? 

## Steps
1. Install [videogrep](https://github.com/antiboredom/videogrep).
2. Download all of Lynch's Weather Reports using [yt-dlp](https://github.com/yt-dlp/yt-dlp).
3. Explore the corpus using
```
videogrep -i *.webm --ngrams 1
```
4. Generate a list of synonyms for wind using ChatGPT:
> Breeze, gust, draft, zephyr, gale, airflow, current, blast, squall, air, hurricane, tempest, air current, cyclone, whirlwind, puff, waft, sirocco, typhoon, chinook, airstream, flutter, blow, bluster, breath, flurry, airstream, windstorm, draught, puff, crosswind, headwind, tailwind, updraft, downdraft, eddy, tornado, storm, twister, funnel, williwaw, mistral, monsoon, samiel, tradewind, airstream, breeze, southerly, northerly, easterly, westerly, Santa Ana.
7. Find further wind-related words based on exploring ngrams and manual review of the videos:
> still
8. New command including added words:
```
videogrep --input *.webm --search 'Breeze|gust|draft|zephyr|gale|airflow|current|blast|squall|air|hurricane|tempest|aircurrent|cyclone|whirlwind|puff|waft|sirocco|typhoon|chinook|airstream|flutter|blow|bluster|breath|flurry|airstream|windstorm|draught|puff|crosswind|headwind|tailwind|updraft|downdraft|eddy|tornado|storm|twister|funnel|williwaw|mistral|monsoon|samiel|tradewind|airstream|breeze|southerly|northerly|easterly|westerly|SantaAna|still' --search-type fragment --demo
```
9. Save list as text file in order to create a visualisation of the wind conditions and show their frequency.
```
videogrep --input *.webm --search 'Breeze|gust|draft|zephyr|gale|airflow|current|blast|squall|air|hurricane|tempest|aircurrent|cyclone|whirlwind|puff|waft|sirocco|typhoon|chinook|airstream|flutter|blow|bluster|breath|flurry|airstream|windstorm|draught|puff|crosswind|headwind|tailwind|updraft|downdraft|eddy|tornado|storm|twister|funnel|williwaw|mistral|monsoon|samiel|tradewind|airstream|breeze|southerly|northerly|easterly|westerly|SantaAna|still' --search-type fragment --demo > lynchianwind.txt
```
10. Use `--search-type fragment --padding 0.22` to capture enough context around each mention.
11. Trial run on a subset of clips from one month.

## Variations
### LA gloom
`videogrep --input *.webm --search 'gloom'`
### Monthly and seasonal reports

## Notes during research
- you have to get a feel for someone's specific speaking patterns
- Is it important to disentangle literal and metaphorical uses of wind-words?
- other search terms of interest: `smoke` `gloom`

## Results
- Learnt about LA's june (and july) gloom
