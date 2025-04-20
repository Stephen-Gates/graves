# SHACL validation tests

The Shapes Constraint Language ([SHACL](https://www.w3.org/TR/shacl/)) is a language for validating RDF graphs against a set of conditions. 

This folder contains a collection of tests to validate data against different aspects of the **[Graves ontology](/ontology/graves.owl)**. 

Each sub-folder in this folder is named for the condition being tested, and contains:

- a `readme.md` file explaining the:
  - test (what is tested, any limitations, the version(s) of ontology the test applies to, etc.)
  - test data
  - expected results
  - a link to run the test using the provided test data
- the SHACL test<!-- written in Terse RDF Triple Language ([Turtle](https://www.w3.org/TR/turtle/))--> <!--written in the Resource Description Framework ([RDF](https://www.w3.org/TR/rdf12-concepts/)) language.-->
- valid and invalid RDF test data
- optionally, any files used to generate the test or test data.


## List of tests

Implemented tests are listed below. Click the link to go to the test's sub-directory.

Other test ideas are listed in **[Potential tests](test-ideas.md)**.

1. **[EmptyGrave contains 0 Remains](/EmptyGrave-contains-zero-remains)**
1. **[Grave contains at least 1 Remains](/Grave-contains-at-least-one-remains)**

## How to create a SHACL test

This approach is designed to make it easy to develop tests and minimise the software needed to be installed. 

Go to [SHACL Play!](https://shacl-play.sparna.fr/play/) and select the **[SHACL editor from Excel](https://shacl-play.sparna.fr/play/shaclexcel)** tool, and follow the steps:

1. Download the template file (a local copy is in `/validation/SHACL-template.xlsx`).
1. Fill in the spreadsheet.
1. Convert the spreadsheet to an RDF file using the [online Excel conversion form](https://skos-play.sparna.fr/play/convert).


## How to create test data

*To do.*


## How to run a test

Go to **[Validate RDF data](https://shacl-play.sparna.fr/play/validate)**

1. Upload, link or paste the test data.
1. Upload, link or paste the SHACL test.
1. Specify the following options: *To be confirmed.*
   - [ ] Closed World (adds sh:closed to NodeShapes)
   - [x] Include details
   - [ ] Activate OWL-Micro inference before validation
1. Press the **Validate** button.
1. Compare the results to the expected results.

<!--
## How to combine multiple tests

*To do.*

1. Optionally [generate documentation](https://shacl-play.sparna.fr/play/doc) using the RDF file. ([Sample output](https://europarl.github.io/org-ep/))
-->

## How to contribute

Contributions are welcome.

- If you find **an issue with an implemented test**, [check that the issue isn't already reported](https://github.com/muninn/graves/issues), and if not, [create an issue](https://github.com/muninn/graves/issues/new).
- If you'd like to **suggest a new test**, **improve an existing test**, or **expand on a test idea**, [continue an existing discussion](https://github.com/muninn/graves/discussions) or [start a new discussion](https://github.com/muninn/graves/discussions/new?category=ideas).