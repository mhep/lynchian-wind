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
4. Generate a list of synonyms for wind using ChatGPT.
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
10. Remove words which are included in other words (like air in airplane).
```
videogrep --input *.webm --search 'Breeze|draft|zephyr|gale|airflow|current|blast|squall|hurricane|tempest|aircurrent|cyclone|whirlwind|puff|waft|sirocco|typhoon|chinook|airstream|flutter|blow|bluster|breath|flurry|airstream|windstorm|draught|puff|crosswind|headwind|tailwind|updraft|downdraft|eddy|tornado|storm|twister|funnel|williwaw|mistral|monsoon|samiel|tradewind|airstream|breeze|southerly|northerly|easterly|westerly|SantaAna|still' --search-type fragment --demo
```
11. Fragment search not sufficient to understand how strong the wind is.
10. Use `--search-type fragment --padding 0.22` to capture enough context around each mention.
11. Trial run on a subset of clips from one month.
12. Sort the clips depending on Lynch's location (at the window or in his workshop).

## Variations
### LA gloom
`videogrep --input *.webm --search 'gloom'`
- learnt the term "june gloom"

### Visualisation of Lynchian wind
1. Get wind descriptions: `videogrep --input *.webm --search 'blowing|wind|breeze|still' --demo > howstrongisthewind.txt`
2. Clean text and create spreadsheet.
3. Create Lynchian wind taxonomy:

| **Types**  | **Strengths**      | **Value** |
|------------|--------------------|-----------|
| **Still**  | very still         |         1 |
|            | quite still        |         2 |
|            | still              |         3 |
| **Breeze** | very slight breeze |         4 |
|            | slight breeze      |         5 |
|            | gentle breeze      |         6 |
|            | breeze             |         7 |
|            | good breeze        |         8 |
|            | strong breeze      |         9 |
| **Wind**   | wind               |        10 |
|            | strong wind        |        11 |
|            | high wind          |        12 |
|------------|--------------------|-----------|

![](https://media.githubusercontent.com/media/mhep/lynchian-wind/main/wind-over-year.png?token=AAHKBD4VEZYRAI7JYFLQSZLEPN2QG)

### Monthly and seasonal reports

## Notes during research
- you have to get a feel for someone's specific speaking patterns
- Is it important to disentangle literal and metaphorical uses of wind-words?
- other search terms of interest: `smoke` `gloom` `blue`
- you can see the trees in the background moving with the wind
- searching only for individual words resulted in to coarse a taxonomy for wind (still and breeze). Expanding the length of each fragment provided access to the adjectives.

## Results
- Learnt about LA's june (and july) gloom
