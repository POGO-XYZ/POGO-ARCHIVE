# POGO Studios Official Archive

This repository is the official public archive of physical artworks created by POGO Studios.

The archive exists to support long-term provenance, authenticity, and accessibility for each physical work through clear records, transparent structure, and cryptographic verification.

This is not a storefront or gallery. It is a reference system designed to remain readable and verifiable over time.

For the philosophy behind this system, see [All Creation Testifies](https://www.pogostudios.xyz/writings/all-creation-testifies), the studio's written piece on the archive's purpose and vision.

The archive can also be browsed, searched, and verified through the **[POGO Studios Archive app](https://app.pogostudios.xyz)** — a public interface that reads directly from this repository. It runs entirely in the browser, can be installed to a phone or desktop, and works offline. Source: [POGO-APP](https://github.com/POGO-XYZ/POGO-APP).

---

## Purpose

POGO Studios assigns a single, consistent identification system across all works, both physical and digital.

This archive focuses specifically on **physical artworks**, providing a durable digital record for art that exists materially in the world. 

The system prioritizes:

* **Legibility as respect**
  No decoder required — the record speaks plainly to anyone who opens it.
* **One language across all media**
  A single system, so every work belongs to the same coherent whole.
* **Truth held apart from presentation**
  What a work *is* does not depend on where it currently appears.
* **A record that speaks for itself**
  Built to remain intact and understandable without its creator present.
* **Testimony, not just storage**
  Permanence as the purpose — not a feature added on top.

---

## Structure

Artworks are organized by calendar year.

Each year contains:

- one index file listing all archived physical works from that year
- a folder of individual artwork records
- a folder of timestamped proofs for those records

```
YYYY/
├── index-YYYY.json
├── records-YYYY/
│   ├── POGO-YYYY-XX-SEQ.json
│   └── ...
└── timestamps-YYYY/
    └── POGO-YYYY-XX-SEQ.json.ots
```

Each official physical artwork has exactly one archive record file.

---

## Artwork Records

Artwork records are stored as JSON files.

Each record may include:

- descriptive information (title, medium, dimensions, date)
- references to publicly viewable images
- cryptographic fingerprints of reference images

Once committed, an artwork record is not altered. It represents a fixed, permanent statement of a work's documentation at the time of archiving. Beginning in 2026, that permanence is made verifiable: each completed record's SHA-256 fingerprint is added to the index, and the record is timestamped on Bitcoin — establishing not only what was recorded, but when.

A work's current status — for example, available, unavailable, or collected — is tracked separately in `links/listings.json`, which is updated continuously as works leave the studio. This keeps the permanent documentation of a work's existence entirely separate from its current market or collection status, and preserves a clear distinction between what is fixed and what is living. Changes to listings are recorded through commits with explanatory messages, preserving a transparent history over time.

This archive stores **references and verification data**, not image files.

Images themselves are hosted in a dedicated companion repository — see Media, below.

---# Addition for POGO-ARCHIVE README

Place this after the **Artwork Records** section, before **Image References & Verification**.

---

## Exhibitions

Where a work has been shown is part of its provenance, and the archive records it.

Exhibition history is held in `LINKS/EXHIBITIONS.JSON`, separate from both the records and the listings, for two reasons. Records are immutable once committed, so an exhibition years later cannot be written into them. And exhibition history is permanent in a way that availability is not — a show that closed in 2026 remains part of a work's history forever, while its status continues to change.

The file is append-only. Past exhibitions are never removed.

Each exhibition lists the works it included:

```json
{
  "id": "EX-2026-01",
  "title": "Exhibition title",
  "venue": "Venue name",
  "location": "City, State",
  "opens": "2026-09-05",
  "closes": "2026-10-10",
  "url": "",
  "acquisition": "venue",
  "works": ["POGO-2026-PO-FA", "POGO-2026-PO-FB"]
}
```

### Exhibition and availability are separate

A work's `status` answers whether it can be acquired. An exhibition answers where it currently is. These are different questions and are recorded separately.

A work on view at a gallery and available for purchase there remains `available`. It is not marked `unavailable`, because it can in fact be acquired — just in person rather than online. Removing its store listing for the duration of the show is sufficient to prevent an online sale; the archive continues to state plainly that the work exists, is available, and is currently hanging at a named venue through a stated date.

The `acquisition` field records how a work may be acquired during a show:

| Value | Meaning |
|---|---|
| `venue` | Available at the exhibition venue for its duration |
| `studio` | Remains available through the studio as usual |
| `none` | On view only; not available during the exhibition |

Nothing needs to be edited when a show ends. Because the dates are recorded, an exhibition passes from upcoming to current to past on its own, and the archive reflects that without intervention.

---

*The [archive app](https://app.pogostudios.xyz) reads this file directly: works currently on view are marked as such, exhibitions can be filtered, and every work displays its full exhibition history.*

## Image References & Verification

Each artwork record includes one or more reference image URLs alongside cryptographic fingerprints (Hashes) of those images.

A work's image may appear in many places over time, and none of them are treated as the source of truth. What matters is not where an image currently lives, but whether it matches what was recorded at the time of documentation.

This is the distinction this archive maintains between:

* **visual presentation** — how and where a work is shown, which is free to change over time.
* **truth and verification** — a fixed, permanent record of what a work's image was, accessible regardless of where it's displayed.

Some records also carry a fingerprint of a web-hosted rendition of the image. These were recorded before the media repository existed, when a website copy was the only publicly reachable version of a work's image. Because hosted renditions can be re-encoded or served at different sizes, the fingerprint is informational rather than for verification. **The source image fingerprint verifies a work's appearance at the time of its completion**and corresponds to the file stored in the media repository.

---

## Media

Reference images for archived works are stored separately in [POGO-ARCHIVE-MEDIA](https://github.com/POGO-XYZ/POGO-ARCHIVE-MEDIA), organized by year and named to match each work's POGO ID exactly.

Each record's image reference links directly to its file in that repository, and the recorded SHA-256 fingerprint corresponds to that exact file as it existed at the time of documentation. If an image is ever missing, moved, or altered, its fingerprint will no longer match — making any discrepancy immediately evident.

Separating media from records keeps this archive lightweight and focused on verification data, while keeping images independently accessible and reusable under the same open license.

---

## Certificates

Each collected physical work is accompanied by a printed certificate. One side carries the studio seal and the phrase that defines the studio's creative philosophy; the other carries essential details, including the work's POGO ID, that cross-reference directly to its digital record, along with a direct reference to the full archive entry.

The certificate is a point of entry, not the final word on authenticity. It travels with the work as a tangible bridge to the permanent verification layer described in this repository, and corresponds to the same ID stamped on the work itself.

This format may be extended in the future — for example, through embedded NFC — without altering its underlying purpose.

---

## IDs & Identification

POGO Studios uses a **single identification system** across all works, regardless of medium.

Each official work — whether physical or digital — is assigned a POGO ID at the time of completion. For physical works only — this will additionally serve as an Archive ID.

This archive records and indexes **physical works only**, but follows the same ID structure used studio-wide.

---

### POGO ID Format

POGO IDs follow this general structure:

```
POGO-YYYY-TT-SSS
```

Where:

- `POGO` identifies POGO Studios
- `YYYY` represents the year of record
- `TT` is a short type code indicating medium or format
- `SSS` is a sequential identifier

Examples:

- POGO-2024-PO-AY
- POGO-2025-PO-CC
- POGO-2024-DO-04
- POGO-2025-BOI-06

---

### Type Codes

The type code indicates the general classification of the work.

Common codes include:

- `PO` — Physical Original
- `PE` — Physical Edition
- `PP` — Physical Print
- `MO` — Mini Original
- `MP` — Mini Print
- `DO` — Digital Original
- `DE` — Digital Edition
- `BOI` — Bitcoin Original Inscription

This list will expand as new formats or media are introduced — including potential future physical authentication layers such as embedded NFC.

---

### Sequencing

Sequencing depends on the type of work:

- **Physical works** use an **alphabetic sequence**

    (A–Z, then AA–AZ, BA–BZ, and onward to AAA and beyond)

- **Digital works** use a **numeric sequence**

    (01, 02, 03, 04, etc.)

The alphabetic sequence is **bijective base-26**: each letter carries a value from A=1 to Z=26, and sequences lengthen only once the previous length is exhausted. A through Z are the first twenty-six works; AA is the twenty-seventh.

This has a practical consequence worth stating plainly, because it is easy to get wrong: **sequences must not be sorted alphabetically.** A plain alphabetical sort places AA immediately after A, skipping B through Z entirely, and would place AAA before B once three-character sequences begin.

Correct chronological order sorts by **length first, then alphabetically within that length**:

A, B, C … Z, AA, AB … AZ, BA, BB … ZZ, AAA, AAB …

Equivalently, rank each sequence by its base-26 value. Any system reading this archive — a catalogue, a spreadsheet, an application — should apply this rule rather than a default string sort.

Sequencing systems are internal to POGO Studios and are recorded for reference, not interpretation.

---

## Archive Scope

Only **physical works** will be archived in this repository.

Digital works may be referenced elsewhere online and on-chain, but are not indexed or recorded here at this time. The use of a unified ID system allows physical and digital works to coexist conceptually without requiring a single archive for all media.

---

## Studio Seal & Authentication Mark

POGO Studios maintains a studio seal used as a marker of authorship and authenticity.

This seal exists in multiple forms:

* stamped physically onto artworks in archival ink
* printed on the certificate paired with each collected work
* inscribed digitally on Bitcoin, serving as a permanent reference

The inscribed seal serves as a symbolic root for the archive, establishing continuity between physical works, certificates, archival records, and cryptographic proof.

While individual artworks are verified through their unique records and yearly proofs, the archival seal represents the broader identity, authorship, and spirit of POGO Studios, adding a further layer of authentication to each finalized work.

---

## Archive Lifecycle & Proofs

The POGO Studios archive is organized by calendar year. Each year remains open while works are actively being created and recorded, and is formally closed once all records for that year are finalized.

At closeout, that year's complete index is cryptographically anchored on Bitcoin — a single, permanent, timestamped commitment marking the transition from active documentation to settled historical record. Proof files related to yearly anchoring are stored in the `proofs/` directory.

All yearly proofs exist within the lineage of the POGO Studios Archive Seal — a foundational Bitcoin inscription representing authorship, identity, and continuity across the archive. The seal functions as a symbolic parent inscription for yearly proofs, establishing a shared root without creating dependency between individual works or years. Each yearly proof remains independently verifiable while participating in this common lineage.

Bitcoin inscriptions are used as cryptographic witnesses rather than storage — preserving decentralization and permanence while keeping the archive human-readable and maintainable over time.

Individual records are timestamped as documented via [OpenTimestamps](https://opentimestamps.org), with proofs stored in each year's `timestamps-YYYY/` folder. This practice began in July 2026; years closed before then are attested by their yearly anchor alone.

**See LEGACY.md** for details on the legacy archival system established in 2024, and its migration into the new canonical system at the start of 2026.

---

## Version History

This repository uses Git version history to preserve transparency over time.

* New records may be added incrementally
* Listing and status changes, corrections, or clarifications are recorded through commits with explanatory messages
* Previously recorded data remains accessible through history

The archive may evolve, but its history remains visible.

---

## Intent

This archive is designed to be:

* public
* inspectable
* resilient
* independent of any single marketplace or platform

It exists to support the long-term integrity of physical artworks while remaining approachable to non-technical explorers.

---

## License

© 2025–2026 POGO Studios. [POGO Studios Archive — System Documentation and Philosophical Framework](https://github.com/POGO-XYZ/POGO-ARCHIVE) by [POGO Studios](https://www.pogostudios.xyz) is licensed under [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/). You are free to share and adapt this material for any purpose provided appropriate credit is given to POGO Studios as the originating source.

[![CC BY 4.0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/by.svg)](https://creativecommons.org/licenses/by/4.0/)

---
