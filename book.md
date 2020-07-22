--- 
title: "Collecte des Données Web avec R"
author: "Armel SOUBEIGA"
date: "juillet 22, 2020"
site: bookdown::bookdown_site
documentclass: book
bibliography: [library.bib, tools.bib]
biblio-style: apalike
nocite: 
link-citations: yes
description: "This hands-on guide demonstrates how the flexibility of the command line can help you become a more efficient and productive data scientist. You’ll learn how to combine small, yet powerful, command-line tools to quickly obtain, scrub, explore, and model your data."
cover-image: "images/cover.png"
github-repo: "armelsoubeiga/web-scraping-r"
---
--- 
title: "Collecte des Données Web avec R"
author: "Armel SOUBEIGA"
date: "juillet 22, 2020"
site: bookdown::bookdown_site
documentclass: book
bibliography: [library.bib, tools.bib]
biblio-style: apalike
nocite: 
link-citations: yes
description: "This hands-on guide demonstrates how the flexibility of the command line can help you become a more efficient and productive data scientist. You’ll learn how to combine small, yet powerful, command-line tools to quickly obtain, scrub, explore, and model your data."
cover-image: "images/cover.png"
github-repo: "armelsoubeiga/web-scraping-r"
---

# Welcome {-}

This is the website for *Data Science at the Command Line*, published by O'Reilly October 2014 First Edition. This hands-on guide demonstrates how the flexibility of the command line can help you become a more efficient and productive data scientist. You’ll learn how to combine small, yet powerful, command-line tools to quickly obtain, scrub, explore, and model your data.

To get you started---whether you’re on Windows, macOS, or Linux---author [Jeroen Janssens](https://twitter.com/jeroenhjanssens) has developed a [Docker image](https://hub.docker.com/r/datascienceworkshops/data-science-at-the-command-line) packed with over 80 command-line tools.

Discover why the command line is an agile, scalable, and extensible technology. Even if you’re already comfortable processing data with, say, Python or R, you’ll greatly improve your data science workflow by also leveraging the power of the command line.


<img src="images/cover.png" width="349px" class="cover" />


* Obtain data from websites, APIs, databases, and spreadsheets
* Perform scrub operations on text, CSV, HTML/XML, and JSON
* Explore data, compute descriptive statistics, and create visualizations
* Manage your data science workflow
* Create reusable command-line tools from one-liners and existing Python or R code
* Parallelize and distribute data-intensive pipelines
* Model data with dimensionality reduction, clustering, regression, and classification algorithms


> The Unix philosophy of simple tools, each doing one job well, then cleverly piped together, is embodied by the command line. Jeroen expertly discusses how to bring that philosophy into your work in data science, illustrating how the command line is not only the world of file input/output, but also the world of data manipulation, exploration, and even modeling.
>
> **---Chris H. Wiggins**
>
> Associate Professor in the Department of Applied Physics and Applied Mathematics at Columbia University and Chief Data Scientist at *The New York Times*

> This book explains how to integrate common data science tasks into a coherent workflow. It's not just about tactics for breaking down problems, it's also about strategies for assembling the pieces of the solution.
>
> **---John D. Cook**
>
> Consultant in applied mathematics, statistics, and technical computing


If you find this content useful, please consider supporting the work by either:

* Sponsoring the author on [GitHub Sponsors](https://github.com/sponsors/jeroenjanssens/).
* Buying the book on [Amazon](https://www.amazon.com/Data-Science-Command-Line-Time-Tested/dp/1491947853) or [bol.com](https://www.bol.com/nl/p/data-science-at-the-command-line/9200000031673818).
* Writing a review on [Amazon](https://www.amazon.com/Data-Science-Command-Line-Time-Tested/dp/1491947853) or [Goodreads](https://www.goodreads.com/book/show/22967424-data-science-at-the-command-line).
* Starring the [Github repository](https://github.com/jeroenjanssens/data-science-at-the-command-line) or [Docker image](https://hub.docker.com/u/datascienceworkshops/).

This work is licensed under the [Creative Commons Attribution-NoDerivatives 4.0 International License](https://creativecommons.org/licenses/by-nd/4.0/).

<a href="https://datascienceworkshops.com">
<img src="images/data-science-workshops.svg" width="350px" style="display: block; margin: auto;" />
</a>

Did you know that the author provides training about this topic and other topics such as R and Python? If you and your colleagues would like to learn from Jeroen in person, please contact [Data Science Workshops B.V.](https://www.datascienceworkshops.com) for more information.




<!--chapter:end:index.Rmd-->


# Preface {-}

Placeholder


## What to Expect from This Book {-}
## How to Read This Book {-}
## Who This Book Is For {-}
## Acknowledgments {-}
## Dedication {-}
## About the Author {-}

<!--chapter:end:00-preface.Rmd-->


# Introduction {#chapter-1-introduction}

Placeholder


## Overview 
## Data Science is OSEMN 
### Obtaining Data 
### Scrubbing Data 
### Exploring Data 
### Modeling Data 
### Interpreting Data 
## Intermezzo Chapters 
## What is the Command Line? 
## Why Data Science at the Command Line? 
### The Command Line is Agile 
### The Command Line is Augmenting 
### The Command Line is Scalable 
### The Command Line is Extensible 
### The Command Line is Ubiquitous 
## A Real-world Use Case 
## Further Reading 

<!--chapter:end:01.Rmd-->


# Getting Started {#chapter-2-getting-started}

Placeholder


## Overview
## Installing the Docker Image {#docker-image}
## Essential GNU/Linux Concepts
### The Environment
### Executing a Command-line Tool
### Five Types of Command-line Tools
### Combining Command-line Tools
### Redirecting Input and Output
### Working With Files
### Help!
## Further Reading

<!--chapter:end:02.Rmd-->

# Methods

We describe our methods in this chapter.

<!--chapter:end:03-method.Rmd-->


# Obtaining Data {#chapter-3-obtaining-data}

Placeholder


## Overview 
## Copying Local Files to the Data Science Toolbox
### Local Version of Data Science Toolbox 
### Remote Version of Data Science Toolbox 
## Decompressing Files 
## Converting Microsoft Excel Spreadsheets
## Querying Relational Databases
## Downloading from the Internet
## Calling a Web API 
## Further Reading 

<!--chapter:end:03.Rmd-->


# Creating Reusable Command-line Tools {#chapter-4-creating-reusable-command-line-tools}

Placeholder


## Overview 
## Converting One-liners into Shell Scripts 
### Step 1: Copy and Paste 
### Step 2: Add Permission to Execute 
### Step 3: Define Shebang 
### Step 4: Remove Fixed Input 
### Step 5: Parametrize 
### Step 6: Extend Your PATH 
## Creating Command-line Tools with Python and R 
### Porting The Shell Script 
### Processing Streaming Data from Standard Input 
## Further Reading 

<!--chapter:end:04.Rmd-->


# Scrubbing Data {#chapter-5-scrubbing-data}

Placeholder


## Overview 
## Common Scrub Operations for Plain Text 
### Filtering Lines 
#### Based on Location 
#### Based on Pattern 
#### Based on Randomness 
### Extracting Values 
### Replacing and Deleting Values 
## Working with CSV 
### Bodies and Headers and Columns, Oh My! 
### Performing SQL Queries on CSV 
## Working with XML/HTML and JSON 
## Common Scrub Operations for CSV 
### Extracting and Reordering Columns 
### Filtering Lines 
### Merging Columns 
### Combining Multiple CSV Files 
#### Concatenate Vertically 
#### Concatenate Horizontally 
#### Joining 
## Further Reading 

<!--chapter:end:05.Rmd-->


# Managing Your Data Workflow {#chapter-6-managing-your-data-workflow}

Placeholder


## Overview 
## Introducing Drake 
## Installing Drake 
## Obtain Top E-books from Project Gutenberg 
## Every Workflow Starts with a Single Step 
## Well, That Depends 
## Rebuilding Certain Targets 
## Discussion 
## Further Reading 

<!--chapter:end:06.Rmd-->


# Exploring Data {#chapter-7-exploring-data}

Placeholder


## Overview 
## Inspecting Data and its Properties 
### Header Or Not, Here I Come 
### Inspect All The Data 
### Feature Names and Data Types 
### Unique Identifiers, Continuous Variables, and Factors 
## Computing Descriptive Statistics 
### csvstat 
### Using R from the Command Line using Rio 
## Creating Visualizations 
### Introducing Gnuplot and Feedgnuplot 
### Introducing ggplot2 
### Histograms 
### Bar Plots 
### Density Plots 
### Box Plots 
### Scatter Plots 
### Line Graphs 
### Summary 
## Further Reading 

<!--chapter:end:07.Rmd-->


# Parallel Pipelines {#chapter-8-parallel-pipelines}

Placeholder


## Overview 
## Serial Processing 
### Looping Over Numbers 
### Looping Over Lines 
### Looping Over Files 
## Parallel Processing 
### Introducing GNU Parallel 
### Specifying Input 
### Controlling the Number of Concurrent Jobs 
### Logging and Output 
### Creating Parallel Tools 
## Distributed Processing 
### Get List of Running AWS EC2 Instances 
### Running Commands on Remote Machines 
### Distributing Local Data among Remote Machines 
### Processing Files on Remote Machines 
## Discussion 
## Further Reading 

<!--chapter:end:08.Rmd-->


# Modeling Data {#chapter-9-modeling-data}

Placeholder


## Overview 
## More Wine Please! 
## Dimensionality Reduction with Tapkee 
### Introducing Tapkee 
### Installing Tapkee 
### Linear and Non-linear Mappings 
## Clustering with Weka 
### Introducing Weka 
### Taming Weka on the Command Line 
#### An Improved Command-line Tool for Weka 
#### Usable Weka Classes 
#### Adding Tab Completion 
### Converting between CSV to ARFF Data Formats 
### Comparing Three Cluster Algorithms 
## Regression with SciKit-Learn Laboratory 
### Preparing the Data 
### Running the Experiment 
### Parsing the Results 
## Classification with BigML 
### Creating Balanced Train and Test Data Sets 
### Calling the API 
### Inspecting the Results 
### Conclusion 
## Further Reading 

<!--chapter:end:09.Rmd-->


# Conclusion {#chapter-10-conclusion}

Placeholder


## Let's Recap 
## Three Pieces of Advice 
### Be Patient 
### Be Creative 
### Be Practical 
## Where To Go From Here? 
### APIs 
### Shell Programming 
### Python, R, and SQL 
### Interpreting Data 
## Getting in Touch 

<!--chapter:end:10.Rmd-->

# References {-}

<!--chapter:end:12-references.Rmd-->

