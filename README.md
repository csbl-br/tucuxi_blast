# Tucuxi-BLAST [v.0.0.5]

Tucuxi-BLAST is a Python-based module for free Record Linkage. 

Our approach was built to convert alphanumerical data to *in silico* DNA sequences, that in turn, can be used as an input to many bioinformatics tools.


### Data example:
Note: `git-lfs` is required for downloading with the `clone`. [Install](https://github.com/git-lfs/git-lfs/wiki/Installation#debian-and-ubuntu)

Or you can download it directly `zip`: [Here](https://drive.google.com/file/d/1jXIAu4Wtx7HzgabNelu4xON1zKp5wmmR/view?usp=sharing)
```
git clone https://github.com/jdeney/tucuxi_blast.git
cd tucuxi_blast/
```
Data source: `/data/`

Tucuxi-BLAST run example:
```
./tucuxi_blast -dl data/testLink_2k.tsv -dr data/testRef_10k.tsv
```
Note: The `testLink2k.tsv` dataset contains 15% of errors attributed to reference to `testRef_10k.tsv` and 50% of the records do not contain pairs in the reference file.

>** -dl -> Database Linkage

>** -dr -> Database Reference

>The results of the record linkage can be checked manually using Tucuxi-Tail tools, available at:: https://tucuxi-tail.csbiology.org/

  * It is important to note that before running Tucuxi-BLAST, the data must be in UPPERCASE and special characters such as #$%&*' removed from your data. Use the Tucuxi-CleanData package:
```
./tucuxi_cleanData -d your-data
```

The results of the analysis are available in the repository: tucuxi_blast/directoryFileInput.

* For more options:
```
./tucuxi_blast -h
```

Tucuxi-Black-White
----------
Tucuxi-BW is a Python-based module to remove duplicated data.
```
./tucuxi_bw -d dataDuplicated.tsv -pid 97.5 -pcov 99.0
```

>** -pid  -> Percentage of identical matches [default = 97.5]

>** -pcov -> Percentage Query Coverage Per Subject [default = 99.0]

* For more options:
```
./tucuxi_bw -h
```

Tucuxi-Clean Data
----------
Tucuxi-Clean Data is a module for properly cleaning data.

This module are able to rapidly convert all characters to upper case and remove special characters. 
```
./tucuxi_cleanData -d your-data
```
* For more options:
```
./tucuxi_cleanData -h
```

Tucuxi-Index
----------
Tucuxi-Index is a module for index creation. For comparisons of multiple databases, this process avoids creating an index when using the same database as a reference, speeding up the process.

```
./tucuxi_index -d your-data
```

* For more options:
```
./tucuxi_index -h
```

### Data availability:
The simulated datasets containing 300M (subject) and 200M (query) are publicly available [Here](https://drive.google.com/drive/folders/1CiNnt3mNBLFxLB56KhNj1SqdaFa5LTSK?usp=sharing). 

Note: The `SINAN databases` are under ethical policies and should not be available.


Tools in use:
-------------
1. Tucuxi-BLAST: BLASTn [v. 2.10.0+]. Altschul SF, Gish W, Miller W, Myers EW, Lipman DJ. Basic local alignment search tool. J Mol Biol. 1990 Oct 5;215(3):403-10. doi: 10.1016/S0022-2836(05)80360-2. PMID: 2231712. Blast+/NCBI algorithm [GPL License](https://www.gnu.org/licenses/gpl-3.0.en.html). For more information [see Blast+/NCBI](https://blast.ncbi.nlm.nih.gov/) 

2. Clustering in Tucuxi-BW: VSEARCH [v. 2.15.2]. Rognes T, Flouri T, Nichols B, Quince C, Mahé F. VSEARCH: a versatile open source tool for metagenomics. PeerJ. 2016 Oct 18;4:e2584. doi: 10.7717/peerj.2584. PMID: 27781170; PMCID: PMC5075697. Vsearch algorithm [GPL License](https://www.gnu.org/licenses/gpl-3.0.en.html). For more information [see Vsearch](https://github.com/torognes/vsearch)
