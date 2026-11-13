# Golfscore — support knowledge

Curated notes for the support agent. **Keep this file up to date at every store delivery**: add each new feature, limit or known issue with the version it appeared in, then tag the repo `release-golfscore-<version>`.

## What it is
- Companion app of **Golforg** for players and scorers. Name in the stores: "Golfscore by Golforg"; name under the icon: "Golfscore". Free, no account, no server: everything stays on the phone.
- Versions: iPhone 1.1.0, Android 1.1.0. iPhone only on Apple (no iPad version).
- Flow: scan the QR of the **printed score card** (made by the organizer with Golforg) → enter strokes and putts hole by hole → show the **results QR** → the organizer scans it in Golforg ("Import results").

## Requirements
- The card must have been printed by Golforg **1.1 or later** (it carries the full card in a larger QR). **Cards printed before cannot be opened**: ask the organizer to print them again. Also reprint if the organizer replaced the day's course or redrew the groups.
- Scan the QR: live camera, or "Choose a photo of the QR code" (screenshot, photo of the printed card).
- The results QR code is read by Golforg on the organizer's device.

## Entering scores
- One screen per hole, one line per player: strokes and putts. Keypad 1-9, "10+", "R" (picked-up ball) and delete. Putts: 0 to 10, never more than the strokes. The putts keypad has the same digit layout as the strokes keypad (0 and 10 where "10+" and "R" are).
- A "putts only" player (counts only putts that day, set by the organizer) gets only the putts box.
- **Picked-up ball (R)**: counts par + N (N set by the organizer, 5 by default) in totals gross and net, 0 point in Stableford. The putts of that hole can still be entered (0-10).
- **Hole validation**: **hold the validate button for 1 second** to validate a hole; a validated hole is locked. To edit it: hold 1.5 seconds and confirm. **Only validated holes go into the results QR code** and into the group count.
- **Auto-lock**: after 30 seconds without touching the app the screen turns black (swipe to unlock); also when the app goes to the background. Nothing is lost.
- The day's format is shown under the hole header. On a Stableford day, Stableford points (net and gross) appear under each player; "Group count" shows the group standing (Stableford ranking, or team total net and gross). Stroke play has no count (totals of strokes).
- Full card view ("Card"): all holes, tap a hole to go back to it. **PDF** button: filled score sheet (A4 landscape) to share or print: gross, to par, net, putts, formula count, signature lines; holes not yet validated appear in orange with a warning.
- A card scanned twice keeps its entries. Delete a card: long-press (Android) or swipe/long-press (iPhone) and confirm.

## Results QR code
- Shown from the last screen; it lists only validated holes. A warning appears if some holes are incomplete. The organizer scans it in Golforg (Enter the results → Import results) — QR in live camera, or a photo of the QR. A results QR is **not** the card QR: scanning it in Golfscore gives "This is a results QR code".

## Common situations
- **"This QR code is not from a Golforg score card"**: old card (printed before 1.1) or not a Golforg card → reprint.
- **"This card needs a newer version of Golfscore"**: update the app.
- **"No QR code found in this photo"**: sharper photo, whole QR in the frame, or scan live.
- **Screen goes black**: the 30-second auto-lock (swipe to unlock).
- **Cannot edit a hole**: it is validated; hold 1.5 s and confirm.
- **Android: live camera does not start**: grant the camera permission; otherwise use the gallery photo.

## Known issues
- **Mac (iPhone app on Apple-silicon Mac)**: version 1.0.0 (3) crashed when tapping the scan button; corrected in 1.1.0 (5), not yet confirmed on a Mac. The live camera is not available on Mac: choose a photo of the QR code. If the crash still happens, ask for the version and build shown in the report.
- TestFlight public link: the build offered can lag behind while Apple reviews a new beta build.

## Not supported / limits
- No sync between phones: one phone per group enters the scores; the organizer collects them via the results QR.
- Golfscore never shows rankings of the tournament (those are in Golforg); it only counts for the group's card.
- **Help screen (versions after 1.1.0)**: the "?" button on the home screen (iPhone) or the "Help" button at the bottom left (Android) opens Help: **Contact support** (prefilled mail with the app version, phone model, language and number of cards — never names or scores), the user guide, the privacy policy, and the version line "Golfscore x.y.z (build)". The same version line is shown at the bottom of the home screen. In version 1.1.0 there is no Help button: use the support address of the online guide.
