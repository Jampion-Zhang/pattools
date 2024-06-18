<img src="docs/image/logo.svg" alt="logo" width="600"/>

[![Documentation](https://img.shields.io/badge/docs-Github_Page-blue?style=flat-square)](https://hcyvan.github.io/pattools/intro.html)
[![Python 3.10](https://img.shields.io/badge/python-3.10+-32cd32)](https://www.python.org/)
[![Development](https://img.shields.io/badge/development-rapid%20progress-orange)](https://github.com/hcyvan/pattools/graphs/commit-activity)
[![Developers](https://img.shields.io/github/contributors/hcyvan/pattools?color=green)](https://github.com/hcyvan/pattools/graphs/contributors)
[![Packagist License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)

## Introduction
Pat format toolkit
<img src="notebook/framework.png" alt="pattools framework" width="500"/>

+ [Pattools Document Website](https://hcyvan.github.io/pattools/intro.html)
+ [Github](https://github.com/hcyvan/pattools)
+ [Open Issues](https://github.com/hcyvan/pattools/issues/)
## Development

1. Create a python 3.10+ environment, you can use conda, virtualenv, docker, etc. Or a local python environment (not
   recommended)
2. Install the project's dependent libraries

```
pip install -r requirements.txt
```

3. *Deprecated* Copy config.yaml.tpl to config.yaml and complete the configuration according to the local environment

## Installation

### Source code

Download the source code and execute the following commands

``` 
cd /path/to/source/code
python ./setup.py install
```

### Install from repository

Note: This project will be synchronized to github in the future and can be installed through the github git url.

#### Install from the master branch

```
pip install git+https://e.coding.net/gomicsgene2/lung_cancer_yixing/pattools.git
```

#### Install from a feature branch

For example: install from dev-xxx branch

```shell
pip install git+https://e.coding.net/gomicsgene2/lung_cancer_yixing/pattools.git@dev-xxx
```

## Usage

### pattools SDK

### pattools toolkit

#### deconv

sun

```
pattools deconv -m sun -g hg38 \
    -c /mnt/d/project/wgbs_tools/references/hg38/CpG.bed.gz \
    -p /mnt/d/data/cacLung/raw/pat/GSM5652289_Blood-T-Eff-CD8-Z0000041F.hg38.pat.gz \
    -o /mnt/d/project/pattools/tmp/out.csv
```

moss

```
pattools deconv -m moss -g hg38 \
    -c /mnt/d/project/wgbs_tools/references/hg38/CpG.bed.gz \
    -p /mnt/d/data/cacLung/raw/pat/GSM5652289_Blood-T-Eff-CD8-Z0000041F.hg38.pat.gz \
    -o /mnt/d/project/pattools/tmp/out.csv
```

loyfer

```
pattools deconv -m loyfer -g hg38 -f Atlas.U25.l4.hg38.tsv\
    -c /mnt/d/project/wgbs_tools/references/hg38/CpG.bed.gz \
    -p /mnt/d/data/cacLung/raw/pat/GSM5652289_Blood-T-Eff-CD8-Z0000041F.hg38.pat.gz \
    -o /mnt/d/project/pattools/tmp/out.csv
```

#### entropy

```
pattools entropy -d 3 -w 4\
    -i /mnt/d/data/cacLung/raw/pat/GSM5652289_Blood-T-Eff-CD8-Z0000041F.hg38.pat.gz \
    -o /mnt/d/project/pattools/tmp/GSM5652289_Blood-T-Eff-CD8-Z0000041F.hg38.entropy
```

#### ratio

```
pattools ratio -d 3\
    -i /mnt/d/data/cacLung/raw/pat/GSM5652289_Blood-T-Eff-CD8-Z0000041F.hg38.pat.gz \
    -o /mnt/d/project/pattools/tmp/GSM5652289_Blood-T-Eff-CD8-Z0000041F.hg38.ratio
```

#### vector

```
pattools vector -i /mnt/d/data/cacLung/raw/pat/GSM5652289_Blood-T-Eff-CD8-Z0000041F.hg38.motif.gz
```

#### vector-multi

This command is used to merge all samples and find different vector

```
pattools vector-multi -i ./tmp/input.list.txt -c /mnt/d/project/wgbs_tools/references/hg38/CpG.bed.gz > ./tmp/ddd.txt
```

#### vector-diff

```
pattools vector-diff -i /mnt/d/data/cacLung/raw/yixing/20240612/merge.motif.gz -g 1
```

#### pat2motif

```
pattools pat2motif -i /mnt/d/data/cacLung/raw/pat/GSM5652289_Blood-T-Eff-CD8-Z0000041F.hg38.pat.gz \
                    -o /mnt/d/data/cacLung/raw/pat/GSM5652289_Blood-T-Eff-CD8-Z0000041F.hg38.motif.gz
```

#### region

This command is used to convert a region between different coordinate systems, such as
genome index coordinates or CpG index coordinates.

```
pattools region -t cpg2genome -i chr1:266762-266762 -c /mnt/d/project/wgbs_tools/references/hg38/CpG.bed.gz
```
## License
Distributed under the MIT License. See [LICENSE](LICENSE) for more information.

## Acknowledgements
+ [wgbstools](https://github.com/nloyfer/wgbs_tools)
+ [pysam](https://github.com/pysam-developers/pysam)
+ [samtools](http://www.htslib.org/)
