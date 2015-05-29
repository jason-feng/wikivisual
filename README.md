# wikivisual

The goal of this project is to take a group of Wikipedia pages in the same category, and reateual representation of their importance calculated as Page Rank. Wikipedia has an enormous amount of information that it can be intimidating and difficult to extract immediately the most important pieces of information about a single topic. This project attempts to give users a very quick way to determine what the most essential articles are for a specific Wikipedia category and navigate to their specific points of interest.

I would like to acknowledge Giuseppe Attardi and his wikiextractor project, Jim Vallandignham and his [gates_bubbles project](https://github.com/vlandham/gates_bubbles) and Professor Mikhail Gronas of the Russian Department at Dartmouth and Tim Tregubov of the CS Department at Dartmouth for all of their advice, and Wikipedia for providing me with the dataset that made this project possible. 

----

### visualization

In the home directory there is a index.html page that uses [d3js](d3js.org) to construct a bubble chart visualization. The size of each bubble is based on the Page Rank and colors for each bubble is assigned by the magnitude of the page rank, which is broken down into 3 groups. By clicking on a bubble, you will be taken to the wikipedia page for that article. The visualization is based off the [gates_bubbles project](https://github.com/vlandham/gates_bubbles). 

### data

The data folder contains lists of pageIds of specific categories. These lists were generated by simple SQL queries on the categoryLinks SQL table. The XML dumps and the SQL tables for this project can be found [here](https://dumps.wikimedia.org/enwiki/latest/).

### scripts

pageRank.py is a Python script that extracts all of the pages from our data lists and calculates Page Rank for those pages. 

[extractPage.py](https://github.com/jason-feng/wikivisual/blob/master/scripts/extractPage.py) is a Python script that extracts a Wikipedia page given the page ID. 

The tool is written in Python and requires no additional library.

For further information about extractPage and wikiextractor, see the [project Home Page](http://medialab.di.unipi.it/wiki/Wikipedia_Extractor) or the [Wiki](https://github.com/attardi/wikiextractor/wiki).

This is a beta version that performs template expansion by preprocesssng the whole dump and extracting template definitions.
The current version keeps a cache of parsed templates, achieving a speedup of twice over the previous version.

#### Script Usage
The pageRank.py script is invoked with a Wikipedia dump file as an argument and the data list as the second argument.

    usage: extractPage.py input1 input2

    positional arguments:
      input1		XML wiki dump file
      input2		Datalist	

The extractPage.py script is invoked with a Wikipedia dump file as an argument.

    usage: extractPage.py [--id PAGEID] input

    positional arguments:
      input                 XML wiki dump file
