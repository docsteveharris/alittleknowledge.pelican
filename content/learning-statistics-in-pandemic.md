Title: Learning statistics in a pandemic
Date: 2020-05-24 23:30
Modified: 2020-05-24 23:30
Category: teaching
Tags: rethinking
Authors: Steve Harris
Status: draft

# Learning statistics in a pandemic

So there’s a global pandemic. Your first task is to report the mortality rate. The government will only be convinced to act if the mortality is greater than that for seasonal flu (approximately 1%).

You have a colleague in Wuhan. She struggles to send you data because she’s worried about censorship so you communicate with a simple code using Twitter. If the last character of the tweet is a punctuation mark or emoji that means a case of COVID-19 admitted to her hospital has died. If the last character is not a punctuation mark or emoji, then the patient has been discharged alive.
 
Here are the  first 3 tweets from her.

> Hi. How are you?  

> It’s cold. Say hi to your family!  

> Better day today, warmer  

So we read this as 

Died
Died
Survived

From now on, we’re going to represent this as a string of characters `DDS`. You receive 7 more tweets over the next couple of days: `DDSDSSDDDS` . That is 6 deaths and 4 survivors, or a 60% mortality rate.

Let’s recap.
1. We have some measurements or observations (our *data*).
2. We want to know the ‘true’ mortality rate, and are nervous about causing unnecessary alarm.

We could just report the proportion of deaths in the sample we have observed. We’d want to also report the number of observations (i.e. the ‘sample size’ ). We’d be a lot more  worried if this was a sample of 1000 cases a not just 10. But why? We have an intuition that the proportion from the bigger sample (600 deaths in 1000 cases) is a more certain estimate. 

But again why? 

To answer this, we need to connect our *data* with the ‘*answer to our question*’ (read target of inference) with a story (read model). The model is a data generating mechanism that in some way depends on the true proportion of deaths among patients with COVID-19.

Let’s go back to the first 3 patients (`DDS`), and invoke a unfair but divine coin labelled with `D` on one side, and `S` on the other. It is flipped for each victim,  and for now, we are going  to assume that the same coin is used for everyone.   The ‘chance’ of the coin landing `D` side up will be called `p`. This is our target of inference. It is an unseen *variable*. The data is summarised as two ‘observed’ variables: the count of `D` and the count of `S`, or equivalent the count of `D` and the total number (`N`) of patients (since the coin has only 2 sides these representations are equivalent.).

 



2020-05-24t231317 @resume
Garden of forking paths
We need a ‘story’ to link our data to our measure
 show how as sample size grows even though the proportion remains the same our ?plausible ‘confidence interval’ narrows