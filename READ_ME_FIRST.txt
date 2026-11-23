POCKET GM BASEBALL 2026 - CALIBRATED V2 TEST
Built November 23, 2026. Use PGM_MLB26_roster_calibrated_v2.json.
Phone import URL:
https://raw.githubusercontent.com/cjhawkins4295/pgm-mlb-2026/refs/heads/main/PGM_MLB26_roster_calibrated_v2.json

WHAT CHANGED
The user's actual game re-export matched all 2,084 imported players by name,
position and unchanged skills. PGM kept those skills but recalculated overalls.
Examples: Vinnie Pasquantino 73 -> 47, Bobby Witt Jr. 87 -> 79,
Aaron Judge 93 -> 89, Paul Skenes 85 -> 97.
The old adapted file is superseded and should not be used for a new test.

V2 translates source attributes into PGM's native skill band and calibrates
each player's attributes toward the exact source overall. This is a fitted
approximation, not a recovered or officially published game formula.
Held-out prediction errors average 1.2-2.0 points by position, with individual
errors as large as 8.2 points. Those checks predict existing exports; they do
NOT establish the overalls that PGM will produce after importing V2.
The model rounds to every target overall for the revised file, but only an
actual game import/export can verify the result. Do not mistake the written
rating field or the model estimate for a confirmed in-game rating.

NEXT TEST ON YOUR PHONE
Scan phone-roster-v2-qr.png, copy the full web address, and use it as the
roster URL when setting up a separate new game. Leave the staff URL blank.
Check Witt (target 87), Pasquantino (target 73), Judge (target 93) and Skenes
(target 85). Export that roster again before advancing the season and transfer
it to this PC the same way as the previous export. This file does not patch
an existing save.

EXACT SOURCE VS CONVERTED ATTRIBUTES
The overall targets remain the exact values in the previously verified official
MLB The Show 26 Diamond Dynasty Live Series snapshot, retrieved Nov 23, 2026.
The latest listed official update was #27, dated Nov 6, 2026.
https://mlb26.theshow.com/apis/roster_updates.json
https://mlb26.theshow.com/apis/items.json?type=mlb_card&page=1
This is not the offline Franchise roster. The unmodified complete source is
MLBTheShow26_Live_EXACT_source.json. Individual V2 attributes are translated
estimates, NOT exact Show numbers. They cannot both stay numerically identical
and be relied upon to produce identical overalls under a different formula.
Contact, vision, discipline, clutch and power use the source's 125-point scale;
other mapped skills use 99 as the conversion scale. All translated skills stay
in the 50-99 band observed in native PGM records. Position-specific overall
calibration shifts those skills and makes small integer refinements.
PGM-only skills remain modeled placeholders. Potential is set to the target
overall as a placeholder; the game was observed to recalculate potential.

CONTENTS / LIMITATIONS
2,084 players: 40 per team plus 884 source Free Agents. Exact 53-key template.
Identity, team assignments and appearance policy remain as in the first file.
No fictional prospects have been added; PGM may generate its own at startup.
Contracts, service time, development curves, personalities and some other
game-only fields still use fictional template values. They are not real MLB
contracts or verified forecasts. Country codes remain template placeholders.
PGM was observed to regenerate IDs, potential, second positions, measurements,
draft years and some contract/team fields. Two-way behavior remains unverified.
MLB30_staff_METADATA_NOT_IMPORT.json and MLB30_team_names_METADATA.json are
reference metadata ONLY. This player-export schema cannot import staff or
change the displayed team names; do not paste those files into the staff box.
The original request for a complete exact-rating roster/staff import therefore
is not fully satisfied. This revision addresses the demonstrated overall issue.

V2_PLAYER_RATING_AUDIT.json lists every changed value and model estimate.
V2_VALIDATION_REPORT.json contains structural checks and holdout errors.
