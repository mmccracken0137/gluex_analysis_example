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

## Analysis steps

## Accessing the JLab CUE system
ssh to the ifarm at JLab.
- Basic info on how this can be done is [here](https://jlab.servicenowservices.com/scicomp?id=kb_article&sysparm_article=KB0015066
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
