# Akamai CLI: Audience Segmentation Cloudlet Update Weights on a Rule

This tool is an example module written in Python for the Akamai CLI Tool although it can be executed individually. A new Cloudlet policy version is created on each change.


## Install

Installation is done via `akamai install`:

```
$ akamai install audience-segmentation
```

Running this will run the system `python setup.py` automatically. 

## Updating

To update to the latest version:

```
$ akamai update audience-segmentation
```

## Usage:
```
usage: akamai audience-segmentation update --policy POLICY --rule RULE
                                              --weights WEIGHTS
                                              [--activate ACTIVATE]
                                              [--edgerc EDGERC]
                                              [--section SECTION] [--verbose]

required arguments:
  --policy POLICY      Policy name
  --rule RULE          Rule name. Example: 'Test Rule #1'
  --weights WEIGHTS    New percentages. Example: '1,50'

optional arguments:
  --activate ACTIVATE  Activate the policy to staging|production
  --edgerc EDGERC      Config file [default: ~/.edgerc]
  --section SECTION    Config section in .edgerc
  --verbose            Enable an interactive verbose mode
```

The --verbose mode goes through every step for every API call and showing the user the generated JSON requests and responses.

### Example 1: update the weights using the default values for .edgerc, seccion and verbose.

Defaults are:
`--edgerc: ~/.edgerc
--section: papi
--verbose: OFF
--activate: OFF`

```
$ akamai audience-segmentation --policy <policy_name> --rule <'rule_name'> --weights <'start_weight_value,end_weight_value'> --activate <staging|production>

```

### Example 2: generate the list overrriding the default values

```
$ akamai as --edgerc <~/other_location/.edgerc> --section <other_section> --policy <policy_name> --rule <'rule_name'> --weights <'start_weight_value,end_weight_value'> --activate <staging|production>
```
