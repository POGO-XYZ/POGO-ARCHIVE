# POGO Studios Official Archive

This repository is the official public archive of physical artworks created by POGO Studios.

The archive exists to support long-term provenance, authenticity, and accessibility for each physical work through clear records, transparent structure, and cryptographic verification.

This is not a storefront or gallery. It is a reference system designed to remain readable and verifiable over time.

---

## Purpose

POGO Studios assigns a single, consistent identification system across all works, both physical and digital.

This archive focuses specifically on **physical artworks**, providing a durable digital record for works that exist materially in the world. While digital works also receive POGO IDs, they are not currently archived within this repository.

The archive prioritizes:

- clarity over complexity
- longevity over convenience
- human readability over automation

---

## Structure

Artworks are organized by calendar year.

Each year contains:

- one index file listing all archived physical works from that year
- a folder of individual artwork records

YYYY/

├── index-YYYY.json

└── records/

├── POGO-YYYY-XX-SEQ.json

├── POGO-YYYY-XX-SEQ.json

└── ...

Each official physical artwork has exactly one archive record file.

---

## Artwork Records

Artwork records are stored as JSON files.

Each record may include:

- descriptive information (title, medium, dimensions, date)
- references to publicly viewable images
- cryptographic fingerprints of reference images
- notes regarding creation , editioning, or status

Images themselves are hosted externally (for example, on the POGO web gallery and/or storefront).

This archive stores **references and verification data**, not image files.

---

## Image References & Verification

Each artwork record includes one or more reference image URLs alongside cryptographic fingerprints.

These fingerprints allow verification that a reference image has not changed since it was recorded, even if the image is viewed or hosted elsewhere.

This approach separates:

- **visual presentation** (websites, galleries)
- **truth and verification** (this archive)

---

## IDs & Identification

POGO Studios uses a **single identification system** across all works, regardless of medium.

Each work—whether physical or digital—is assigned a POGO ID at the time of creation.

This archive records and indexes **physical works only**, but follows the same ID structure used studio-wide.

---

### POGO ID Format

POGO IDs follow this general structure:

POGO-YYYY-TT-SSS

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

This list will expand as new formats or media are introduced.

---

### Sequencing

Sequencing depends on the type of work:

- **Physical works** typically use an **alphabetic sequence**
    
    (A–Z, AA–AZ, BA–BZ, etc.)
    
- **Digital works** typically use a **numeric sequence**
    
    (01, 02, 03, etc.)
    

Sequencing systems are internal to POGO Studios and are recorded for reference, not interpretation.

---

### Archive Scope

Only **physical works** are currently archived in this repository.

Digital works may be referenced elsewhere online and on-chain, but are not indexed or recorded here at this time. The use of a unified ID system allows physical and digital works to coexist conceptually without requiring a single archive for all media.

---

## Proofs & Permanence

Once per year, the yearly index file is anchored via external cryptographic proofs recorded on Bitcoin.

These proofs establish a permanent public timestamp showing that the archive existed in its recorded form by that date.

Proof files related to yearly anchoring are stored in the `proofs/` directory.

---

## Version History

This repository uses Git version history to preserve transparency over time.

- New records may be added incrementally
- Corrections or clarifications are recorded through commits
- Previously recorded data remains accessible through history

The archive may evolve, but its history remains visible.

---

## Studio Seal & Authentication Mark

POGO Studios maintains a studio seal used as a marker of authorship and authenticity.

The seal exists in both physical and digital forms:

- as a visual mark applied to physical artworks or certificates when applicable
- as a design inscribed on Bitcoin as a permanent digital reference

The inscribed seal serves as a symbolic root for the archive, establishing continuity between physical works, archival records, and cryptographic proof.

While individual artworks are verified through their own records and yearly proofs, the seal represents the broader identity and authorship of POGO Studios rather than a dependency for individual verification.

---

## Intent

This archive is designed to be:

- public
- inspectable
- resilient
- independent of any single marketplace or platform

It exists to support the long-term integrity of physical artworks while remaining approachable to non-technical explorers.
