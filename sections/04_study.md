## How is deep learning used to study basic biological processes in a manner that may provide future insights into human disease?

*The (awkward) placeholder section title is intended to help define the scope.
We do not want this section to become a miscellaneous collection of everything
that does not fit in Categorize and Treat.*

*One proposal is that we organize this roughly by what is being predicted,
which will generally correspond to the types of data being used.  For each
sub-section we can quickly introduce the prediction problem and cite some
examples of the relevance to disease.  Hypothetically, if we had an algorithm
that produced perfect predictions on the task, what would we learn and how
could those predictions be used?*

*Existing reviews could be mentioned briefly.*

*It may not fit here, but there could be a general discussion of why different
neural network architectures are particularly well-suited for different types
of input data.  For example, CNNs and RNNs for 1-dimensional data are used
in several categories below.*

*A few suggestions for sub-sections follow.  Some of these could be left out
because our goal is not an exhaustive enumeration of methods.  Some
are important areas of biology, but there may not be much deep learning-
specific content to present.  Others may be important areas where we lack
expertise, in which case we may acknowledge the application area but not
dive into merits or weaknesses of individual methods.*

### Gene expression

*Predicting gene expression levels and unsupervised approaches for learning
from gene expression.  Those could be divided into separate sub-sections.*

### Splicing

*A separate section from general gene expression section above.*

### Transcription factors and RNA-binding proteins

*Existing reviews have covered some of these papers rather well and we do not
want to repeat what has already been well-stated elsewhere.  This could
be split into two sub-sections or kept very brief.*

### Promoters, enhancers, and related epigenomic tasks

*We may want to be selective about what we discuss and not list every
application in this area.*

### Micro-RNA binding

*miRNAs are important biologically, but have neural networks produced anything
particularly notable in this area?*

### Protein secondary and tertiary structure

*Jinbo Xu is writing this*

### Signaling

*There is not much content here.  Can [@tag:Chen2015_trans_species] be covered
elsewhere?*

### Morphological phenotypes

A field poised for dramatic revolution by deep learning is
bioimage analysis.
Thus far, the primary use of deep learning for biological
images has been for segmentation - that is, for the identification
of biologically relevant structures in images such as nuclei,
infected cells, or vasculature, in fluorescence or even brightfield
channels [@doi:10.1371/journal.pcbi.1005177]. Once so-called regions of
interest have been identified, it is often straightforward
to measure biological properties of interest, such as fluorescence
intensities, textures, and sizes. Given the dramatic successes of
deep learning in biological imaging, we simply refer to articles that
review recent advancements [@doi:10.3109/10409238.2015.1135868
@doi:10.1371/journal.pcbi.1005177 @doi:10.1007/978-3-319-24574-4_28].
We believe deep learning will become a commonplace tool for
biological image segmentation once user-friendly tools exist.

We anticipate an additional kind of paradigm shift in bioimaging that
will be brought about by deep learning: what if images of biological
samples, from simple cell cultures to three-dimensional organoids and
tissue samples, could be mined for much more extensive biologically
meaningful information than is currently standard? In biomedical research,
by far the most common paradigm is for biologists to decide in advance
what feature to measure in images from their assay system. But images
of cells contain a wide variety of quantitative information, and deep
learning may just be the tool to extract it. Although classical methods
of segmentation and feature extraction can produce hundreds of metrics
per cell in an image, deep learning is unconstrained by human intuition
and can in theory extract more subtle features. Already, there is evidence
deep learning can surpass the efficacy of classical methods
[@doi:10.1101/081364], even using generic deep convolutional networks
trained on natural images [@doi:10.1101/085118], known as transfer learning.

The impact of further improvements on biomedicine could be enormous.
Comparing cell population
morphologies using conventional methods of segmentation and feature
extraction has already proven useful for functionally annotating genes
and alleles, identifying the cellular target of small molecules, and
identifying disease-specific phenotypes suitable for drug screening
[@doi:10.1016/j.copbio.2016.04.003 @doi:10.1002/cyto.a.22909
@doi:10.1083/jcb.201610026].
Deep learning would bring to these new kinds of experiments - known
as image-based profiling or morphological profiling - a higher degree of
accuracy, stemming from the freedom from human-tuned feature extraction
strategies.

`TODO: Make sure that at the end we clearly emphasize our excitement around
unsupervised uses.`

### Single-cell

*There are not many neural network papers in this area (yet), unless we count
imaging applications.  But there is still plenty to discuss.  The existing
methods [@tag:Arvaniti2016_rare_subsets @tag:Angermueller2016_single_methyl]
use interesting network architectures to approach single-cell data.
[@tag:Shaham2016_batch_effects] could fit here.*

### Metagenomics

**TODO: Add reference tags to this section**
Metagenomics (which refers to the study of genetic material, 16S rRNA 
and/or whole-genome shotgun DNA, from microbial communities) has 
revolutionized the study of micro-scale ecosystems within us and around us. 
There is increasing literature of applying machine learning in general to 
metagenomic analysis.  In the late 2000’s, a plethora of machine learning 
methods were applied to classifying DNA sequencing reads to the thousands of 
species within a sample.  An important problem is genome assembly from these 
mixed-organism samples. And to do that, the organisms should be “binned” 
before assembling.  Binning methods began with many k-mer techniques [refs] 
and then delved into other clustering algorithms, such as self-organizing maps 
(SOM).  Then came the taxonomic classification problem,  with researchers 
naturally using BLAST [blast], followed by other machine learning techniques 
such as SVMs [McHardy], naive Bayesian classifiers [nbc], etc. to classify 
each read.  Then, researchers began to use techniques that could be used to 
estimate relative abundances of an entire sample, instead of the precise but
painstakingly slow read-by-read classification.  Relative abundance
estimators (a.k.a diversity profilers) are MetaPhlan[ref], (WGS)Quikr[ref],
and some configurations of tools like OneCodex[ref] and LMAT[ref].  While one
cannot identify which reads were mapped back to an organism using relative
abundance estimators, they can be useful for faster comparative and other
downstream analyses.   Newer methods hope to classify reads and estimate
relative abundances at faster rates [Vervier] and as of this writing, there
are more than 70 metagenomic taxonomic classifiers in existence.  Besides
binning and classification of species, there is functional identification and
annotation of sequence reads [Yok,Soueidan]. However, the focus on
taxonomic/functional annotation is just the first step.  Once organisms are
identified, there is the interest in understanding the interrelationship
between these organisms and host/environment phenotypes [Guetterman].  One of
the first attempts was a survey of supervised classification methods for
microbes->phenotype classification [Knights], followed by similar studies
that are more massive in scale [Stratnikov, Segata].  There have been
techniques that bypass the taxonomic classification step altogether [ Ding et al]
, (sequence composition to phenotype classification).  Also, researchers have
looked into how feature selection can improve classification [Liu, Segata],
and techniques have been proposed that are classifier-independent
[Ditzler,Ditzler].

So, how have neural networks (NNs) been of use?    Most neural networks are being 
used for short sequence->taxa/function classification, where there is a lot of data 
for training (and thus suitable for NNs).  Neural networks have been applied 
successfully to gene annotation (e.g. Orphelia [Hoff] and FragGeneScan [@doi:10.1093/nar/gkq747]), 
which usually has plenty of training examples.  Representations (similar to Word2Vec [ref] in 
natural language processing) for protein family classification has been introduced and classified 
with a skip-gram  neural network [Asgari].  Recurrent neural networks show good performance for 
homology and protein family identification [Hochreiter, Sonderby].  Interestingly, 
Hochreiter, who invented Long Short Term Memory, delved into homology/protein family
classification in 2007, and therefore, deep learning is deeply rooted in
functional classification methods.

One of the first techniques of “de novo” genome binning used self-organizing maps, a 
type of NN [Abe].  Essinger et al. use ART, a neural network algorithm called Adaptive 
Resonance Theory, to cluster similar genomic fragments and showed that it has better 
performance than K-means.  However, other methods based on interpolated Markov models 
[Salzberg] have performed better than these early genome binners.  Also, neural networks 
can be slow, and therefore, have had limited use for reference-based taxonomic 
classification, with TAC-ELM [tac-elm] being the only NN-based algorithm to taxonomically 
classify massive amounts of metagenomic data.  Also, neural networks can fail to perform 
if there are not enough training examples, which is the case with taxonomic classification 
(since only ~10% of estimated species have been sequenced).   An initial study shows that 
deep neural networks have been successfully applied to  taxonomic classification of 16S rRNA genes,
with convolutional networks  provide about 10% accuracy genus-level improvement over RNNs and even random 
forests [Mrzelj].  However, this study performed 10-fold cross-validation on 3000 sequences in total. 

Due to the traditionally small numbers of metagenomic samples in studies, neural network uses for 
classifying phenotype from microbial composition are just beginning.   A standard MLP 
was able to classify wound severity from microbial species present in the wound [Kizek,
2015].  Recently, multi-layer, recurrent networks (and convolutional
networks) have been applied to microbiome genotype-phenotype, with Ditzler et
al. being the first to associate soil samples with pH level using multi-layer
perceptrons, deep-belief networks, and recursive neural networks (RNNs) 
[Ditzler] .  Besides classifying the samples appropriately, Ditzler shows
that internal phylogenetic tree nodes inferred by the networks are
appropriate features representing low/high pH, which can provide additional
useful information and new features for future metagenomic sample comparison.
 Also, an initial study has show promise of these networks for diagnosing
disease [Faruqi].  

There are still a lot of challenges with applying deep neural networks to metagenomics problems.  They are not ideal for microbial/functional composition->phenotype classification because most studies contain tens of samples (~20->40) and
hundreds/thousands of features (aka species).  Such underdetermined/ill-conditioned problems
are still a challenge for deep neural networks that require many more training examples than 
features to sufficiently converge the weights on the hidden layers.  Also, due to convergence issues 
(slowness and instability due to large neural networks modeling very large datasets [arxiv:1212.0901v2]), 
taxonomic classification of reads from whole genome sequencing seems out of reach at the moment for deep neural 
networks -- due to only thousands of full-sequenced genomes as compared to hundreds of thousands of 16S rRNA sequences 
available for training.

However, because recurrent neural networks are showing success for base-calling (and thus removing the large error in 
the measurement of a pore's current signal) for the relatively new Oxford Nanopore sequencer [Boza], there is hope that
the process of denoising->organism/function classification can be combined into one step in using powerful LSTM's.  LSTM's
are working miracles in raw speech signal->meaning translation [ref], and combining steps in metagenomics are not out of the 
question.  For example, metagenomic assembly usually requires binning then assembly, but could deep neural nets accomplish
both tasks in one network?  Does functional/taxonomic classification need to be separate processes?  The largest potential
in deep learning is to learn "everything" in one complex network, with a plethora of labeled (reference) data and unlabeled 
(microbiome experiments) examples.

### Sequencing and variant calling

*We have one nanopore paper in the issues and very recent work on variant calling
that looks worthy of inclusion.*
