# Rosetta
(this is the notes, while following the documentation from https://www.rosettacommons.org as a complete new user)
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

this line finds the binary excutable in Rosetta which we use to relax the structure. Different users have a different address for the binary excutables. It is *$where your Rosetta file/main/source/bin/...*

-
>...-in:file:s input_files/from_rcsb/1qys.pdb

**-in:file:s** show is a single pdb file input. The rest shows the input file.

-
>...@flag_input_relax

This is command for flag file. The flag file contains the parameters for the run. The content is shown below:

~~~
-nstruct 2

-relax:constrain_relax_to_start_coords
-relax:ramp_constraints false

-ex1
-ex2

-use_input_sc
-flip_HNQ
-no_optH false

~~~





