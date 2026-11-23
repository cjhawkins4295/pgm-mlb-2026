POCKET GM BASEBALL / MLB THE SHOW 26 ROSTER PACKAGE
Built for the request dated November 23, 2026.

STATUS: PLAYER IMPORT CANDIDATES, NOT AN IN-GAME-TESTED COMPLETE CONVERSION
The two PGM roster files use exactly the 53 keys and value types from your
uploaded fictional-player JSON. Both contain 2,084 real Live Series records:
40 players for each of the 30 teams, plus 884 in The Show's Free Agents bucket.
The 538 fictional future rookies from your template are not carried over.
No unrated prospects or invented Show ratings have been added.

The files have passed structural and source-comparison validation. I cannot
claim they import successfully or play correctly without running them in the
iPhone game. The game's numeric limits, roster-size handling, startup draft
population, and recalculation of overall ratings remain untested.

WHICH FILE TO USE
1. PGM_MLB26_roster_adapted.json
   Conservative player import candidate. All 2,084 source overall ratings are
   copied unchanged into PGM's rating field. Direct attributes are copied;
   values above 99 are capped to the range observed in your export. There are
   58 capped fields across 50 players. PGM-specific fields are documented below.

2. PGM_MLB26_roster_unclamped_EXPERIMENTAL.json
   Same structure and players, but mapped attribute numbers above 99 are kept.
   Use only for an experimental new-game import. The sample does not establish
   that PGM accepts values above 99. This version still cannot preserve every
   Show attribute exactly because PGM has different fields.

3. MLBTheShow26_Live_EXACT_source.json
   Exact unmodified Live Series item records returned by the official MLB26
   public items API. This is the complete source archive, NOT a PGM import.
   All original split attributes, pitches, quirks and source numbers remain.

4. MLB30_staff_METADATA_NOT_IMPORT.json
   636 sourced staff records: coaches, published support/medical staff, and
   baseball-operations leadership across all 30 clubs. There are 29 managers
   listed; the Angels directory has no manager listed at retrieval. Vacancies
   are not filled with invented names. This is NOT a staff import file. Do not
   paste it into the game's STAFF field. The uploaded export contains players
   only, and a compatible Baseball staff schema could not be verified.

5. MLB30_team_names_METADATA.json
   All 30 official MLB names and their PGM team IDs. This is reference metadata,
   NOT a team-renaming import. The supplied player schema has no team-name
   fields. OAK must remain the PGM ID even though the real name is Athletics.

RATINGS SOURCE AND DATE
Official game: MLB The Show 26, public Diamond Dynasty Live Series data.
Latest published roster update: #27, November 6, 2026.
Retrieved for this build on November 23, 2026.
Official index: https://mlb26.theshow.com/apis/roster_updates.json
Official items: https://mlb26.theshow.com/apis/items.json?type=mlb_card&page=1
API documentation: https://mlb26.theshow.com/apis/docs/items
146 pages / 3,630 total cards downloaded; only series == Live was included.
The API's legacy series_year value is not the game edition. The MLB26 endpoint
and its update index establish the edition. Special-series cards, legends and
temporary Inside Edge boosts were not substituted for Live Series ratings.

These are NOT verified offline Exhibition/Franchise roster ratings. A complete
public export of the offline roster was not obtained. Public Live Series
ratings are the verified dataset available here.

All 172 overall values in update #27 agree with the current items snapshot.
Historical changes were cross-checked, not blindly replayed: 23 old overall
entries and four old control entries differ from current items. Current items
remain authoritative for this build; source_history_crosscheck.json records
every discrepancy. No guessed correction was applied.

WHAT CANNOT BE EXACT IN PGM
- One PGM batPower field cannot hold two Show power splits. The conversion uses
  their rounded arithmetic mean, then caps in the adapted file if necessary.
- PGM left/right pitching control both receive Show pitch_control. The Show
  does not supply that same handed control split.
- Pitch velocity/break/clutch are analogous numeric copies, not proof of equal
  simulation behavior. Hitter stamina uses durability as a proxy; injury
  proneness uses inverse durability. These are conversion assumptions.
- Baseball IQ, pitch variety/consistency/holding runners, baserunning,
  personality, potential and growth curves retain fictional-template values.
- Contracts, guarantees, extension terms, service time and draft pick numbers
  are template gameplay placeholders, NOT real MLB contract or history data.
  Draft year is corrected only when verified in the matched MLB biography.
- Country remains the only demonstrated template enum, USA. This is wrong for
  foreign-born players; actual MLB birth country / Show birthplace is recorded
  in the audit. Other accepted PGM country codes could not be verified.
- Appearance stays fictional, as requested. No likeness work was performed.
- PGM has only one secondary-position field. It uses the first available
  source secondary; repeats the primary when none is given. That no-secondary
  representation is structurally valid but not proven in-game. Ohtani retains
  his source pitching and hitting data and uses DH as his secondary; PGM's
  two-way behavior is unverified.
- PGM may recalculate overall ratings, especially after position changes.
  Storing the exact Show overall does not guarantee the same displayed rating
  or player performance in PGM.

ROSTER AND BIOGRAPHY COVERAGE
Team membership follows the downloaded Show snapshot, not later MLB offseason
transactions. The Show Free Agents bucket also includes some minor-league or
inactive players; it is not a verified legal free-agent list.
There are 169 positively matched team differences against MLB's November 23
40-man rosters. See team_assignment_differences.json.
1,794 records matched MLB biographies; ages are calculated from birth dates.
290 unmatched or ambiguous records keep the source card age, which can be
stale. Source names, IDs, matching methods and original donor IDs are recorded
in player_conversion_audit.json. Namesakes are not merged into one player.
This does not include all minor leaguers or all future draft prospects.

HOW TO TRY THE PLAYER IMPORT
Your supplied screenshot has separate ROSTERS and STAFF URL fields.
1. Choose one of the two PGM_MLB26_roster files above.
2. Host that JSON at a publicly accessible direct HTTPS file URL (for example,
   upload it to a GitHub repository and use the file's Raw link). The link must
   return JSON, not a preview page, sign-in screen or ZIP. No file was published
   publicly on your behalf. These downloads are local files, not import URLs.
3. Start a new game, put the direct file URL into ROSTERS, and leave STAFF blank.
4. Check roster counts, team assignments, payroll and displayed attributes in
   that new save before relying on it. Import/startup/season simulation remain
   untested. The full pool assigns 40 players per team, while your template
   assigned 28-35; PGM may require demotions or roster adjustments.

TO FINISH THE MISSING IMPORT WORK
A real Pocket GM: Baseball staff export (even fictional staff) is needed to
establish required keys, enum values, roles and types. The player export cannot
establish that schema; football/basketball staff files are not safe substitutes.
A verified team-settings import or in-game team-edit workflow is also needed
to apply the real team names. Staff/team metadata is ready for that conversion.
An offline Show roster export is needed if offline Franchise ratings are the
specific rating set intended, rather than public Live Series values.

AUDIT FILES
VALIDATION_REPORT.json: completed checks and explicitly untested checks.
FIELD_MAPPING_AND_LIMITATIONS.json: exact copies, conversions and defaults.
player_conversion_audit.json: every player's source and template donor.
rating_clamps.json: all 58 capped fields, including original values.
uploaded_player_schema_INFERRED.json: schema inferred from your actual export.
SOURCE_MANIFEST.json: source URLs and download manifest.
OFFICIAL_roster_update_index.json / OFFICIAL_update_27.json: release evidence.
CHECKSUMS.json: SHA-256 hashes for delivered files.

Import-format research:
https://apps.apple.com/us/app/pocket-gm-baseball-sim/id6786448308
https://www.reddit.com/r/pocketGM/comments/1umw314/2026_mlb_rosterjays/
https://www.reddit.com/r/pocketGM/comments/1lrfqnc/created_a_roster_causing_crash/
https://github.com/PGM21-json/PGM21 (football, not used as Baseball schema)

MLB team, player and staff metadata: https://statsapi.mlb.com/api/v1/
Each staff entry contains its specific official MLB source URL. Published
directories may lag unannounced or recently announced changes. Front-office
coverage is leadership only, not every scout or organizational employee.
