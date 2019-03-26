# Notes

# Data exploration

## Basic data exploration analyses

- alpha diversity
- PCA
    - "A good rule of thumb for data visualization is that trying to represent three dimensions on a two dimensional printed or web page is almost always one dimension too many, " - paldhous.github.io
- etc

## Basic visualization types

- heatmap
- PCA
- line plots
- boxplots
- paired data

--> bring up the idea of continuous vs. categorical data, and which type of viz works for each (maybe go back to Sean K's notes from the brief biostats class he gave?)

--> also stress importance of keeping data as raw as possible: show Ancombe's quartet

https://rafalab.github.io/dsbook/introduction-to-data-visualization.html
viz types: https://rafalab.github.io/dsbook/distributions.html

### Other resources

Rafa's book: https://rafalab.github.io/dsbook/introduction-to-data-visualization.html
Flowing Data
The Pudding
Twitter!!

Need to look over myself:
http://paldhous.github.io/ucb/2016/dataviz/index.html
https://www.biostat.wisc.edu/~kbroman/presentations/graphs2017.pdf
http://courses.had.co.nz/

## Different viz for different questions

"different ways of visualizing same data to get at different questions"

- from paldous.github.io "data visualization basic principles": what do you want to show? distribution, relation, connection (i.e. networks), comparison, composition

- my aerodigestive paper:
    - across people vs. within people
    - "do lungs have more stomach bugs or throat bugs?"

- my meta-analysis
    - show the heatmaps sorted by "phylogeny" vs. by "blue-ness" and "red-ness"

- maybe: 24hr paper
    - show the overall heatmap (to give a sense of scale of data and overall noise)
    - vs. the line plots (to see the dynamics more clearly)

- maybe scott's tex mex paper?
    - not sure, will have to look into these

### Listen to what the viz is telling you

- cholera example from Hsiao: the PCA looked wonky, which led me to an interesting observation


## Presenting visualizations

### Basic principles

- color!!
    - diverging vs qualitative
    - usually need less than you think
    - keep color-blind folks in mind
    - many tools to help decide: If you intend to roll your own color scheme, try experimenting with I want hue (http://tools.medialab.sciences-po.fr/iwanthue) for qualitative color schemes, the Chroma.js Color Scale Helper (https://vis4.net/labs/multihue/) for sequential schemes, and this color ramp generator (http://www.zonums.com/online/color_ramp/), in combination with Colorizer or another online color picker, for diverging schemes.
    - maybe give examples of a viz with default colors vs. hand-picked colors? (my meta-analysis paper?)
- shapes
- opacity
    - don't forget: this is an important way to modulate what gets attention
- line and text sizes matter too
- order of values
- show the data
- no 3D unless you are committed to 3D printing your plot.

### different viz for different audience

- make this point in the third section
- use dbOTUs as an example, maybe?

### Great visualization examples

Go through these and try to think about what makes them great

- Smillie's strain finder results and paper
    - thinking of the tree showing correct/incorrect classification (i think this is from engraftment paper, which may be the same)
    - and the pie charts (zomg pie charts)
- Maybe something from Eran Segal's glycemic response paper??

### Visualization tools (some for exploration, some for presentation)

- python and R
    - this is what I use
    - code to reproduce all figures in this talk are on my github
- Calour
    - for visualizing tabular data (e.g. OTU tables); interactive heatmaps
        - can also do differential abundance, correlation (with metadata), dbBact term enrichment (don't know what these are)
    - http://biocore.github.io/calour/
    - https://msystems.asm.org/content/4/1/e00269-18
    - Full GUI version: https://github.com/amnona/EZCalour
- Anvio
    - to visualize metagenomics data
    - https://peerj.com/articles/1319/
    - http://merenlab.org/software/anvio/
- QIIME 2 view
    - PCA
        - also compatible with striped Unifrac, if you have very large sample size and/or your viz is too slow
    - taxonomy barplots
    - many others, check out their docs!
- Tableau
    - public version is free: https://public.tableau.com/s/
