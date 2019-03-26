# Notes

# Data exploration

## Basic data exploration analyses

- alpha diversity
- PCA
- etc

## Basic visualization types

- heatmap
- PCA
- line plots
- boxplots
- paired data

--> bring up the idea of continuous vs. categorical data, and which type of viz works for each (maybe go back to Sean K's notes from the brief biostats class he gave?)

--> also stress importance of keeping data as raw as possible: show Ancombe's quartet

## Different viz for different questions

"different ways of visualizing same data to get at different questions"

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
