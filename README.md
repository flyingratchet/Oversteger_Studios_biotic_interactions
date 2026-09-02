[![GloBI Review by Elton](../../actions/workflows/review.yml/badge.svg)](../../actions/workflows/review.yml) [![GloBI](https://api.globalbioticinteractions.org/interaction.svg?accordingTo=globi:flyingratchet/Oversteger_Studios_biotic_interactions)](https://globalbioticinteractions.org/?accordingTo=globi:flyingratchet/Oversteger_Studios_biotic_interactions)

# Oversteger Studios — Biotic Interactions

Part of [**Oversteger Studios**](https://overstegerstudios.com).

Species interactions — predation, pollination, herbivory, parasitism, and the
like — observed at a residential yard in Tempe, Arizona; Fish Creek Canyon, a
drainage in the Superstition Wilderness Area; and Redfield Canyon, a
wilderness area in southeastern Arizona — shared here through
[Global Biotic Interactions (GloBI)](http://globalbioticinteractions.org).

This dataset draws from two ongoing projects: [Rewilding Our Yard](https://overstegerstudios.com/work/rewilding),
an effort to turn a suburban yard into a refuge for the native plants and
wildlife of our home county, and the [Sonoran Species Compendium](https://overstegerstudios.com/work/compendium),
a broader natural history record of field sites including Fish Creek Canyon
and Redfield Canyon. Both involve carefully documenting what's found at each
place, year after year. This repository is the part of that record that's
specifically about *relationships*: not just what showed up, but who it ate,
who it pollinated, who preyed on it.

## About this data

Records here are kept simple and direct — what interacted with what, and
when — and periodically brought up to date. If you notice an error or want to
suggest a correction, please [open an issue](../../issues/new); we welcome
that kind of conversation.

`interactions.tsv` is a compiled output rather than a working file — edits
made directly to it will be overwritten the next time it's refreshed, so
corrections are best raised as an issue rather than a direct edit.

## Data Format and Dictionary

The file [interactions.tsv](./interactions.tsv) uses GloBI's standard tab
separated interaction format. Each term generally has two columns: an id (to
make it machine readable) and a label (to make it human readable).

term | example | description |
--- | --- | ---
sourceOccurrenceId | 83742b5e-f0fd-4c12-a0af-c97191ea7722 | globally unique id to reference the individual originating organism, specimen. Inspired by http://rs.tdwg.org/dwc/terms/#occurrenceID .
sourceTaxonId | GBIF:1234567 | taxon classification id of originating organism in some taxon name authority
sourceTaxonName | Enhydra lutris | scientific name of taxon classification of originating organism
sourceBodyPartId / sourceBodyPartName | http://purl.obolibrary.org/obo/UBERON_0000178 / blood | identifier/label of the source body part interacted with
sourceLifeStageId / sourceLifeStageName | http://purl.obolibrary.org/obo/UBERON_0007023 / adult | identifier/label of the source's life stage
sourcePhysiologicalStateId / sourcePhysiologicalStateName | http://purl.obolibrary.org/obo/PATO_0001422 / dead | identifier/label of the source's physiological state
interactionTypeId | RO:0002470 | id of interaction as described by the [OBO Relations Ontology](https://github.com/oborel/obo-relations)
interactionTypeName | eats | human readable description of the interaction
targetTaxonId / targetTaxonName | GBIF:1971 / Echinoidea | taxon classification id/name of the target organism of the interaction
habitatId / habitatName | ENVO:00000067 / cave | reference to a habitat classification, e.g. [Environmental Ontology](http://environmentontology.org/)
localityId / localityName | GEONAMES:5391961 / Fish Creek, Arizona | reference to a geo classification like geonames.org
decimalLatitude / decimalLongitude | -41.0983423 / -121.1761111 | geographic center of the interaction observation location
depth / altitude | 123.2 / 4553.2 | distance below surface / height above sea level, in meters
observationDateTime | 2024-05-01T14:32:10 | [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) formatted date time string
referenceDoi / referenceUrl / referenceCitation | 10.1007/s13127-011-0039-1 / ... / ... | reference to the source of the record, when it comes from published literature rather than direct observation

*(target-side columns mirror the source-side ones above: `targetOccurrenceId`,
`targetBodyPartId`/`Name`, `targetLifeStageId`/`Name`,
`targetPhysiologicalStateId`/`Name`.)*

### Term Id Sources
Rather than only a name, a reference to an established taxonomy and/or geo
database is preferred where available. Taxon id sources used here include
[GBIF](http://gbif.org) and [ITIS](http://itis.gov). Geo database/vocabulary
references, where used, come from [geonames](http://geonames.org).

### Interaction Type Cheatsheet
For the full list, see the [OBO Relations Ontology](https://github.com/oborel/obo-relations).

interactionTypeId | interactionTypeName
--- | ---
[RO:0002470](http://www.ontobee.org/browser/rdf.php?o=RO&iri=http://purl.obolibrary.org/obo/RO_0002470) | eats
[RO:0002444](http://www.ontobee.org/browser/rdf.php?o=RO&iri=http://purl.obolibrary.org/obo/RO_0002444) | parasite of
[RO:0002455](http://www.ontobee.org/browser/rdf.php?o=RO&iri=http://purl.obolibrary.org/obo/RO_0002455) | pollinates
[RO:0002556](http://www.ontobee.org/browser/rdf.php?o=RO&iri=http://purl.obolibrary.org/obo/RO_0002556) | pathogen of

## Citation & License

> Rick Overson. 2026. Species interactions observed at Tempe House, Fish Creek,
> and Redfield Canyon, Arizona, as part of the Rewilding Our Yard and Sonoran
> Species Compendium projects.

Licensed [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/) — reuse is
welcome with attribution.

## More from this project

- [overstegerstudios.com](https://overstegerstudios.com) — the broader studio
- [Rewilding Our Yard](https://overstegerstudios.com/work/rewilding) — the yard observations come from
- [Sonoran Species Compendium](https://overstegerstudios.com/work/compendium) — the field-site observations come from, and a fuller reference for the species involved

Comments or questions about GloBI itself: [open an issue on the GloBI project](https://github.com/globalbioticinteractions/globalbioticinteractions/issues/new).
