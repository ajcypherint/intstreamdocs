.. IntStream documentation master file, created by
   sphinx-quickstart on Fri Feb 26 02:53:58 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Usage
#####

.. contents:: Contents
   :depth: 3
   :backlinks: top


Intstream classifies incoming intelligence reports and enriches indicators.  

Home Page
=========

See Main|Articles

Main
========

View articles and indicators

Articles
********

Here you can sort articles
by their classified category, start date, end date, and group similar articles

Filter articles by start date, end date, source, and model.  (note you first must
visit the training page and create a model)

To view an article click on the article title.

To view similar articles click on the similar articles number displayed

**Max Cluster Diff** similar articles can be grouped.
The threshold for grouping is set to 0 on initial page load.  This means that 
an article less than 0 % different will group.  Raising the 'Max Cluster Diff' to 
a higher threshold will group more articles together based on their content.

**Min Doc Freq** is used to tell IntStream the number of documents a word 
must appear in for it to be used in grouping.  The higher the frequency the fewer words 
used.

**Max Doc Freq** tells IntStream the maximum documents a word should be in to be used
for grouping.  Words like 'the', 'and', 'is' occur in almost 100 % of documents so setting an
80% threshold will filter out these words and only use important words. Lowering the
threshold will include fewer words when grouping.

Indicators
************

View Indicators and enriched information.
Choose a start date, end data, source and columns to diplay.  
Look for indicators of interest for further investigation.

Sources 
============

Add sources to pull articles, indicators, or enrich indicators

Upload
************

Manually uploaded docs
1. Click add
2. Give a name
3. Save

RSS
************

Rss feeds that are pulled on an hourly basis

1. Click add
2. Name source and add url
3. Save.


Hunting Job
************

Hunting jobs run after indicators are uploaded. They are used to add data related to the indicator.
As an example you could add traffic found to an ip address.

Scheduled Job
*************

Scheduled jobs run on a cron schedule.  
An example of a scheduled job would be to pull indicators on an hourly basis from 
a github page.

see Scheduled Jobs section on how to write and test Schedule Jobs

Training 
===========

Create models and train.

Models
**********

Create Model to train and use to filter articles.

1. click add
2. choose a name
3. add sources
4. choose active. 
5. save

History
***********

Models can be created using the history page.  

1. Select your model
2. Select start date and end date
3. Choose Source to further filter articles
4. Now you can select True or False if the article relates to the model you are classifying.
5. Click Create to train the model.

