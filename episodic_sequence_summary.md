# File with the outline of plots and questions about these first draft of plots for Sequence paper

# Questions for Ian:

**Below I have a few important questions for my analysis (specifically for moving onto SNPeff or Gowinda). Further down I have the plots with the questions and others pertaining to visualization and final plots required.**

### 1. Filtering positions for Fst values:

**Currently can filter both model output and selection coefficients for significance after adjusting p values, but how to filter the Fst values (other than keeping all those with a Fst value)?**

  Note: Fst values are windows, so use of comparison with other measures here is to ensure Fst is sufficiently high in window around positions of interest.

  Should I downscale the Fst values with Sel:Sel and Con:Con comparisons? (below are the plots for 115 Sel:Sel and Con:Con)
    
     -- Method? (previous ideas were (Fst_C:C + Fst_S:S)/2 for scaling)
  
### 2. Adjusting P values: Chromosome OR full genome ??
  
  When performing p.adjust, should the adjustments be for the full genome (all positions) or on a per chromosome basis?
  
    -- Currently am doing full genome, but not sure if this should be a per Chromosome adjustment

### 3. Bonferroni vs. Fdr:

**Fdr adjustment for p-values keeps more positions but Bonferroni gives more visually appealling plots (see below) and more accuracy for positions**

  For plots: would Bonferroni plots be better?
  
  For finding positions of interest: is FDR still prefered better?
  
  OR: keep consistent between the two (which method)?
  
### 4. Selection Coeffcient Filtering:

 **Current method is to keep any significant (after FDR p.adjust) selection coefficients that are unique to predation lines (i.e no Selcoeef for Con).**

**This is the average Selcoef b/w two mappers (keeping the less significant p-value).**
 
 Does this method make sense?
  
____________________________________________________________________________  
____________________________________________________________________________
# Plots with specific questions below for plots:
____________________________________________________________________________
____________________________________________________________________________

## Pi: Ancestral Pi for Novoalign:

### Outline

The ancestral nucleotide diversity:

![Ancestral Pi Plot for Novoalign](https://github.com/PaulKnoops/episodicSequenceData/blob/master/Analysis_after_sync_2018_plots/Ancestral_Pi.png)

### Questions

  1. Necessary for all populations?
  
    -- Have all populations (and for bowtie and novoalign mappers)

  2. Average Pi for all mappers??
  
    -- Calculate bwa Pi and average between three? or show one (or 2) mappers as a represenation?

  3. Overlay for changes in diversity over time?
   
    -- Do we want overlay plots with ~splines showing the change in diversity from Ancestor --> 115?

____________________________________________________________________________

## Fst Plots:

### Outline

Average  pairwise Fst between control and selection replicates

  -- Average b/w mappers and replicates

**Generation 38:**
![meanFst for F38](https://github.com/PaulKnoops/episodicSequenceData/blob/master/Analysis_after_sync_2018_plots/F38_meanFstPlot.png)

**Generation 77:**
![meanFst for F77](https://github.com/PaulKnoops/episodicSequenceData/blob/master/Analysis_after_sync_2018_plots/F77_meanFstPlot.png)

**Generation 115:** 
![meanFst for F115](https://github.com/PaulKnoops/episodicSequenceData/blob/master/Analysis_after_sync_2018_plots/F115_meanFstPlot.png)


### Questions

  1. **Downscaling** (available for all generations): Necessary? and methods?
  
    -- previous ideas were (Fst_C:C + Fst_S:S)/2 for scaling
  ___________________________________________________
**meanFst: Selection vs. Control: Generation115**
![meanFst for F115](https://github.com/PaulKnoops/episodicSequenceData/blob/master/Analysis_after_sync_2018_plots/F115_meanFstPlot.png)

**meanFst: Control vs. Control: Generation115**
![Fst_Con:Con_115](https://github.com/PaulKnoops/episodicSequenceData/blob/master/Analysis_after_sync_2018_plots/F115_Control:Control_FST.png)

**meanFst: Selection vs. Selection: Generation115**
![Fst_Sel:Sel_115](https://github.com/PaulKnoops/episodicSequenceData/blob/master/Analysis_after_sync_2018_plots/F115_Selection:Selection_FST.png)
____________________________________________________
  
  3. Cut off for positions? 
  
    -- Currently keeping anything with an Fst value for Con:Sel_115 comparison: any way to filter more deeply for peeks 
    
    -- Should I keep the top 50%? the top 10% Fst values?

____________________________________________________________________________

## Model Outputs

### Outline

Plots for original values and FDR adjusted

-- Sizing is a bit off (differently saved, but these are still rough until I know the final plan)

**None corrected P values: TxG -log10(meanP-value)**
![FullGenomeTxGPlot](https://github.com/PaulKnoops/episodicSequenceData/blob/master/Analysis_after_sync_2018_plots/CHROMO_meanP.png)


**FDR Corrected P-values: TxG -log10(meanP-value)**
![FDRcorrection](https://github.com/PaulKnoops/episodicSequenceData/blob/master/Analysis_after_sync_2018_plots/Fdr_adjustP.png)

### Questions: 

   1. is Bonferroni a better visualization for the paper (much less going on)
   
**TxG: -log10(meanP) with Bonferroni Correction for multiple comparisons**
![BonferroniCorrection_2200x1100](https://github.com/PaulKnoops/episodicSequenceData/blob/master/Analysis_after_sync_2018_plots/Bonferroni_p.adjust_TxG.png)

 Advantage with this: Can create a plot on with valued of the regular plot (first one) with coloured sig. values: Would not look good with FDR:
  
  ![Coloured Sig](https://github.com/PaulKnoops/episodicSequenceData/blob/master/Analysis_after_sync_2018_plots/fdr_bonf_adjustP_sigColoured.png)
  
____________________________________________________________________________

## Poolseq outputs:

### Outline

Output from PoolSeq package: the significant selection coeffients that were significant for Predation lines and not for controls

Ongoing with the slow pace of Poolseq: almost complete (just the 4th and X chomosome left for BWA and X for novoalign)

This is the average b/w two mappers (bwa and novoalign), keeping the least significant pvalue.

Note: below 4th and 3R are only from Novoalign (have not gotton to combine the Bwa ones yet).

![poolseq_2L-4_D1](https://github.com/PaulKnoops/episodicSequenceData/blob/master/Analysis_after_sync_2018_plots/selcoeff_2L-4_D1.png)

### Questions

1. Does another full chomosome plot (same colours) work for these, like above? 

2. Any cut off for selection coefficients or just any significant selection coefficients unique to predator lines?

3. Overlay positions with selection coefficients onto model outputs?

![overlaySelcoef and model](https://github.com/PaulKnoops/episodicSequenceData/blob/master/Analysis_after_sync_2018_plots/overlay_2L-4_model_selcoef.png)

____________________________________________________________________________

## Trajectories and positions:
 
### Outline
 
 Filtered positions for:
 
 -- pvalues <0.05 after FDR from model output 
 
 -- similar positions in the poolseq significant selection coefficients
 
 -- Then found any overlapping windows with these positions with Fst values != 0. 
 
 Tentative positions overlapping based on this criteria (will change with additional chromosomes/mappers completing poolseq):
 **2L**
```
With Bonferroni: 50 positions
With FDR: 378 positions
```
**2R**
```
With Bonferroni: 110 positions
With FDR: 504 positions
```
**3L**
```
With Bonferroni: 15 positions
With FDR: 71 positions
```
**3R**
```
With Bonferroni: 24 positions
With FDR: 270 positions
```
**4**
```
With Bonferroni: 1 positions
With FDR: 2 positions
```
**X** 
Not complete
```
With Bonferroni:  positions
With FDR:  positions
```

 Trajectories are the mean absolute difference the treatments had from the ancestor
 
 ![Trajectory_2ndChromo](https://github.com/PaulKnoops/episodicSequenceData/blob/master/Analysis_after_sync_2018_plots/Trajectory_diff_2Chromo.png)

### Questions:

1. Plots of individual positions?

  -- Is it informative to select some large peaked positions that are shared and show the actual trajectories of frequencies?

2. Overlay the postions of interest onto the output from the model:  (like above but with positions overlapping Fst windows as well?)

  
  2L with FDR: 1st draft, initial (wrong) screen for positions overlapping all three)
  
![FDR_col](https://github.com/PaulKnoops/episodicSequenceData/blob/master/Analysis_after_sync_2018_plots/colouredPositions2L_Practice.png)
  
  

