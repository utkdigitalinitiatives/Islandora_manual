# Basic Solr Config Test #

#### What is this test? ####
We will add a new field to the Solr index using the `basic-solr-config/islandora_tranforms/slurp_all_MODS_to_solr.xslt`. 

#### What is this going to test? ####
The field is added and populated with the correct values in the Solr index.

#### Technology requirements: ####
* Web browser
* Terminal(s)
* Text editor

#### Test environment requirements: ####
[Islandora Vagrant](https://github.com/Islandora-Labs/islandora_vagrant)

#### Test input requirements: ####
```terminal
./This repo/
├── modules
│   └── tests
│       └── test_files
│           └── basic-solr-config-test.zip
```

#### Test possibilities & Step-by-step Replication ####
1. Start your Islandora Vagrant; e.g.
````terminal
$ cd path/to/your/islandora_vagrant
$ vagrant up
````
2. After the virtual machine has started, `vagrant ssh` into the box.
#### Test Failure(s): Deliberate & Otherwise ####