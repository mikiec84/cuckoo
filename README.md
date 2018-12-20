# cuckoo
Implementation of the cuckoo filter


### Compiling

Run `make` in the root folder then run `cuckoo`

### Running unit tests

Run `make test` in the root folder then run `test`


### Generating input data

Run `make gen` to compile the KMer Generator.
Use the Generator to create input files of either random k-mers or k-mers extracted from a file.
#### Usage:
`./kmergen <len> <iterations> <outputFile> <type> [inputFile]`
<type> is 'gen' (for generating random k-mers) or 'ext' (for extraction from [inputFile])
  
#### Example:
`./kmergen 20 1000000 input.txt gen`
This generates one million random 20-mers and writes them to input.txt.


### Running performance analysis

Run `make bench` to create the benchmark program.
#### Usage:
`./benchmark <for_insertion> <non_existing_for_FP>`

The first argument is the file containing k-mers for insertion into the Cuckoo filter. One k-mer per line, lines must be separated by the newline character.
The second argument are k-mers that are not found in the first file. These k-mers are used to check for false positives. The format of the file is the same as the first one.
