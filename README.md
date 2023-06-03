# Lynchian wind

## Goal
Explore the nature of wind through David Lynch's [Weather Reports](https://www.youtube.com/playlist?list=PLTPQcjlcvvXExy6Ti4TccyRvwntL00b2w).

From [IMDb](https://www.imdb.com/title/tt12313750/trivia/?ref_=tt_trv_trv):
> David Lynch first started reporting weather on Los Angeles indie radio 103.1, via telephone. He then moved practice as a web-series to his official website in 2006, where it continued until 2010. The series suddenly returned on YouTube in 2020, during the COVID-19 pandemic quarantine.

## Research questions
1. How does Lynch describe the weather?
2. What sort of weather is prominent?
3. Is Lynch describing the weather or climate of Los Angeles?
4. Is the influence of the pandemic and its lockdowns noticeable? 

## Steps
1. Install [videogrep](https://github.com/antiboredom/videogrep).
2. Download all of Lynch's Weather Reports using [yt-dlp](https://github.com/yt-dlp/yt-dlp).
3. Explore the corpus using `videogrep -i *.webm --ngrams 1`
4. Generate a list of synonyms for wind using ChatGPT.
7. Find further wind-related words based on exploring ngrams and manual review of the videos, like `still`/
8. New command including added words: ``videogrep --input *.webm --search 'breeze|gust|draft|zephyr|gale|airflow|current|blast|squall|air|hurricane|tempest|aircurrent|cyclone|whirlwind|puff|waft|sirocco|typhoon|chinook|airstream|flutter|blow|bluster|breath|flurry|airstream|windstorm|draught|puff|crosswind|headwind|tailwind|updraft|downdraft|eddy|tornado|storm|twister|funnel|williwaw|mistral|monsoon|samiel|tradewind|airstream|breeze|southerly|northerly|easterly|westerly|SantaAna|still' --search-type fragment --demo`
10. Use `--search-type fragment --padding 0.75` to capture enough context around each mention.
11. Trial run on a subset of clips from one month.
12. Sort the clips depending on Lynch's location (at the window or in his workshop).

## Variations
### June Gloom
> "June Gloom" is a Southern California term used to describe a weather pattern that results in cloudy, overcast skies with cool temperatures during the late spring and early summer. Despite its name, June Gloom can occur in May or July as well. It is caused by the marine layer effect, a phenomenon where a layer of marine air (which is cooler and more humid than the inland air) is trapped between the ocean surface and a warmer, drier air mass above, leading to the formation of clouds and fog.
> This effect is particularly strong in the mornings and can even result in drizzle. The clouds and fog usually burn off to some extent by the afternoon, revealing clearer skies, but the cloud cover can sometimes persist all day, especially at the coast.
> June Gloom is a prominent aspect of the climate in coastal Southern California, including Los Angeles and San Diego, but it also affects other parts of the California coast and can even be observed along the coasts of other western U.S. states and parts of western Mexico.

`videogrep --input *.webm --search 'gloom'`

### Visualisation of Lynchian wind
1. Get wind descriptions: `videogrep --input *.webm --search 'blowing|wind|breeze|still' --demo > howstrongisthewind.txt`
2. Clean text and create spreadsheet.
3. Create Lynchian wind taxonomy:

| **Types**  | **Strengths**      | **Value** | **Frequency** |
|------------|--------------------|-----------|---------------|
| **Still**  | very still         |         1 | 		   541|
|            | quite still        |         2 |				 1|
|            | still              |         3 |				 1|
| **Breeze** | very slight breeze |         4 |				16|
|            | slight breeze      |         5 |				76|
|            | gentle breeze      |         6 |				22|
|            | breeze             |         7 |				10|
|            | good breeze        |         8 |				37|
|            | strong breeze      |         9 |				47|
| **Wind**   | wind               |        10 |				 2|
|            | strong wind        |        11 |				 3|
|            | high wind          |        12 |				 1|

#### Wind speed frequencies I (11.2020–12.2022)
![](https://github.com/mhep/lynchian-wind/blob/main/img/wind-strength-frequency.png)

#### Wind speed frequencies II (11.2020–12.2022)
![](https://github.com/mhep/lynchian-wind/blob/main/img/wind-over-year.png)

#### [Average Wind Speed in Los Angeles](https://weatherspark.com/y/1705/Average-Weather-in-Los-Angeles-California-United-States-Year-Round#Figures-WindSpeed)
![](https://github.com/mhep/lynchian-wind/blob/main/img/average-la-windspeed.png)


### Lynchian clouds
`videogrep --input *.webm --search 'clouds' -o lynchian-clouds-supercut.mp4`

## Terms of interest
- `smoke`
- `gloom`
- `cloud`
- `blue`

## Notes during research
- You have to get a feel for someone's specific speaking patterns.
- Is it important to disentangle literal and metaphorical uses of wind-words?
- You can see the trees in the background moving with the wind
- Searching only for individual words resulted in too coarse a taxonomy for wind (still and breeze). Expanding the length of each fragment provided access to the adjectives.

## Results
- Learnt about LA's June (and July) gloom
