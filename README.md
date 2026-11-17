# Who keeps their nerve? Pressure Reliability Index

An interactive dashboard and methodology for SupeRR Selector Season 2, Round 1
(Rajasthan Royals x Unstop). Built by **Paridhi Jain**.

**Live dashboard:** https://YOURUSERNAME.github.io/superr-dashboard/

## The question
Which batters and bowlers deliver most consistently when the match is on the
line, compared with their own usual level?

## Data
The six CSVs supplied in the data pack: ball-by-ball, matches, competitions,
teams, playing XIs and competition-team-player mapping. IPL and T20I matches
from 2022 to 2026 (818 matches, about 195,000 deliveries after cleaning).

## Method in four steps
1. **Pressure.** A win-probability model gives every ball a leverage score: how
   far the result is expected to swing on that delivery. The top 20% of balls
   within each innings count as high pressure, with a small uplift for
   knockout matches.
2. **Performance.** Each ball is scored against what an average player does in
   the same situation, adjusted for the opponent. Wickets count as runs lost
   or saved.
3. **Rating.** The Pressure Reliability Index combines pressure output (60%),
   improvement on the player's usual level (15%) and consistency across
   pressure innings (25%).
4. **Checks.** Bootstrap resampling, sensitivity tests on 10 model settings,
   and a later-seasons test.

## Honest limits
- Ball-by-ball outcomes are noisy. Bowling ratings predicted later pressure
  performance (correlation 0.28); batting ratings did not.
- Players with fewer than about 60 pressure balls are shrunk toward average
  and flagged as tentative.
- The data pack has no pitch, venue, toss or batting-position detail, and no
  information on contracts or the auction pool.

## What is in this repo
- `index.html`: the dashboard (open it in any browser, no setup needed).

## Submission
The full methodology report is submitted separately as a PDF on Unstop.
