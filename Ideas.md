## PROJECT IDEAS

### 1. Developing a novel format for phylogenomic data


#### Background
Phylogenetic trees are usually encoded using the so called Newick format. While convenient, this format has limitations to store metadata associated to the different nodes in a tree. Some alternative formats exist (NeXML, PhyloXML, Nexus) which are already supported by the ETE toolkit.  However, none of those formats is optimal to i) encode ETE graphical properties associated to nodes ii) store large trees or huge collections of trees iii) access metadata from large datasets in an indexed way.
 
In addition, a community of developers specialized in tree visualization software is brainstorming about possible ways to make the process of composing and sharing figures more portable and transparent. It is expected that this project keeps in sync with the expected outcome of such meetings and provide support for the conventions and tree annotation vocabulary agreed.

#### Goals
- Develop a data format capable of storing trees, metadata and graphical features associated to nodes. The following features are ambitioned: Tree structure and node metadata indexing, data compression, possibility of having multiple trees in a file, possibility of exporting in plain text, portability.
- Integrate the format into ETE, so annotated ETE trees (including graphical features) can be read, exported and exchanged with ease. 
- Develop basic converters from most common formats to date: i.e. Newick, Extended Newick and Nexus. 

#### Possible approaches
Use SQLite: See this prototype API implementation currently used to store and query a very large tree
Use a novel data format based indexing a tabular tree format
  
#### Difficulty
Medium

#### Languages and skills
Good Python programming skills
Experience on Object Oriented Programming in Python

#### Mentors
Jaime Huerta-Cepas (EMBL, Germany)
Francois Serra (CNAG-CRG, Spain)

### 2. Improve the usability of the command line tools and develop a (web?) Graphical User Interface (GUI) to execute jobs 

#### Background
ETE-build is a command line tool that provides a unified interface for the  reproducible execution of complex phylogenetic workflows. Those workflows are composed of several steps that require calling multiple third-party programs as well as parsing and processing results. At the moment, ETE-build can be used to easily execute those workflows with a single command line. All the required tasks are then handled by an internal scheduling system, so third party software is executed transparently.

#### Goals
- Developing a graphical user interface that allows to run workflows and visualize results 
- Adding windows support (currently only Linux and OSX are officially supported). 
- Fixing and improving known issues in the scheduling and pipeline system
- Adding new workflows and application bindings. 

#### Difficulty
Medium
#### Languages and skills
- Good Python programming skills
- Experience on Object Oriented Programming in Python
- Some tasks will require basic understanding of the phylogenetic reconstruction process. 

#### Mentors
Jaime Huerta-Cepas (EMBL, Germany)


### 3. Data visualization: developing a gallery of predefined tree layouts targeting publication ready figures

#### Background
Although the syntax of ETE’s tree rendering engine is highly flexible and allows creating a variety of complex tree visualizations, this usually involves substantial scripting work. Predefined layouts could be provided in the form of ETE python scripts, that permit to style trees according to most common usages. For instance, the following tree figures could be entirely renderable using ETE, but not predefined scripts exist yet for that purpose: 

#### Goals
- Develop a gallery of layouts in the form of Python scripts that cover most common visualizations in phylogenetics, including 
- Selection of good color schemes
- Deciding what graphical features to show or hide depending on context
- Improve ETE’s rendering system, so multiple layouts can be applied as semantic layers. For instance:
- TreeStyle.layout = [block_alignment_layout, color_duplication_nodes_layout, ….] 
#### Difficulty
Easy (from a programming point of view, but good graphical designing skills necessary)
#### Languages and skills
- Good Python programming skills
- Experience on Object Oriented Programming in Python
- Good in data visualization

#### Mentors 
Jaime Huerta-Cepas (EMBL, Germany)
Francois Serra (CNAG-CRG, Spain)
Renato Alves (EMBL, Germany)

### 4. Tree searching using regular-expression-like queries
#### Background
Although several methods allow comparing trees using ETE, no search capabilities exist that permit to query tree topologies for specific patterns. The goal of this project is to develop a new ETE module that allows querying large collections of trees using custom criteria. Searches should be flexible and allow for regular-expression-like queries, returning a list of all internal nodes in the matching trees where the criteria is fulfilled.
Applications of the framework would enable any user to perform complex queries on a variety of tree-like data in research, such as clustering results and phylogenetic trees. This is specially relevant in the Phylogenomics field (ETE focus), where thousands of phylogenetic trees are being generated and scanned for specific evolutionary patterns. Based on previous ETE developments and last-year GSoC work, a prototype tree-matcher program exists, which provides basic functionality and examples. 
#### Goals
- Improve the tree-matcher module to permit searching for complex patterns (i.e. allow for complex queries using wildcards)  
- Improve and extend the tree search command line tool
- Integrate tree-matcher as a new ETE module, including complete unitests and documentation.
- Optional: Develop a visualization framework based on ETE’s tree rendering engine to display tree matches and differences.
#### Difficulty
Medium
#### Languages and skills
- All code should be written in Python, with compatibility for Py2 and Py3.
- Skills required:
  - Good Python programming skills
  - Experience on Object Oriented Programming in Python
- Familiarity with the Newick Tree format and the concept of phylogenetic gene trees (i.e. see this)
- Familiarity with tree related algorithms (i.e. tree traversing, tree comparison)
- Optional (for addressing visualization): familiarity of Qt4 drawing system (QGraphicsScenes)
#### Mentors
Francois Serra (CNAG-CRG, Spain)
Jaime Huerta-Cepas (EMBL, Germany)
Łukasz Roguski (CNAG-CRG, Spain)
Renato Alves (EMBL, Germany)
