# Gendered collaboration amongst German researchers

## tl;dr
A visualization of gendered collaboration amongst researchers funded by the DFG in order to explore gender equality within academia.

## Table of Contents

* [Project description](#project-description)
  * [Target audience](#target)
  * [Functionality](#functionality)
  * [External Data](#external)
* [Design Decicions based on “Four Nested Levels of Visualization Design” by Munzner](#design)
  * [Domain problem characterization](#domain)
  * [Data / task abstraction](#abstraction)
  * [Visual encoding / interaction design](#encoding)
  * [Algorithm design](#algorithm)
* [Validation](#validation)
* [Installation](#installation)
* [Manual](#manual)
* [Contributors](#contributors)
* [Copyright](#copyright)

## <a name="project-description"></a> Project description
As one of the largest German instutition to fund research is [commited to gender equality](https://www.dfg.de/en/service/press/press_releases/2017/press_release_no_24/index.html "Press Release No. 24 | 5 July 2017"), it makes sense to look at their own data in order to analyze how and where measures need to be taken to own up to these promises. We're using parts of the [GEPRIS data](https://gepris.dfg.de/gepris/OCTOPUS) to look at collaborations within research project that are funded by the DFG. As [research](https://www.equityinstem.org/networks-metaanalysis/) shows, people tend to form their networks with people who are similar to them, which can hinder gender inclusion in fields that have traditionally been shaped by male networks. To find out whether this is the case for German academia and research as well, we are visualizing the collaboration amongst researchers funded by DFG.

###  <a name="target"></a> Target audience
The target audience for this project are equal opportunity commissioners at universities and people interested in gender equality.

###  <a name="functionality"></a> Functionality
We're giving you the opportunity to explore different universities' degrees of gender equality to see where there's still work to be done.

###  <a name="external"></a> External data
[GEPRIS data](https://gepris.dfg.de/gepris/OCTOPUS)

[Worldwide Gender-Name Dictionary](https://ideas.repec.org/c/wip/eccode/10.html)

Geodata from ?

External libraries in addition to d3.js?

##  <a name="design"></a> Design Decicions based on “Four Nested Levels of Visualization Design” by Munzner

### <a name="domain"></a> Domain problem characterization
"There is now abundant data that diversity is essential to scientific excellence, with experiments showing that diverse teams have cognitive diversity that allows them to outperform homogeneous teams." reads a [statement](https://fas.columbia.edu/files/fas/content/Columbia-ArtsandSciences-PPC-Equity-Reports-2018.pdf) by Columbia University in 2018. While their statement focuses on students, the same applies to researchers.

We are thus interested in gender relations (as one aspect of diversity) within German academia. This is important knowledge for equal opportunity commissioners at German universities: How diverse are research projects regarding the gender ratios of their teams? How diverse are individual researchers' collaborations? And how diverse are universities regarding the gender ratio of projects that they host?

Our data is the [GEPRIS dataset](https://gepris.dfg.de/gepris/OCTOPUS) that contains projects funded by the DFG, including the people and institutions involved in those projects upon application. Please note that the GEPRIS data does not consider time, meaning that locations and titles represent the most current data. This could lead to bias and spurious links. We've also derived a probable gender for each person based on the first name. This data stems from [Lax-Martinez, G., Raffo, J. and Saito, K. 2016. "Identifying the Gender of PCT inventors", WIPO Economic Research Working Paper 33.](https://ideas.repec.org/c/wip/eccode/10.html). We validated this assignment by picking the title "Professor" and "Professorin", and comparing them to the gender assignment. Less than 1% of the assignments were in contrast to the titles, meaning that we would assume a similar error ratio for the entire data set. Additionally, around 19% of first names could not be assigned a gender at all.

### <a name="abstraction"></a> Data / task abstraction

The original GEPRIS dataset is made up of tables of mainly nominal data (project IDs, person IDs, institution IDs, names, institution address...). We've created additional nominal data for an inferred gender and spatial data (geo position) for the insitutions. Beyond that, we calculated a project_gender_index. This is value between 0 and 1, based on the gender ratio of all people involved in a specific project (that has more than one person). 0 indicates that there are only men in a project whereas 1 indicates that there are only women in a project. Following, the person_gender_index is the mean of project_gender_index for all projects a person is involved in and institution_gender_index is the mean of person_gender_index of all people related to that institution. 
Dataset overall: tables
Project IDs: nominal
Person IDs: nominal
Person Gender: nominal
Project role: nominal
Insitution adress: position

Discovery distribution. Browse topology. Identify & compare universities & individuals.
(Formulate the tasks in a domain-independent vocabulary. How did you prepare (aggregate, filter...) the data to support the tasks?)

### <a name="encoding"></a> Visual encoding / interaction design
(Describe the visual encoding and why you decided for it. What interaction types did you use and why?)

### <a name="algorithm"></a>Algorithm design
(How did you make sure that the computational complexity of your solution is appropriate? What is the bottleneck with respect to performance?)

## <a name="validation"></a> Validation
(Validate your design and document lessons learned: Conduct an informal validation with at least one person who has not seen the visualization before. Let the person use the visualization and comment on it (“think aloud”; https://en.wikipedia.org/wiki/Think_aloud_protocol). Try to address the threats mentioned in the Munzner 2009 paper for the first three categories (domain, data/task, and visual encoding / interaction) and summarize the person’s answers. What did you learn from the validation for possible improvements of your visualization?)

## <a name="installation"></a> Installation
(How can I install the visualization project (step-by-step manual)?

## <a name="manual"></a> Manual
(A brief manual about how to use the software. For this it makes sense to use screencasts or screenshots.)

## <a name="contributors"></a> Contributors
Johannes P. and Laura L.

## <a name="copyright"></a> Data copyright
Data derived from original data provided by https://gepris.dfg.de (c) Deutsche Forschungsgemeinschaft
