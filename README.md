# Bioinformatics curriculum
This document is an incomplete list of suitable topics to study to learn the basics of DNA sequencing-based bioinformatics.

## Learn to work on the Linux command line
As most bioinformatics tools are written to run in a Linux environment it is important to learn how to work on the command line. 
In addition, accessing high-performance computer resources is also normally done via a terminal interface. 
There is a lot to learn, but after learning the 20 or so most used commands you can start to be productive on the command line! 

- Basic file handling and navigation: `ls`, `cd`, `mkdir`, `cp`, `mv`, `rm`, `cat`, `less`/`more`, `chmod`, etc...
- At least one terminal editor: `nano`, `emacs`, `vim`
- Learn to use terminal multiplexers: `screen` or preferably `tmux`
- Advanced tools: 
  - Pipes, output redirection (`<`, `>`, `stdout`, and `stderr`)  
  - Shell scripts
  - Regular expressions in `grep`, `sed`, `awk`...
  - Non-standard power tools, e.g. GNU `parallel`, Ebay's `tsv-utils`, etc.
- Learn to work remotely over SSH
- Connect to remote computers
	- Transfer files to/from remote computer using command line interface, e.g. `scp`, `sftp`, `rsync`, `lftp`
	- Work on shared cluster systems with job submission systems (e.g. [Slurm](http://www.uppmax.uu.se/support/user-guides/slurm-user-guide/) on [UPPMAX](https://www.uppmax.uu.se/))

### Linux books:
- [The Linux Command Line](https://nostarch.com/tlcl)
- [Bash Pocket Reference](http://shop.oreilly.com/product/0636920010166.do)
- [Linux, MacOs, Windows and more command line reference](https://ss64.com/) - Nothing extra

## Programming
Knowing basic programming is essential for a bioinformatician. Programming is often used to handle input and output files, pre-process data files, create plots, create workflows that run several different tools in a specified order. A well-constructed bioinformatics data analysis is **reproducible**, meaning that any one can run the same analysis on a different computer using the same input files to produce the same output results. This is challenging in practice, but it is important to consider all scripts that are written in the course of a bioinformatics analysis project as the "log book" or "lab book" of how the analysis was actually performed. And while it can be rewarding to do a quick analysis of some output files at the command line, you should make it a habit to always include everything you do to the data in a script that you can come back to in the future when you have forgotten exactly what you did. 

### Version control systems
There are several revision control systems that one can use to maintain a versioned history of for example program code. The most popular version control system in widespread use today is [Git](https://git-scm.com/). Three common places to publish code are [Github](https://github.com/), [Gitlab](https://about.gitlab.com/), and [Bitbucket](https://bitbucket.org/). They all work pretty much the same. 

There are some very good guides and tutorials listed below that will introduce you to the vocabulary and concepts concerning version control. Version control rocks(!) and is a crucial tool in a bioinformatician's tool belt, so take the opportunity to learn it as soon as possible. When you start writing code, you will eventually encounter a situation where you want to make changes to the code, but without losing the older version (that you know worked). Version control makes it possible to go back in time to older versions of the code, without having to mess with copies of files called `my_code_version-20181015_final_final2.py`. It will make your life so much easier and you will enjoy it!

#### Tutorials 
Here are some nice introductions to version control:
- [git - the simple guide](http://rogerdudler.github.io/git-guide/)
- [Github resources for learning git](http://try.github.io/)
- Blog post: [A visual guide to version control](https://betterexplained.com/articles/a-visual-guide-to-version-control/)
- Blog post: [Source control for scientists and soloists](http://tonysyu.github.io/source-control-for-scientists-and-soloists.html#.W81r_i3njTY)
- Online tutorial: [Atlassian Git tutorials and introduction to workflows](https://www.atlassian.com/git/tutorials)

#### Academic accounts on GitHub
GitHub has some nice resources for research/education. Check out their [education portal](https://education.github.com/)! You can also get a free researcher account that enables unlimited free private repositories.

### Python
Python is the most common (and in my opinion most easy to learn) programming language. It is typically available on all Linux systems. Some resources for learning about Python in general:

- https://automatetheboringstuff.com/
- http://rosalind.info (specifically "Python Village", but then later also "Bioinformatics Stronghold")

There was  a big debate a couple of years ago about which version of Python to learn. That discussion is no longer valid: you should learn Python 3 (start by installing the latest available version (3.6+)). There are several ways to download and install Python, but I recommend learning to use [conda](https://conda.io). There is a conda [getting started guide](https://conda.io/docs/user-guide/getting-started.html) that is OK, after you are familiar with the command line. 

Unfortunately, there are no de facto standard integrated development environments (IDEs) for Python like there is for R (i.e. RStudio, see more below). The most common alternatives are probably Microsofts' [Visual Studio Code](https://code.visualstudio.com/) and JetBrain's [PyCharm](https://www.jetbrains.com/pycharm/), both are great and cross-platform. VS Code is free for everyone, and a free community edition (without professional support) is available for PyCharm. An other important Python programming tool you should learn is [Jupyter](http://jupyter.org/). It is a tool to work with interactive programming notebooks where you can combine blocks of [Markdown](https://daringfireball.net/projects/markdown/syntax) formatted notes with individually executable code blocks (with inline plots!). It is actually not specific to Python: it started out as a notebook format for the languages Julia, Python, and R (JuPyteR), but now runs more than a hundred different language kernels. It is often used in bioinformatics analyses and is getting more and more common nowadays as a way to share how analyses and plots were made for scientific papers. 

### R
R is by far the most commonly used language/environment for any type of data analysis that requires statistics. A bioinformatician has to be familiar with R. There is a very good Integrated Development Environment (IDE) available for R: [RStudio](https://www.rstudio.com). Ensure you become familiar with [R](https://www.r-project.org/), [RStudio](https://www.rstudio.com), and [R Markdown](https://rmarkdown.rstudio.com/) (kind of like Jupyter notebooks, but focused on R). 

### Databases
There are several database systems, but the most common are some kind of relational database system (often called SQL databases). There are others, especially NoSQL-databases, that are gaining popularity (MongoDB is a NoSQL database that is seeing some use in bioinformatics applications). A bioinformatician can definitely benefit from learning the basics of SQL and a NoSQL system.

### A word on coding style
Using a consistent coding style is important to ensure code readability (you are going to read your code much more than you write it). Python has a style document called [PEP8](https://www.python.org/dev/peps/pep-0008/) (Python Enhancement Proposal number 8), which is a great starting point for a standard Python coding style. Every Python programmer should read and try their best to follow PEP8 to make it easy for other Python programmers to read and understand your code. In addition, have a look at [The Zen of Python](https://www.python.org/dev/peps/pep-0020/) (i.e. PEP20).

There are style guides for R and SQL as well. A decent style guide for R is explained in the R for Data Science book (see link below).

### Workflows
Workflow managers are tools that help you write reliable and easy-to-use bioinformatics workflows. They make it easy to run several different programs after each other, or sometimes in parallel. This is an advanced bioinformatics topic that will be most useful after you have learnt the basics of programming (in either Python or R) and started using established bioinformatics tools to process your data. 

- [Nextflow](https://www.nextflow.io/), also checkout [nf-core](https://nf-co.re/)
- [Snakemake](https://snakemake.readthedocs.io)


## General data analysis

### General techniques
- Ordination: PCA/PCoA, NMDS, t-SNE, OPLS-DA etc.
- Classification: LDA, Decision trees, Random Forests, SVM, ANN, ROC curves, supervised/un-supervised, etc.
- Clustering: Hierarchical, k-means, etc.
- [GUSTAME](https://mb3is.megx.net/gustame) is a very useful field guide to multivariate statistics  

### Statistics
- Simple hypothesis tests (T-tests, etc.)
- Multiple testing correction: Bonferroni, FDR
- ANOVA
- Regression
- Differential abundance testing
 - Published article: [ANCOM](https://www.tandfonline.com/doi/abs/10.3402/mehd.v26.27663)
 - Official tutorial: [DESeq2](https://bioconductor.org/packages/release/bioc/vignettes/DESeq2/inst/doc/DESeq2.html) (for RNA-seq, but applicable to metagenomics as well)
 - Official user's guide: [edgeR](https://bioconductor.org/packages/release/bioc/vignettes/edgeR/inst/doc/edgeRUsersGuide.pdf)
 - [Build your own differential abundance tool](https://mortonjt.github.io/probable-bug-bytes/probable-bug-bytes/differential-abundance/)

### Python
- Book: [Python for Data Anlysis](http://shop.oreilly.com/product/0636920023784.do)
- Book: [Pthon Data Science Handbook](http://shop.oreilly.com/product/0636920034919.do)
- Blog post: [Greg Reda's Intro to pandas data structures](http://gregreda.com/2013/10/26/intro-to-pandas-data-structures/)
- YouTube channel: [Kevin Markham's pandas video series](https://www.dataschool.io/easier-data-analysis-with-pandas/)
- Package docs: [Pandas' 10 minutes to pandas](http://pandas.pydata.org/pandas-docs/stable/10min.html)
- Package docs: [Seaborn](https://seaborn.pydata.org/tutorial.html)
- Package docs: [Jupyter](https://jupyterlab.readthedocs.io/en/latest/)

### R 
- (Online) book: [R for Data Science](http://r4ds.had.co.nz/) (If you're only going to read one book about R; this is the one!)
- Online course: [Coursera R-programming](https://www.coursera.org/learn/r-programming)
- Online course: [Data Science in a Box](https://datasciencebox.org/)

### Databases
- Online course: [Stanfords Mini-Courses, Practical Relational Databases and SQL]
(https://lagunita.stanford.edu/courses/DB/2014/SelfPaced/about)
- SQL
  - Python documentation: [SQLite3](https://docs.python.org/3/library/sqlite3.html)
  - Online tutorial: [PostgreSQL](http://www.postgresqltutorial.com/)
- NoSQL
  - Official website: [MongoDB](https://www.mongodb.com/)

## Bioinformatics stuff
### General sequencing stuff
- Common file formats:
   - [FASTA](https://en.wikipedia.org/wiki/FASTA_format) / [FASTQ](https://en.wikipedia.org/wiki/FASTQ_format)
   - SAM/BAM (see [Samtools](http://www.htslib.org/)
   - ([Newick](https://en.wikipedia.org/wiki/Newick_format))
- Quality assessment
   - [FastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/)
- Adapter trimming and quality filtering 
  - BBDuk (part of the BBMap suite of tools, see link below)
  - Older, but still commonly used tools: Trimmomatic, FASTX-toolkit, TrimGalore!
- Mapping/aligning reads (maybe also something general on sequence alignment)
  - [Bowtie2](http://bowtie-bio.sourceforge.net/bowtie2/index.shtml)
  - [BWA](http://bio-bwa.sourceforge.net/)
  - [BBMap](https://jgi.doe.gov/data-and-tools/bbtools/bb-tools-user-guide/bbmap-guide/)
  - [BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi)
  - [USEARCH](https://www.drive5.com/usearch/)
  - [VSEARCH](https://github.com/torognes/vsearch)
  - [MiniMap2](https://github.com/lh3/minimap2)
  - [HMMER](http://hmmer.org/) (also read about Profile Hidden Markov Models in this fantastic book (PDF): [Durbin et al. 1998, Biological Sequence Analysis](https://pdfs.semanticscholar.org/2ed5/d6b35f8971fb9d7434a2683922c3bfcc058e.pdf) )
- Assembling reads
  - [MEGAHIT](https://github.com/voutcn/megahit)
  - [SPAdes](http://cab.spbu.ru/software/spades/)
- Phylogenetic trees

### 16S read processing and OTU picking
- [QIIME2](https://qiime2.org/)
- [DADA2](https://benjjneb.github.io/dada2/tutorial.html)
- The [Unoise](http://drive5.com/usearch/) suite
- For functional predictions (use with caution): [PICRUSt](http://picrust.github.io/picrust/) or [Tax4Fun](http://tax4fun.gobics.de/)

### 16S taxonomic annotation
- [RDP](https://rdp.cme.msu.edu/classifier/classifier.jsp)
- [SILVA](https://www.arb-silva.de/aligner/)

### General 16S tools
- QIIME2 (again)
- [Mothur](https://www.mothur.org/)
- [Microbiome analyst](http://www.microbiomeanalyst.ca)
- The [Huttenhower](http://huttenhower.sph.harvard.edu/galaxy/) Galaxy server
- Take a look at [Luisa's review](https://www.frontiersin.org/articles/10.3389/fmicb.2017.01561/full)

### Shotgun metagenomics
- Taxonomic profiling 
  - Using marker genes: [MetaPhlAn2](https://bitbucket.org/biobakery/biobakery/wiki/metaphlan2) and [mOTU](http://www.bork.embl.de/software/mOTU/)
  - Using whole genome references: [Kraken](https://github.com/DerrickWood/kraken2), [Kaiju](http://kaiju.binf.ku.dk/), etc. 
- Functional profiling
  - [HUMANn2](http://huttenhower.sph.harvard.edu/humann2)
  - [SUPERFOCUS](https://github.com/metageni/SUPER-FOCUS)
  - Mapping to gene database (e.g. [IGC](http://meta.genomics.cn/meta/home))
- Metagenome assembly 
  - [MEGAHIT](https://github.com/voutcn/megahit)
- Binning 
  - Binning tools: [CONCOCT](https://concoct.readthedocs.io/en/latest/), [MaxBin](https://sourceforge.net/projects/maxbin/), etc.
  - Check quality of bins: [CheckM](http://ecogenomics.github.io/CheckM/)
- Metagenome-assembled genomes, MAGs

## Online resources for bioinformatics questions
- seqanswers.com
- biostars.com
- SciLifeLab Slack
- [wiki for terminology](http://www.metagenomics.wiki/pdf)
