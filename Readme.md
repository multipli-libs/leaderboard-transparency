# Multipli × Kaito Transparency Data

This repository hosts public transparency data for the **Kaito × Multipli Leaderboard**.
Each dataset reflects the raw API response received from Kaito, showing Crystal distributions and ranking details for the top Yappers during a given period.

All data is published exactly as received, with no manual modification, to ensure full transparency and auditability.

---

## Repository Structure

```
.
├── snapshot/
│   └── kaito_leaderboard_2025-10-13.json
├── signature/
│   └── kaito_leaderboard_2025-10-13_hash.txt
└── Readme.md
```

* `snapshot/` contains the raw JSON data from Kaito’s API.
* `signature/` contains the SHA256 hash of the JSON file for integrity verification.
* Each file is named by date using the format `kaito_leaderboard_YYYY-MM-DD.json`.
* Each upload represents a single leaderboard snapshot.

---

## File Descriptions

### `snapshot/kaito_leaderboard_2025-10-13.json`

Official leaderboard data as returned by the Kaito API.
Contains the ranked list of Yappers with mindshare, contribution values, and all engagement metrics.

**Structure (summarized; see the snapshot for the full schema):**

```json
[
  {
    "rank": "1",
    "mindshare": 0.010413377768675222,
    "contribution": 0.010413377768675222,
    "username": "@example",
    "total_impressions": 12450,
    "total_likes": 890,
    "total_smart_engagements": 210,
    "tweet_counts": 42,
    "peripheral_tweet_urls": [],
    "tweet_urls": []
  }
]
```

### `signature/kaito_leaderboard_2025-10-13_hash.txt`

SHA256 checksum of the JSON file for verification.

---

## Verification and Authenticity

* The JSON file was generated directly from the Kaito API response.
* No post-processing, filtering, or manual edits were made.
* File integrity can be verified using the SHA256 checksum below.

**Important — line endings:** the hash in `signature/` is computed over the committed file content with **LF** line endings, exactly as stored in this repository. If your local checkout converts line endings (e.g. Git `autocrlf` on Windows), normalize to LF first — the shipped `.gitattributes` file pins `snapshot/*.json` and `signature/*.txt` to LF, so a clean fresh clone always matches.

**SHA256 Checksum**

```
sha256(kaito_leaderboard_2025-10-13.json)= f9c423185ad8c3d9202d495b2a9c9a77cd90481c8680d7430cd6deaa0b96be2d
```

**Verify locally**

```bash
# Use the committed (LF) content of the file
git show HEAD:snapshot/kaito_leaderboard_2025-10-13.json | shasum -a 256

# Or, on a fresh clone with .gitattributes honored:
shasum -a 256 snapshot/kaito_leaderboard_2025-10-13.json
```

---

## Update Policy

* **Update Frequency:** Weekly (every Tuesday)
* **Next Update:** 2025-10-21
* **Last Updated:** 2025-10-13

All previous snapshots will remain permanently accessible for audit and comparison.

---

## Transparency Note

This repository is part of Multipli’s ongoing effort to maintain open and verifiable data practices.
By publishing the unaltered Kaito leaderboard data, we aim to provide the community with clear insight into leaderboard activity, Crystal emissions, and engagement distribution.
