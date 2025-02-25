---
title: BioJava:CookBook:Phylo:Overview
permalink: wiki/BioJava%3ACookBook%3APhylo%3AOverview
---

The biojava3-phylo module provides a biojava3 interface layer to the
forester phylogenomics library for constructing phylogenetic trees found
at <https://code.google.com/p/forester/wiki/forester>. The forester
library is used by Archaeopteryx application which provides a full
featured java application for doing phylogenetics. In the future we may
add additional helper classes to make integration of biojava3 a little
easier as forester jar file is primarily designed to be used from
command line where input and output are files. The following is an
example of taking a BioJava3 MultipleSequenceAlignment and constructing
a Neighbor Joining tree using Percent Identity Difference to calculate
the Distance Matrix between all sequences.

```java

`           TreeConstructor`<ProteinSequence, AminoAcidCompound>` treeConstructor = new TreeConstructor`<ProteinSequence, AminoAcidCompound>`(multipleSequenceAlignment, TreeType.NJ, TreeConstructionAlgorithm.PID, new ProgessListenerStub());`  
`           treeConstructor.process();`  
`           String newick = treeConstructor.getNewickString(true, true);`

```

The TreeConstructor class is a Biojava3 class that handles the
complexity of using the forester library and serves as a convenience
class.
