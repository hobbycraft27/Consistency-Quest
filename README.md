# Consistency Quest Nutrition 2.0

GitHub-ready static PWA release, version 0.11.0.

## Nutrition 2.0

- Removes calorie entry and calorie-derived XP from new logs.
- Adds Quick logging with optional Guided protein/plant detail.
- Daily raw Nutrition score: Protein 50, Plants 25, Balanced meals 15, Foundations 10.
- Existing Nutrition XP scaling remains part of the shared five-skill core economy.
- Adds weekly Nutrition Mastery as a separate, uncapped prestige balance.
- Nutrition Mastery does not enter skill XP, Account XP, Health XP or Reward Tokens.
- Adds protein goal bands and Nutrition reviews at each 10 Account Levels.

## Save migration

The save format is upgraded from v3 to v4 on load.

- Existing daily records are retained.
- Existing calorie fields remain only as inert legacy data for backup compatibility.
- Each legacy day receives `legacyNutritionRaw`, calculated from the previous rules before the new rules are applied.
- Legacy daily Nutrition XP is therefore preserved during future recalculation.
- A legacy day changes to Nutrition 2.0 only if the player deliberately opens and saves that date.
- Existing Agility, Endurance and Strength Mastery balances are recalculated as before.
- Nutrition Mastery starts from completed Nutrition 2.0 calendar weeks; legacy calorie history does not create Nutrition Mastery.
- Imports are copied to the existing pre-import safety backup before replacement.

## Weekly Nutrition Mastery

A completed Monday-Sunday week scores Protein, Plants, Balanced Meals and Foundations from 0-5 each.

- Weekly quality 0-13: 0 Mastery
- 14: +1
- 15: +2
- 16: +3
- 17: +4
- 18: +5
- 19: +7
- 20: +10

Protein consistency must score at least 4/5 before any weekly Nutrition Mastery is awarded.

## Deployment

Upload the files in this archive to the root of the GitHub repository used for GitHub Pages. Keep both icon files alongside `index.html`.

### Multiple Endurance sessions
- Multiple Endurance sessions can be added to the same day.
- Existing single `cardio` records migrate into `cardioSessions` without losing history.
- Session raw XP contributions combine, while core Endurance remains capped at 100 raw XP per day.
- Mastery remains session-specific for qualifying 60+ minute sessions.
- Air Bike and Air Bike Intervals earn reduced XP from 5 minutes; other activities retain the 10-minute minimum.
