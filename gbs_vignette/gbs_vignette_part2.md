# GBS vignette part 2

## aligning RADseq data to the reference genome

We will be using the program bwa to perform reference-based alignment of our sequencing data to our reference genome. Please carefully read the `bwa` [manual page](http://bio-bwa.sourceforge.net/bwa.shtml) before moving forward. Pay particular attention to the `index`, `aln`, and `samse` commands and their associated options.

To access bwa commands on Tom’s server, we will have to load the `bwa` module. You can view available program modules using:

      $ module avail

We will be using version 0.7.8. To load the `bwa` module, type:

      $ module load bwa/0.7.8

We will first use the `index` command to create an index of the sequences found in our reference genome:

      $ bwa index -p aries_ref -a bwtsw aries_genome.fa

This command will likely take a long time, so you may want to put the job in the background so you can do other things. To stop the job, type control-Z at the same time. To restart the job in the background, type:

      $ bg

You can visually monitor the progress of your job using the Unix command `top`. To exit the top window, simply type `q` (just like exiting a `less` window).

What files were produced from the index command? Next, we will be using a Perl wrapper (run_bwa.pl) to perform the `aln` and `samse` commands of `bwa`. Carefully inspect this file and interpret what each line is doing. Pay close attention to the different options employed for each command. What input do you need to give this file for it to be able to work? Use the run_bwa.pl script to perform the reference-based alignment (you will likely want to place this job in the background as well). At the start of the second week, we will use Unix and Perl to assess the quality of our assembly.

You can learn a lot about the format of SAM files at the [SAMtools documentation page](https://samtools.github.io/hts-specs/SAMv1.pdf).

