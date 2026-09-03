[![GloBI Review by Elton](../../actions/workflows/review.yml/badge.svg)](../../actions/workflows/review.yml) [![GloBI](https://api.globalbioticinteractions.org/interaction.svg?accordingTo=globi:flyingratchet/Oversteger_Studios_biotic_interactions)](https://globalbioticinteractions.org/?accordingTo=globi:flyingratchet/Oversteger_Studios_biotic_interactions)

# Oversteger Studios — Biotic Interactions

Part of [**Oversteger Studios**](https://overstegerstudios.com).

Natural history is about more than knowing which species live in a place. It
is also about understanding the relationships among them: who eats whom,
which insects visit which flowers, where parasites find their hosts, and the
many other interactions that knit an ecological community together.

This repository is our growing record of those relationships, documented
through direct observations at several places in Arizona that we return to
again and again. They currently include our residential yard in Tempe; Fish
Creek Canyon, a drainage in the Superstition Wilderness Area; and Redfield
Canyon, a wilderness area in southeastern Arizona.

The observations come from two ongoing Oversteger Studios projects.
[**Rewilding Our Yard**](https://overstegerstudios.com/work/rewilding) follows
the plants and animals of a suburban yard as we work to make it a richer
refuge for native biodiversity. The
[**Sonoran Species Compendium**](https://overstegerstudios.com/work/compendium)
documents the natural history of field sites across Arizona, including Fish
Creek Canyon and Redfield Canyon.

Both projects grow from the same basic practice: paying close attention to
particular places over long periods of time. As those observations accumulate,
we want to record not only *what lives there*, but *what those organisms are
doing together*.

This repository makes that part of the record openly available through
[**Global Biotic Interactions (GloBI)**](http://globalbioticinteractions.org),
where individual observations can become part of a larger, searchable body of
ecological interaction data.

## About this data

Records are intentionally kept simple and direct: what interacted with what,
where, and when. The dataset is periodically regenerated as new observations
are added and existing records are refined.

We care about making these records useful beyond our own projects, so
corrections and questions are very welcome. If you notice an identification
error, a problem with an interaction record, or something else that could be
improved, please [open an issue](../../issues/new).

`interactions.tsv` is a compiled output rather than a working file. Direct
edits to it will be overwritten the next time the dataset is refreshed, so
corrections are best raised through an issue.


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
