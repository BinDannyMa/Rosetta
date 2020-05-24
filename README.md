# Rosetta
## Getting Started
### Download Rosetta

- Go to the website, and find the software download. The source plus binaries is favored.
  >Rosetta 3.12 source + binaries for Mac - as one bundle (14G)

- Unfold the .tar

### Input and Output

The pdb files directly downloaded from rcsb usually needs to be modified to be suited in the Rosetta.

1. Relax the structure from rcsb:

>/Users/mabin/Documents/rosetta_bin_mac_2019.35.60890_bundle/main/source/bin/relax.static.macosclangrelease -in:file:s input_files/from_rcsb/1qys.pdb @flag_input_relax


-
>/Users/mabin/Documents/rosetta_bin_mac_2019.35.60890_bundle/main/source/bin/relax.static.macosclangrelease 

this line finds the binary excutable in Rosetta which we use to relax the structure.





