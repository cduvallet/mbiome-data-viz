<!-- .slide: data-background="#3F51B5" class="dark" -->

### Intro to microbiome data visualization

**Claire Duvallet**

Microbiome Hack 2019

Cornell University

Slides: [cduvallet.github.io/mbiome-data-viz](https://cduvallet.github.io/mbiome-data-viz/)

---

<!-- .slide: data-background="#767171" class="dark" -->

### Who am I?

- Former PhD student in Eric Alm's lab at MIT    
- Future data scientist at Biobot Analytics

_almlab.mit.edu | www.biobot.io_

---

<!-- .slide: data-background="#767171" class="dark" -->

### Why this talk?

- Encourage you to dig into your data
- Provide starting examples and tools to continue learning about data viz
- Go through real-world visualizations

---

<!-- .slide: data-background="#767171" class="dark" -->

### 1. Looking at your raw data
### 2. Exploring your processed data
### 3. Visualizing your data

---

<link href="https://afeld.github.io/emoji-css/emoji.css" rel="stylesheet">

## Most important data viz tools:

## :eyes: and <i class="em em-brain"></i>

---

<!-- .slide: data-background="#767171" class="dark" -->

## Looking at your raw data

----

Crucial core concept:

_Most things in bioinformatics are text files_

:spiral_note_pad:

----

<img src="img/twitter_parsing_txt.png" width="80%">

Note: https://twitter.com/popgengoogling/status/1108372032339800064

----

**DNA sequences**: fasta or fastq    

**OTU tables**: tab- or comma-delimited    
_biom files are text files too_

**QIIME 2 artifacts**: zip files containing text files     
`unzip artifact.qza`

----

`less` is your friend!

<insert gif of using less>

\*_`grep` is also great_

----

Many specialized tools and scripts to interact with raw data:

* QIIME 2 View
* FastQC
* Scott's `caravan` scripts: [github.com/swo/caravan/tools](https://github.com/swo/caravan/tree/master/tools)

_But just looking at the raw files gets you ~90% of the way_

---

<!-- .slide: data-background="#767171" class="dark" -->

### ~~1. Looking at your raw data~~
### 2. Exploring your processed data
### 3. Visualizing your data

---

<!-- .slide: data-background="#767171" class="dark" -->

<link href="https://afeld.github.io/emoji-css/emoji.css" rel="stylesheet">

## Exploring your data

1. Good sanity checks
2. Basic microbiome analyses
3. Using your <i class="em em-brain"></i>

----

<!-- .slide: data-background="#767171" class="dark" -->

## Good sanity checks

Know and trust your data before you start!

----

* All your samples are there?
* Reads per sample
* Reads per OTU
* Does it look like a stool sample?

Note: also can use diversity as a proxy for things that went really bad. i.e. if you only see one bug, prob a contaminant.

----

Stool samples should have at least ~10,000 reads each

<img src="img/reads-per-sample.png">

----

OTUs are usually very sparse

<img src="img/otu-distribution.png" width="50%">

---

<!-- .slide: data-background="#767171" class="dark" -->

<link href="https://afeld.github.io/emoji-css/emoji.css" rel="stylesheet">

## Exploring your data

1. ~~Good sanity checks~~
2. Basic microbiome analyses
3. Using your <i class="em em-brain"></i>

----

<!-- .slide: data-background="#767171" class="dark" -->

## Basic microbiome analyses

Good places to start (but not usually to finish)

Note: we'll be thinking through ways to visualize these later, so keep it in mind.

----

### Alpha diversity

_How diverse is the community in each sample?_

<img src="img/alpha-diversity.png">

----

### Beta diversity & PCA

_How different are all the samples from each other?_

<img src="img/beta-diversity.png">

----

### Differential abundance

_Are any taxa differently abundant between condition A and B?_

<img src="img/diff-abun.png" width="60%">

----

### Differential abundance

### \*and variability

<img src="img/corncob-ex.png" width="80%">

 _Martin, Witten, and Willis (2019)._

 _http://arxiv.org/abs/1902.02776_

----

### Correlation with a metadata variable

_Is BMI correlated with abundance of taxa X?_

_Is alpha diversity correlated with age?_

<img src="img/correlation-ex.png" width="35%">

Note: fun game: http://guessthecorrelation.com/

----

Always look at the raw data!

<img src="img/different-correlations.png">

Note: source is https://github.com/janhove/cannonball

----

### Correlation between taxa

_Is taxa X correlated with taxa Y?_

<img src="img/spiec-easy.png" width="70%">

_Be careful of compositional effects! Use methods like SparCC or SPIEC-EASY._

----

### Prediction

_Can the microbiome predict a certain metadata variable?_

<img src="img/confusion-matrix.png" width="80%">

---

<!-- .slide: data-background="#767171" class="dark" -->

<link href="https://afeld.github.io/emoji-css/emoji.css" rel="stylesheet">

## Exploring your data

1. ~~Good sanity checks~~
2. ~~Basic microbiome analyses~~
3. Using your <i class="em em-brain"></i>

----

<!-- .slide: data-background="#767171" class="dark" -->

<link href="https://afeld.github.io/emoji-css/emoji.css" rel="stylesheet">

## Don't forget to use your <i class="em em-brain"></i>!

Data exploration can lead to new hypotheses

----

### Examples from lung, throat, and stomach microbiome dataset

#1. Lung data: where to put your sample read cutoff?

<img src="img/lung-reads-per-sample.png" width="60%">

Duvallet et al, _bioRxiv_ (2019)

Note: Lung example (where are you gonna put your reads cutoff? can't just use same values as for poop)

----

#2. Attempt to define "stomach" bacteria failed to identify site-specific bacteria...

<img src="img/gastric-otus.png" width="35%">

Note: clinical collaborator wanted to identify "stomach" bacteria but this was difficult for a lot of reasons, mostly that everything in the throat is also in the stomach. Led us to a different analysis approach, looking at beta-diversity between these communities. But it also eventually led us to an interesting discovery...

----

...which led us to find large overlap between lung, stomach, and throat microbiomes within people.

<img src="img/figure.within_pt_vs_between_pt.png">

Note: we'll pick apart this figure later.

----

### Pay attention to what your data is trying to tell you

<img src="img/hsiao-pca.png">

Hsiao et al, _Nature_ (2014). doi:10.1038/nature13738

----

One OTU is driving the majority of the variance...

<img src="img/hsiao-pca-components.png">

----

...and it seems to bloom during diarrhea recovery.

<img src="img/hsiao-pc1-otu.png">

---

<!-- .slide: data-background="#767171" class="dark" -->

### ~~1. Looking at your raw data~~
### ~~2. Exploring your processed data~~
### 3. Visualizing your data

---

<!-- .slide: data-background="#767171" class="dark" -->

## Visualizing your data

1. Basic plot types and principles
2. Different viz for different purposes
3. Microbiome visualization tools
4. Examples from literature and Biobot

----

<!-- .slide: data-background="#767171" class="dark" -->

## Basic plot types

_What kind of data do you have?_

_What do you want to show?_

----

<img src="img/data-to-viz.png">

----

<img src="img/data-viz-catalogue.png">

----

### Kinds of data

* Categorical (ordinal or not)
* Numeric (discrete or continuous)

Note: continuous includes dates, percentages/proportions

----

**Distributions**: "what sorts of values does this one variable take?"     

**Relationships**: "what happens to y when x changes?"

**Comparisons**: "which one is bigger?"

----

#### Distributions

_What sorts of values does this one variable take?_

Histograms (usually); frequency bar plots (for categorical data)

<img src="img/distributions.png">

Note: distributions are good for showing relative abundances of single OTUs, alpha diversity

----

#### Relationship between two variables

_What happens to y when x changes?_

Scatter plot (almost always), boxplot (if one variable is categorical)    

<img src="img/alpha-diversity-correlations.png" width="70%">

----

#### Relationship between more than two variables

Scatter plot with additional encoding (color, shape), facets       

<img src="img/figure5.reflux_correlations.png" width="70%">

----

#### Paired data

_What happens to the "same" y when x changes?_

Scatter plot or slope graph; boxplot of differences or MA-plot             

<img src="img/paired-data.png" width="80%">

Note: Paired data is when the two measurements belong to the same thing. So, for example, the abundance of an OTU in _the same mouse_ at two times points. slope graph is for when you're comparing the same data at different time points and for a relatively small number of comparisons. It also emphasizes the _direction_ of the change rather than the magnitude (show example from Rafa's ch11 book).

----

#### Comparisons

_Which one is bigger?_

**Most comparisons**: boxplots and/or stripplots        

<img src="img/boxplot-stripplot-both.png" width="70%">

Note: I think of relationship as "if x increases, what happens to y?" and comparisons as "which one is bigger?" -- but they're quite similar concepts so don't worry about the distinction too much. Bar plots: because they rely on the length of the bars to encode data, you must start the bars at zero.

----

#### Other comparisons

**Single values**: bar plots      
**Temporal**: line plots      
**High-dimensional**: heatmaps      
**Distributions**: ridge plots or violin plots      

----

#### Compositions

_What's this made up of?_

Stacked bar plot; pie chart

<img src="img/stacked-barplot.png">

Note: pie chart only if you are showing few things and you're _really_ sure about it

----

### Basic principles for data visualization

Note: there's only really two.

----

## Show the data!

<img src="img/ancombes-quartet.gif" width="45%">

https://www.autodeskresearch.com/publications/samestats

Note: For pretty visualizations, this can be relaxed a little bit -- but you still always need to make sure your data is reliably represented and adds something to the viz.

----

## Think of your audience.

## Focus on "what's the point?"

----

### Many other principles for

* color, opacity, shapes, and size of points
* annotations and size of plot decorators
* order and size of things you're presenting

Read more: github.com/cduvallet/mbiome-data-viz/refs

Note: these are also things you tweak to change your message.

---

<!-- .slide: data-background="#767171" class="dark" -->

## Visualizing your data

1. ~~Basic plot types and principles~~
2. Different viz for different questions and audiences
3. Microbiome visualization tools
4. Examples from literature and Biobot

----

## Different visualizations answer different questions

----

Duvallet et al. "Meta-analysis of gut microbiome studies identifies disease-specific and shared responses." _Nature Communications_ 2017.

Heatmaps sorted by phylogeny provide broad overview and reveal few patterns.

Heatmaps sorted by direction of effect reveal strong disease-specific patterns.

----

<img src="img/overall-heatmap.png" width="55%">

----

<img src="img/heatmaps-paper.png" width="55%">

----

### You can show the same data multiple ways to make your points

----

<img src="img/heatmaps-paper.png" width="55%">

----

<img src="img/direction-of-shift.png" width="30%">

----

### You can also modulate how much of the data you show

<img src="img/reviewer.ppi_vs_lung_gastric.png" width="40%">

Note: even though you could get the boxplot out of the reflux figure, it's nicer to have it directly shown.

----

<img src="img/reviewer.reflux_correlations_ppi_status.png" width="75%">

----

### Different plot types highlight different takeaways

Matus et al. "24-hour multi-omics analysis of residential sewage reflects human activity and informs public health." _In preparation_.

----

<img src="img/matus-bar-plot.png" width="43%"> <img src="img/matus-line-plot.png" width="45%">

----

<img src="img/matus-heatmap.png" width="50%">

----

## Different audiences need different visualizations

----

The figure in the paper...

<img src="img/heatmaps-paper.png" width="55%">

----

in my defense...

<img src="img/heatmaps-defense.png">

----

...and in a public outreach talk.

<img src="img/heatmaps-soe-talk.png">

----

### Sometimes words are worth a thousand figures

<img src="img/figure.within_pt_vs_between_pt.png">

----

<img src="img/within_pt_vs_between_pt_slide.png">


----

The BE Communication Lab has great resources to help you think through communicating science to different audiences.

Read more: [mitcommlab.mit.edu/be/commkit/figure-design/](http://mitcommlab.mit.edu/be/commkit/figure-design/)

---

<!-- .slide: data-background="#767171" class="dark" -->

## Visualizing your data

1. ~~Basic plot types and principles~~
2. ~~Different viz for different questions and audiences~~
3. Microbiome visualization tools
4. Examples from literature and Biobot

----

## Visualization tools

- python, R, MATLAB
- Tableau, D3, etc
- Interactive: Bokeh, R Shiny, etc
- Microbiome-specific: Calour, Anvio, QIIME 2 View, ITOL

---

<!-- .slide: data-background="#767171" class="dark" -->

## Visualizing your data

1. ~~Basic plot types and principles~~
2. ~~Different viz for different questions and audiences~~
3. ~~Microbiome visualization tools~~
4. Examples from literature and Biobot

----

- What's the main point of each figure?
- How is that point communicated?
- How could it be clearer?
- How would you adapt this figure for this hackathon?

----

Smillie et al. "Strain tracking reveals the determinants of bacterial engraftment in the human gut following fecal microbiota transplantation." _Cell host & microbe_. 2018.

----

Simplify a complicated study design:

<img src="img/smillie-study-design.png" width="50%">

----

<img src="img/smillie-ml-results.png">

----

<img src="img/smillie-strains.png">

----

Taur et al. "Reconstitution of the gut microbiota of antibiotic-treated patients by autologous fecal microbiota transplant." _Science Translational Medicine_. 2018.

----

<img src="img/auto-fmt.png">

----

<img src="img/auto-fmt-trajectory.png" width="47%%">

----

Rothschild, Weissbrod, Barken, et al. "Environment dominates over host genetics in shaping human gut microbiota." _Nature_ 2018.

----

<img src="img/ancestry-vs-microbiome.png" width="60%">

"N.S." means "Not significant"

Note: main point of the figure: no significant association between microbiome and ancestry, esp when compared to genetics. What works: explicitly writing the p-values on the figures; matching colors between a and b to show that it's the same people. What could be better: confusing that colors in c are the same as in a and b (this is showing bacteria). Zoom in on panel e: should be a scatter plot instead of categorical (if the data allows). Point of e is that there microbiome doesn't become more dissimilar with more genetic dissimilarity. In a talk, would want to put arrows describing axes.

----

### Biobot Analytics

<img src="img/biobot-mission.png">

Real-life example: data visualization for opioid public health response.

----

### Challenge: communicate complex data to city officials

<img src="img/biobot-basic-data.png" width="80%">

----

### Overdose reversal drug vs. reported overdoses

<img src="img/biobot-narcan.png" width="80%">

----

<img src="img/biobot-narcan-2.png">

---

<!-- .slide: data-background="#3F51B5" class="dark" -->

### Thanks!

**Claire Duvallet**

Slides: [cduvallet.github.io/mbiome-data-viz](https://cduvallet.github.io/mbiome-data-viz/)

_Look at your data, focus your message._

---

<!-- - what do officials want to know? do they care about non-fatal OD's, or non-fatal OD's vs. narcan use? do they want to see info about each community, or do they just know already?
- public health officials: need to show data (via tables) but also condense it (via viz). have to find a balance -->

----

<!-- - fig 3 tsne plot
    - point out the use of color to encode high vs. low diversity. what other ways could they have done this?
    - what about the color-coding, what do you think about that? how else could they have done it?
- fig 3 (?) small multiples of trajectories
    - the point of this figure is supposed to be: auto-FMT patients consistently regained diversity (even if they weren’t the same as their initial sample); no-FMT controls did not
    - what are some things that make this clear? unclear?
        - clear: highlighting the start and end with color
        - unclear: background blob colors. connecting the start and end with a bold line. adding the percent on top of each plot (should be a separate bar plot, probably)
- fig ... heatmaps
    - main takeaway? (top three plots go from dark to light back to dark; bottom three go from dark to light and stay light)
    - what is all the info encoded on here?
        - diversity: why did they categorize this? should be a gradient with the raw values
        - similarity: same, should not categorize this. adds noise and hides data.
        - color coding microbial species: i'm torn on this one. but problem is that there's no legend so not great.
    - how else could they show this data? can we draw out a schematic of what it would look like? -->

----
