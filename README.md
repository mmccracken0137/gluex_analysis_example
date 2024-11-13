# gluex_analysis_example

GlueX Analysis Example with (hopefully) complete documentation

Author: Mike McCracken, github: mmccracken0137

## Helpful links

- Brad Sawatzky, [Jefferson Lab Scientific Computing Infrastructure Update](https://indico.jlab.org/event/863/contributions/14830/attachments/11384/17588/SciComp-Update-CLAS_June2024_Sawatzky.pdf) (CLAS Collab Meeting, June 2024).  This presentation describes some of the features of SciComp at JLab, including which disks are appropriate for which uses.
- [AmpTools Starter Hints](https://halldweb.jlab.org/wiki-private/index.php/Amptools_starter_hints)
- [Naomi's personal link dump](https://halldweb.jlab.org/wiki-private/index.php/User:Njarvis)
- Brad Sawatzky, Basics of the JLab Computing Farm sessions from the [JLab GSPDA Mini Software Workshop](https://indico.jlab.org/event/879/) (6 Sep 2024)
- Naomi's [GoogleDoc about MCWrapper](https://docs.google.com/document/d/1m8ZWj1mVdu7c4xOZpdhYuzTFrJAwJzNtjgV9JQMDqzc/edit?tab=t.0)
- Alex Austregesilo, [Plug-ins, ReactionFilter and Analysis Submit Form](https://halldweb.jlab.org/DocDB/0040/004010/001/presentation.pdf) (May 2019)
- [How to choose software versions on the MC submit form](https://halldweb.jlab.org/wiki/index.php/How_to_choose_software_versions_on_the_MC_submission_form)
- For example, [Spring 2017 Analysis Launch](https://halldweb.jlab.org/wiki-private/index.php/Spring_2017_Analysis_Launch) information
- [GlueX Data Information](https://halldweb.jlab.org/wiki-private/index.php/GlueX_Data_Information)
- [MC Submit form](https://halldweb.jlab.org/gluex_sim/SubmitSim.html)
- [Private GlueX Wiki](https://halldweb.jlab.org/wiki-private/index.php/Main_Page)
- Analysis Launch [Reaction Submit form](https://halldweb.jlab.org/analysis/SubmitReaction.html)
- [DSelector info](https://halldweb.jlab.org/wiki/index.php/DSelector)

## Analysis steps

## Accessing the JLab CUE system
ssh to the ifarm at JLab.
- Basic info on how this can be done is [here](https://jlab.servicenowservices.com/scicomp?id=kb_article&sysparm_article=KB0015066)
- Suggestions on how to possibly streamline the process are [here](https://jlab.servicenowservices.com/scicomp?id=kb_article&sysparm_article=KB0014918)

## Environment set-up
If you are computing on the CUE system at JLab and using `tcsh` (or `csh`) as your shell, add the following lines to the `.tcshrc` or `.cshrc` file in your home directory:
```
source /group/halld/Software/build_scripts/gluex_env_boot_jlab.csh
gxenv
```
If you're using bash as your shell, the two lines above should also work.
(Note: I am using `tcsh`.  Some of what follows below will assume that you are also using `tcsh` or `csh`.  If you're a basher and encounter problems, keep in mind that the shell mismatch could be a cause.)

You can check the extent to which this worked by executing commands like
```
ccdb -i
root
hd_root
```
and making sure they don't crash.

## Using git

To clone this repo
> git clone https://github.com/mmccracken0137/gluex_analysis_example.git
Please contribute!

### Data
#### 1. File types and the many things that we call them
#### 2. Analysis launch
#### 3. Moving files from tape to cache
#### 4. Making and running a DSelector
#### 5. Running on the computing cluster
#### 6. Tuning cuts
#### 7. Creating and using plots

### Simulation







## Unorganized notes
Log into ifarm
Can pretty much get rid of everything in your .cshrc.  Environment is managed by gxenv.  Add the following lines to .cshrc:
> source /group/halld/Software/build_scripts/gluex_env_boot_jlab.csh
> gxenv

How to set up .cshrc at the lab and at CMU?



Glossary:
- exclusive -- reconstructing all final-state particles of the desired reaction
- inclusive -- not reconstructing all final-state particles of desired reaction.  Could possibly include some reactions other than the target.

Questions:
- What are the "versions" that accompany the different runs?  "Data versions"?  Why are there so many for each run period?
- Where does the data live?  How do I run over it?  Do I need to move it from tape every time I need to run over it?
- 


https://halldweb.jlab.org/data_monitoring/launch_analysis/index.html
What is each of the following things?
- Offline monitoring 
- Full Reconstruction Launch
- Analysis Launch
- Analysis Launch (Simulation)

Now we have to build some analysis code


Where are the data skims?  What do we actually run over?


Monte Carlo

With Naomi:
raw data is in /cache/halld files that should be there are shown /mss/halld/
evio are raw files
rest files are skims
RunPeriod/analysis/verXX
versions mean which batch a particular analysis launch skim is part of 
Look at run period 2017 -- small dataset, in process of being recalibrated.  2020 has good calibration.  Fall 2018 is enormous.

Write a DSelector to analyze the root tree files for a given reaction from analysis launch
be on gluon00 through 03

**How to get the files off of tape?**

use globus to transfer files from lab to CMU.  Broken at the moment.  globus.org

jcache get to move data from /mss to /cache
jcache -h for more info

For submitting Monte Carlo
https://halldweb.jlab.org/gluex_sim/SubmitSim.html
Run range looks at the flux for each run and generates the number of events in proportion to the flux of each run.  Number of events is total
Output directory is ONE directory.  MC Wrapper will put the files somewhere weird
Full path to generator -- put in /work/

EVIO is raw data
REST -- reconstructed showers and tracks
PART -- physics analysis ROOT tree, generated by running ReactionFilter on REST files

Write up analysis example.  Put it on the private wiki

Copy one datafile from jlab CMU to do prototyping.  
Need to loging to ernest then: sbatch <jobfile>