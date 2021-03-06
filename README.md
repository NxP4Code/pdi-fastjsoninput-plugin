# _Fast_ JSON Input - PDI Plugin

[![Build Status](https://travis-ci.org/graphiq-data/pdi-fastjsoninput-plugin.svg?branch=master)](https://travis-ci.org/graphiq-data/pdi-fastjsoninput-plugin)

This is an alternate version of the "JSON Input" step that uses [Jayway JsonPath](https://github.com/jayway/JsonPath) instead of a parser based on JavaScript. It is intended to be a drop-in replacement for the "JSON Input" step but should be much faster and memory efficient.

## Features over PDI JSON Input

* [[PDI-10344](http://jira.pentaho.com/browse/PDI-10344)] Replaced JavaScript parsing engine with Jayway JsonPath
* [[PDI-10858](http://jira.pentaho.com/browse/PDI-10858)] Checkbox to "Remove source field from output stream"
* Checkbox to enable JsonPath's `DEFAULT_PATH_LEAF_TO_NULL` [option](https://github.com/jayway/JsonPath#options) which returns `null` for missing leafs:

```python
[
    {
        "name": "Jesse Adametz",
        "gender": "male"
    },
    {
        "name": "Etienne Dube"
    }
]
```

* Tests! There are currently 4 test cases which test the permutations of "Ignore missing path" and "Default path leaf to null"

## Help

Help for the step and its usage can be found in the [Help documentation](help.md).

## Development

### Build
To build (requires Apache Maven 3 or later):

```shell
mvn package
```

### Install

1. Run mvn install -Dpdi.home=/path/to/local/data-integration (e.g. - mvn install -Dpdi.home=/ssd/graphiq/gq-kettle/dist)

## Authors:
- [Etienne Dube](https://github.com/etdube) - etdube (at) gmail (dot) com
- [Jesse Adametz](https://github.com/jadametz) - jesse (at) graphiq (dot) com
- [James Ebentier](https://github.com/jebentier) - jebentier (at) graphiq (dot) com
