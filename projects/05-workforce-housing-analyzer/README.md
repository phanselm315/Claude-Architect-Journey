# Workforce Housing Analyzer

**Status:** 🔄 Active  
**Started:** Mar 2026  

## What This Is

Iterative Excel + AI parcel analysis tool for a land acquisition campaign in Leelanau
County, Michigan. Now at v102+. Each version adds analytical layers: ownership clustering,
parcel size filtering, proximity scoring. Used to identify acquisition targets for a
workforce housing initiative.

## Architecture

- **Data source:** Michigan tax parcel records (extracted via Python — see Key Decisions)
- **Core tool:** Excel workbook with AI-assisted analysis layers
- **AI layer:** Claude as iterative analytical partner — reviewing parcels, flagging
  clusters, suggesting scoring criteria
- **Versioning:** v102+ — each version represents a meaningful analytical iteration

**Analysis layers (cumulative across versions):**
- Ownership clustering (identify common owners across multiple parcels)
- Parcel size filtering (exclude non-viable lot sizes)
- Proximity scoring (distance to services, infrastructure, employment centers)
- Zoning compatibility flags

## Key Decisions

**Python extraction over county purchase.** The county charges $2,500 for a full parcel
data extract. A Python script pulling the same data from public records took a few hours
to write and ran in minutes. This was the right call — not because $2,500 is prohibitive,
but because the script can be rerun as data updates and modified to pull exactly the fields
needed.

**Excel as the primary interface.** The end consumer of this analysis is not a developer.
Excel is the right tool for a collaborator who needs to filter, sort, and annotate without
technical friction. The AI layer assists the analysis; it doesn't replace the workflow
the user already has.

**Iterative versioning over "final" releases.** Land acquisition analysis evolves as
criteria sharpen. v102 is better than v1 because 101 rounds of feedback refined what
matters. Treating each iteration as a version rather than an overwrite preserves
the reasoning history.

## Lessons Learned

Claude works best as an analytical partner when you treat it as a peer reviewing your
methodology — not just a tool executing instructions. The most useful sessions were the
ones where I brought a hypothesis and let Claude stress-test it.

Public data is underused. Most of what people pay for is already available if you're
willing to write the extraction layer.

---

*Part of the [Claude Architect Journey](../../README.md)*
