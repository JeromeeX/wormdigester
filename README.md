## Description
**WormDigester** is an *C. elegans* genomic DNA digestion *in silico* simulator. With an input as one or two endonucleases from the *[common enzyme pool](#Common-enzyme-pool)*, WormDigester can generate two figures.\
\
In the first figure, the length distribution of digested fragments would be illustrated with $\lg$(fragment count) as *y*-axis and fragment length as *x*-axis, the dashed lines indicate the proportion of fragments shorter than indicated length in the whole genome (e.g., 95% dashed line indicated that 95% of the genome is composed of fragments to the left of the dashed line).\
\
In the second figure, size selection with [SRE XS](https://www.circulomics.com/store/SRE-XS-kit-p480688541) or [SRE](https://www.circulomics.com/store/SRE-kit-p480686536) is conducted and the proportion of intact extrachromosomal array fragments in the size-selected DNA was illustrated. The cutoff size of SRE XS was assumed to be 3 kb and SRE 10 kb based on pre-tests (unpublished), and extrachromosomal array was assumed to be intact after digestion since it was designed to lack restriction sites, the array fragments are supposed to have an average size of 17 kb and total length of 5 Mb after [genomic DNA extraction](https://international.neb.com/products/t3010-monarch-genomic-dna-purification-kit#Product%20Information_Product%20Notes).

## Common enzyme pool
Including AflII, ApaI, ApaLI, BamHI-HF, BglII, BsmAI, DpnI, DraI, EagI-HF, EcoRI-HF, EcoRV-HF, HindIII-HF, HpaII, KpnI-HF, MboI, NaeI, NcoI, NdeI, NheI, PmlI, PstI-HF, PvuII, SacI-HF, SacII, SalI-HF, SapI, XbaI, XhoI.\
\
Restriction sites are indicated in **lab_enzymes.fa**.

## Acknowledgement
[N2 genomic data](https://www.dropbox.com/scl/fi/tf16pu1pp9no8u83d6nsj/genome.fa?rlkey=mqsyk6w31gf6s85cd38g8x5rq&dl=0) was adapted from [WormBase](https://downloads.wormbase.org/species/c_elegans/PRJNA13758/sequence/genomic/), of which the whole length is 100286394 bases. The size of extrachromosomal array is estimated to be 5 Mb [(El Mouridi et al., 2022)](http://dx.doi.org/10.1093/g3journal/jkac184). Please put the genomic data in the subdirectory folder before running the **wormdigester.ipynb**.