# FIFA World Cup 2026 Matchup Checker

A lightweight, mobile-friendly, single-page matchup checker for the FIFA World Cup 2026.

The app lets users select any two teams and see whether they can meet, the earliest possible stage, and the bracket logic behind the result. It also includes a full fixture view covering generated group-stage pairings and the published knockout-stage bracket skeleton.

## Live Demo

If you upload this project to GitHub Pages, the app can run as a static site with no backend.

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

## Files

```text
wc2026-matchup-checker-light.html
README.md
```

## How to Use

1. Open `wc2026-matchup-checker-light.html` in a browser.
2. Select Team A and Team B.
3. Click **Analyse matchup**.
4. Use **See whole fixture** to browse the tournament fixture list.

## GitHub Pages Setup

1. Create a new GitHub repository.
2. Upload the HTML file and this README.
3. Rename the HTML file to `index.html` if you want it to open automatically as the homepage.
4. Go to **Settings > Pages**.
5. Under **Build and deployment**, choose:
   - Source: `Deploy from a branch`
   - Branch: `main`
   - Folder: `/root`
6. Save.
7. GitHub will provide a public Pages URL.

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

## Recommended Repository Name

```text
wc2026-matchup-checker
```

## License

MIT License. Free to use, modify, and share.
