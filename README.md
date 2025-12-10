# MI-GRAAL: Matching-based Integrative GRAph ALigner

A matching-based integrative graph alignment algorithm for biological networks.

## Authors

- Oleksii Kuchaiev
- Natasa Przulj

**Corresponding Author:** Prof. Natasa Przulj  
📧 natasa.przulj@mbzuai.ac.ae

## Overview

MI-GRAAL (Matching-based Integrative GRAph ALigner) is an advanced network alignment algorithm that integrates multiple graph matching strategies to align biological networks effectively.

## Resources

### Supplementary Materials

- **[Supplementary Figure 1](http://www0.cs.ucl.ac.uk/staff/natasa/MI-GRAAL/SupplementaryFigure1.png)**
- **[Supplementary File 1](http://www0.cs.ucl.ac.uk/staff/natasa/MI-GRAAL/SupplementaryFile1.xls)**
- **[Supplementary File 2](http://www0.cs.ucl.ac.uk/staff/natasa/MI-GRAAL/SupplementaryFile2.xls)**
- **[Supplementary File 3](http://www0.cs.ucl.ac.uk/staff/natasa/MI-GRAAL/SupplementaryFile3.xls)**
- **[All Supplementary Materials (ZIP)](http://www0.cs.ucl.ac.uk/staff/natasa/MI-GRAAL/ALL_SI.zip)**

*Note: If download links don't work when clicked, copy and paste the URLs directly into your browser's address bar.*

## System Requirements

- **Operating System**: Linux (tested on Gentoo and Mandriva distributions, should work on others)
- **Python**: Required for running MI-GRAAL
- **Network Format**: LEDA `.gw` format

## Installation

```bash
git clone https://github.com/przulj-lab/MI-GRAAL.git
cd MI-GRAAL
chmod +x MI-GRAALRunner.py
```

## Requirements

- Networks in LEDA `.gw` format
- Python installed on your system

### Important Constraint

⚠️ **The number of nodes in the first network must not be greater than the number of nodes in the second network!**

## Usage

### Display Help

```bash
./MI-GRAALRunner.py
```

This will display usage directions and available parameters.

### Basic Command

```bash
./MI-GRAALRunner.py network1.gw network2.gw output_prefix [options]
```

### Sample Usage

Navigate to the MI-GRAAL directory and run:

```bash
./MI-GRAALRunner.py testGraph1.gw testGraph2.gw result -p 3
```

### Parameters

- `network1.gw` - First network file (LEDA format)
- `network2.gw` - Second network file (LEDA format)
- `output_prefix` - Prefix for output alignment files
- `-p` - Number of parallel processes (optional)

## Input File Formats

### Network Format

MI-GRAAL accepts networks in LEDA `.gw` format.

## Converting Edge Lists to LEDA Format

If your network is in edge list format:
```
node1 node2
node3 node4
...
```

Use the provided `list2leda` script (included in `CodeAndTestData.zip`):

```bash
./list2leda edgelist.txt >> graph.gw
```

**Note:** Self-loops, directionality, and double edges will be ignored during conversion.

## Example Workflow

1. **Prepare your networks in edge list format**
2. **Convert to LEDA format**:
   ```bash
   ./list2leda network1_edgelist.txt >> network1.gw
   ./list2leda network2_edgelist.txt >> network2.gw
   ```
3. **Run alignment**:
   ```bash
   ./MI-GRAALRunner.py network1.gw network2.gw alignment_result -p 3
   ```

## Output

MI-GRAAL produces alignment files with the specified output prefix, containing node-to-node mappings between the input networks.

## Related Tools

- **[GRAAL](https://github.com/przulj-lab/GRAAL/)** - GRaph ALigner
- **[C-GRAAL](https://github.com/przulj-lab/C-GRAAL/)** - Common-neighbors-based alignment
- **[L-GRAAL]((https://github.com/przulj-lab/L-GRAAL/)** - Lagrangian-based alignment

## Troubleshooting

### Python Not Found
Ensure Python is installed and in your PATH:
```bash
python --version
```

### Permission Denied
Make the runner script executable:
```bash
chmod +x MI-GRAALRunner.py
```

### Network Size Mismatch
Ensure the first network is smaller than or equal to the second network in size.

## Citation

If you use this code or data in your research, please cite:

```
Oleksii Kuchaiev, Nataša Pržulj
Integrative network alignment reveals large regions of global network similarity in yeast and human
Bioinformatics, Volume 27, Issue 10, May 2011, Pages 1390–1396
https://doi.org/10.1093/bioinformatics/btr127
```

## Contact

For questions or issues, please contact Prof. Natasa Przulj at natasa.przulj@mbzuai.ac.ae
