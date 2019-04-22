# basic-analysis-of-behavioural-data
Basic templates for behavioural analysis.
See Wiki for documentation. Wiki references screenshot .doc file "basic-analysis-of-behavioural-data_ERB".

ReadMe covers prelim items only, see Wiki for documentation. 






ANCOVA (using baseline values as a co-variate) is still best applied in SPSS.
For RM-ANCOVA, I broadly follow the relevent early steps in Lawrence's protocol which is then nicely extended using syntax to include interaction of time (wave of data collection) with treatment factor (group)...then extends further to generate a Mixed Model....  but we can stop at the ANCOVA stage if we want. 

http://www.lawrencemoon.co.uk/publications/Duricki_Soleman_Moon_2016.pdf.

This protocol also includes the relevant info to change between short and long format data in SPSS, this can be done in a few lines of copypaste R code which I will upload soon incase useful.


The syntax at step 21 has a tiny typo error in it for pairwise comparisons of group * wave. Its this:

/EMMEANS=TABLES(group*wave) WITH(mean_preop=MEAN)COMPARE (group) ADJ(LSD) /EMMEANS=TABLES(group*wave) WITH(mean_preop=MEAN)COMPARE (wave) ADJ(LSD).


I usually amend the above syntax to this, for inclusion of correction for multiple comparisons to see what it looks like. 

 /EMMEANS=TABLES(group) WITH(mean_preop=MEAN)COMPARE ADJ(BONFERRONI) 
  /EMMEANS=TABLES(wave) WITH(mean_preop=MEAN)COMPARE ADJ(BONFERRONI)


I aim to put relevant syntax in a code file soon for ANCOVA, but you just need to follow Lawrence's protocol , play around with syntax, but most importantly have background knowledge as to the data. You can't jump to SPSS without understanding everything that happens in Prism with ease. You need to understand where stuff comes from before using syntax which goes beyond click n play. 
