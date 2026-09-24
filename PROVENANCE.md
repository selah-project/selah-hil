# PROVENANCE — how this rendering came to be

*Hiligaynon (Ilonggo), chair 94. Lit 2026-09-21. Floor 23,213 verses.*

This is the record of how the text in this repository was produced and
what went wrong with it. A machine-assisted rendering has no standing
unless you can see how it was made, so this file says both. The
verse-by-verse notes, and the classes still uncured, are in
[NOTES.md](NOTES.md).

---

## The approach

Every verse is rendered from the Hebrew of that verse, under a written
discipline — `docs/methodology/translation-discipline/hil.md` in the
Selah repository, itself written in Hiligaynon and built on the nearest
sibling chair, `ceb.md` (Binisayâ / Sinugboanon). Eight rules govern it:
the Hebrew token is the unit; the Name stays the Name; both truths of
Deuteronomy 6:4; no foreknowledge (Genesis 22:1 does not know Genesis
22:13); numbers and letters stay put; the translator has no word of its
own; the heavy verse goes in bare; and the rails' own words never enter
a verse.

**The `⟨ ⟩` brackets do two different jobs.** `⟨את⟩` is the Hebrew
direct-object marker, which Hiligaynon has no word for; it is left
standing so the reader sees it. `⟨pulong⟩` is a word the Hebrew did not
write but the Hiligaynon sentence requires — visibly marked, so you can
always tell what the Hebrew said from what the grammar needed.

Every verse file names the model that wrote it: **glm-5.3**, on the
**glm-5.2** tier.

## The fight on this chair is the neighbours

| Hebrew | here | rejected |
|---|---|---|
| יהוה | **Yahweh** | GINOO, Ginoo (a title, not a name), Jehova, Yawe |
| אלהים | **Elohim** | Dios / Diyos in the Name's place |
| אדני | **Adonay** | Ginoo |
| שדי | **Shadday** | Makaako, Labing Gamhanan as the whole rendering |
| אל | **El** | *dios* as a type-name |
| צבאות | **Tsevaot** | "sang mga Kasoldadosan" as the whole rendering |

**Name seats reading Yahweh: 6,828 of 6,828.** No erasure word stands
on a Name seat.

But the Name held from the first hour, and the pressure on this chair
came from somewhere else. The model knows more Tagalog and more
Cebuano than it knows Hiligaynon, and those two are close enough that a
half-Cebuano verse still reads as almost-sense. The thermometer is
therefore **vocabulary, whole words, whitelist first** — a shared word
is not a fault — and it was read at three gates, by hand.

## The burn and the gates

Lit about 12:20 EDT, engine-side relay. The first pass landed **22,972
of 23,213** with a residue of 241; the refill brought the floor whole
the same day.

| gate | at | the Name | what it sent back |
|---|---|---|---|
| 1 | 1,519 verses | 179 of 179 | *karon* 28 · *yuta* 2 · *kini* 3 · *hindi* 1 |
| 2 | 4,950 | 1,468 of 1,468 | 43 verses of bleed; Exod 26:1, where the rails' own word stood for the Mishkan |
| 3 | 22,332 | 6,555 of 6,555 | about 130 verses of bleed, two of them holding a digit |

At every gate the numbers were read by eye rather than scanned — Genesis
2:2–3 (the seventh day), Genesis 5:5 and 5:27 (930, 969), Genesis 11:13,
Numbers 1:21 (46,500), 1 Kings 10:16 (two hundred shields, six hundred),
1 Chronicles 12:28 (3,700), Ezra 2:3 (2,172) — and they came out right.
That check exists because the Chichewa chair, lit the same day, had just
shown that a row scan is blind to a wrong number in the flow.

The corpus was committed to git **before any pass touched it**
(`84dabf43`, "the burn as it landed"), so every repair is a diff you can
read.

## Finding: the rails can speak inside a verse — and did

Exodus 26:1 called the Mishkan *ang pulungkoan* — the document's own
word for a chair, standing where משכן belongs. The verse was deleted and
re-pressed. Counting the whole chair afterwards showed משכן rendered six
ways (Mishkan 21 · tabernakulo 13 · tolda 8 · Balay-Katalagman 3 ·
puyuan 2), so the rails were amended mid-burn to pin **Mishkan** and
**Tolda sang Katipunan**, and the cache was cleared so the new word
would take. Isaiah 53:5 — the verse that caught this fault on the
Chichewa chair — landed clean here: *labod*, a wound.

## Finding: the chair spends every alphabet it knows into the Hebrew

`dev/scripts/surface_restore.py hil` touched **363 files** and restored
**416 Hebrew surfaces** from the floor. **82** of them had held
something that was not Hebrew at all, and the substitutions are logged
letter by letter in `audit/surface-restore-2026-09-21.txt`: Latin
(*hodil* for הלוא, *masham* for משם, *kaspa* for כסף), Cyrillic (мאד,
зכרתני, пניו), Arabic (لכי, مצרים), Georgian (ჰשבע for השבע), and
Devanagari — one Hebrew he replaced by ह. One surface had swallowed a
whole Hiligaynon clause where כי belonged (Genesis 37:3). Nothing was
laundered: the floor holds the true surface, and the report names every
swap.

Ruth 1:19, whose rows had moved out of order, was deleted for a
re-press rather than restored.

## Finding: a marker check cannot see a placeholder

43 flows carry doubled or empty brackets — `⟨⟨⟩⟩`, `⟨gap⟨ara⟩⟩`,
`⟨⟨walâ⟩⟩`. A bracket with nothing in it, or with a word-shaped
placeholder inside it, passes every marker and parity check there is.
This is the fleet-wide lesson filed on the Bulgarian chair, and it
stands here uncured.

## Hand work: none

No verse in this repository was written or spliced by hand. No file
carries a `hand` field. Every repair was a re-press, a deletion for
refill, or a restore against the floor.

## The cure, in order

| pass | what |
|---|---|
| gate 1 · 2 · 3 | bleed verses deleted for refill, verified gone; the rails amended twice mid-burn (*subong*, **Mishkan**) |
| surface restore | 363 files · 416 surfaces · 82 non-Hebrew reported, not laundered |
| re-press | Ruth 1:19, whose rows had moved |
| refill relay | the 241 residue seats |

## Open — declared, not repaired

- **The census and convict round, and the final gate.** This is the one
  thing owed before seating. [NOTES.md](NOTES.md) carries the count as
  it stands: 464 flows short of their rows · 47 with extra markers · 8
  fabricated row markers · 79 empty gloss rows · 80 flows using ASCII
  `<…>` · 43 doubled or empty brackets · 8 files with English inside
  brackets · 103 names spelt with a Latin *j* · 13 words carrying a
  foreign letter · 2 verses whose Hebrew surface is still off the floor
  (1 Samuel 12:25, wholly transliterated, and Numbers 31:49, one
  surface split by a space).
- **Aramaic** — Daniel 3:12's יתהון carries `⟨ית⟩` where the floor
  carries nothing. Aramaic is unruled across the fleet.
- **אדון and human אדני** — no row of their own in the Name table;
  Isaiah 1:24 and Genesis 23:6 both read *Adonay*.
- **Words for a native ear** — *Dayoranon*, *gin-esturya*, the *j*
  names, and the pairs the rails leave open (*ginsuguran* /
  *ginmulaan*, *gintuga* / *ginhimo*, *kasugtanan* / *katipan*).
- **The UI catalog** is not yet made; it gates seating, not the text.

## Final

**23,213 / 23,213 verses.** Yahweh in **6,828 of 6,828** Name seats.
Three gates read by hand, the numbers read by eye, no digits and no
Spanish numerals in any verse. The census round is owed, and until it
runs this chair is **version 1, not seated**.
