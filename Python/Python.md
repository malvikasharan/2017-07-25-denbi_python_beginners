# Python

## Motivation (run by the instructor)

This exampale should show you that you can write very powerful tool
with only a few lines of code. In this example we plot the gene length
distribution of *Salmonella* Typhimurium using the gff file we
downloaded for the Unix Shell part. If you do not have the file please
download it again.

```
wget ftp://ftp.ncbi.nlm.nih.gov/genomes/archive/old_refseq/Bacteria/\
Salmonella_enterica_serovar_Typhimurium_SL1344_uid86645/\
NC_016810.gff
```

Run the final version of the Python script
`plot_gff_gene_length_distribution.py` and run it on `NC_016810.gff`.
Then open the resulting file NC_016810.gff_gene_length_distribution.pdf.

## Python basics in a Jupyter notebook

The following topics are taught in a Jupyter notebook

- Print, literal constants
- Variables
- String format operators
- Data structures: str, int, float, list, dict
- File handling
- New lines, tab etc., regular expression
- `if` `else` startement
- `for` loop

## Writing Python scripts

Here we will create the file `plot_gff_gene_length_distribution.py`
from scratch and add successively features.

```
for line in open("NC_016810.gff"):
    print(line)
```

```
python plot_gff_gene_length_distribution.py
```

```
import sys

print(sys.argv)

for line in open("NC_016810.gff"):
    # print(line)
    pass
```

```
python plot_gff_gene_length_distribution.py NC_016810.gff
```

```
['temp.py', 'NC_016810.gff']
```


```
import sys

for line in open(sys.argv[1]):
    print(line)
```

```
import sys

for line in open(sys.argv[1]):
    split_line = line.split()
    print(split_line)
```


```
import sys

for line in open(sys.argv[1]):
    split_line = line.split()
    print(split_line)
    print(split_line[4] - split_line[3])
```

```
['##gff-version', '3']
Traceback (most recent call last):
  File "plot_gff_gene_length_distribution.py", line 5, in <module>
      print(split_line[4] - split_line[3])
      IndexError: list index out of range
```

```
import sys
for line in open(sys.argv[1]):
    if line.startswith("#"):
        continue
    split_line = line.split()
    print(split_line)
    print(split_line[4] - split_line[3])
```

```
[...]
Traceback (most recent call last):
  File "plot_gff_gene_length_distribution.py", line 7, in <module>
      print(split_line[4] - split_line[3])
      TypeError: unsupported operand type(s) for -: 'str' and 'str'
```

```
import sys
for line in open(sys.argv[1]):
    if line.startswith("#"):
        continue
    split_line = line.split()
    print(split_line)
    print(int(split_line[4]) - int(split_line[3]))
```


```
import sys

gene_lengths = []

for line in open(sys.argv[1]):
    if line.startswith("#"):
        continue
    split_line = line.split()
    curr_gene_length = int(split_line[4]) - int(split_line[3])
    gene_lengths.append(curr_gene_length)

print(gene_lengths)
```

```
import sys
import matplotlib
matplotlib.use('Agg')
import matplotlib.pyplot as plt

gene_lengths = []
for line in open(sys.argv[1]):
    if line.startswith("#"):
        continue
    split_line = line.split()
    if split_line[2] == "gene":
        cur_gene_length = int(split_line[4]) - int(split_line[3])
        gene_lengths.append(cur_gene_length)

plt.hist(gene_lengths, bins=100, color="gray")
plt.savefig("{}_gene_length_distribution.pdf".format(sys.argv[1]))
```
