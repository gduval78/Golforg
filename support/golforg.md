# Golforg — support knowledge

Curated notes for the support agent. **Keep this file up to date at every store delivery**: add each new feature, limit or known issue with the version it appeared in, then tag the repo `release-golforg-<version>`.

## Versions
- iPhone / iPad: 1.2.0. Android: 1.2.0. Same features on both, same data format: a backup file made on one can be restored on the other.
- Golforg is the **organizer's** app. Players and scorers use the companion app **Golfscore** (separate app, see its own notes).
- No account, no server, no internet needed: all data (players, courses, tournaments, scores) lives on the device. A lost or reset device without a backup means lost data.

## Free and Pro
- Free: any number of tournaments, but each with at most **4 players and 1 day**. Everything else (draw, scanner, rankings, PDF) is free.
- **Golforg Pro**, monthly subscription (about 3 EUR/month, price shown by the store): unlimited players, up to 14 days per tournament.
- Only *creating* is limited: a restored backup with a big tournament, or a cancelled subscription, never blocks reading, entering scores or exporting.
- Restore a purchase: Settings and help → Golforg Pro → Restore purchases, signed in with the same Apple ID (iOS) or Google account (Android).
- Refunds and charges are handled by Apple / Google, not by us.

## Backups (important)
- Backup screen: counts, date of the last backup, **Back up now** (a `.sqlite` file shared via the system share sheet: Files, iCloud Drive, AirDrop, mail), **Restore a backup…** (shows the content and asks confirmation; the previous data is kept in a side file).
- An orange reminder appears on the home screen if never backed up or older than 7 days.
- Switching phones or platforms (iPhone ↔ Android): back up, send the file, restore on the other device.

## Tournament set-up
- A tournament has days (up to 14, golf days and rest days). Each golf day has its own course(s) and its own **format** (Stableford, Shamble, Scramble, best N scores, stroke play…). The same course can be used on several days with different formats.
- Rest day: "Pause" in the schedule. **Cancel a golf day** (bad weather) turns it into a rest day and deletes that day's draw. **Exchange two days** swaps golf/rest days and keeps the draw. **Replace a day's course** keeps format and groups. These actions are refused (error) once scores exist on the day affected.
- Shamble / Scramble and Stableford rankings exist in **net and gross** versions.
- Strokes received for net: handicap rounded; `handicap // 18` strokes everywhere plus one more on the holes whose index is at most `handicap % 18`.
- Picked-up ball: counts "par + N" (N = 5 by default, adjustable 0-10 per tournament) in gross and net, 0 point in Stableford; in team formats it only counts when no teammate has a valid score on the hole.

## Draw (groups)
- "Draw the groups": constraints (do not replay together, balance handicaps, keep apart, keep together, fixed group, unavailable), then propose, adjust by swapping two players, apply.
- The **first draw of a day is accepted directly**; redoing or cancelling a day that already has groups asks for a 6-digit **code to retype**. Refused if scores already exist.
- **Partial draw** (absent players): choose the day and the absent players; either keep untouched groups and only rebuild the affected ones, or redraw the whole day. Absent players are not remembered.
- Group sizes are balanced (e.g. 27 players = 6 groups of 4 + 1 of 3).

## Score cards and scanner
- Blank cards are printed from "Draw the groups" (PDF of the day, or one group). Each card has **4 black squares in the corners**, a short QR code (`GOLFORG:…`) used by the paper scanner, and a larger QR code with the full card for Golfscore.
- **Cards printed before version 1.1 cannot be read** (no corner marks, or no full card QR): print them again. If the **course of a day is replaced, or the draw changed, print again**.
- Entering results: "Enter the results" → pick a group → buttons, or **Scan a score card** (photo of the filled card), or **Import results** (QR code shown by Golfscore).
- Paper scan: whole card in the frame, good light, flat, pencil or pen dark enough. A review screen shows each cell: **orange = uncertain**, **red = blocking error** (putts greater than strokes, missing value). Nothing is saved before the user validates. "R" = picked-up ball. A confident but wrong reading is not flagged: compare the thumbnails with the values.
- Reading accuracy on real handwriting depends on the writing; digits must be clear and inside the boxes.
- Importing results from Golfscore: the same review screen appears. A warning (not blocking) says if the card changed after printing.
- A score that is already saved and gets changed asks for confirmation ("old → new").
- A group's status in "Enter the results": green = complete, orange = incomplete, blue = not started. A player with no score at all (withdrawn) does not make the group incomplete.
- Show a card's QR on screen (no printing): swipe a group to the right, or the QR button in the group.
- Android: scanning uses the Google document scanner (the module may need to be downloaded the first time); long-press to delete (no swipe).

## Rankings and export
- Gross, net, putts, and one ranking per formula (Stableford net/gross, Shamble, Scramble…). "Generate from the formulas" creates the missing ones, never modifies existing ones.
- PDF export: choose the rankings; same on iPhone and Android. Pick-up holes appear in a "Pick-ups" column.
- Delete **all scores** of a tournament (to restart a test): button in the tournament page, asks a code to retype; players, schedule, draw and rankings are kept. Deleting the tournament is also protected by a retyped code; players and courses stay.

## Settings and help
- "Settings and help": language (8: English, French, German, Spanish, Italian, Portuguese, Chinese simplified, Russian; default = system language), **Contact support** (prefilled mail: app version, build, device, languages and *counts* only — never names or scores), diagnostic log, documentation, privacy policy.

## Common situations
- **"Subscription not loaded"**: the store is unreachable or the product is not available yet; check the connection and the store account, then Restore purchases.
- **Cannot add a 5th player / second day**: free limit (see above).
- **Scan finds no QR**: the card is too old (printed before 1.1) or the photo is blurred / cropped; reprint, or use "Import results" with Golfscore, or enter by buttons.
- **Rankings look wrong after a late edit**: they are recomputed on opening; check the day's format and that every group is complete.
- **A day cannot be cancelled / exchanged / replaced**: scores already exist on it.

## Not supported / limits
- No online sync, no shared access: one organizer holds the data (players use Golfscore for entry).
- iPad is supported (centred content column on large screens). Golforg on a Mac ("Designed for iPad") is untested.
- Maximum 14 days per tournament.
