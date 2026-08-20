# Working on this site

This is a real person's professional web presence. Camille Zolopa is a PhD
candidate in Counselling Psychology at McGill, supervised by Dr Dennis
Wendt, and this site is what a hiring committee, a prospective supervisor,
or a future client will find when they search her name. Treat accuracy and
her privacy as the first constraints, ahead of anything visual.

Read `README.md` for how the page is built. This file is about judgment
calls.

## Content rules

**Never invent biographical facts.** Degrees, dates, supervisors, awards,
journals, funding amounts, publication details — every one of these comes
from a source document she supplied. If something is missing, leave it out
and say so; do not fill the gap with a plausible guess. A fabricated
publication or a wrong institution on an academic CV is a serious problem
for her, not a cosmetic one.

**Don't publish her phone numbers.** She asked for them off. The CV in this
repo is a redacted copy: the phone row is removed from the PDF's *text
layer* via PyMuPDF redaction, not covered with a white box, so the digits
cannot be selected, copied, or scraped. If the CV is ever replaced, redo
that redaction and verify with `page.get_text()` that no number survives.

**Source documents are not website copy.** Her CV, a practicum application
letter, and a statement of purpose were used as raw material. Some of it
must never appear:

- The application letter describes **specific therapy clients and their
  presenting concerns**. That is confidential clinical material. It is not
  on the site and must not go on.
- The letter is an *application* to MUHC, not a placement she holds. Don't
  list it as experience.
- The statement of purpose was written years ago for a different program.
  Parts of it are now out of date — it says substance use is not a topic
  she intends to pursue, and it is now her dissertation.

**Photos of other people need their consent.** `conference.jpg` shows three
colleagues alongside her. They are deliberately unnamed in the caption.
Don't add names, and flag it if that photo is ever the subject of a change.

**Don't use university logos.** The McGill crest and wordmark are
trademarked and reserved for official university communications. Education
entries use plain initial monograms instead. This came up and was decided
deliberately.

## Design

Muted cream paper, oxblood accent, serif body text (Source Serif 4), name
in Cormorant Garamond, sans-serif for labels and UI (Inter). Restrained and
academic — the visual interest comes from structure, spacing, and small
line icons rather than colour or ornament.

Motion is welcome but must stay subtle: content rises in as it enters the
viewport, cards lift on hover, the portrait drifts against the scroll.
**All of it is gated behind `prefers-reduced-motion: no-preference`**, and
the parallax is also disabled on narrow screens. Keep it that way.

Photos are shown as shot. An earlier attempt to warm them with a sepia
filter was removed — it read as a strange lighting edit rather than a tone
match.

## Verify before pushing

There is no test suite, so check in a real browser (Playwright is
available, Chromium at `/opt/pw-browsers/chromium`):

- No horizontal overflow at 390px wide, on every tab
- Every panel visible with JavaScript disabled
- Nothing stuck at `opacity: 0` under `prefers-reduced-motion: reduce`
- No failed image requests
- Bump the `style.css?v=` string if the stylesheet changed

## Deploying

Push to `main`. GitHub Pages publishes within about a minute. There is no
staging branch, so **a push is a publish** — pushing and going live are the
same act here.
