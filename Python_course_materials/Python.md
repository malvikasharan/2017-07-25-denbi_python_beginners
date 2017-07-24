# Python

Count the number of occurances of each feature (gene) in the gff file from
Shell script part. If you do not have the file plese download it.

```
wget ftp://ftp.ncbi.nlm.nih.gov/genomes/archive/old_refseq/Bacteria/\
Salmonella_enterica_serovar_Typhimurium_SL1344_uid86645/\
NC_016810.gff
```

Open a file called `count_features.py`


```
wget ftp://ftp.ncbi.nlm.nih.gov/genomes/archive/old_refseq/Bacteria/\
Salmonella_enterica_serovar_Typhimurium_SL1344_uid86645/\
NC_016810.gff
```

```
import sys
import defaultdict

feature_counter = defaultdict(int)
for line in open(sys.argv[1]):
    feature_counter[line.split()[2]] +=1

for feature, counting in feature_counter.items():
   print(feature, counting)
```

```
$ count_features.py NC_016810.gff
```