# Who Ranked a Film They Never Watched?

Dataquest guided project, *Star Wars Survey*. Dataset: FiveThirtyEight's Star Wars survey, 1,186 respondents polled via SurveyMonkey Audience in June 2014.

## The thing that changes the answer

The survey asks respondents to rank all six films, and the usual analysis averages those ranks into a definitive ordering. But the survey never checked whether respondents had seen the films before asking them to rank them, and it asks separately which films they have seen, so the two can be compared.

**364 of the 833 people who ranked all six films (43.7%) had not seen all six.** One ranked all six having seen none.

## Findings

### 1. Ranking a film you have not seen is not an opinion about it

| Film | Seen it | Had not | Gap |
|---|---|---|---|
| Ep VI Return of the Jedi | 2.734 | 5.378 | **+2.643** |
| Ep V Empire Strikes Back | 2.296 | 4.590 | **+2.294** |
| Ep IV A New Hope | 2.649 | 4.921 | **+2.273** |
| Ep III Revenge of the Sith | 4.164 | 4.692 | +0.528 |
| Ep II Attack of the Clones | 4.130 | 4.004 | -0.126 |
| Ep I The Phantom Menace | 3.789 | 3.506 | **-0.283** |

Gaps of over two rank positions on a six-point scale. The mechanism is the forced-choice format: with six slots to fill, a respondent who saw only the prequels ranks those 1 to 3 and dumps the unseen originals into 4 to 6.

Non-viewers systematically push the originals down and the prequels up.

### 2. The clean sample reorders the list

| | Full sample | Clean sample (n=469) |
|---|---|---|
| 1st | Ep V (2.510) | Ep V (2.369) |
| 2nd | Ep VI (3.044) | **Ep IV (2.861)** |
| 3rd | Ep IV (3.272) | **Ep VI (2.925)** |
| 4th | Ep I (3.734) | Ep I (4.247) |
| 5th | Ep II (4.090) | **Ep III (4.260)** |
| 6th | Ep III (4.345) | **Ep II (4.337)** |

Two pairs swap. *Empire* holds first either way, the one robust result.

**The Phantom Menace is the casualty.** A comfortable fourth at 3.734 in the full sample, it falls to 4.247 among people who saw everything, landing in a three-way tie at the bottom with all three prequels within a tenth of a rank. Its respectability came from people who never watched it.

### 3. The generational prediction was backwards

| Age in 2014 | Born | Prequels judged worse by |
|---|---|---|
| 18-29 | 1985-96 | +1.46 |
| **30-44** | 1970-84 | **+2.04 (harshest)** |
| 45-60 | 1954-69 | +1.61 |
| **over 60** | before 1954 | **+0.72 (kindest)** |

The obvious hypothesis is that the youngest respondents, who grew up with the prequels, would be kindest, with the gap widening by age. The opposite holds: the kindest group is the over-60s, and the harshest is the 30-44 band, who were children during the original trilogy and adults when the prequels arrived.

**The effect tracks childhood attachment, not recency.** The youngest group sits in the middle; they simply dislike the prequels less than people who were ten years old in 1980.

### 4. Characters

- **Most liked: Han Solo**, 93.5% favourable against 1.1% unfavourable (net +92.4). Luke (+91.5) and Obi-Wan (+91.0) are within two points, so this is a near-tie.
- **Most disliked: Jar Jar Binks**, the only net-negative character (-9.1), at 43.0% unfavourable.
- **Most controversial** depends on how "unfamiliar" responses are handled. Measuring controversy as 2 x min(favourable%, unfavourable%), Jar Jar scores 67.8 and Darth Vader 61.6. But 13.3% had never heard of Jar Jar and 23.1% are neutral, while **Vader is known to 98.8%, leaves only 10.3% neutral, and still divides 59 to 31.** Vader is the character this audience has actually made up its mind about, in two directions.

## What I would not claim

- **A 2014 SurveyMonkey Audience panel is not a probability sample.** FiveThirtyEight published it with that caveat.
- **Ranks are compositional:** the six means must sum to 21, so they cannot move independently.
- **"Had not seen it" is self-reported** in a separate question; some may have seen a film and failed to tick it, which would make the gaps an overestimate, though not enough to explain 2.6 ranks.
- **The cohort story is an interpretation.** The data shows a non-monotonic age pattern; the nostalgia explanation fits but is not tested, and the over-60 cell is the smallest at 72.
- **Character favourability has no error bars.** The top six sit within three points, well inside sampling noise at n around 830.
- **The controversy metric is a choice,** defensible but not unique.

## Files

- `notebook.ipynb`: full analysis, executed, with three charts.

## Stack

pandas, NumPy, Matplotlib (fivethirtyeight style). No seaborn.