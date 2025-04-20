# Test ideas
 
Ideas for tests against the Graves ontology, grouped by Class and Property

<!--
## Things to test

The Graves ontology has these main Classes:

- **Dead_people_place** (Cemetery, Columbarium, Shipwreck, Dig_site, etc.) *which containsGrave...*
- **Container_for_human_remains** (Grave, EmptyGrave, WarGrave, etc.) *which hasRemains...*
- **Remains** (Skeleton, Ashes, Partial_remains) *which isRemainsOf...*
- **Person** (an external reference) *who isCommemoratedBy...*
- **Monument** (Memorial, Tombstone, Headstone, Footstone, Plaque, etc.)

## Types of tests

Tests can include: 

- Missing values [`hasValue`](https://www.w3.org/TR/shacl/#HasValueConstraintComponent)
- Values are within a [value range](https://www.w3.org/TR/shacl/#core-components-range)
	- For example:  Grave Lat, Lon within Cemetery Lat, Lon `minInclusive` and `maxInclusive`
- Values are [`in`](https://www.w3.org/TR/shacl/#InConstraintComponent) a list of valid values. For example: 
	- Tombstone `hasState` values
	- Cemetery `denomination` values 
- Values match the  defined [`datatype`](https://www.w3.org/TR/shacl/#DatatypeConstraintComponent)
- [Cardinality constrains](https://www.w3.org/TR/shacl/#core-components-count). For example: 
	- an EmptyGrave must have zero Remains

-->


### Dead_people_place class

<!-- For reader convenience, consider linking each class to either the documentation or the first line of its defintion in graves.owl however this is fragile and will require ongoing maintenance. -->

The [`Dead_people_place`](https://github.com/muninn/graves/blob/main/ontology/graves.owl#L254) class has the sub-classes: `Burial Mound`, `Cemetery`, `Churchyard`, `Columbarium`, `Crypt`, `Dig_site`, `Graveyard`, `MilitaryCemetery`, `Sarcophagus`, `Shipwreck`.

1. Cemetery contains at least 1 Container_for_human_remains


### Container_for_human_remains class 

The [`Container_for_human_remains`](https://github.com/muninn/graves/blob/main/ontology/graves.owl#L296) class has the sub-classes: `EmptyGrave`, `FuneraryUrn`, `Grave`, `Mass_grave`, `Ossuary`, `WarGrave`.

1. FuneraryUrn contains Ashes
1. Grave Lat, Lon location is within Cemetery Lat, Lon minimum and maximum values


### Remains class

The [`Remains`](https://github.com/muninn/graves/blob/main/ontology/graves.owl#L309) class has the sub-classes `Skeleton`, `Ashes`, `Partial_remains`. 

1. Remains are contained in a Container_for_human_remains


### Monument class

The [`Monument`](https://github.com/muninn/graves/blob/main/ontology/graves.owl#L267) class has the sub-classes:  `Plaque`, `Statue`, `Memorial`, `Marker`, `Cenotaph`, `Crypt`, `Tumulus`, `Shrine`, `Sarcophagus`, `Tombstone` (same as `Gravestone`), `Headstone`, `Footstone`, `Khachkar`.

1. Cenotaph is not related to a Grave that contains Remains

### hasLocation property

1. hasLocation Lat is within +/- 90
1. hasLocation Lon is within +/- 180


<!--
## Tests not possible with current ontology

1. **GraveHasLocationWithinCemeteryMBR** - tests is a Graves point location (lat, lon) is within the [Minimum Bounding Rectangle](https://en.wikipedia.org/wiki/Minimum_bounding_rectangle) of the Cemetery's geographic shape.
-->

<!--
## Derived values

In addition to testing conditions, SHACL can also derive values.

1. PersonAgeAtDeath - a Person's deathDate minus birthDate either an exact calculation or an approximation based on the precision available.
-->