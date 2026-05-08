# FIFA World Cup 2026 Matchup Checker

A lightweight, mobile-friendly, single-page matchup checker for the FIFA World Cup 2026.

The app lets users select any two teams and see whether they can meet, the earliest possible stage, and the bracket logic behind the result. It also includes a full fixture view covering generated group-stage pairings and the published knockout-stage bracket skeleton.

## Features

- Light, clean, mobile-friendly layout
- Team-vs-team matchup checker
- Stage-by-stage possibility result
- Group-stage guaranteed matchup detection
- Knockout-stage logic based on published Round of 32 slots and bracket progression
- Conditional third-place pathway handling
- Full fixture view with search and Group/Knockout filters
- No build tools required
- Pure HTML, CSS, and JavaScript

## How to Use

1. Select Team A and Team B.
2. Click **Analyse matchup**.
3. Use **See whole fixture** to browse the tournament fixture list.

## Data Notes

The app uses the 2026 tournament format:

- 48 teams
- 12 groups of 4
- Top 2 from each group qualify
- 8 best third-place teams qualify
- Round of 32 onward is single elimination

The checker treats third-place entries as conditional because only eight of twelve third-place teams advance and their exact Round of 32 placement depends on the final set of qualifying third-place groups.

## Logic Summary

The app checks matchup possibility in this order:

1. **Same group**
   - The teams are guaranteed to meet in the group stage.

2. **Round of 32**
   - The app checks whether the teams' groups can appear on opposite sides of a published Round of 32 fixture.

3. **Later knockout rounds**
   - The app follows the bracket tree to see when both teams' possible paths can merge.

4. **Earliest stage**
   - The earliest valid stage is shown as the main result.

## Important Limitation

This is a possibility checker, not a prediction model. “Possible” means the bracket allows the matchup if teams finish in compatible positions and keep advancing. It does not estimate probability.

## Customization

You can edit:

- `GROUPS` for updated teams or positions
- `R32` for Round of 32 slot changes
- `TREE` for knockout bracket changes
- CSS variables under `:root` for colors and theme
