# Introduction
It's always great when I find a new show that hounds
my attention on Hulu or Netflix or HBO Max or YouTube
or ... (seriously, Paramount+ and Peacock were just
released in the last 6 months.) And it's even better
when I find that I want to tie this new obsession 
to a data science learning objective. So, I've found
a question that I wanted to answer as I was watching
Season 22 of America's Next Top Model (ANTM). Was Mame going 
to win the competition? How would height factor into
a contestant's competitiveness? Match that with my 
want to explore new techniques in data science, and 
we have a great start to a side project! We are going
to use survival analysis and a survival regression to
learn how to handle censored data and perform a 
survival regression.

# Problem Statement
So, given a dataset of ANTM contestants' age, height,
and weeks/rounds lasted in their respective season, 
how long would a contestant last in the next season
of ANTM?

Update 11MAR2021: Target will be a "death" variable 
of whether the contestant made it to the TOP 3
of the season. 

Update 22MAR2021: using the 11MAR update logic, I can
then also extend the somewhat weak variables (recall:
I only have height and age) by creating dummies for
models considered "tall" and "young". Formal definitions
will follow. these can then be be used to explore 
the bias against shorter models or the like... 

So, the purpose of this project is evolving in 
interesting ways:
1. ~Perform Cox proportional hazard model to learn
survival regression techniques.~
2. Use the data cleaning process for the manually retrieved
data as an opportunity to practice data pipeline unit
testing.
    * Also a good opportunity to explore Test Driven 
    Development. Starting with writing the tests
    in test_DatEng.py and then writing the functions
    to perform the data engineering.
3. Exploration of bias in modelling by using a dataset and
industry with known bias toward taller women as models to
explore AI explainability and outcomes analysis.

Update 28MAR2021: as per usual I added another goal 
as part of this project:
4. Project Configuration with YAML files. Going to try 
exploring the pyyaml or confuse libraries for leveraging
YAMLs to coordinate the project. I hate it but I may also
go down the route of virtual environments too... gonna
try to resist that...

Update 04APR2021: talking to Daniel helped challenge an
assumption that this problem may not be a survival analysis
problem at all. Two things I'm realizing:
1. Contestants are not directly comparable across seasons.
Contestant X in season 4 that was in the top 2 may have only
may have been eliminated in the first three episodes of season 21.
So, at minimum, I would need a more complex approach to the problem. 
As it stands I have a dataset of 22 different trials (seasons), while I was 
designing a problem statement that hoped I could use the 22 trials as a
single dataset. 
2. Lesser to (1), my planned target variable is not a time to event
variable, which is just wholly against the design of the Cox proportional
hazards models.

Exploring more of my hope for survival analysis, perhaps going to 
a tried-and-true project using a loan default dataset as my source
for my survival analysis itch.




# Notes and Starting Thoughts
Note: sex is limited to only female contestants
in the dataset. Season 22 had male contestants 
and certainly future seasons may have male 
contestants, but the sample size across is too
small for me to add that dimension in the current
version of the tool. Secondly, I will need to spend
some time thinking about the assumptions/implications
of building a dataset from a fashion show. That is, 
model preferences for high fashion tend to favor
taller, skinnier models. So, like similar issues
in explainability and societal bias in models, I will
need to spend some time understanding any new features
that I may add to the model.

Further, Season 18 or 19 had contestants coming back
from previous seasons which may have have be a bit
of target leakage. My thought is that since the sample
or competition scenario is different from when they
first competed for the different mix of models in that
season. I'm unsure if this is sound yet, but I can explore
that in my write-up of of the model. 

Also, I should probably switch to Jupyter for this to 
replace the scripts that I was planning to use.

