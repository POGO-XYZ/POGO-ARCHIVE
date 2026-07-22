# Legacy Archive — 2024

This document explains the relationship between the current POGO Studios Archive and the system that preceded it.

## What Existed Before

In 2024, POGO Studios recorded physical works under an earlier archival approach — the studio's first formal archival practice. That system used the same POGO ID naming convention and SHA-256 image hashing as today, but distributed verification across multiple blockchain networks simultaneously.

The 2024 system worked as follows:

Each work was assigned a reference image and its cryptographic hash, then deployed across multiple platforms for redundancy:

* **IPFS** — images were pinned for distributed access and retrieval
* **Solana blockchain** — reference images were inscribed and minted, with optional collectibility for interested parties
* **Arweave blockchain** — composite "permafiles" were created and stored permanently, containing the image, full metadata, and active links to all other record components (the most interactive and complete representation)
* **Bitcoin blockchain** — records were inscribed, cross-referencing all other components

Each system referenced all the others equally — IPFS pointed to Solana and Arweave and Bitcoin, Solana pointed back to all three, and so on. No single system was the authority; instead, all components verified each other across the network. The Arweave permafile was the most complete and interactive representation, but all four systems were meant to function as equal, mutually-verifying records.

The intent was elegant: maximum decentralization with no hierarchy and no single point of authority. But managing four interconnected systems simultaneously proved difficult to sustain at scale.

## What Changed in 2025

The 2024 approach proved difficult to sustain at scale. Managing three blockchain networks simultaneously, maintaining IPFS pinning indefinitely, covering Arweave storage costs, and cross-referencing records across all platforms introduced substantial complexity and expense with diminishing returns on actual durability and accessibility.

The current canonical system — described in the primary [README](./README.md) — simplified the architecture by prioritizing what actually matters: a permanent, human-readable archive anchored once per year on Bitcoin, with image verification through hashing rather than blockchain inscription, and media stored in a dedicated, accessible repository rather than distributed across multiple chains.

At the start of 2026, both the 2025 archive and the preceding 2024 legacy archive were finalized together: 2025 as the first canonical year under the new system, and 2024 works migrated from the legacy system into the same canonical structure and ID format used studio-wide.

## What This Means for Legacy References

Works originally archived in 2024 may still be associated with Solana inscriptions, IPFS hashes, Arweave permafiles, and Bitcoin cross-references from that system. These earlier records remain historically valid as part of a given work's provenance — they document a real moment in the work's lifecycle — but they are not the current source of verification.

The Solana and Arweave records will continue to exist as long as those networks operate, but they are no longer actively maintained or updated. The IPFS pinning, if it lapses, will cause those records to become inaccessible.

**The canonical record for any physical work — regardless of when it was created — is its entry in the POGO Studios Archive under its current POGO ID.** If a discrepancy exists between a legacy reference and the current archive record, the archive record governs.

## Why This Document Exists

An archive is only as trustworthy as its ability to be understood by someone encountering it without prior context. This document exists so that anyone — a collector, a researcher, an heir, or POGO Studios itself in the future — can understand how earlier records relate to the current system, and why the approach changed, without needing to ask.

---

*This document is part of the POGO Studios Archive and is licensed under [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).*