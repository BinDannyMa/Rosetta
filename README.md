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







# Questions After

- what is Relax:
~~~
Relax is the main protocol for relaxing a structure in Rosetta; it samples conformations of a given structure close to it in 3D space to find the lowest-scoring variant, running both the packer and minimizer alternately. This is usually done to enable an apples-to-apples comparison between disparate structures, including crystal structures and the output of Rosetta' sampling protocols, by first minimizing them in local space according to the same score function. It is therefore advisable to run relax on any structure you intend to compare to each other.
~~~
- constraints Tutorial
~~~
Some biological or functioanl considerations may not be relfected within a PDB file or evaluated by normal score functions. Constraints are a general way of scoring how well a structure adheres to these additional considerations; for example, one might wish to relax a structure with constraints in place to ensure that suspected disulfides are maintained. It work in the following ways:
1. Some measure is calculated in a given conformation
2. There is a suitable function that describes which values are good and which ones are bad, e.g. the ideal bond length could be the minimum of a parabolic function(harmonic potential). By evaluating the function for the measuresd value, a penalty is calculated. For the harmonic potential, the penalty increases the further away the measured bond length is from the ideal length.
3. This penalty is multiplied by a weighting factor and added to the energy.
~~~







