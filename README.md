## Environment
Python 3, `pandas`, `matplotlib`, and `numpy` are required.

## Getting Started
1. Clone the Git repository to your computer, download the [N2 genomic data](https://www.dropbox.com/scl/fi/tf16pu1pp9no8u83d6nsj/genome.fa?rlkey=mqsyk6w31gf6s85cd38g8x5rq&dl=0) (reformatted from [PRJNA13758](https://downloads.wormbase.org/species/c_elegans/PRJNA13758/sequence/genomic/)) and put the downloaded genome file to the parent folder.
2. Run wormdigester.ipynb and generate your results by following the annotated instructions.

## Overview
WormDigester is a versatile program that simulates genomic DNA digestion of an N2 *C. elegans* strain and provides preliminary theoretical data for targeted sequencing of arrays in *C. elegans*. The strain is assumed to have a 5-Mb array [(El Mouridi et al., 2022)](http://dx.doi.org/10.1093/g3journal/jkac184) where the restriction sites of one or two certain endonucleases (e.g., *Eco*RI-HF and *Hin*dIII-HF) are absent, thus the array will remain undigested during the digestion. After digestion, size selection is conducted to remove all the fragments shorter than the cutoff size with either [SRE XS](https://www.circulomics.com/store/SRE-XS-kit-p480688541) or [SRE](https://www.circulomics.com/store/SRE-kit-p480686536) kits (the SRE XS cutoff size is assumed to be 3 kb and SRE 10 kb). This program is used for:

1. Generating the result of **genomic DNA** digestion by one or two endonucleases (annotated as **figure 1**).
2. Generating the comparison of **array fragment percentage in size-selected DNA** inbetween unselected, SRE XS selected, and SRE selected DNA (annotated as **figure 2**).

By depleting shredded gDNA fragments while keeping the array undigested, size selection can enrich array DNA and contribute to a potential strategy in targeted sequencing of array.

### General usage
You can check the enzyme list by running the following code:
```python
print(enzymes) # Generating a list that includes all the available endonucleases
```

To generate **figure 1**:
```python
fig1(zyme1, zyme2) # Replace zyme1 and zyme2 by endonucleases in the enzyme list generated above
```

To generate **figure 2**:
```python
fig2(zyme1, zyme2) # Replace zyme1 and zyme2 by endonucleases in the enzyme list generated above
```

Examples have been included in the repository.

### Enzymes
The existing enzyme list included AflII, ApaI, ApaLI, BamHI-HF, BglII, BsmAI, DpnI, DraI, EagI-HF, EcoRI-HF, EcoRV-HF, HindIII-HF, HpaII, KpnI-HF, MboI, NaeI, NcoI, NdeI, NheI, PmlI, PstI-HF, PvuII, SacI-HF, SacII, SalI-HF, SapI, XbaI, and XhoI. The restriction sites are recorded in **lab_enzymes.fa**, to append the enzyme list, you can add the enzyme information to **lab_enzymes.fa** in this form:
```python
>New enzyme         # Replace with enzyme name here, e.g., SgbI
restriction site    # Replace with restriction site here in ALL CAPITAL, e.g., ATGCTATC
```