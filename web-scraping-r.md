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



\includegraphics[width=349px,class="cover"]{images/cover} 


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

\begin{center}\includegraphics[width=350px]{images/data-science-workshops} \end{center}
</a>

Did you know that the author provides training about this topic and other topics such as R and Python? If you and your colleagues would like to learn from Jeroen in person, please contact [Data Science Workshops B.V.](https://www.datascienceworkshops.com) for more information.




<!--chapter:end:index.Rmd-->

# Preface {-}

Data science is an exciting field to work in. It’s also still very young. Unfortunately, many people, and especially companies, believe that you need new technology in order to tackle the problems posed by data science. However, as this book demonstrates, many things can be accomplished by using the command line instead, and sometimes in a much more efficient way.

Around five years ago, during my PhD program, I gradually switched from using Microsoft Windows to Linux. Because it was a bit scary at first, I started with having both operating systems installed next to each other (known as dual-boot). The urge to switch back and forth between Microsoft Windows faded and at some point I was even tinkering around with Arch Linux, which allows you to build up your own custom Linux machine from scratch. All you’re given is the command line, and it’s up to you what you want to make of it. Out of necessity I quickly became very comfortable using the command line. Eventually, as spare time got more precious, I settled down with a Linux distribution known as Ubuntu because of its ease of use and large community. However, the command line is still where I’m spending most of time.

It actually hasn’t been too long ago that I realized that the command line is not just for installing software, system configuration, and searching files. I started learning about command-line tools such as `cut`, `sort`, and `sed`. These are examples of command-line tools that take data as input, do something to it, and print the result. Ubuntu comes with quite a few of them. Once I understood the potential of combining these small tools, I was hooked.

After my PhD, when I became a data scientist, I wanted to use this approach to do data science as much as possible. Thanks to a couple of new, open-source command-line tools including `xml2json`, `jq`, and `json2csv` I was even able to use the command line for tasks such as scraping websites and processing lots of JSON data. In September 2013, I decided to write a blog post titled *Seven Command-line Tools for Data Science*, which is available at <http://www.jeroenjanssens.com/2013/09/19/seven-command-line-tools-for-data-science.html>. To my surprise, the blog post got quite some attention and I received a lot of suggestions of other command-line tools. I started wondering whether this blog post could be turned into a book. I’m pleased that, some ten months later, with the help of many talented people (see the acknowledgments below), the answer is a yes.

I am sharing this personal story not so much because I think you should know how this book came about, but because I want to you know that I had to learn about the command line as well. Because the command line is so different from using a graphical user interface, it can seem scary at first. But if I can learn it, then you can as well. No matter what your current operating system is and no matter how you currently work with data, after reading this book you will be able to do data science at the command line. If you’re already familiar with the command line, or even if you’re already dreaming in shell scripts, chances are that you’ll still discover a few interesting tricks or command-line tools to use for your next data science project.

## What to Expect from This Book {-}

In this book, we’re going to obtain, scrub, explore, and model data - a lot of it. This book is not so much about how become *better* at those data science tasks. There are already great resources available that discuss, for example, when to apply which statistical test or how data can be best visualized. Instead, this practical book aims to make you more *efficient* and *productive* by teaching you how to perform those data science tasks at the command line.

While this book discusses over 80 command-line tools, it’s not the tools themselves that matter most. Some command-line tools have been around for a very long time, while others will be replaced by better ones. There are even command-line tools that are being created as you’re reading this. In the past nine months, I have discovered many amazing command-line tools. Unfortunately, some of them were discovered too late to be included in the book. In short, command-line tools come and go. But that’s OK.

What matters most is the underlying idea of working with tools, pipes, and data. Most of the command-line tools do one thing and do it well. This is part the UNIX philosophy, which makes several appearances throughout the book. Once you become familiar with the command line, know how to combine command-line tools, and can even create new ones, you have developed an invaluable skill.

## How to Read This Book {-}

In general, you’re advised to read this book in a linear fashion. Once a concept or command-line tool has been introduced, chances are that we employ it in a later chapter. For example, in Chapter 9, we make heavy use of `parallel`, which is introduced extensively in Chapter 8.

Data science is a broad field that intersects many other fields such as programming, data visualization, and machine learning. As a result, this book touches on many interesting topics which unfortunately cannot be discussed at full length. Throughout the book, there are suggestions for additional reading. It’s not required to read this material in order to follow along with the book, but when you are interested, you know that there’s much more to learn.

## Who This Book Is For {-}

This book makes just one assumption about you: that you work with data. It doesn’t matter which programming language or statistical computing environment you’re currently using. The book explains all the necessary concepts from the beginning.

It also doesn’t matter whether your operating system is Microsoft Windows, MacOS, or some form of Linux. The book comes with a Docker image, which is an easy-to-install virtual environment. It allows you to run the command-line tools and follow along with the code examples in the same environment as this book was written. You don’t have to waste time figuring out how to install all the command-line tools and their dependencies.

The book contains some code in Bash, Python, and R so it’s helpful if you have some programming experience, but it’s by no means required to follow along with the examples.


## Acknowledgments {-}

First of all, I’d like to thank Mike Dewar and Mike Loukides for believing that my blog post [Seven Command-Line Tools for Data Science](http://jeroenjanssens.com/2013/09/19/seven-command-line-tools-for-data-science.html), which I wrote in September 2013, could be expanded into a book.

Special thanks to my technical reviewers Mike Dewar, Brian Eoff, and Shane Reustle for reading various drafts, meticulously testing all the commands, and providing invaluable feedback. Your efforts have improved the book greatly. The remaining errors are entirely my own responsibility.

I had the privilege of working together with three amazing editors, namely: Ann Spencer, Julie Steele, and Marie Beaugureau. Thank you for your guidance and for being such great liaisons with the many talented people at O’Reilly. Those people include: Laura Baldwin, Huguette Barriere, Sophia DeMartini, Yasmina Greco, Rachel James, Ben Lorica, Mike Loukides, and Christopher Pappas. There are many others whom I haven’t met because they are operating behind the scenes. Together they ensured that working with O’Reilly has truly been a pleasure.

This book discusses over 80 command-line tools. Needless to say, without these tools, this book wouldn’t have existed in the first place. I’m therefore extremely grateful to all the authors who created and contributed to these tools. The complete list of authors is unfortunately too long to include here; they are mentioned in the Appendix. Thanks especially to Aaron Crow, Jehiah Czebotar, Christoph Groskopf, Dima Kogan, Sergey Lisitsyn, Francisco J. Martin, and Ole Tange for providing help with their amazing command-line tools.

Eric Postma and Jaap van den Herik, who supervised me during my PhD program, deserve a special thank you. Over the course of five years they have taught me many lessons. Although writing a technical book is quite different from writing a PhD thesis, many of those lessons proved to be very helpful in the past nine months as well.

Finally, I’d like to thank my colleagues at YPlan, my friends, my family, and especially my wife Esther for supporting me and for pulling me away from the command line at just the right times.

## Dedication {-}

*To my wife, Esther. Without her encouragement, support, and patience, this book would surely have ended up in `/dev/null`.*


## About the Author {-}


[Jeroen Janssens](http://jeroenjanssens.com/) is the founder and CEO of [Data Science Workshops](https://datascienceworkshops.com), which provides on-the-job training and coaching in data visualisation, machine learning, and programming. Previously, he was an assistant professor at Jheronimus Academy of Data Science and a data scientist at Elsevier in Amsterdam and startups YPlan and Outbrain in New York City. He is the author of Data Science at the Command Line, published by O’Reilly Media. Jeroen holds a PhD in machine learning from Tilburg University and an MSc in artificial intelligence from Maastricht University. He can be found on [Twitter](https://twitter.com/jeroenhjanssens/), [LinkedIn](http://www.linkedin.com/in/jeroenjanssens), and [GitHub](https://github.com/jeroenjanssens).


<!--chapter:end:00-preface.Rmd-->

# Introduction {#chapter-1-introduction}

This book is about doing data science at the command line. Our aim is to make you a more efficient and productive data scientist by teaching you how to leverage the power of the command line. 

Having both the terms "data science" and "command line" in the title requires an explanation. How can a technology that is over 40 years old[^1] be of any use to a field that is only a few years young?

Today, data scientists can choose from an overwhelming collection of exciting technologies and programming languages. Python, R, Hadoop, Julia, Pig, Hive, and Spark are but a few examples. You may already have experience in one or more of these. If so, then why should you still care about the command line for doing data science? What does the command line have to offer that these other technologies and programming languages do not?

These are all valid questions. In this first chapter we will answer these questions as follows. First, we provide a practical definition of data science that will act as the backbone of this book. Second, we'll list five important advantages of the command line. Third, we demonstrate the power and flexibility of the command line through a real-world use case. By the end of this chapter we hope to have convinced you that the command line is indeed worth learning for doing data science.

## Overview 

In this chapter, you’ll learn:

- A practical definition of data science
- What the command line is exactly and how you can use it
- Why the command line is a wonderful environment for doing data science

## Data Science is OSEMN 

The field of data science is still in its infancy, and as such, there exist various definitions of what it encompasses. Throughout this book we employ a very practical definition by @Mason2010. They define data science according to the following five steps: (1) obtaining data, (2) scrubbing data, (3) exploring data, (4) modeling data, and (5) interpreting data. Together, these steps form the OSEMN model (which is pronounced as *awesome*). This definition serves as the backbone of this book because each step, (except step 5, interpreting data, which we explain below) has its own chapter. Below we explain what each step entails.

\BeginKnitrBlock{rmdcomment}
Although the five steps are discussed in a linear and incremental fashion, in practice it is very common to move back and forth between them or to perform multiple steps at the same time. Doing data science is an iterative and non-linear process. For example, once you have modeled your data, and you look at the results, you may decide to go back to the scrubbing step to the adjust the features of the data set.
\EndKnitrBlock{rmdcomment}

### Obtaining Data 

Without any data, there is little data science you can do. So the first step is the obtain data. Unless you are fortunate enough to already possess data, you may need to do one or more of the following:

- Download data from another location (e.g., a webpage or server)
- Query data from a database or API (e.g., MySQL or Twitter)
- Extract data from another file (e.g., an HTML file or spreadsheet)
- Generate data yourself (e.g., reading sensors or taking surveys)

In [Chapter 3](#chapter-3-obtaining-data), we discuss several methods for obtaining data using the command line. The obtained data will most likely be in either text, CSV, JSON of HTML/XML format. The next step is to scrub this data.

### Scrubbing Data 

It is not uncommon that the obtained data has missing values, inconsistencies, errors, weird characters, or uninteresting columns. In that case, you have to *scrub*, or clean, the data before you can do anything interesting with it. Common scrubbing operations include:

- Filtering lines
- Extracting certain columns
- Replacing values
- Extracting words
- Handling missing values
- Converting data from one format to another

While we data scientists love to create exciting data visualizations and insightful models (steps 3 and 4), usually much effort goes into obtaining and scrubbing the required data first (steps 1 and 2). In *Data Jujitsu*, @Patil2012 states that "80% of the work in any data project is in cleaning the data". In [Chapter 5](#chapter-5-scrubbing-data), we demonstrate how the command line can help accomplish such data scrubbing operations.

### Exploring Data 

Once you have scrubbed your data, you are ready to explore it. This is where it gets interesting because here you will get really into your data. In [Chapter 7](#chapter-7-exploring-data) we show you how the command line can be used to:

- Look at your data
- Derive statistics from your data
- Create interesting visualizations

Command-line tools introduced in [Chapter 7](#chapter-7-exploring-data) include: `csvstat` [@csvstat], `feedgnuplot` [@feedgnuplot], and `Rio` [@Rio].

### Modeling Data 

If you want to explain the data or predict what will happen, you probably want to create a statistical model of your data. Techniques to create a model include clustering, classification, regression, and dimensionality reduction. The command line is not suitable for implementing a new model from scratch. It is, however, very useful to be able to build a model from the command line. In [Chapter 9](#chapter-9-modeling-data) we will introduce several command-line tools that either build a model locally or employ an API to perform the computation in the cloud.

### Interpreting Data 

The final and perhaps most important step in the OSEMN model is interpreting data. This step involves:

- Drawing conclusions from your data
- Evaluating what your results mean
- Communicating your result

To be honest, the computer is of little use here, and the command line does not really come into play at this stage. Once you have reached this step, it is up to you. This is the only step in the OSEMN model which does not have its own chapter. Instead, we kindly refer you to *Thinking with Data* by @Shron2014.

## Intermezzo Chapters 

In between the chapters that cover the OSEMN steps, there are three intermezzo chapters. Each intermezzo chapter discusses a more general topic concerning data science, and how the command line is employed for that. These topics are applicable to any step in the data science process.

In [Chapter 4](#chapter-4-creating-reusable-command-line-tools), we discuss how to create reusable tools for the command line. These personal tools can come from both long commands that you have typed on the command line, or from existing code that you have written in, say, Python or R. Being able to create your own tools allows you to become more efficient and productive.

Because the command line is an interactive environment for doing data science, it can become challenging to keep track of your workflow. In [Chapter 6](#chapter-6-managing-your-data-workflow), we demonstrate a command-line tool called Drake [@drake], which allows you to define your data science workflow in terms of tasks and the dependencies between them. This tool increases the reproducibility of your workflow, not only for you but also for your colleagues and peers.

In [Chapter 8](#chapter-8-parallel-pipelines), we explain how your commands and tools can be sped up by running them in parallel. Using a command-line tool called GNU Parallel [@parallel], we can apply command-line tools to very large data sets and run them on multiple cores and remote machines.

## What is the Command Line? 

Before we discuss *why* you should use the command line for data science, let's take a peek at *what* the command line actually looks like (it may be already familiar to you). Figure \@ref(fig:mac-terminal) and Figure \@ref(fig:ubuntu-terminal) show a screenshot of the command line as it appears by default on macOS and Ubuntu, respectively. Ubuntu is a particular distribution of GNU/Linux, which we’ll be assuming throughout the book.

\begin{figure}

{\centering \includegraphics[width=9.5in]{images/screenshot_terminal_mac_dst} 

}

\caption{Command line on macOS}(\#fig:mac-terminal)
\end{figure}

\begin{figure}

{\centering \includegraphics[width=10.06in]{images/screenshot_terminal_ubuntu_dst} 

}

\caption{Command line on Ubuntu}(\#fig:ubuntu-terminal)
\end{figure}

The window shown in the two screenshots is called the terminal. This is the program that enables you to interact with the shell. It is the shell that executes the commands we type in. (On both Ubuntu and macOS, the default shell is Bash.)

\BeginKnitrBlock{rmdnote}
We’re not showing the Microsoft Windows command line (also known as the Command Prompt or PowerShell), because it's fundamentally different and incompatible with the commands presented in this book. The good news is that you can install the Data Science Toolbox on Microsoft Windows, so that you’re able to follow along. How to install the Data Science Toolbox is explained in [Chapter 2](#chapter-2-getting-started).
\EndKnitrBlock{rmdnote}

Typing commands is a very different way of interacting with your computer than through a graphical user interface. If you are mostly used to processing data in, say, Microsoft Excel, then this approach may seem intimidating at first. Don’t be afraid. Trust us when we say that you’ll get used to working at the command line very quickly.

In this book, the commands that we type in, and the output that they generate, is displayed as text. For example, the contents of the terminal (after the welcome message) in the two screenshots would look like this:


```bash
$ whoami
vagrant
$ hostname
data-science-toolbox
$ date
Tue Jul 22 02:52:09 UTC 2014
$ echo 'The command line is awesome!' | cowsay
 ______________________________
< The command line is awesome! >
 ------------------------------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```

You’ll also notice that each command is preceded with a dollar sign (**$**). This is called the prompt. The prompt in the two screenshots showed more information, namely the username (`vagrant`), the hostname (`data-science-toolbox`) and the current working directory (`\~`). It’s a convention to show only a dollar sign in examples, because the prompt (1) can change during a session (when you go to a different directory), (2) can be customized by the user (e.g., it can also show the time or the current `git` [@git] branch you’re working on), and (3) is irrelevant for the commands themselves.

In the next chapter we’ll explain much more about essential command-line concepts. Now it’s time to first explain *why* you should learn to use the command line for doing data science.

## Why Data Science at the Command Line? 

The command line has many great advantages that can really make you a more efficient and productive data scientist. Roughly grouping the advantages, the command line is: agile, augmenting, scalable, extensible, and ubiquitous. We elaborate on each advantage below.

### The Command Line is Agile 

The first advantage of the command line is that it allows you to be agile. Data science has a very interactive and exploratory nature, and the environment that you work in needs to allow for that. The command line achieves this by two means.

First, the command line provides a so-called read-eval-print-loop (REPL). This means that you type in command, press **<Enter>**, and the command is evaluated immediately. A REPL is often much more convenient for doing data science than the edit-compile-run-debug cycle associated with scripts, large programs, and, say, Hadoop jobs. Your commands are executed immediately, may be stopped at will, and can be changed quickly. This short iteration cycle really allows you to play with your data.

Second, the command line is very close to the file system. Because data is the main ingredient for doing data science, it is important to be able to easily work with the files that contain your data set. The command line offers many convenient tools for this.

### The Command Line is Augmenting 

Whatever technology your data science workflow currently includes (whether it's R, IPython, or Hadoop), you should know that we’re not suggesting you abandon that workflow. Instead, the command line is presented here as an augmenting technology that amplifies the technologies you’re currently employing.

The command line integrates well with other technologies. On the one hand, you can often employ the command line from your own environment. Python and R, for instance, allow you to run command-line tools and capture their output. On the other hand, you can turn your code (e.g., a Python or R function that you have already written) into a command-line tool. We will cover this extensively in [Chapter 4](#chapter-4-creating-reusable-command-line-tools). Moreover, the command line can easily cooperate with various databases and file types such as Microsoft Excel.

In the end, every technology has its advantages and disadvantages (including the command line), so it’s good to know several and use whichever is most appropriate for the task at hand. Sometimes that means using R, sometimes the command line, and sometimes even pen and paper. By the end of this book you’ll have a solid understanding of when you could use the command line, and when you’re better off continuing with your favorite programming language or statistical computing environment.

### The Command Line is Scalable 

Working on the command line is very different from using a graphical user interface (GUI). On the command line you do things by typing, whereas with a GUI, you do things by pointing and clicking with a mouse.

Everything that you type manually on the command line, can also be automated through scripts and tools. This makes it very easy to re-run your commands in case you made a mistake, when the data set changed, or because your colleague wants to perform the same analysis. Moreover, your commands can be run at specific intervals, on a remote server, and in parallel on many chunks of data (more on that in Chapter 8).

Because the command line is automatable, it becomes scalable and repeatable. It is not straightforward to automate pointing and clicking, which makes a GUI a less suitable environment for doing scalable and repeatable data science.

### The Command Line is Extensible 

The command line itself was invented over 40 year ago. Its core functionality has largely remained unchanged, but the *tools*, which are the workhorses of the command-line, are being developed on a daily basis.

The command line itself is language agnostic. This allows the command-line tools to be written in many different programming languages. The open source community is producing many free and high-quality command-line tools that we can use for data science.

These command-line tools can work together, which makes the command line very flexible. You can also create your own tools, allowing you to extending the effective functionality of the command line.

### The Command Line is Ubiquitous 

Because the command line comes with any Unix-like operating system, including Ubuntu Linux and macOS, it can be found in many places. According to [an article on Top 500 Supercomputer Sites](http://top500.org/blog/lists/2013/11/press-release), 95% of the top 500 supercomputers are running GNU/Linux. So, if you ever get your hands on one of those supercomputers (or if you ever find yourself in Jurassic Park with the doors locks not working), you better know your way around the command line!

But GNU/Linux not only runs on supercomputers. It also runs on servers, laptops, and embedded systems. These days, many companies offer cloud computing, where you can easily launch new machines on the fly. If you ever log in to such a machine (or a server in general), there’s a good chance that you’ll arrive at the command line.

Besides mentioning that the command line is available in a lot of places, it is also important to note that the command line is not a hype. This technology has been around for more than four decades, and we're personally convinced that it's here to stay for another four. Learning how to use the command line (for data science) is therefore a worthwhile investment.

## A Real-world Use Case 

In the previous sections, we’ve given you a definition of data science and explained to you why the command line can be a great environment for doing data science. Now it’s time to demonstrate the power and flexibility of the command line through a real-world use case. We'll go pretty fast, so don't worry if some things don't make sense yet.

Personally, we never seem to remember when Fashion Week is happening in New York. We know it’s held twice a year, but every time it comes as a surprise! In this section we’ll consult the wonderful API of *The New York Times* to figure out when it's being held. Once you have obtained your own API keys on [the developer website](http://developer.nytimes.com), you’ll be able to, for example, search for articles, get the list of best sellers, and see a list of events.

The particular API endpoint that we’re going to query is the article search one. We expect that a spike in the amount of coverage in *The New York Times* about New York Fashion week indicates whether it’s happening. The results from the API are paginated, which means that we have to execute the same query multiple times but with different page number. (It’s like clicking Next on a search engine.) This is where GNU Parallel [@parallel] comes in real handy because it can act as a `for` loop. The entire command looks as follows (don’t worry about all the command-line arguments given to `parallel`; we’re going to discuss this in great detail in [Chapter 8](#parallel-pipelines]):


```bash
$ cd ~/book/ch01/data
$ parallel -j1 --progress --delay 0.1 --results results "curl -sL "\
> "'http://api.nytimes.com/svc/search/v2/articlesearch.json?q=New+York+'"\
> "'Fashion+Week&begin_date={1}0101&end_date={1}1231&page={2}&api-key='"\
> "'<your-api-key>'" ::: {2009..2013} ::: {0..99} > /dev/null

Computers / CPU cores / Max jobs to run
1:local / 4 / 1

Computer:jobs running/jobs completed/%of started jobs/Average seconds to complete
local:1/9/100%/0.4s
```

Basically, we’re performing the same query for years 2009-2014. The API only allows up to 100 pages (starting at 0) per query, so we’re generating 100 numbers using brace expansion. These numbers are used by the *page* parameter in the query. We’re searching for articles that contain the search term `New+York+Fashion+Week`. Because the API has certain limits, we ensure that there’s only one request at a time, with a one-second delay between them. Make sure that you replace `<your-api-key>` with your own API key for the article search endpoint.

Each request returns 10 articles, so that’s 1,000 articles in total. These are sorted by page views, so this should give us a good estimate of the coverage. The results are in JSON format, which we store in the *results* directory. The command-line tool `tree` [@tree] gives an overview of how the subdirectories are structured:


```bash
$ tree results | head
results
└── 1
    ├── 2009
    │   └── 2
    │       ├── 0
    │       │   ├── stderr
    │       │   └── stdout
    │       ├── 1
    │       │   ├── stderr
    │       │   └── stdout
```

We can combine and process the results using `cat` [@cat], `jq` [@jq], and `json2csv` [@json2csv]:


```bash
$ cat results/1/*/2/*/stdout |                                             
> jq -c '.response.docs[] | {date: .pub_date, type: .document_type, '\     
> 'title: .headline.main }' | json2csv -p -k date,type,title > fashion.csv 
```

Let’s break down this command:

- We combine the output of each of the 500 `parallel` jobs (or API requests).
- We use `jq` to extract the publication date, the document type, and the headline of each article.
- We convert the JSON data to CSV using `json2csv` and store it as *fashion.csv*.

With `wc -l` [@wc], we find out that this data set contains 4,855 articles (and not 5,000 because we probably retrieved everything from 2009):


```bash
$ wc -l fashion.csv
4856 fashion.csv
```

Let’s inspect the first 10 articles to verify that we have succeeded in obtaining the data. Note that we’re applying `cols` [@cols] and `cut` [@cut] to the *date* column in order to leave out the time and timezone information in the table:


```bash
$ < fashion.csv cols -c date cut -dT -f1 | head | csvlook
|-------------+------------+-----------------------------------------|
|  date       | type       | title                                   |
|-------------+------------+-----------------------------------------|
|  2009-02-15 | multimedia | Michael Kors                            |
|  2009-02-20 | multimedia | Recap: Fall Fashion Week, New York      |
|  2009-09-17 | multimedia | UrbanEye: Backstage at Marc Jacobs      |
|  2009-02-16 | multimedia | Bill Cunningham on N.Y. Fashion Week    |
|  2009-02-12 | multimedia | Alexander Wang                          |
|  2009-09-17 | multimedia | Fashion Week Spring 2010                |
|  2009-09-11 | multimedia | Of Color | Diversity Beyond the Runway  |
|  2009-09-14 | multimedia | A Designer Reinvents Himself            |
|  2009-09-12 | multimedia | On the Street | Catwalk                 |
|-------------+------------+-----------------------------------------|
```

That seems to have worked! In order to gain any insight, we’d better visualize the data. Figure \@ref(fig:fashion-week) contains a line graph created with R [@R], `Rio` [@Rio], and `ggplot2` [@Wickham2009].


```bash
$ < fashion.csv Rio -ge 'g + geom_freqpoly(aes(as.Date(date), color=type), '\
> 'binwidth=7) + scale_x_date() + labs(x="date", title="Coverage of New York'\
> ' Fashion Week in New York Times")' | display
```

\begin{figure}

{\centering \includegraphics[width=32.81in]{images/nyt-fashion-week-multi} 

}

\caption{Coverage of New York Fashion Week in the New York Times}(\#fig:fashion-week)
\end{figure}

By looking at the line graph we can infer that New York Fashion Week happens two times per year. And now we know when: once in February and once in September. Let’s hope that it’s going to be the same this year so that we can prepare ourselves! In any case, we hope that with this example, we’ve shown that *The New York Times* API is an interesting source of data. More importantly, we hope that we’ve convinced you that the command line can be a very powerful approach for doing data science.

In this section we’ve peeked at some important concepts and some exciting command-line tools. Don’t worry if some things don’t make sense yet. Most of the concepts will be discussed in [Chapter 2](#chapter-2-getting-started), and in the subsequent chapters we’ll go into more detail for all the command-line tools used in this section.

## Further Reading 

* Mason, Hilary, and Chris H. Wiggins. 2010. “A Taxonomy of Data Science.” <a href="http://www.dataists.com/2010/09/a-taxonomy-of-data-science" class="uri">http://www.dataists.com/2010/09/a-taxonomy-of-data-science</a>.
* Patil, DJ. 2012. <em>Data Jujitsu</em>. O’Reilly Media.
* O'Neil, C. \& Schutt, R. 2013. <em>Doing Data Science</em>. O'Reilly Media.
* Shron, Max. 2014. <em>Thinking with Data</em>. O’Reilly Media.


[^1]: The development of the UNIX operating system [started back in 1969](http://www.unix.org/what_is_unix/history_timeline.html). It featured a command line since the beginning, and the important concept of pipes was added in 1973.

<!--chapter:end:01.Rmd-->

# Getting Started {#chapter-2-getting-started}

In this chapter we are going to make sure that you have all the prerequisites for doing data science at the command line. The prerequisites fall into two parts: (1) having a proper environment with all the command-line tools that we employ in this book installed, and (2) understanding the essential concepts that come into play when using the command line.

First, we describe how to install the Docker image, which is a virtual environment based on Linux that contains all the necessary command-line tools. Subsequently, we explain the essential command-line concepts through examples.

By the end of this chapter, you’ll have everything you need in order to continue with the first step of doing data science, namely obtaining data.

## Overview

In this chapter, you’ll learn:

- How to install the Docker image.
- Essential concepts and tools necessary to perform data science at the command line.

## Installing the Docker Image {#docker-image}

\BeginKnitrBlock{rmdnote}
This section used to be called *Setting up the Data Science Toolbox* and described how to install a Vagrant box containing all the command-line tools. This Vagrant box was created in 2014, and because technology around virtualisation and containerisation has moved on, it became high time for an update. So now, instead of a Vagrant box, we use a Docker image.
\EndKnitrBlock{rmdnote}


In this book we use many different command-line tools. Linux often comes with a whole bunch of command-line tools pre-installed. Moreover, Linux offers many packages that contain other, relevant tools. Installing these packages yourself is not too difficult. However, we also use tools that are not available as packages and require a more manual, and more involved, installation. In order to acquire the necessary command-line tools without having to go through the involved installation process of each, we encourage you to install a Docker image that was created specifically for this book.

\BeginKnitrBlock{rmdtip}
If you still prefer to run the command-line tools natively rather than inside a Docker image, then you can, of course, install the command-line tools individually yourself. Please be aware that this is a very time-consuming process. The Appendix lists all the command-line tools used in the book. The installation instructions are for Ubuntu only. The scripts and data sets used in the book can be obtained by cloning this book’s [GitHub repository](https://github.com/jeroenjanssens/data-science-at-the-command-line).
\EndKnitrBlock{rmdtip}

To install the Docker image, you first need to download and install Docker itself from [the Docker website](https://www.docker.com/products/docker).
Once Docker is installed, you invoke the following command on your terminal or command prompt to download the Docker image (don't type the dollar sign):


```bash
$ docker pull datascienceworkshops/data-science-at-the-command-line
```

You can run the Docker image as follows:


```bash
$ docker run --rm -it datascienceworkshops/data-science-at-the-command-line
```

You're now inside an isolated Linux environment---known as a *Docker container*---with all the necessary command-line tools installed. If the following command produces an enthusiastic cow, then you know everything is working correctly:


```bash
$ cowsay "Let's go!"
 ___________
< Let's go! >
 -----------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```

Run `exit` to exit the container. If you want to get data in and out of the container, you can add a volume, which means that a local directory gets mapped to a directory inside the container. We recommend that you create a new directory, navigate to this new directory, and then run the following when you're on macOS or Linux:


```bash
$ docker run --rm -it -v`pwd`:/data datascienceworkshops/data-science-at-the-command-line
```

Or the following when you're on Windows and using the command line:


```bash
$ docker run --rm -it -v %cd%:/data datascienceworkshops/data-science-at-the-command-line
```

Or the following when you're using Windows PowerShell:


```bash
$ docker run --rm -it -v ${PWD}:/data datascienceworkshops/data-science-at-the-command-line
```

In the above commands, the option `-v` instructs `docker` to map the current directory to the */data* directory inside the container, so this is the place to get data in and out of the Docker container.


\BeginKnitrBlock{rmdnote}
If you would like to know more about the Docker image you can [visit it on Docker Hub](https://hub.docker.com/r/datascienceworkshops/data-science-at-the-command-line/).
\EndKnitrBlock{rmdnote}


## Essential GNU/Linux Concepts

In [Chapter 1](#chapter-1-introduction), we briefly showed you what the command line is. Now that you are running the [Docker image](#docker-image), we can really get started. In this section, we discuss several concepts and tools that you will need to know in order to feel comfortable doing data science at the command line. If, up to now, you have been mainly working with graphical user interfaces, then this might be quite a change. But don’t worry, we’ll start at the beginning, and very gradually go to more advanced topics.

\BeginKnitrBlock{rmdnote}

This section is not a complete course in GNU/Linux. We will only explain the concepts and tools that are relevant for to doing data science. One of the advantages of the [Docker image](#docker-image) is that a lot is already set up. If you wish to know more about GNU/Linux, consult the Further Reading Section at the end of this chapter.
\EndKnitrBlock{rmdnote}

### The Environment

So you’ve just logged into a brand new environment. Before we do anything, it is worthwhile to get a high-level understanding of this environment. The environment is roughly defined by four layers, which we briefly discuss from the top down.

Command-line tools

:   First and foremost, there are the command-line tools that you work with. We use them by typing their corresponding commands. There are different types of command-line tools, which we will discuss in the next section. Examples of tools are: `ls` [@ls], `cat` [@cat], and `jq` [@jq].

Terminal

:   The terminal, which is the second layer, is the application where we type our commands in. If you see the following text:

    
    ```bash
    $ seq 3
    1
    2
    3
    ```

    then you would type `seq 3` into your terminal and press `<Enter>`. (The command-line tool `seq` [@seq] generates a sequence of numbers.) You do not type the dollar sign. It is just there to tell you that this a command you can type in the terminal. This dollar sign is known as the prompt. The text below `seq 3` is the output of the command. In [Chapter 1](#chapter-1-introduction), we showed you two screenshots of how the default terminal looks like in macOS and Ubuntu with various commands and their output.

Shell

:   The third layer is the shell. Once we have typed in our command and pressed `<Enter>`, the terminal sends that command to the shell. The shell is a program that interprets the command. The [Docker image](#docker-image) uses Bash as the shell, but there are many others available. Once you have become a bit more proficient at the command line, you may want to look into a shell called the Z shell. It offers many additional features that may increase your productivity at the command line.

Operating system

:   The fourth layer is the operating system, which is GNU/Linux in our case. Linux is the name of the kernel, which is the heart of the operating system. The kernel is in direct contact with the CPU, disks, and other hardware. The kernel also executes our command-line tools. GNU, which stands for GNU’s not UNIX, refers to the set of basic tools. The [Docker image](#docker-image) is based on a particular Linux distribution called Alpine Linux.

### Executing a Command-line Tool

Now that you have a basic understanding of the environment, it is high time that you try out some commands. Type the following in your terminal (without the dollar sign) and press `<Enter>`:


```bash
$ pwd
/home/vagrant
```

Sometimes we are using commands and pipelines that are too long to fit on the page. In that case you’ll see something like the following:


```bash
$ echo 'Hello'\
> ' world' |
> wc
```

The greater-than sign is the continuation prompt, which indicates that this line is a continuation of the previous one. A long command can be broken up with either a backslash or a pipe symbol. Be sure to first match any quotation marks. The following command is exactly the same:


```bash
$ echo 'Hello world' | wc
```

This is as simple as it gets. You just executed a command that contained a single command-line tool. The command-line tool `pwd` [@pwd] prints the name of the directory where you currently are. By default, when you login, this is your home directory. You can view the contents of this directory with `ls` [@ls]:


```bash
$ ls
book
```

The command-line tool `cd`, which is a Bash builtin, allows you to navigate to a different directory:


```bash
$ cd book/ch02/
$ cd data
$ pwd
/home/vagrant/book/ch02/data
$ cd ..
$ pwd
/home/vagrant/book/ch02/
```

The part after `cd` specifies to which directory you want to navigate to. Values that come after the command are called command-line arguments or options. The two dots refer to the parent directory. Let’s try a different command:


```bash
$ head -n 3 data/movies.txt
Matrix
Star Wars
Home Alone
```

Here we pass three command-line arguments to `head` [@head]. The first one is an option. The second one is a value that belongs to the option. The third one is a filename. This particular command outputs the first three lines of file *book/ch02/data/movies.txt*.

### Five Types of Command-line Tools

We employ the term command-line tool a lot, but so far, we have not yet explained what we actually mean by it. We use it as an umbrella term for *anything* that can be executed from the command line. Under the hood, each command-line tool is one of the following five types:

- A binary executable.
- A shell builtin.
- An interpreted script.
- A shell function.
- An alias.

It’s good to know the difference between the types. The command-line tools that come pre-installed with the [Docker image](#docker-image) mostly comprise of the first two types (binary executable and shell builtin). The other three types (interpreted script, shell function, and alias) allow us to further build up our data science toolbox and become more efficient and more productive data scientists.

Binary Executable

:   Binary executables are programs in the classical sense. A binary executable is created by compiling source code to machine code. This means that when you open the file in a text editor you cannot read it.

Shell Builtin

:   Shell builtins are command-line tools provided by the shell, which is Bash in our case. Examples include `cd` and `help`. These cannot be changed. Shell builtins may differ between shells. Like binary executables, they cannot be easily inspected or changed.

Interpreted Script

:   An interpreted script is a text file that is executed by a binary executable. Examples include: Python, R, and Bash scripts. One great advantage of an interpreted script is that you can read and change it. Example \@ref(exm:script-fac) shows a script named *\~/book/ch02/fac.py*. This script is interpreted by Python not because of the file extension *.py*, but because the first line of the script defines the binary that should execute it.

    \BeginKnitrBlock{example}\iffalse{-91-80-121-116-104-111-110-32-115-99-114-105-112-116-32-116-104-97-116-32-99-111-109-112-117-116-101-115-32-116-104-101-32-102-97-99-116-111-114-105-97-108-32-111-102-32-97-110-32-105-110-116-101-103-101-114-93-}\fi{}
    <span class="example" id="exm:script-fac"><strong>(\#exm:script-fac)  \iffalse (Python script that computes the factorial of an integer) \fi{} </strong></span>
    \EndKnitrBlock{example}
    
    ```python
    ##!/usr/bin/env python
    
    def factorial(x):
        result = 1
        for i in xrange(2, x + 1):
            result *= i
        return result
    
    if __name__ == "__main__":
        import sys
        x = int(sys.argv[1])
        print factorial(x)
    ```

    This script computes the factorial of the integer that we pass as a parameter. It can be invoked from the command line as follows:

    
    ```bash
    $ book/ch02/fac.py 5
    120
    ```

    In [Chapter 4](#chapter-4-creating-reusable-command-line-tools), we’ll discuss in great detail how to create reusable command-line tools using interpreted scripts.

Shell Function

:   A shell function is a function that is, in our case executed by Bash. They provide similar functionality to a Bash script, but they are usually (but not necessarily) smaller than scripts. They also tend to be more personal. The following command defines a function called `fac`, which, just like the interpreted Python script above, computes the factorial of the integer we pass as a parameter. It does by generating a list of numbers using `seq`, putting those numbers on one line with `*` as the delimiter using `paste` [@paste], and passing this equation into `bc` [@bc], which is evaluates it and outputs the result.

    
    ```bash
    $ fac() { (echo 1; seq $1) | paste -s -d\* - | bc; }
    $ fac 5
    120
    ```

    The file *.bashrc*, which is a configuration file for Bash, is a good place to define your shell functions, so that they are always available.

Alias

:   Aliases are like macros. If you often find yourself executing a certain command with the same parameters (or a part of it), you can define an alias for this. Aliases are also very useful when you continue to misspell a certain command (see <https://github.com/chrishwiggins/mise/blob/master/sh/aliases-public.sh> for a long list of useful aliases). The following command defines such an alias:

    
    ```bash
    $ alias l='ls -1 --group-directories-first'
    $ alias moer=more
    ```

    Now, if you type the following on the command line, the shell will replace each alias it finds with its value:

    
    ```bash
    $ cd ~
    $ l
    book
    ```

    Aliases are simpler than shell functions as they don’t allow parameters. The function `fac` could not have been defined using an alias because of the parameter. Still, aliases allow you to save lots of keystrokes. Like shell functions, aliases are often defined in *.bashrc* or *.bash\_aliases* configuration files, which are located in your home directory. To see all aliases currently defined, you simply run `alias` without arguments. Try it, what do you see?

In this book we will focus mostly on the last three types of command-line tools: interpreted scripts, shell functions, and aliases. This is because these can easily be changed. The purpose of a command-line tool is to make your life on the command line easier, and to make you a more productive and more efficient data scientist. You can find out the type of a command-line tool with `type` (which is itself a shell builtin):


```bash
$ type -a pwd
pwd is a shell builtin
pwd is /bin/pwd
$ type -a cd
cd is a shell builtin
$ type -a fac
fac is a function
fac ()
{
    ( echo 1;
    seq $1 ) | paste -s -d\* - | bc
}
$ type -a l
l is aliased to `ls -1 --group-directories-first'
```

`type` returns two command-line tools for `pwd`. In that case, the first reported command-line tool is used when you type `pwd`. In the next section we will look at how to combine command-line tools.

### Combining Command-line Tools

Because most command-line tools adhere to the UNIX philosophy, they are designed to do only thing, and do it really well. For example, the command-line tool `grep` [@grep] can filter lines, `wc` [@wc] can count lines, and `sort` [@sort] can sort lines. The power of the command line comes from its ability to combine these small, yet powerful command-line tools. The most important way of combining command-line tools is through a so-called pipe. The output from the first tool is passed to the second tool. There are virtually no limits to this.

Consider, for example, the command-line tool `seq`, which generates a sequence of numbers. Let us generate a sequence of five numbers.


```bash
$ seq 5
1
2
3
4
5
```

The output of a command-line tool is by default passed on to the terminal, which displays it on our screen. We can *pipe* the ouput of `seq` to a second tool, called `grep`, which can be used to filter lines. Imagine that we only want to see numbers that contain a "3". We can combine `seq` and `grep` as follows:


```bash
$ seq 30 | grep 3
3
13
23
30
```

And if we wanted to know *how many* numbers between 1 and 100 that contain a three, we can use `wc`, that is very good at counting things:


```bash
$ seq 100 | grep 3 | wc -l
19
```

The option `-l` specifies that `wc` should only output the number of lines that are pass into it. By default it also returns the number of characters and words.

You may start to see that combining command-line tools is a very powerful concept. In the rest of the book you will be introduced to many more tools and the functionality they offer when combining them.

### Redirecting Input and Output

We mentioned that, by default, the output of the last command-line tool in the pipeline is outputted to the terminal. You can also save this output to a file. This is called output redirection, and works as follows:


```bash
$ seq 10 > data/ten-numbers
```

Here, we save the output of the `seq` tool to a file named *ten-numbers* in the directory *\~/book/ch02/data*. If this file does not exist yet, it is created. If this file already did exist, its contents would have been overwritten. You can also append the output to a file with `>>`, meaning the output is put after the original contents:


```bash
$ echo -n "Hello" > hello-world
$ echo " World" >> hello-world
```

The tool echo just outputs the value you specify. The `-n` option specifies that `echo` should not output a trailing newline.

Saving the output to a file is useful if you need to store intermediate results, for example for continuing with your analysis at a later stage. To use the contents of the file *hello-world* again, we can use `cat` [@cat], which reads a file prints it.


```bash
$ cat hello-world | wc -w
2
```

(Note that the `-w` option indicates `wc` to only count words.) The same result can be achieved with the following notation:


```bash
$ < hello-world wc -w
2
```

This way, you are directly passing the file to the standard input of `wc` without running an additional process. If the command-line tool also allows files to be specified as command-line arguments, which many do, you can also do the following for `wc`:


```bash
$ wc -w hello-world
2 hello-world
```

### Working With Files

As data scientists, we work with a lot of data. This data is often stored in files. It is important to know how to work with files (and the directories they live in) on the command line. Every action that you can do using a graphical user interface, you can do with command-line tools (and much more). In this section we introduce the most important ones to create, move, copy, rename, and delete files and directories.

You have already seen how we can create new files by redirecting the output with either `>` or `>>`. In case you need to move a file to a different directory you can use `mv` [@mv]:


```bash
$ mv hello.txt ~/book/ch02/data/
```

You can also rename files with `mv`:


```bash
$ cd data
$ mv hello.txt bye.txt
```

You can also rename or move entire directories. In case you no longer need a file, you delete (or remove) it with `rm` [@rm]:


```bash
$ rm bye.txt
```

In case you want to remove an entire directory with all its contents, specify the `-r` option, which stands for recursive:


```bash
$ rm -r book/ch02/data/old
```

In case you want to copy a file, use `cp` [@cp]. This is useful for creating backups:


```bash
$ cp server.log server.log.bak
```

You can create directories using `mkdir` [@mkdir]:


```bash
$ cd data
$ mkdir logs
```

Using the command-line tools to manage your files can be scary at first, because you have no graphical overview of the file system to provide immediate feedback.

All of the above command-line tools accept the `-v` option, which stands for verbose, so that they output what’s going on. All but `mkdir` accept the `-i` option, which stands for interactive, and causes the tools to ask you for confirmation.

### Help!

As you are finding your way around the command-line, it may happen that you need help. Even the most-seasoned Linux users need help at some point. It is impossible to remember all the different command-line tools and their possible arguments. Fortunately, the command line offers severals ways to get help.

The most important command to get help is perhaps `man` [@man], which is short for *manual*. It contains information for most command-line tools. Imagine that we forgot the different options to the tool `cat`. You can access its man page using:


```bash
$ man cat | head -n 20
CAT(1)                           User Commands                          CAT(1)



NAME
       cat - concatenate files and print on the standard output

SYNOPSIS
       cat [OPTION]... [FILE]...

DESCRIPTION
       Concatenate FILE(s), or standard input, to standard output.

       -A, --show-all
              equivalent to -vET

       -b, --number-nonblank
              number nonempty output lines, overrides -n

       -e     equivalent to -vE
```

\BeginKnitrBlock{rmdtip}

Sometimes you’ll see us use `head`, `fold`, or `cut` at the end of a command. This is only to ensure that the output of the command fits on the page; you don’t have to type these. For example, `head -n 5` only prints the first five lines, `fold` wraps long lines to 80 characters, and `cut -c1-80` trims lines that are long than 80 characters.
\EndKnitrBlock{rmdtip}

Not every command-line tool has a man page. For shell builtins, such as `cd`, you need to use the `help` command-line tool:


```bash
$ help cd | head -n 20
cd: cd [-L|[-P [-e]] [-@]] [dir]
    Change the shell working directory.

    Change the current directory to DIR.  The default DIR is the value of the
    HOME shell variable.

    The variable CDPATH defines the search path for the directory containing
    DIR.  Alternative directory names in CDPATH are separated by a colon (:).
    A null directory name is the same as the current directory.  If DIR begins
    with a slash (/), then CDPATH is not used.

    If the directory is not found, and the shell option `cdable_vars' is set,
    the word is assumed to be  a variable name.  If that variable has a value,
    its value is used for DIR.

    Options:
        -L      force symbolic links to be followed: resolve symbolic links in
        DIR after processing instances of `..'
        -P      use the physical directory structure without following symbolic
        links: resolve symbolic links in DIR before processing instances
```

This help also covers other topics of Bash, in case you are interested (try `help` without command-line arguments for a list of topics). Remember that you can use `type` to figure out the kind of a specific command-line tool.

Newer tools that can be used from the command-line, often lack a man page as well. In that case, your best bet is to invoke the tool with the `--help` option (and sometimes the `-h` option). For example:


```bash
jq --help

jq - commandline JSON processor [version 1.4]
Usage: jq [options] <jq filter> [file...]

For a description of the command line options and
how to write jq filters (and why you might want to)
see the jq manpage, or the online documentation at
http://stedolan.github.com/jq
```

Specifying the `--help` option also works for the GNU command-line tools such as `cat`. However, the corresponding man page often provides more information. If, after trying these three approaches, you are still stuck, then it is perfectly acceptable to consult the Internet. In the appendix, there’s a list of all command-line tools used in this book. Besides how each command-line tool can be installed, it also shows how you can get help.

## Further Reading

* Heddings, Lowell. 2006. “Keyboard Shortcuts for Bash.” <a href="http://www.howtogeek.com/howto/ubuntu/keyboard-shortcuts-for-bash-command-shell-for-ubuntu-debian-suse-redhat-linux-etc" class="uri">http://www.howtogeek.com/howto/ubuntu/keyboard-shortcuts-for-bash-command-shell-for-ubuntu-debian-suse-redhat-linux-etc</a>.
* Peek, Jerry, Shelley Powers, Tim O’Reilly, and Mike Loukides. 2002. <em>Unix Power Tools</em>. 3rd Ed. O’Reilly Media.

<!--chapter:end:02.Rmd-->

# Methods

We describe our methods in this chapter.

<!--chapter:end:03-method.Rmd-->

# Obtaining Data {#chapter-3-obtaining-data}

This chapter deals with the first step of the OSEMN model: obtaining data. After all, without any data, there is not much data science that we can do. We assume that the data that is needed to solve the data science problem at hand already exists at some location in some form. Our goal is to get this data onto your computer (or into your Data Science Toolbox) in a form that we can work with.

According to the Unix philosophy, text is a universal interface. Almost every command-line tool takes text as input, produces text as output, or both. This is the main reason why command-line tools can work so well together. However, as we'll see, even just text can come in multiple forms.

Data can be obtained in several ways---for example by downloading it from a server, by querying a database, or by connecting to a Web API. Sometimes, the data comes in a compressed form or in a binary format such as Microsoft Excel. In this chapter, we discuss several tools that help tackle this from the command line, including: `curl` [@curl], `in2csv` [@in2csv], `sql2csv` [@sql2csv], and `tar` [@tar].

## Overview 

In this chapter, you’ll learn how to:

- Obtain data from the Internet
- Query databases
- Connect to Web APIs
- Decompress files
- Convert Microsoft Excel spreadsheets into usable data

## Copying Local Files to the Data Science Toolbox

A common situation is that you already have the necessary files on your own computer. This section explains how you can get those files onto the local or remote version of the Data Science Toolbox.

### Local Version of Data Science Toolbox 

We mentioned in [Chapter 2](#chapter-2-getting-started) that the Vagrant version of the Data Science Toolbox is an isolated virtual environment. Luckily there is one exception to that: files can be transfered in and out the Data Science Toolbox. The local directory from which you ran `vagrant up` (which is the one that contains the file *Vagrantfile*), is mapped to a directory in the Data Science Toolbox. This directory is called */vagrant*. Please note that this is not your home directory. Let us check the contents of this directory:


```bash
$ ls -1 /vagrant
build
Vagrantfile
```

If you have a file on your local computer, and you want to apply some command-line tools to it, all you have to do is copy or move the file to that directory. Let’s assume that you have a file called *logs.csv* on your Desktop. If you are running Linux or macOS, execute the following command on your operating system (and not inside the Data Science Toolbox):


```bash
$ cp ~/Desktop/logs.csv .
```

And if you are running Windows, you can run the following commands on the command prompt:

```powershell
> cd %UserProfile%\Desktop
> copy logs.csv MyDataScienceToolbox\
```

You may also drag-and-drop the file into the directory using Windows Explorer.

The file is now located in the directory */vagrant*. It is a good idea to keep your data in a separate directory, like we have *\~/book/ch03/data*. So, after you have copied the file, you can move it by running:


```bash
$ mv /vagrant/logs.csv ~/book/ch03/data
$ cd ~/book/ch03
$ cat data/logs.csv
```

### Remote Version of Data Science Toolbox 

If you are running Linux or macOS, you can use `scp` [@scp], which stands for *secure copy*, to copy files onto the EC2 instance. You will need the same key pair file that you used to login to the EC2 instance.


```bash
$ scp -i  mykey.pem ~/Desktop/logs.csv \
> ubuntu@ec2-184-73-72-150.compute-1.amazonaws.com:data
```

Replace the host name in the example *ec2-184-73-72-150.compute-1.amazonaws.com* with the value you see on the EC2 overview page in the AWS console.

## Decompressing Files 

If the original data set is very large or it's a collection of many files, the file may be a (compressed) archive. Data sets which contain many repeated values (such as the words in a text file or the keys in a JSON file) are especially well suited for compression.

Common file extensions of compressed archives are: *.tar.gz*, *.zip*, and *.rar*. To decompress these, you would use the command-line tools `tar` [@tar], `unzip` [@unzip], and `unrar` [@unrar], respectively. There exists a few more, though less common, file extensions for which you would need yet other tools. For example, in order to extract a file named *logs.tar.gz*, you would use:


```bash
$ cd ~/book/ch03
$ tar -xzvf data/logs.tar.gz
```

Indeed, `tar` is notorious for its many command-line arguments. In this case, the four command-line arguments `x`, `z`, `v`, and `f` specify that `tar` should *extract* files from an archive, use *gzip* as the decompression algorithm, be *verbose* and use file *logs.tar.gz*. In time, you'll get used to typing these four characters, but there's a more convenient way.

Rather than remembering the different command-line tools and their options, there's a handy script called `unpack` [@unpack], which will decompress many different formats. `unpack` looks at the extension of the file that you want to decompress, and calls the appropriate command-line tool.

The `unpack` tool is part of the Data Science Toolbox. Remember that you can look up how it can be installed in the appendix. Example \@ref(exm:script-unpack) shows the source of `unpack`. Although Bash scripting is not the focus of this book, it’s still useful to take a moment to figure out how it works.

\BeginKnitrBlock{example}\iffalse{-91-68-101-99-111-109-112-114-101-115-115-32-118-97-114-105-111-117-115-32-102-105-108-101-32-102-111-114-109-97-116-115-93-}\fi{}
<span class="example" id="exm:script-unpack"><strong>(\#exm:script-unpack)  \iffalse (Decompress various file formats) \fi{} </strong></span>
\EndKnitrBlock{example}

```bash
#!/usr/bin/env bash
# unpack: Extract common file formats

# Display usage if no parameters given
if [[ -z "$@" ]]; then
    echo " ${0##*/} <archive> - extract common file formats)"
    exit
fi

# Required program(s)
req_progs=(7z unrar unzip)
for p in ${req_progs[@]}; do
    hash "$p" 2>&- || \
    { echo >&2 " Required program \"$p\" not installed."; exit 1; }
done

# Test if file exists
if [ ! -f "$@" ]; then
    echo "File "$@" doesn't exist"
    exit
fi

# Extract file by using extension as reference
case "$@" in
    *.7z ) 7z x "$@" ;;
    *.tar.bz2 ) tar xvjf "$@" ;;
    *.bz2 ) bunzip2 "$@" ;;
    *.deb ) ar vx "$@" ;;
    *.tar.gz ) tar xvf "$@" ;;
    *.gz ) gunzip "$@" ;;
    *.tar ) tar xvf "$@" ;;
    *.tbz2 ) tar xvjf "$@" ;;
    *.tar.xz ) tar xvf "$@" ;;
    *.tgz ) tar xvzf "$@" ;;
    *.rar ) unrar x "$@" ;;
    *.zip ) unzip "$@" ;;
    *.Z ) uncompress "$@" ;;
    * ) echo " Unsupported file format" ;;
esac
```

Now, in order to decompress this same file, you would simply use:


```bash
$ unpack logs.tar.gz
```

## Converting Microsoft Excel Spreadsheets

For many people, Microsoft Excel offers an intuitive way to work with small data sets and perform calculations on them. As a result, a lot of data is embedded into Microsoft Excel spreadsheets. These spreadsheets are, depending on the extension of the filename, stored in either a proprietary binary format (*.xls*) or as a collection of compressed XML files (*.xlsx*). In both cases, the data is not readily usable by most command-line tools. It would be a shame if we could not use those valuable data sets just because they are stored this way.

Luckily, there is a command-line tool called `in2csv` [@in2csv], which is able to convert Microsoft Excel spreadsheets to CSV files. CSV stands for comma-separated values. Working with CSV can be tricky because it lacks a formal specification. [RFC 4180](http://www.ietf.org/rfc/rfc4180.txt) defines the CSV format according to the following three points:

1.  Each record is located on a separate line, delimited by a line break (CRLF). For example:

        aaa,bbb,ccc CRLF
        zzz,yyy,xxx CRLF

2.  The last record in the file may or may not have an ending line break. For example:

        aaa,bbb,ccc CRLF
        zzz,yyy,xxx

3.  There maybe an optional header line appearing as the first line of the file with the same format as normal record lines. This header will contain names corresponding to the fields in the file and should contain the same number of fields as the records in the rest of the file (the presence or absence of the header line should be indicated via the optional header parameter of this MIME type). For example:

        field_name,field_name,field_name CRLF
        aaa,bbb,ccc CRLF
        zzz,yyy,xxx CRLF

Let’s demonstrate `in2csv` using a spreadsheet that contains the top 250 movies from the Internet Movie Database (IMDb). The file is named *imdb-250.xlsx* and can be obtained from <http://www.overthinkingit.com/2011/10/11/imdb-top-250-movies-4th-edition/2>. To extract its data, we invoke `in2csv` as follows:


```bash
$ cd book/ch03
$ in2csv data/imdb-250.xlsx > data/imdb-250.csv
```

The format of the file is automatically determined by the extension, *.xlsx* in this case. If we were to pipe the data into `in2csv`, we would have to specify the format explicitly. Let's look at the data:


```bash
$ in2csv imdb-250.xlsx | head | cut -c1-80
Title,title trim,Year,Rank,Rank (desc),Rating,New in 2011 from 2010?,2010 rank,R
Sherlock Jr. (1924),SherlockJr.(1924),1924,221,30,8,y,n/a,n/a,
The Passion of Joan of Arc (1928),ThePassionofJoanofArc(1928),1928,212,39,8,y,n/
His Girl Friday (1940),HisGirlFriday(1940),1940,250,1,8,y,n/a,n/a,
Tokyo Story (1953),TokyoStory(1953),1953,248,3,8,y,n/a,n/a,
The Man Who Shot Liberty Valance (1962),TheManWhoShotLibertyValance(1962),1962,2
Persona (1966),Persona(1966),1966,200,51,8,y,n/a,n/a,
Stalker (1979),Stalker(1979),1979,243,8,8,y,n/a,n/a,
Fanny and Alexander (1982),FannyandAlexander(1982),1982,210,41,8,y,n/a,n/a,
Beauty and the Beast (1991),BeautyandtheBeast(1991),1991,249,2,8,y,n/a,n/a,
```

As you can see, CSV by default is not too readable. You can pipe the data to a tool called `csvlook` [@csvlook], which will nicely format the data into a table. Here, we’ll display a subset of the columns using `csvcut` such that the table fits on the page:


```bash
$ in2csv data/imdb-250.xlsx | head | csvcut -c Title,Year,Rating | csvlook
|------------------------------------------+------+---------|
|  Title                                   | Year | Rating  |
|------------------------------------------+------+---------|
|  Sherlock Jr. (1924)                     | 1924 | 8       |
|  The Passion of Joan of Arc (1928)       | 1928 | 8       |
|  His Girl Friday (1940)                  | 1940 | 8       |
|  Tokyo Story (1953)                      | 1953 | 8       |
|  The Man Who Shot Liberty Valance (1962) | 1962 | 8       |
|  Persona (1966)                          | 1966 | 8       |
|  Stalker (1979)                          | 1979 | 8       |
|  Fanny and Alexander (1982)              | 1982 | 8       |
|  Beauty and the Beast (1991)             | 1991 | 8       |
|------------------------------------------+------+---------|
```

A spreadsheet can contain multiple worksheets. By default, `in2csv` extracts the first worksheet. To extract a different worksheet, you need to pass the name of worksheet to the `--sheet` option.

The tools `in2csv`, `csvcut`, and `csvlook` are actually part of Csvkit, which is collection of command-line tools to work with CSV data. Csvkit will be used quite often in this book because it has so many valuable tools. If you’re running the Data Science Toolbox, you already have Csvkit installed. Otherwise, see the appendix for instructions on how to install it.

\BeginKnitrBlock{rmdnote}
An alternative approach to `in2csv` is to open the spreadsheet in Microsoft Excel or an open source variant such as LibreOffice Calc, and manually export it to CSV. While this works as a one-off solution, the disadvantage is that it does not scale well to multiple files and is not automatable. Furthermore, when you are working on the command line of a remote server, chances are that you don't have such an application available.
\EndKnitrBlock{rmdnote}

## Querying Relational Databases

Most companies store their data in a relational database. Examples of relational databases are MySQL, PostgreSQL, and SQLite. These databases all have a slightly different way of interfacing with them. Some provide a command-line tool or a command-line interface, while others do not. Moreover, they are not very consistent when it comes to their usage and output.

Fortunately, there is a command-line tool called `sql2csv`, which is part of the Csvkit suite. Because it leverages the Python SQLAlchemy package, we only have to use one tool to execute queries on many different databases through a common interface, including MySQL, Oracle, PostgreSQL, SQLite, Microsoft SQL Server, and Sybase. The output of `sql2csv` is, as its name suggests, in CSV format.

We can obtain data from relational databases by executing a `SELECT` query on them. (`sql2csv` also support `INSERT`, `UPDATE`, and `DELETE` queries, but that's not the purpose of this chapter.) To select a specific set of data from an SQLite database named *iris.db*, `sql2csv` can be invoked as follows:


```bash
$ sql2csv --db 'sqlite:///data/iris.db' --query 'SELECT * FROM iris '\
> 'WHERE sepal_length > 7.5'
sepal_length,sepal_width,petal_length,petal_width,species
7.6,3.0,6.6,2.1,Iris-virginica
7.7,3.8,6.7,2.2,Iris-virginica
7.7,2.6,6.9,2.3,Iris-virginica
7.7,2.8,6.7,2.0,Iris-virginica
7.9,3.8,6.4,2.0,Iris-virginica
7.7,3.0,6.1,2.3,Iris-virginica
```

Here, we are selecting all rows where `sepal\_length` is larger than 7.5. The `--db` option specifies the database URL, of which the typical form is: `dialect+driver://username:password@host:port/database`.

## Downloading from the Internet

The Internet provides without a doubt the largest resource for data. This data is available in various forms, using various protocols. The command-line tool cURL [@curl] can be considered the command line's Swiss Army knife when it comes to downloading data from the Internet.

When you access a URL, which stands for *uniform resource locator*, through your browser, the data that is being downloaded can be interpreted. For example, an HTML file is rendered as a website, an MP3 file may be automatically played, and a PDF file may be automatically downloaded or opened by a viewer. However, when cURL is used to access a URL, the data is downloaded as is printed to standard output. Other command-line tools may then be used to process this data further.

The easiest invocation of cURL is to simply specify a URL as a command-line argument. For example, to download the book *Adventures of Huckleberry Finn* by Mark Twain from Project Gutenberg, we can run the following command:


```bash
$ curl -s http://www.gutenberg.org/files/76/76-0.txt | head -n 10

The Project Gutenberg EBook of Adventures of Huckleberry Finn, Complete
by Mark Twain (Samuel Clemens)

This eBook is for the use of anyone anywhere at no cost and with almost
no restrictions whatsoever. You may copy it, give it away or re-use
it under the terms of the Project Gutenberg License included with this
eBook or online at www.gutenberg.net
```

By default, cURL outputs a progress meter that shows how the download rate and the expected time of completion. If you are piping the output directly to another command-line tool, such as `head`, be sure to specify the `-s` command-line argument, which stands for *silent*, so that the progress meter is disabled. Compare, for example, the output with the following command:


```bash
$ curl http://www.gutenberg.org/files/76/76-0.txt | head -n 10
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed

  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--

The Project Gutenberg EBook of Adventures of Huckleberry Finn, Complete
by Mark Twain (Samuel Clemens)

This eBook is for the use of anyone anywhere at no cost and with almost
no restrictions whatsoever. You may copy it, give it away or re-use
it under the terms of the Project Gutenberg License included with this
eBook or online at www.gutenberg.net
```

Note that the output of the second command, where we do not disable the progress meter, contains the unwanted text and even an error message. If you save the data to a file, then you do not need to necessarily specify the `-s` option:


```bash
$ curl http://www.gutenberg.org/files/76/76-0.txt > data/finn.txt
```

You can also save the data by explicitly specifying the output file with the `-o` option:


```bash
$ curl -s http://www.gutenberg.org/files/76/76-0.txt -o data/finn.txt
```

When downloading data from the Internet, the URL will most likely use the protocols HTTP or HTTPS. To download from an FTP server, which stands for File Transfer Protocol, you use cURL in exactly the same way. When the URL is password protected, you can specify a username and a password as follows:


```bash
$ curl -u username:password ftp://host/file
```

If the specified URL is a directory, `curl` will list the contents of that directory.

When you access a shortened URL, such as the ones that start with *http://bit.ly/* or *http://t.co/*, your browser automatically redirects you to the correct location. With `curl`, however, you need to specify the `-L` or `--location` option in order to be redirected:


```bash
$ curl -L j.mp/locatbbar
```

If you do not specify the `-L` or `--location` option, you may get something like:


```bash
$ curl j.mp/locatbbar
<html>
<head>
<title>bit.ly</title>
</head>
<body>
<a href="http://en.wikipedia.org/wiki/List_of_countries_and_territories_by_bo
rder/area_ratio">moved here</a>
</body>
```

By specifying the `-I` or `--head` option, `curl` fetches only the HTTP header of the response:


```bash
$ curl -I j.mp/locatbbar
HTTP/1.1 301 Moved Permanently
Server: nginx
Date: Wed, 21 May 2014 18:50:28 GMT
Content-Type: text/html; charset=utf-8
Connection: keep-alive
Cache-Control: private; max-age=90
Content-Length: 175
Location: http://en.wikipedia.org/wiki/List_of_countries_and_territories_by_bo
Mime-Version: 1.0
Set-Cookie: _bit=537cf574-002ba-07d79-2e1cf10a;domain=.j.mp;expires=Mon Nov 17
```

The first line indicates the HTTP status code, which is 301 (moved permanently) in this case. You can also see the location this URL redirects to: <http://en.wikipedia.org/wiki/List_of_countries_and_territories_by_border/area_ratio>. Inspecting the header and getting the status code is a useful debugging tool in case `curl` does not give you the expected result. Other common HTTP status codes include 404 (not found) and 403 (forbidden). This page lists all HTTP status codes: <http://en.wikipedia.org/wiki/List_of_HTTP_status_codes>.

To conclude this section, cURL is a straight-forward command-line tool for downloading data from the Internet. Its three most common command-line arguments are `-s` to suppress the progress meter, `-u` to specify a username and password, and `-L` to automatically follow redirects. See its man page for more information.

## Calling a Web API 

In the previous section we explained how to download individual files from the Internet. Another way data can come from the Internet is through a web API, which stands for *Application Programming Interface*. The number of APIs that are being offered by organizations is growing at increasing rate, which means a lot of interesting data for us data scientists.

Web APIs are not meant to be presented in nice layout, such as websites. Instead, most web APIs return data in a structured format, such as JSON or XML. Having data in a structured form has the advantage that the data can be easily processed by other tools, such as `jq`. For example, the API from <https://randomuser.me> returns data in the following JSON structure.


```bash
$ curl -s https://randomuser.me/api/1.2/ | jq .
{
  "results": [
    {
      "gender": "male",
      "name": {
        "title": "mr",
        "first": "jeffrey",
        "last": "lawson"
      },
      "location": {
        "street": "838 miller ave",
        "city": "washington",
        "state": "maryland",
        "postcode": 81831,
        "coordinates": {
          "latitude": "81.9488",
          "longitude": "-67.8247"
        },
        "timezone": {
          "offset": "+4:00",
          "description": "Abu Dhabi, Muscat, Baku, Tbilisi"
        }
      },
      "email": "jeffrey.lawson@example.com",
      "login": {
        "uuid": "78918f6c-2658-4915-bebf-bfaa61a1624c",
        "username": "silverzebra774",
        "password": "treble",
        "salt": "iAtIKhvB",
        "md5": "4c02abeca4d6ca4dbfc0ddb33dcef29f",
        "sha1": "36e109513abf73df460cead89b78c749abe908fa",
        "sha256": "0155d9e6cabedfc3ad0f21d18b3ca3e738a8f17811dd57dc3b4dd386cd021963"
      },
      "dob": {
        "date": "1996-07-04T02:49:46Z",
        "age": 22
      },
      "registered": {
        "date": "2013-01-13T13:37:21Z",
        "age": 5
      },
      "phone": "(406)-041-2792",
      "cell": "(831)-085-8264",
      "id": {
        "name": "SSN",
        "value": "629-40-9671"
      },
      "picture": {
        "large": "https://randomuser.me/api/portraits/men/62.jpg",
        "medium": "https://randomuser.me/api/portraits/med/men/62.jpg",
        "thumbnail": "https://randomuser.me/api/portraits/thumb/men/62.jpg"
      },
      "nat": "US"
    }
  ],
  "info": {
    "seed": "4bd9f66fd83a6ec7",
    "results": 1,
    "page": 1,
    "version": "1.2"
  }
}
```

The data is piped to a command-line tool `jq` in order to display it in a nice way. `jq` has many more possibilities that we will explore in [Chapter 5](#chapter-5-scrubbing-data).

Some web APIs return data in a streaming manner. This means that once you connect to it, the data will continue to pour in forever. A well-known example is the Twitter "firehose", which constantly streams all the tweets being sent around the world. Luckily, most command-line tools that we use also operate in a streaming matter, so that we also use this kind of data.

Some APIs require you to log in using the OAuth protocol. There is a handy command-line tool called `curlicue` [@curlicue] that assists in performing the so-called "OAuth dance". Once this has been set up, it `curlicue` will call `curl` with the correct headers. First, you set things up once for a particular API with `curlicue-setup`, and then you can call that API using `curlicue`. For example, to use `curlicue` with the Twitter API you would run:


```bash
$ curlicue-setup \
> 'https://api.twitter.com/oauth/request_token' \
> 'https://api.twitter.com/oauth/authorize?oauth_token=$oauth_token' \
> 'https://api.twitter.com/oauth/access_token' \
> credentials
$ curlicue -f credentials \
> 'https://api.twitter.com/1/statuses/home_timeline.xml'
```

For more popular APIs, there are specialized command-line tools available. These are wrappers that provide a convenient way to connect to the API. In [Chapter 9](#chapter-9-modeling-data), for example, we’ll be using the command-line tool `bigmler` that only connects to BigML’s prediction API.

## Further Reading 

* Molinaro, Anthony. 2005. <em>SQL Cookbook</em>. O’Reilly Media.
* Wikipedia. 2014. “List of Http Status Codes.” <a href="http://en.wikipedia.org/wiki/List_of_HTTP_status_codes" class="uri">http://en.wikipedia.org/wiki/List_of_HTTP_status_codes</a>.



<!--chapter:end:03.Rmd-->

# Creating Reusable Command-line Tools {#chapter-4-creating-reusable-command-line-tools}

Throughout the book, we use a lot of commands and pipelines that basically fit on one line. Let us call those one-liners. Being able to perform complex tasks with just a one-liner is what makes the command line powerful. It’s a very different experience from writing traditional programs.

Some tasks you perform only once, and some you perform more often. Some tasks are very specific and others can be generalized. If you foresee or notice that you need to repeat a certain one-liner on a regular basis, it is worthwhile to turn this into a command-line tool of its own. So, both one-liners and command-line tools have their uses. Recognizing the opportunity requires practice and skill. The advantage of a command-line tool is that you do not have to remember the entire one-liner and that it improves readability if you include it into some other pipeline.

The benefit of a working with a programming language, however, is that you have the code in a file. This means that you can easily reuse that code. If the code has parameters it can even be applied to problems that follow a similar pattern.

Command-line tools have the best of both worlds: they can be used from the command line, accept parameters, and only have to be created once. In this chapter we’re going to get familiar creating reusable command-line tools in two ways. First, we explain to turn those one-liners into reusable command-line tools. By adding parameters to our commands, we can add the same flexibility that a programming language offers. Subsequently, we demonstrate how to create reusable command-line tools from code you have written in a programming language. By following the UNIX philosophy, your code can be combined with other command-line tools, which may be written in an entirely different language. We will focus on three programming languages: Python, R, and Java.

We believe that creating reusable command-line tools makes you a more efficient and productive data scientist in the long run. You gradually build up your own data science toolbox from which you can draw existing tools and apply it to problems you have encountered previously. It requires practice in order to be able to recognize the opportunity to turn a one-liner or existing code into a command-line tool.

In order to turn a one-liner into a shell script, we need to use some shell scripting. We shall only demonstrate the usefulness a small subset of concepts from shell scripting. This subset includes variables, conditionals, and loops. A complete course in shell scripting deserves a book on its own, and is therefore beyond the scope of this one. If you want to dive deeper into shell scripting, we recommend *Classic Shell Scripting* by @Robbins2005.

## Overview 

In this chapter, you’ll learn how to:

- Convert one-liners into shell scripts.
- Make existing Python, R, and Java code part of the command line.

## Converting One-liners into Shell Scripts 

In this section we are going to explain how to turn a one-liner into a reusable command-line tool. Imagine that we have the following one-liner:


```bash
$ curl -s http://www.gutenberg.org/files/76/76-0.txt |
> tr '[:upper:]' '[:lower:]' | 
> grep -oE '\w+' |             
> sort |                       
> uniq -c |                    
> sort -nr |                   
> head -n 10                   
   6441 and
   5082 the
   3666 i
   3258 a
   3022 to
   2567 it
   2086 t
   2044 was
   1847 he
   1778 of
```

In short, as you may have guessed from the output, this one-liner returns the top ten words of the e-book version of *Adventures of Huckleberry Finn*. It accomplishes this by:

- Downloading an ebook using `curl`.
- Converting the entire text to lowercase using `tr` [@tr].
- Extracting all the words using `grep` [@grep] and put each word on separate line.
- Sort these words in alphabetical order using `sort` [@sort].

- Remove all the duplicates and count how often each word appears in the list using `uniq` [@uniq].
- Sort this list of unique words by their count in descending order using `sort`.
- Keep only the top 10 lines (i.e., words) using `head`.

\BeginKnitrBlock{rmdtip}

Each command-line tool used in this one-liner offers a man page. So in case you would like to know more about, say, `grep`, you can run `man grep` from the command line. The command-line tools `tr`, `grep`, `uniq`, and `sort` will be discussed in more detail in the next chapter.
\EndKnitrBlock{rmdtip}

There is nothing wrong with running this one-liner just once. However, imagine if we wanted to have the top 10 words of every e-book on Project Gutenberg. Or imagine that we wanted the top 10 words of a news website on a hourly basis. In those cases, it would be best to have this one-liner as a separate building block that can be part of something bigger. Because we want to add some flexibility to this one-liner in terms of parameters, we will turn it into a shell script.

Because we use Bash as our shell, the script will be written in the programming language Bash. This allows us to take the one-liner as the starting point, and gradually improve on it. To turn this one-liner into a reusable command-line tool, we’ll walk you through the following six steps:

1.  Copy and paste the one-liner into a file.

2.  Add execute permissions.

3.  Define a so-called shebang.

4.  Remove the fixed input part.

5.  Add a parameter.

6.  Optionally extend your PATH.

### Step 1: Copy and Paste 

The first step is to create a new file. Open your favorite text editor and copy and paste our one-liner. We use name the file *top-words-1.sh* (The *1* stands for the first step towards our new command-line tool), and put it in the *\~/book/ch04* directory, but you may choose a different name and location. The contents of the file should look something like Example \@ref(exm:top-words-1).

\BeginKnitrBlock{example}\iffalse{-91-126-47-98-111-111-107-47-99-104-48-52-47-116-111-112-45-119-111-114-100-115-45-49-46-115-104-93-}\fi{}
<span class="example" id="exm:top-words-1"><strong>(\#exm:top-words-1)  \iffalse (~/book/ch04/top-words-1.sh) \fi{} </strong></span>
\EndKnitrBlock{example}

```bash
curl -s http://www.gutenberg.org/files/76/76-0.txt |
tr '[:upper:]' '[:lower:]' | grep -oE '\w+' | sort |
uniq -c | sort -nr | head -n 10
```

We are using the file extension *.sh* to make clear that we are creating a shell script. However, command-line tools do not need to have an extension. In fact, command-line tools rarely have extensions.

\BeginKnitrBlock{rmdtip}

Here is a nice little command-line trick. On the command-line, `!!` will be substituted with the previous command. So, if you realize you needed superuser privileges for the previous command, you can run `sudo !!` [@sudo]. And if you want to save the previous command into a file without have to copy and paste it, you can run `echo "!!" > scriptname`. Be sure to check the contents of the file *scriptname* for correctness before executing it because it may not always work when your command has quotes.
\EndKnitrBlock{rmdtip}

We can now use `bash` [@bash] to interpret and execute the commands in the file:


```bash
$ bash book/ch04/top-words-1.sh
   6441 and
   5082 the
   3666 i
   3258 a
   3022 to
   2567 it
   2086 t
   2044 was
   1847 he
   1778 of
```

This already saves us from typing the one-liner. Because the file cannot be executed on its own, it is not yet a true command-line tool. Let us change that in the next step.

### Step 2: Add Permission to Execute 

The reason we cannot execute our file directly is that we do not have the correct access permissions. In particular, you, as a user, need to have the permission to execute the file. In this section we change the access permissions of our file.

\BeginKnitrBlock{rmdnote}

In order to compare differences between steps, we copy the file to *top-words-2.sh* using `cp top-words-{1,2}.sh`. You can keep working with the same file if you want to.
\EndKnitrBlock{rmdnote}

To change the access permissions of a file, we need to use a command-line tool called `chmod` [@chmod], which stands for *change mode*. It changes the file mode bits of a specific file. The following command gives the user, you, the permission to execute *top-words-2.sh*:


```bash
$ cd ~/book/ch04/
$ chmod u+x top-words-2.sh
```

The command-line argument `u+x` consists of three characters: (1) `u` indicates that we want to change the permissions for the user who owns the file, which is you, because you created the file; (2) `+` indicates that we want to add a permission; and (3) `x`, which indicates the permissions to execute. Let us now have a look at the access permissions of both files:


```bash
$ ls -l top-words-{1,2}.sh
-rw-rw-r-- 1 vagrant vagrant 145 Jul 20 23:33 top-words-1.sh
-rwxrw-r-- 1 vagrant vagrant 143 Jul 20 23:34 top-words-2.sh
```

The first column shows the access permissions for each file. For *top-words-2.sh*, this is `-rwxrw-r--`. The first character `-` indicates the file type. A `-` means regular file and a `d` means directory. The next three characters `rwx` indicate the access permissions for the user who owns the file. The `r` and `w` mean read and write respectively. (As you can see, *top-words-1.sh* has a `-` instead of an `x`, which means that we cannot execute that file.) The next three characters `rw-` indicate the access permissions for all members of the group that owns the file. Finally, the last three characters in the column `r--` indicate access permissions for all other users.

Now you can execute the file as follows:


```bash
$ book/ch04/top-words-2.sh
   6441 and
   5082 the
   3666 i
   3258 a
   3022 to
   2567 it
   2086 t
   2044 was
   1847 he
   1778 of
```

Note that if you’re ever in the same directory as the executable, you need to execute it as follows:


```bash
$ cd ~/book/ch04
$ ./top-words-2.sh
```

If you try to execute a file for which you do not have the correct access permissions, as with *top-words-1.sh*, you will see the following error message:


```bash
$ ./top-words-1.sh
bash: ./top-words-1.sh: Permission denied
```

### Step 3: Define Shebang 

Although we can already execute the file on its own, we should add a so-called *shebang* to the file. The shebang is a special line in the script, which instructs the system which executable should be used to interpret the commands.

In our case we want to use `bash` to interpret our commands. Example \@ref(exm:top-words-3) shows what the file *top-words-3.sh* looks like with a shebang. 

\BeginKnitrBlock{example}\iffalse{-91-126-47-98-111-111-107-47-99-104-48-52-47-116-111-112-45-119-111-114-100-115-45-51-46-115-104-93-}\fi{}
<span class="example" id="exm:top-words-3"><strong>(\#exm:top-words-3)  \iffalse (~/book/ch04/top-words-3.sh) \fi{} </strong></span>
\EndKnitrBlock{example}

```bash
#!/usr/bin/env bash
curl -s http://www.gutenberg.org/files/76/76-0.txt |
tr '[:upper:]' '[:lower:]' | grep -oE '\w+' | sort |
uniq -c | sort -nr | head -n 10
```

The name shebang comes from the first two characters: a hash (she) and an exclamation mark (bang). It is not a good idea to leave it out, as we have done in the previous step, because then the behavior of the script is undefined. The Bash shell, which is the one that we are using, uses the executable */bin/sh* by default. Other shells may have different defaults.

Sometimes you will come across scripts that have a shebang in the form of *!/usr/bin/bash* or *!/usr/bin/python* (in the case of Python, as we will see in the next section). While this generally works, if the `bash` or `python` [@python] executables are installed in a different location than */usr/bin*, then the script does not work anymore. It is better to use the form that we present here, namely *!/usr/bin/env bash* and *!/usr/bin/env python*, because the `env` [@env] executable is aware where `bash` and `python` are installed. In short, using `env` makes your scripts more portable.

### Step 4: Remove Fixed Input 

We know have a valid command-line tool that we can execute from the command line. But we can do better than this. We can make our command-line tool more reusable. The first command in our file is `curl`, which downloads the text from which we wish to obtain the top 10 most-used words. So, the data and operations are combined into one.

What if we wanted to obtain the top 10 most-used words from another e-book, or any other text for that matter? The input data is fixed within the tools itself. It would be better to separate the data from the command-line tool.

If we assume that the user of the command-line tool will provide the text, it will become generally applicable. So, the solution is to simply remove the `curl` command from the script. See Example \@ref(exm:top-words-4) for the updated script named *top-words-4.sh*.

\BeginKnitrBlock{example}\iffalse{-91-126-47-98-111-111-107-47-99-104-48-52-47-116-111-112-45-119-111-114-100-115-45-52-46-115-104-93-}\fi{}
<span class="example" id="exm:top-words-4"><strong>(\#exm:top-words-4)  \iffalse (~/book/ch04/top-words-4.sh) \fi{} </strong></span>
\EndKnitrBlock{example}

```bash
#!/usr/bin/env bash
tr '[:upper:]' '[:lower:]' | grep -oE '\w+' | sort |
uniq -c | sort -nr | head -n 10
```

This works because if a script starts with a command that needs data from standard input, like `tr`, it will take the input that is given to the command-line tools. For example:

    $ cat data/finn.txt | top-words-4.sh

\BeginKnitrBlock{rmdtip}

Although we have not done so in our script, the same principle holds for saving data. It is, in general, better to let the user take care of that. Of course, if you intend to use a command-line tool only for own projects, then there are no limits to how specific you can be.
\EndKnitrBlock{rmdtip}

### Step 5: Parametrize 

There is one more step that we can perform in order to make our command-line tool even more reusable: parameters. In our command-line tool there are a number of fixed command-line arguments, for example `-nr` for `sort` and `-n 10` for `head`. It is probably best to keep the former argument fixed. However, it would be very useful to allow for different values for the `head` command. This would allow the end user to set the number of most-often used words to be outputted. Example \@ref(exm:top-words-5) shows what our file *top-words-5.sh* looks like if we parametrize `head`.

\BeginKnitrBlock{example}\iffalse{-91-126-47-98-111-111-107-47-99-104-48-52-47-116-111-112-45-119-111-114-100-115-45-53-46-115-104-93-}\fi{}
<span class="example" id="exm:top-words-5"><strong>(\#exm:top-words-5)  \iffalse (~/book/ch04/top-words-5.sh) \fi{} </strong></span>
\EndKnitrBlock{example}

```bash
#!/usr/bin/env bash
NUM_WORDS="$1"                                        
tr '[:upper:]' '[:lower:]' | grep -oE '\w+' | sort |
uniq -c | sort -nr | head -n $NUM_WORDS               
```

* The variable *NUM\_WORDS* is set to the value of *\$1*, which is a special variable in Bash. It holds the value of the first command-line argument passed to our command-line tool. The table below lists the other special variables that Bash offers.
* Note that in order to use the value of the *\$NUM\_WORDS* variable, you need to put a dollar sign in front of it. When you set it, you do not write a dollar sign.

\BeginKnitrBlock{rmdtip}

We could have also used *\$1* directly as an argument for `head` and not bother creating an extra variable such *NUM\_WORDS*. However, with larger scripts and a few more command-line arguments such as *\$2* and *\$3*, the code becomes more readable when you use named variables.
\EndKnitrBlock{rmdtip}

Now if we wanted to see the top 5 most-used words of our text, we would invoke our command-line tool as follows:

    $ cat data/finn.txt | top-words-5 5

If the user does not provide an argument then `head` will return an error message, because the value of *\$1*, and therefore *\$NUM\_WORDS* will be an empty string.


```bash
$ cat data/finn.txt | top-words-5
head: option requires an argument -- 'n'
Try 'head --help' for more information.
```

### Step 6: Extend Your PATH 

After the previous five steps we are finally finished building a reusable command-line tool. There is, however, one more step that can be very useful. In this optional step we are going to ensure that you can execute your command-line tools from everywhere.

Currently, when you want to execute your command-line tool, you either have to navigate to the directory it is in or include the full path name as shown in step 2. This is fine if the command-line tool is specifically built for, say, a certain project. However, if your command-line tool could be applied in multiple situations, then it is useful to be able to execute form everywhere, just like the command-line tools that come with Ubuntu.

To accomplish this, Bash needs to know where to look for your command-line tools. It does this by traversing a list of directories which are stored in an environment variable called *PATH*. In a fresh Data Science Toolbox, the *PATH* looks like this:

    $ echo $PATH | fold

The directories are delimited by colons. Here is the list of directories:

    $ echo $PATH | tr ':' '\n'

To change the *PATH* permanently, you’ll need to edit the *.bashrc* or *.profile* file located in your home directory. If you put all your custom command-line tools into one directory, say, *\~/tools*, then you only change the *PATH* once. As you can see, the Data Science Toolbox already has */home/vagrant/.bin* in its *PATH*. Now, you no longer need to add the *./*, but you can just use the filename. Moreover, you do no longer need to remember where the command-line tool is located.

## Creating Command-line Tools with Python and R 

The command-line tool that we created in the previous section was written in Bash. (Sure, not every feature of the Bash language was employed, but the interpreter still was `bash`.) As you may know by now, the command line is language agnostic, so we do not necessarily have to use Bash for creating command-line tools.

In this section we are going demonstrate that command-line tools can be created in other programming languages as well. We will focus on Python and R because these are currently the two most popular programming languages within the data science community. We cannot offer a complete introduction to either language, so we assume that you have some familiarity with Python and or R. Programming languages such as Java, Go, and Julia, follow a similar pattern when it comes to creating command-line tools.

There are three main reasons for creating command-line tools in a programming language instead of Bash. First, you may have existing code that you wish be able to use from the command line. Second, the command-line tool would end up encompassing more than a hundred lines of code. Third, the command-line tool needs to be very fast.

The six steps that we discussed in the previous section roughly apply to creating command-line tools in other programming languages as well. The first step, however, would not be copy pasting from the command line, but rather copy pasting the relevant code into a new file. Command-line tools in Python and R need to specify `python` [@python] and `Rscript` [@R], respectively, as the interpreter after the shebang.

When it comes to creating command-line tools using Python and R, there are two more aspects that deserve special attention, which will be discuss below. First, processing standard input, which comes natural to shell scripts, has to be taken care of explicitly in Python and R. Second, as command-line tools written in Python and R tend to be more complex, we may also want to offer the user the ability to specify more complex command-line arguments.

### Porting The Shell Script 

As a starting point, let’s see how we would port the prior shell script to both Python and R. In other words, what Python and R code gives us the top most-often used words from standard input? It is not important whether implementing this task in anything else than a shell programming language is a good idea. What matters is that it gives us a good opportunity to compare Bash with Python and R.

We will first show the two files *top-words.py* and *top-words.R* and then discuss the differences with the shell code. In Python, the code could would look something like Example \@ref(exm:top-words-py).

\BeginKnitrBlock{example}\iffalse{-91-126-47-98-111-111-107-47-99-104-48-52-47-116-111-112-45-119-111-114-100-115-46-112-121-93-}\fi{}
<span class="example" id="exm:top-words-py"><strong>(\#exm:top-words-py)  \iffalse (~/book/ch04/top-words.py) \fi{} </strong></span>
\EndKnitrBlock{example}

```python
#!/usr/bin/env python
import re
import sys
from collections import Counter
num_words = int(sys.argv[1])
text = sys.stdin.read().lower()
words = re.split('\W+', text)
cnt = Counter(words)
for word, count in cnt.most_common(num_words):
    print "%7d %s" % (count, word)
```

\BeginKnitrBlock{rmdnote}

Example
\@ref(exm:top-words-py)
 uses pure Python. When you want to do advanced text processing we recommend you check out the NLTK package [@Perkins2010]. If you are going to work with a lot of numerical data, then we recommend you use the Pandas package [@McKinney2012].
\EndKnitrBlock{rmdnote}

And in R, the code would look something like Example \@ref(exm:top-words-5) (thanks to Hadley Wickham):

\BeginKnitrBlock{example}\iffalse{-91-126-47-98-111-111-107-47-99-104-48-52-47-116-111-112-45-119-111-114-100-115-46-82-93-}\fi{}
<span class="example" id="exm:top-words-5"><strong>(\#exm:top-words-5)  \iffalse (~/book/ch04/top-words.R) \fi{} </strong></span>
\EndKnitrBlock{example}

```r
#!/usr/bin/env Rscript
n <- as.integer(commandArgs(trailingOnly = TRUE))
f <- file("stdin")
lines <- readLines(f)
words <- tolower(unlist(strsplit(lines, "\\W+")))
counts <- sort(table(words), decreasing = TRUE)
counts_n <- counts[1:n]
cat(sprintf("%7d %s\n", counts_n, names(counts_n)), sep = "")
close(f)
```

Let’s check that all three implementations (i.e., Bash, Python, and R) return the same top 5 words with the same counts:


```bash
$ < data/76.txt top-words.sh 5
   6441 and
   5082 the
   3666 i
   3258 a
   3022 to
$ < data/76.txt top-words.py 5
   6441 and
   5082 the
   3666 i
   3258 a
   3022 to
$ < data/76.txt top-words.R 5
   6441 and
   5082 the
   3666 i
   3258 a
   3022 to
```

Wonderful! Sure, the output itself is not very exciting. What is exciting is the observation that we can accomplish the same task with multiple approaches. Let’s have a look at the differences between the approaches.

First, what’s immediately obvious is the difference in amount of code. For this specific task, both Python and R require much more code than Bash. This illustrates that, for some tasks, it is better to use the command line. For other tasks, you may better off using a programming language. As you gain more experience on the command-line, you will start to recognize when to use which approach. When everything is a command-line tool, you can even split up the task into subtasks, and combine a Bash command-line tool with a, say, Python command-line tool. Whichever approach works best for the task at hand.

### Processing Streaming Data from Standard Input 

In the previous two code snippets, both Python and R read the complete standard input at once. On the command line, most command-line tools pipe data to the next command-line tool in a streaming fashion. (There are a few command-line tools which require the complete data before they write any data to standard output, like `sort` and `awk` [@awk].) This means the pipeline is blocked by such command-line tools. This does not have to be a problem when the input data is finite, like a file. However, when the input data is a non-stop stream, such blocking command-line tools are useless.

Luckily Python and R support processing streaming data. You can apply a function on a line-per-line basis, for example. Example \@ref(exm:stream-py) and Example \@ref(exm:stream-r) are two minimal examples that demonstrate how this works in Python and R, respectively.

\BeginKnitrBlock{example}\iffalse{-91-126-47-98-111-111-107-47-99-104-48-52-47-115-116-114-101-97-109-46-112-121-93-}\fi{}
<span class="example" id="exm:stream-py"><strong>(\#exm:stream-py)  \iffalse (~/book/ch04/stream.py) \fi{} </strong></span>
\EndKnitrBlock{example}

```python
#!/usr/bin/env python
from sys import stdin, stdout
while True:
    line = stdin.readline()
    if not line:
        break
    stdout.write("%d\n" % int(line)**2)
    stdout.flush()
```

\BeginKnitrBlock{example}\iffalse{-91-126-47-98-111-111-107-47-99-104-48-52-47-115-116-114-101-97-109-46-82-93-}\fi{}
<span class="example" id="exm:stream-r"><strong>(\#exm:stream-r)  \iffalse (~/book/ch04/stream.R) \fi{} </strong></span>
\EndKnitrBlock{example}

```r
#!/usr/bin/env Rscript
f <- file("stdin")
open(f)
while(length(line <- readLines(f, n = 1)) > 0) {
        write(as.integer(line)^2, stdout())
}
close(f)
```

## Further Reading 

* Docopt. 2014. “Command-Line Interface Description Language.” <a href="http://docopt.org" class="uri">http://docopt.org</a>.
* Robbins, Arnold, and Nelson H. F. Beebe. 2005. <em>Classic Shell Scripting</em>. O’Reilly Media.
* Peek, Jerry, Shelley Powers, Tim O’Reilly, and Mike Loukides. 2002. <em>Unix Power Tools</em>. 3rd Ed. O’Reilly Media.
* Perkins, Jacob. 2010. <em>Python Text Processing with Nltk 2.0 Cookbook</em>. Packt Publishing.
* McKinney, Wes. 2012. <em>Python for Data Analysis</em>. O’Reilly Media.
* Rossant, Cyrille. 2013. <em>Learning Ipython for Interactive Computing and Data Visualization</em>. Packt Publishing.
* Wirzenius, Lars. 2013. “Writing Manual Pages.” <a href="http://liw.fi/manpages/" class="uri">http://liw.fi/manpages/</a>.
* Raymond, Eric Steven. 2014. “Basics of the Unix Philosophy.” <a href="http://www.faqs.org/docs/artu/ch01s06.html" class="uri">http://www.faqs.org/docs/artu/ch01s06.html</a>.

<!--chapter:end:04.Rmd-->

# Scrubbing Data {#chapter-5-scrubbing-data}

Two chapters ago, in Step 1 of the OSEMN model for data science, we looked at how to obtain data from a variety of sources. It’s not uncommon for this data to have missing values, inconsistencies, errors, weird characters, or uninteresting columns. Sometimes we only need a specific portion of the data. And sometimes we need the data to be in a different format. In those cases, we have to scrub, or clean, the data before we can move on to Step 3: Exploring Data.

The data we obtained in Chapter 3 can come in a variety of formats. The most common ones are plain text, CSV, JSON, and HTML/XML. Since most command-line tools operate on one format only, it is worthwhile to be able to convert data from one format to another.

CSV, which is the main format we’re working with in this chapter, is actually not the easiest format to work with. Many CSV data sets are broken or incompatible with each other because there is no standard syntax, unlike XML and JSON.

Once our data is in the format we want it to be, we can apply common scrubbing operations. These include filtering, replacing, and merging data. The command line is especially well-suited for these kind of operations, as there exist many powerful command-line tools that are optimized for handling large amounts of data. Tools that we’ll discuss in this chapter include classic ones such as: `cut` [@cut] and `sed` [@sed], and newer ones such as `jq` [@jq] and `csvgrep` [@csvgrep].

The scrubbing tasks that we discuss in this chapter not only apply to the input data. Sometimes, we also need to reformat the output of some command-line tools. For example, to transform the output of `uniq -c` to a CSV data set, we could use `awk` [@awk] and `header`:


```bash
$ printf 'foo\nbar\nfoo' | sort | uniq -c | sort -nr
      2 foo
      1 bar
$ printf 'foo\nbar\nfoo' | sort | uniq -c | sort -nr |
> awk '{print $2","$1}' | header -a 'value, count'
value,count
foo,2
bar,1
```

If your data requires additional functionality than that is offered by (a combination of) these command-line tools, you can use `csvsql`. This is a new command-line tool that allow you to perform SQL queries directly on CSV files. And remember, if after reading this chapter you still need more flexibility, you’re free to use R, Python, or whatever programming language you prefer.

The command-line tools will be introduced on a need-to-use basis. You will notice that sometimes we can use the same command-line tool to perform multiple operations, or vice versa, multiple command-line tools to perform the same operation. This chapter is more structured like a cookbook, where the focus is on the problems or recipes, rather than on the command-line tools.

## Overview 

In this chapter, you’ll learn how to:

- Convert data from one format to another.
- Apply SQL queries to CSV.
- Filter lines.
- Extract and replace values.

- Split, merge, and extract columns.

## Common Scrub Operations for Plain Text 

In this section we describe common scrubbing operations for plain text. Formally, plain text refers to a sequence of human-readable characters and optionally, some specific types of control characters (for example a tab or a newline) (see: <http://www.linfo.org/plain_text.html>). Examples include: e-books, emails, log files, and source code.

For the purpose of this book, we assume that the plain text contains some data, and that it has no clear tabular structure (like the CSV format) or nested structure (like the JSON and HTML formats). We discuss those formats later in this chapter. Although these operations can also be applied to CSV, JSON and XML/HTML formats, keep in mind that the tools treat the data as plain text.

### Filtering Lines 

The first scrubbing operation is filtering lines. This means that from the input data, each line will be evaluated whether it may be passed on as output.

#### Based on Location 

The most straightforward way to filter lines is based on their location. This may be useful when you want to inspect, say, the top 10 lines of a file, or when you extract a specific row from the output of another command-line tool. To illustrate how to filter based on location, let’s create a dummy file that contains 10 lines:


```bash
$ seq -f "Line %g" 10 | tee data/lines
Line 1
Line 2
Line 3
Line 4
Line 5
Line 6
Line 7
Line 8
Line 9
Line 10
```

We can print the first 3 lines using either `head`, `sed`, or `awk`:


```bash
$ < lines head -n 3
$ < lines sed -n '1,3p'
$ < lines awk 'NR<=3'
Line 1
Line 2
Line 3
```

Similarly, we can print the last 3 lines using `tail` [@tail]:


```bash
$ < lines tail -n 3
Line 8
Line 9
Line 10
```

You can also you use `sed` and `awk` for this, but `tail` is much faster.

Removing the first 3 lines goes as follows:


```bash
$ < lines tail -n +4
$ < lines sed '1,3d'
$ < lines sed -n '1,3!p'
Line 4
Line 5
Line 6
Line 7
Line 8
Line 9
Line 10
```

Please notice that with tail you have to add one.

Removing the last 3 lines can be done with `head`:


```bash
$ < lines head -n -3
Line 1
Line 2
Line 3
Line 4
Line 5
Line 6
Line 7
```

You can print (or extract) specific lines (4, 5, and 6 in this case) using a either `sed`, `awk`, or a combination of `head` and `tail`:


```bash
$ < lines sed -n '4,6p'
$ < lines awk '(NR>=4)&&(NR<=6)'
$ < lines head -n 6 | tail -n 3
Line 4
Line 5
Line 6
```

Print odd lines with `sed` by specifying a start and a step, or with `awk` by using the modulo operator:


```bash
$ < lines sed -n '1~2p'
$ < lines awk 'NR%2'
Line 1
Line 3
Line 5
Line 7
Line 9
```

Printing even lines works in a similar manner:


```bash
$ < lines sed -n '0~2p'
$ < lines awk '(NR+1)%2'
Line 2
Line 4
Line 6
Line 8
Line 10
```

#### Based on Pattern 

Sometimes you want to extract or remove lines based on their contents. Using `grep`, the canonical command-line tool for filtering lines, we can print every line that matches a certain pattern or regular expression. For example, to extract all the chapter headings from *Alice’s Adventures in Wonderland*:


```bash
$ grep -i chapter alice.txt
CHAPTER I. Down the Rabbit-Hole
CHAPTER II. The Pool of Tears
CHAPTER III. A Caucus-Race and a Long Tale
CHAPTER IV. The Rabbit Sends in a Little Bill
CHAPTER V. Advice from a Caterpillar
CHAPTER VI. Pig and Pepper
CHAPTER VII. A Mad Tea-Party
CHAPTER VIII. The Queen's Croquet-Ground
CHAPTER IX. The Mock Turtle's Story
CHAPTER X. The Lobster Quadrille
CHAPTER XI. Who Stole the Tarts?
CHAPTER XII. Alice's Evidence
```

Here, `-i` means case-insensitive. We can also specify a regular expression. For example, if we only wanted to print out the headings which start with *The*:


```bash
$ grep -E '^CHAPTER (.*)\. The' alice.txt
CHAPTER II. The Pool of Tears
CHAPTER IV. The Rabbit Sends in a Little Bill
CHAPTER VIII. The Queen's Croquet-Ground
CHAPTER IX. The Mock Turtle's Story
CHAPTER X. The Lobster Quadrille
```

Please note that you have to specify the `-E` command-line argument in order to enable regular expressions. Otherwise, `grep` interprets the pattern as a literal string.

#### Based on Randomness 

When you’re in the process of formulating your data pipeline and you have a lot of data, then debugging your pipeline can be cumbersome. In that case, sampling from the data might be useful. The main purpose of the command-line tool `sample` [@sample] is to get a subset of the data by outputting only a certain percentage of the input on a line-by-line basis.


```bash
$ seq 1000 | sample -r 1% | jq -c '{line: .}'
{"line":53}
{"line":119}
{"line":141}
{"line":228}
{"line":464}
{"line":476}
{"line":523}
{"line":657}
{"line":675}
{"line":865}
{"line":948}
```

Here, every input line has a one percent chance of being forwarded to `jq`. This percentage could also have been specified as a fraction (*1/100*) or as a probability (*0.01*).

`sample` has two other purposes, which can be useful when you’re in debugging. First, it’s possible to add some delay to the output. This comes in handy when the input is a constant stream (for example, the Twitter firehose), and the data comes in too fast to see what’s going on. Secondly, you can put a timer on `sample`. This way, you don’t have to kill the ongoing process manually. To add a 1 second delay between each output line to the previous command and to only run for 5 seconds:


```bash
$ seq 10000 | sample -r 1% -d 1000 -s 5 | jq -c '{line: .}'
```

In order to prevent unnecessary computation, try to put `sample` as early as possible in your pipeline (this argument holds any command-line tool that reduces data, like `head` and `tail`). Once you’re done debugging you can simply take it out of the pipeline.

### Extracting Values 

To extract the actual chapter headings from our example earlier, we can take a simple approach by piping the output of `grep` to `cut`:


```bash
$ grep -i chapter alice.txt | cut -d' ' -f3-
Down the Rabbit-Hole
The Pool of Tears
A Caucus-Race and a Long Tale
The Rabbit Sends in a Little Bill
Advice from a Caterpillar
Pig and Pepper
A Mad Tea-Party
The Queen's Croquet-Ground
The Mock Turtle's Story
The Lobster Quadrille
Who Stole the Tarts?
Alice's Evidence
```

Here, each line that’s passed to `cut` is being split on spaces into fields, and then the third field to the last field is being printed. The total number of fields may be different per input line. With `sed` we can accomplish the same task in a much more complex manner:


```bash
$ sed -rn 's/^CHAPTER ([IVXLCDM]{1,})\. (.*)$/\2/p' alice.txt > /dev/null
```

(Since the output is the same it’s omitted by redirecting it to */dev/null*.) This approach uses a regular expression and a back reference. Here, `sed` also takes over the work done by `grep`. This complex approach is only advisable when a simpler one would not work. For example, if *chapter* was ever part of the text itself and not just used to indicate the start of a new chapter. Of course there are many levels of complexity which would have worked around this, but this was to illustrate an extremely strict approach. In practice, the challenge is to find a good balance between complexity and flexibility.

It’s worth noting that `cut` can also split on characters positions. This is useful for when you want to extract (or remove) the same set of characters per input line:


```bash
$ grep -i chapter alice.txt | cut -c 9-
I. Down the Rabbit-Hole
II. The Pool of Tears
III. A Caucus-Race and a Long Tale
IV. The Rabbit Sends in a Little Bill
V. Advice from a Caterpillar
VI. Pig and Pepper
VII. A Mad Tea-Party
VIII. The Queen's Croquet-Ground
IX. The Mock Turtle's Story
X. The Lobster Quadrille
XI. Who Stole the Tarts?
XII. Alice's Evidence
```

`grep` has a great feature that outputs every match onto a separate line:


```bash
$ < alice.txt grep -oE '\w{2,}' | head
Project
Gutenberg
Alice
Adventures
in
Wonderland
by
Lewis
Carroll
This
```

But what if we wanted to create a data set of all the words that start with an *a* and end with an *e*. Well, of course there’s a pipeline for that too:


```bash
$ < alice.txt tr '[:upper:]' '[:lower:]' | grep -oE '\w{2,}' |
> grep -E '^a.*e$' | sort | uniq -c | sort -nr |
> awk '{print $2","$1}' | header -a word,count | head | csvlook
|-------------+--------|
|  word       | count  |
|-------------+--------|
|  alice      | 403    |
|  are        | 73     |
|  archive    | 13     |
|  agree      | 11     |
|  anyone     | 5      |
|  alone      | 5      |
|  age        | 4      |
|  applicable | 3      |
|  anywhere   | 3      |
|  alive      | 3      |
|-------------+--------|
```

### Replacing and Deleting Values 

You can use the command-line tool `tr`, which stands for translate, to replace individual characters. For example, spaces can be replaced by underscores as follows:


```bash
$ echo 'hello world!' | tr ' ' '_'
hello_world!
```

If more than one character needs to be replaced, then you can combine that:


```bash
$ echo 'hello world!' | tr ' !' '_?'
hello_world?
```

`tr` can also be used to delete individual characters by specifying the argument `-d`:


```bash
$ echo 'hello world!' | tr -d -c '[a-z]'
helloworld
```

Here, we’ve actually used two more features. First we’ve specified a set of characters (all lowercase letters). Second we’ve indicated that the complement `-c` should be used. In other words, this command only retains lowercase letters. We can even use `tr` to convert our text to uppercase:


```bash
$ echo 'hello world!' | tr '[a-z]' '[A-Z]'
HELLO WORLD!
$ echo 'hello world!' | tr '[:lower:]' '[:upper:]'
HELLO WORLD!
```

The latter command is preferable because that also handles non-ASCII characters. If you need to operate on more than individual characters, then you may find `sed` useful. We’ve already seen an example of `sed` with extracting the chapter headings from Alice in Wonderland. Extracting, deleting, and replacing is actually all the same operation in `sed`. You just specify different regular expressions. For example, to change a word, remove repeated spaces, and remove leading spaces:


```bash
$ echo ' hello     world!' | sed -re 's/hello/bye/;s/\s+/ /g;s/\s+//'
bye world!
```

The argument `-g` stands for global, meaning that the same command can be applied more than once on the same line. We do not need that with the second command, which removes leading spaces. Note that regular expressions of the first and the last command could have been combined into one regular expression.

## Working with CSV 

### Bodies and Headers and Columns, Oh My! 

The command-line tools that we’ve used to scrub plain text, such as `tr` and `grep`, cannot always be applied to CSV. The reason is that these command-line tools have no notion of headers, bodies, and columns. What if we wanted to filter lines using `grep` but always include the header in the output? Or what if we only wanted to uppercase the values of a specific column using `tr` and leave the other columns untouched? There are multi-step workarounds for this, but they are very cumbersome. We have something better. In order to leverage ordinary command-line tools for CSV, we’d like to introduce you to three command-line tools, aptly named: `body` [@body], `header` [@header], and `cols` [@cols].

Let’s start with the first command-line tool, `body`. With `body` you can apply any command-line tool to the body of a CSV file, that is, everything excluding the header. For example:


```bash
$ echo -e "value\n7\n2\n5\n3" | body sort -n
value
2
3
5
7
```

It assumes that the header of the CSV file only spans one row. Here’s the source code for completeness:


```bash
#!/usr/bin/env bash
IFS= read -r header        
printf '%s\n' "$header"    
$@                         
```

It works like this:

- Take one line from standard in and store it as a variable named *\$header*.
- Print out the header.
- Execute all the command-line arguments passed to `body` on the remaining data in standard in.

Here’s another example. Imagine that we count the lines of the following CSV file:


```bash
$ seq 5 | header -a count
count
1
2
3
4
5
```

With `wc -l`, we can count the number of all lines:


```bash
$ seq 5 | header -a count | wc -l
6
```

If we only want to consider the lines in the body (so everything except the header), we simply add `body`:


```bash
$ seq 5 | header -a count | body wc -l
count
5
```

Note that the header is not used and is also printed again in the output.

The second command-line tool, `header` allows us, as the name implies, to manipulate the header of a CSV file. The complete source code is as follows:


```bash
#!/usr/bin/env bash
get_header () {
        for i in $(seq $NUMROWS); do
                IFS= read -r LINE
                OLDHEADER="${OLDHEADER}${LINE}\n"
        done
}

print_header () {
        echo -ne "$1"
}

print_body () {
        cat
}

OLDHEADER=
NUMROWS=1

while getopts "dn:ha:r:e:" OPTION
do
        case $OPTION in
                n)
                        NUMROWS=$OPTARG
                        ;;
                a)
                        print_header "$OPTARG\n"
                        print_body
                        exit 1
                        ;;
                d)
                        get_header
                        print_body
                        exit 1
                        ;;
                r)
                        get_header
                        print_header "$OPTARG\n"
                        print_body
                        exit 1
                        ;;
                e)
                        get_header
                        print_header "$(echo -ne $OLDHEADER | eval $OPTARG)\n"
                        print_body
                        exit 1
                        ;;
                h)
                        usage
                        exit 1
                        ;;
        esac
done

get_header
print_header $OLDHEADER
```

If no argument are provided, the header of the CSV file is printed:


```bash
$ < tips.csv | header
bill,tip,sex,smoker,day,time,size
```

This is the same as `head -n 1`. If the header spans more than one row, which is not recommended, you can specify `-n 2`. We can also add a header to a CSV file:


```bash
$ seq 5 | header -a count
count
1
2
3
4
5
```

This is equivalent to `echo "count" | cat - <(seq 5)`. Deleting a header is done with the `-d` command-line argument:


```bash
$ < iris.csv | header -d | head
5.1,3.5,1.4,0.2,Iris-setosa
4.9,3.0,1.4,0.2,Iris-setosa
4.7,3.2,1.3,0.2,Iris-setosa
4.6,3.1,1.5,0.2,Iris-setosa
5.0,3.6,1.4,0.2,Iris-setosa
5.4,3.9,1.7,0.4,Iris-setosa
4.6,3.4,1.4,0.3,Iris-setosa
5.0,3.4,1.5,0.2,Iris-setosa
4.4,2.9,1.4,0.2,Iris-setosa
4.9,3.1,1.5,0.1,Iris-setosa
```

This is similar to `tail -n +2`, but it’s a bit easier to remember. Replacing a header, which is basically first deleting a header and then adding one if you look at the above source code, is accomplished with specifying `-r`. Here, we combine it with `body`:


```bash
$ seq 5 | header -a line | body wc -l | header -r count
count
5
```

And last but not least, we can apply a command to just the header, similar to what the `body` command-line tool does to the body:


```bash
$ seq 5 | header -a line | header -e "tr '[a-z]' '[A-Z]'"
LINE
1
2
3
4
5
```

The third command-line tool is called `cols`, which is similar to `header` and `body` in that it allows you to apply a certain command to only a subset of the columns. The code is as follows:


```bash
#!/usr/bin/env bash
ARG="$1"
shift
COLUMNS="$1"
shift
EXPR="$@"
DIRTMP=$(mktemp -d)
mkfifo $DIRTMP/other_columns
tee $DIRTMP/other_columns | csvcut $ARG $COLUMNS | ${EXPR} |
paste -d, - <(csvcut ${ARG~~} $COLUMNS $DIRTMP/other_columns)
rm -rf $DIRTMP
```

For example, if we wanted to uppercase the values in the day column in the tips data set (without affecting the other columns and the header), we would use `cols` in combination with `body`, as follows:


```bash
$ < tips.csv cols -c day body "tr '[a-z]' '[A-Z]'" | head -n 5 | csvlook -I
|------+-------+------+--------+--------+--------+-------|
|  day | bill  | tip  | sex    | smoker | time   | size  |
|------+-------+------+--------+--------+--------+-------|
|  SUN | 16.99 | 1.01 | Female | No     | Dinner | 2     |
|  SUN | 10.34 | 1.66 | Male   | No     | Dinner | 3     |
|  SUN | 21.01 | 3.5  | Male   | No     | Dinner | 3     |
|  SUN | 23.68 | 3.31 | Male   | No     | Dinner | 2     |
|------+-------+------+--------+--------+--------+-------|
```

Please note that passing multiple command-line tools and arguments as command to `header -e`, `body`, and `cols` can lead to tricky quoting citations. If you ever run in such problems, it is best to create a separate command-line tool for this and pass that as command.

In conclusion, while it is generally preferable to use command-line tools which are specifically made for CSV data, `body`, `header`, and `cols` also allow you to apply the classic command-line tools to CSV files if needed.

### Performing SQL Queries on CSV 

In case the command-line tools mentioned in this chapter do not provide enough flexibility, then there is another approach to scrub your data from the command line. The command-line tool `csvsql` [@csvsql] allows you to execute SQL queries directly on CSV files. As you may know, SQL is a very powerful language to define operations for scrubbing data; it is a very different way than using individual command-line tools.

\BeginKnitrBlock{rmdnote}

If your data originally comes from a relational database, then, if possible, try to execute SQL queries on that database and subsequently extract the data as CSV. As discussed in Chapter 3, you can use the command-line tool `sql2csv` for this. When you first export data from the database to a CSV file, and then apply SQL, it is not only slower, but there is also a possibility that the column types are not correctly inferred from the CSV data.
\EndKnitrBlock{rmdnote}

In the scrubbing tasks below, we’ll include several solutions that involve `csvsql`. The basic command is this:


```bash
$ seq 5 | header -a value | csvsql --query "SELECT SUM(value) AS sum FROM stdin"
sum
15
```

If you pass standard input to `csvsql`, then the table is named *stdin*. The types of the column are automatically inferred from the data. As you will see later, in the combining CSV files section, you can also specify multiple CSV files. Please keep in mind that `csvsql` employs SQLite dialect. While SQL is generally more verbose than the other solutions, it is also much more flexible. If you already know how to tackle a scrubbing problem with SQL, then there’s no shame in using it from the command line!

## Working with XML/HTML and JSON 

As we have seen in Chapter 3, our obtained data can come in a variety of formats. The most common ones are plain text, CSV, JSON, and HTML/XML. In this section we are going to demonstrate a couple of command-line tools that can convert our data from one format to another. There are two reasons to convert data.

First, oftentimes, the data needs to be in tabular form, just like a database table or a spreadsheet, because many visualization and machine learning algorithms depend on it. CSV is inherently in tabular form, but JSON and HTML/XML data can have a deeply nested structure.

Second, many command-line tools, especially the classic ones such as `cut` and `grep`, operate on plain text. This is because text is regarded as a universal interface between command-line tools. Moreover, the other formats are simply younger. Each of these formats can be treated as plain text, allowing us to apply such command-line tools to the other formats as well.

Sometimes we can get away with applying the classic tools to structured data. For example, by treating the JSON data below as plain text, we can change the attribute *gender* to *sex* using `sed`:

    $ sed -e 's/"gender":/"sex":/g' data/users.json | fold | head -n 3

Like many other command-line tools, `sed` does not make use of the structure of the data. Better is to either use a command-line tool that makes use of the structure of the data (such as `jq` which we discuss below), or first convert the data to a tabular format such as CSV and then apply the appropriate command-line tool.

We’re going to demonstrate converting XML/HTML and JSON to CSV through a real-world use case. The command-line tools that we’ll be using here are: `curl`, `scrape` [@scrape], `xml2json` [@xml2json], `jq` [@jq], and `json2csv` [@json2csv].

Wikpedia holds a wealth of information. Much of this information is ordered in tables, which can be regarded as data sets. For example, the page <http://en.wikipedia.org/wiki/List_of_countries_and_territories_by_border/area_ratio> contains a list of countries and territories together with their border length, their area, and the ration between the two.

Let’s imagine that we’re interested in analyzing this data. In this section, we’ll walk you through all the necessary steps and their corresponding commands. We won’t go into every little detail, so it could be that you won’t understand everything right away. Don’t worry, we’re confident that you’ll get the gist of it. Remember that the purpose of this section is to demonstrate the command line. All tools and concepts used in this section (and more) will be explained in the subsequent chapters.

The data set that we’re interested in, is embedded in HTML. Our goal is to end up with a representation of this data set that we can work with. The very first step is to download the HTML using `curl`:


```bash
$ curl -sL 'http://en.wikipedia.org/wiki/List_of_countries_and_territories_'\
> 'by_border/area_ratio' > data/wiki.html
```

The option `-s` causes `curl` to be silent and not output any other information but the actual HTML. The HTML is saved to a file named `data/wiki.html`. Let’s see how the first 10 lines look like:


```bash
$ head -n 10 data/wiki.html | cut -c1-79
<!DOCTYPE html>
<html lang="en" dir="ltr" class="client-nojs">
<head>
<meta charset="UTF-8" /><title>List of countries and territories by border/area
<meta http-equiv="X-UA-Compatible" content="IE=EDGE" /><meta name="generator" c
<link rel="alternate" type="application/x-wiki" title="Edit this page" href="/w
<link rel="edit" title="Edit this page" href="/w/index.php?title=List_of_countr
<link rel="apple-touch-icon" href="//bits.wikimedia.org/apple-touch/wikipedia.p
<link rel="shortcut icon" href="//bits.wikimedia.org/favicon/wikipedia.ico" />
<link rel="search" type="application/opensearchdescription+xml" href="/w/opense
```

That seems to be in order. (Note that we’re only showing the first 79 characters of each line so that output fits on the page.)

Using the developer tools of our browser, we were able to determine that the root HTML element that we’re interested in is a *&lt;table&gt;* with the class *wikitable*. This allows us to look at the part that we’re interest in using `grep` (the `-A` command-line argument specifies the number of lines we want to see after the matching line):


```bash
$ < data/wiki.html grep wikitable -A 21
<table class="wikitable sortable">
<tr>
<th>Rank</th>
<th>Country or territory</th>
<th>Total length of land borders (km)</th>
<th>Total surface area (kmÂ²)</th>
<th>Border/area ratio (km/kmÂ²)</th>
</tr>
<tr>
<td>1</td>
<td>Vatican City</td>
<td>3.2</td>
<td>0.44</td>
<td>7.2727273</td>
</tr>
<tr>
<td>2</td>
<td>Monaco</td>
<td>4.4</td>
<td>2</td>
<td>2.2000000</td>
</tr>
```

We now actually see the countries and their values that we first saw in the screenshot. The next step is to extract the necessary elements from the HTML file. For this we use the `scrape` tool:


```bash
$ < data/wiki.html scrape -b -e 'table.wikitable > tr:not(:first-child)' \
> > data/table.html
$ head -n 21 data/table.html
<!DOCTYPE html>
<html>
<body>
<tr><td>1</td>
<td>Vatican City</td>
<td>3.2</td>
<td>0.44</td>
<td>7.2727273</td>
</tr>
<tr><td>2</td>
<td>Monaco</td>
<td>4.4</td>
<td>2</td>
<td>2.2000000</td>
</tr>
<tr><td>3</td>
<td>San Marino</td>
<td>39</td>
<td>61</td>
<td>0.6393443</td>
</tr>
```

The value passed to argument `-e`, which stands for *expression* (also with many other command-line tools), is a so-called CSS-selector. The syntax is usually used to style web pages, but we can also use it to select certain elements from our HTML. In this case, we wish to select all *&lt;tr&gt;* elements or *rows* (except the first) that are part of a table which belongs to the *wikitable* class. This is precisely the table that we’re interested in. The reason that we don’t want the first row (specified by *:not(first-child)*) is that we don’t want the header of the table. This results in a data set where each row represents a country or territory. As you can see, we now have a *&lt;tr&gt;* elements that we’re looking for, encapsulated in *&lt;html&gt;\` and '&lt;body&gt;* elements (because we specified the `-b` argument). This ensures that our next tool, `xml2json`, can work with it.

As its name implies, `xml2json` converts XML (and HTML) to JSON.


```bash
$ < data/table.html xml2json > data/table.json
$ < data/table.json jq '.' | head -n 25
{
  "html": {
    "body": {
      "tr": [
        {
          "td": [
            {
              "$t": "1"
            },
            {
              "$t": "Vatican City"
            },
            {
              "$t": "3.2"
            },
            {
              "$t": "0.44"
            },
            {
              "$t": "7.2727273"
            }
          ]
        },
        {
          "td": [
```

The reason we convert the HTML to JSON is because there is a very powerful tool called `jq` that operates on JSON data. The following command extracts certain parts of the JSON data and reshapes it into a form that we can work with:


```bash
$ < data/table.json jq -c '.html.body.tr[] | {country: .td[1][],border:'\
> '.td[2][], surface: .td[3][]}' > data/countries.json
$ head -n 10 data/countries.json
{"surface":"0.44","border":"3.2","country":"Vatican City"}
{"surface":"2","border":"4.4","country":"Monaco"}
{"surface":"61","border":"39","country":"San Marino"}
{"surface":"160","border":"76","country":"Liechtenstein"}
{"surface":"34","border":"10.2","country":"Sint Maarten (Netherlands)"}
{"surface":"468","border":"120.3","country":"Andorra"}
{"surface":"6","border":"1.2","country":"Gibraltar (United Kingdom)"}
{"surface":"54","border":"10.2","country":"Saint Martin (France)"}
{"surface":"2586","border":"359","country":"Luxembourg"}
{"surface":"6220","border":"466","country":"Palestinian territories"}
```

Now we’re getting somewhere. JSON is a very popular data format, with many advantages, but for our purposes, we’re better off with having the data in CSV format. The tool `json2csv` is able to convert the data from JSON to CSV:


```bash
$ < data/countries.json json2csv -p -k border,surface > data/countries.csv
$ head -n 11 data/countries.csv | csvlook
|---------+----------|
|  border | surface  |
|---------+----------|
|  3.2    | 0.44     |
|  4.4    | 2        |
|  39     | 61       |
|  76     | 160      |
|  10.2   | 34       |
|  120.3  | 468      |
|  1.2    | 6        |
|  10.2   | 54       |
|  359    | 2586     |
|  466    | 6220     |
|---------+----------|
```

The data is now in a form that we can work with. Those were quite a few steps to get from a Wikipedia page to a CSV data set. However, when you combine all of the above commands into one, you will see that it’s actually really concise and expressive:


```bash
$ curl -sL 'http://en.wikipedia.org/wiki/List_of_countries'\
> '_and_territories_by_border/area_ratio' |
> scrape -be 'table.wikitable > tr:not(:first-child)' |
> xml2json | jq -c '.html.body.tr[] | {country: .td[1][],'\
> 'border: .td[2][], surface: .td[3][], ratio: .td[4][]}' |
> json2csv -p -k=border,surface | head -n 11 | csvlook
|---------+----------|
|  border | surface  |
|---------+----------|
|  3.2    | 0.44     |
|  4.4    | 2        |
|  39     | 61       |
|  76     | 160      |
|  10.2   | 34       |
|  120.3  | 468      |
|  1.2    | 6        |
|  10.2   | 54       |
|  359    | 2586     |
|  466    | 6220     |
|---------+----------|
```

That concludes the demonstration of conversion XML/HTML to JSON to CSV. While `jq` can perform much more operations, and while there exist specialized tools to work with XML data, in our experience, converting the data to CSV format as quickly as possible tends to work well. This way, you can spend more time becoming proficient at generic command-line tools, rather than very specific tools.

## Common Scrub Operations for CSV 

### Extracting and Reordering Columns 

Columns can be extracted and reordered using the command-line tool: `csvcut` [@csvcut]. For example, to keep only the columns in the Iris data set that contain numerical values *and* reorder the middle two columns:


```bash
$ < iris.csv csvcut -c sepal_length,petal_length,sepal_width,petal_width |
> head -n 5 | csvlook
|---------------+--------------+-------------+--------------|
|  sepal_length | petal_length | sepal_width | petal_width  |
|---------------+--------------+-------------+--------------|
|  5.1          | 1.4          | 3.5         | 0.2          |
|  4.9          | 1.4          | 3.0         | 0.2          |
|  4.7          | 1.3          | 3.2         | 0.2          |
|  4.6          | 1.5          | 3.1         | 0.2          |
|---------------+--------------+-------------+--------------|
```

Alternatively, we can also specify the columns we want to leave out with `-C`, which stands for *complement*:


```bash
$ < iris.csv csvcut -C species | head -n 5 | csvlook
|---------------+-------------+--------------+--------------|
|  sepal_length | sepal_width | petal_length | petal_width  |
|---------------+-------------+--------------+--------------|
|  5.1          | 3.5         | 1.4          | 0.2          |
|  4.9          | 3.0         | 1.4          | 0.2          |
|  4.7          | 3.2         | 1.3          | 0.2          |
|  4.6          | 3.1         | 1.5          | 0.2          |
|---------------+-------------+--------------+--------------|
```

Here, the included columns are kept in the same order. Instead of the column names, you can also specify the indices of the columns, which start at 1. This allows you to, for example, select only the odd columns (should you ever need it!):


```bash
$ echo 'a,b,c,d,e,f,g,h,i\n1,2,3,4,5,6,7,8,9' |
> csvcut -c $(seq 1 2 9 | paste -sd,)
a,c,e,g,i
1,3,5,7,9
```

If you’re certain that there are no comma’s in any of the values, then you can also use `cut` to extract columns. Be aware that `cut` does not reorder columns, as is demonstrated with the following command:


```bash
$ echo 'a,b,c,d,e,f,g,h,i\n1,2,3,4,5,6,7,8,9' | cut -d, -f 5,1,3
a,c,e
1,3,5
```

As you can see, it does not matter in which order we specify the columns with `-f`, with `cut` they will always appear in the original order. For completeness, let’s also take a look at the SQL approach for extracting and reordering the numerical columns of the Iris data set:


```bash
$ < iris.csv csvsql --query "SELECT sepal_length, petal_length, "\
> "sepal_width, petal_width FROM stdin" | head -n 5 | csvlook
|---------------+--------------+-------------+--------------|
|  sepal_length | petal_length | sepal_width | petal_width  |
|---------------+--------------+-------------+--------------|
|  5.1          | 1.4          | 3.5         | 0.2          |
|  4.9          | 1.4          | 3.0         | 0.2          |
|  4.7          | 1.3          | 3.2         | 0.2          |
|  4.6          | 1.5          | 3.1         | 0.2          |
|---------------+--------------+-------------+--------------|
```

### Filtering Lines 

The difference between filtering lines in a CSV file as opposed to a plain text file is that you may want to base this filtering on values in a certain column, only. Filtering on location is essentially the same, but you have to take into account that the first line of a CSV file is usually the header. Remember that you can always use the `body` command-line tool if you want to keep the header:


```bash
$ seq 5 | sed -n '3,5p'
3
4
5
$ seq 5 | header -a count | body sed -n '3,5p'
count
3
4
5
```

When it comes down to filtering on a certain pattern within a certain column, we can use either `csvgrep`, `awk`, or, of course, `csvsql`. For example, to exclude all the bills of which the party size was 4 or less:


```bash
$ csvgrep -c size -i -r "[1-4]" tips.csv | csvlook
|--------+------+--------+--------+------+--------+-------|
|  bill  | tip  | sex    | smoker | day  | time   | size  |
|--------+------+--------+--------+------+--------+-------|
|  29.8  | 4.2  | Female | No     | Thur | Lunch  | 6     |
|  34.3  | 6.7  | Male   | No     | Thur | Lunch  | 6     |
|  41.19 | 5.0  | Male   | No     | Thur | Lunch  | 5     |
|  27.05 | 5.0  | Female | No     | Thur | Lunch  | 6     |
|  29.85 | 5.14 | Female | No     | Sun  | Dinner | 5     |
|  48.17 | 5.0  | Male   | No     | Sun  | Dinner | 6     |
|  20.69 | 5.0  | Male   | No     | Sun  | Dinner | 5     |
|  30.46 | 2.0  | Male   | Yes    | Sun  | Dinner | 5     |
|  28.15 | 3.0  | Male   | Yes    | Sat  | Dinner | 5     |
|--------+------+--------+--------+------+--------+-------|
```

Both `awk` and `csvsql` can also do numerical comparisons. For example, to get all the bills above 40 USD on a Saturday or a Sunday:


```bash
$ < tips.csv awk -F, '($1 > 40.0) && ($5 ~ /S/)' | csvlook -I
|--------+------+--------+-----+-----+--------+----|
|  48.27 | 6.73 | Male   | No  | Sat | Dinner | 4  |
|--------+------+--------+-----+-----+--------+----|
|  44.3  | 2.5  | Female | Yes | Sat | Dinner | 3  |
|  48.17 | 5.0  | Male   | No  | Sun | Dinner | 6  |
|  50.81 | 10.0 | Male   | Yes | Sat | Dinner | 3  |
|  45.35 | 3.5  | Male   | Yes | Sun | Dinner | 3  |
|  40.55 | 3.0  | Male   | Yes | Sun | Dinner | 2  |
|  48.33 | 9.0  | Male   | No  | Sat | Dinner | 4  |
|--------+------+--------+-----+-----+--------+----|
```

The `csvsql` solution is more verbose but is also more robust as it uses the names of the columns instead of their indexes:


```bash
$ < tips.csv csvsql --query "SELECT * FROM stdin "\
> "WHERE bill > 40 AND day LIKE '%S%'" | csvlook -I
|--------+------+--------+--------+-----+--------+-------|
|  bill  | tip  | sex    | smoker | day | time   | size  |
|--------+------+--------+--------+-----+--------+-------|
|  48.27 | 6.73 | Male   | 0      | Sat | Dinner | 4     |
|  44.3  | 2.5  | Female | 1      | Sat | Dinner | 3     |
|  48.17 | 5.0  | Male   | 0      | Sun | Dinner | 6     |
|  50.81 | 10.0 | Male   | 1      | Sat | Dinner | 3     |
|  45.35 | 3.5  | Male   | 1      | Sun | Dinner | 3     |
|  40.55 | 3.0  | Male   | 1      | Sun | Dinner | 2     |
|  48.33 | 9.0  | Male   | 0      | Sat | Dinner | 4     |
|--------+------+--------+--------+-----+--------+-------|
```

It should be noted that the flexibility of the *WHERE* clause in an SQL query cannot be easily matched with other command-line tools, as SQL can operate on dates and sets, and form complex combinations of clauses.

### Merging Columns 

Merging columns is useful for when the values of interest are spread over multiple columns. This may happen with dates (where year, month, and day could be separate columns) or names (where the first name and last name are separate columns). Let’s consider the second situation.

The input CSV is a list of contemporary composers. Imagine our task is to combine the first name and the last name into a full name. We’ll present four different approaches for this task: `sed`, `awk`, `cols` + `tr`, and `csvsql`. Let’s have a look at the input CSV:


```bash
$ < names.csv csvlook -I
|-----+-----------+------------+-------|
|  id | last_name | first_name | born  |
|-----+-----------+------------+-------|
|  1  | Williams  | John       | 1932  |
|  2  | Elfman    | Danny      | 1953  |
|  3  | Horner    | James      | 1953  |
|  4  | Shore     | Howard     | 1946  |
|  5  | Zimmer    | Hans       | 1957  |
|-----+-----------+------------+-------|
```

The first approach, `sed`, uses two statements. The first is to replace the header and the second is a regular expression with back references applied to the second row onwards:


```bash
$ < names.csv sed -re '1s/.*/id,full_name,born/g;'\
> '2,$s/(.*),(.*),(.*),(.*)/\1,\3 \2,\4/g' | csvlook -I
|-----+---------------+-------|
|  id | full_name     | born  |
|-----+---------------+-------|
|  1  | John Williams | 1932  |
|  2  | Danny Elfman  | 1953  |
|  3  | James Horner  | 1953  |
|  4  | Howard Shore  | 1946  |
|  5  | Hans Zimmer   | 1957  |
|-----+---------------+-------|
```

The `awk` approach looks as follows:


```bash
$ < names.csv awk -F, 'BEGIN{OFS=","; print "id,full_name,born"}'\
> '{if(NR > 1) {print $1,$3" "$2,$4}}' | csvlook -I
|-----+---------------+-------|
|  id | full_name     | born  |
|-----+---------------+-------|
|  1  | John Williams | 1932  |
|  2  | Danny Elfman  | 1953  |
|  3  | James Horner  | 1953  |
|  4  | Howard Shore  | 1946  |
|  5  | Hans Zimmer   | 1957  |
|-----+---------------+-------|
```

The `cols` approach in combination with `tr`:


```bash
$ < names.csv | cols -c first_name,last_name tr \",\" \" \" |
> header -r full_name,id,born | csvcut -c id,full_name,born | csvlook -I
|-----+---------------+-------|
|  id | full_name     | born  |
|-----+---------------+-------|
|  1  | John Williams | 1932  |
|  2  | Danny Elfman  | 1953  |
|  3  | James Horner  | 1953  |
|  4  | Howard Shore  | 1946  |
|  5  | Hans Zimmer   | 1957  |
|-----+---------------+-------|
```

Please note that `csvsql` employ SQLite as the database to execute the query and that `||` stands for concatenation:


```bash
$ < names.csv csvsql --query "SELECT id, first_name || ' ' || last_name "\
> "AS full_name, born FROM stdin" | csvlook -I
|-----+-----------------------+-------|
|  id | full_name             | born  |
|-----+-----------------------+-------|
|  1  | John Williams         | 1932  |
|  2  | Danny Elfman          | 1953  |
|  3  | James Horner          | 1953  |
|  4  | Howard Shore          | 1946  |
|  5  | Hans Zimmer           | 1957  |
|-----+-----------------------+-------|
```

What if *last\_name* would contain a comma? Let’s have a look at the raw input CSV for clarity sake:


```bash
$ cat names-comma.csv
id,last_name,first_name,born
1,Williams,John,1932
2,Elfman,Danny,1953
3,Horner,James,1953
4,Shore,Howard,1946
5,Zimmer,Hans,1957
6,"Beethoven, van",Ludwig,1770
```

Well, it appears that the first three approaches fail; all in different ways. Only `csvsql` is able to combine first\_name and full\_name:


```bash
$ < names-comma.csv sed -re '1s/.*/id,full_name,born/g;'\
> '2,$s/(.*),(.*),(.*),(.*)/\1,\3 \2,\4/g' | tail -n 1
6,"Beethoven,Ludwig  van",1770
```


```bash
$ < names-comma.csv awk -F, 'BEGIN{OFS=","; print "id,full_name,born"}'\
> '{if(NR > 1) {print $1,$3" "$2,$4}}' | tail -n 1
6, van" "Beethoven,Ludwig
```


```bash
$ < names-comma.csv | cols -c first_name,last_name tr \",\" \" \" |
> header -r full_name,id,born | csvcut -c id,full_name,born | tail -n 1
6,"Ludwig ""Beethoven  van""",1770
```


```bash
$ < names-comma.csv csvsql --query "SELECT id, first_name || ' ' || last_name"\
> " AS full_name, born FROM stdin" | tail -n 1
6,"Ludwig Beethoven, van",1770
```


```bash
$ < names-comma.csv Rio -e 'df$full_name <- paste(df$first_name, df$last_name);'\
> 'df[c("id","full_name","born")]' | tail -n 1
6,"Ludwig Beethoven, van",1770
```

Wait a minute! What’s that last command? Is that R? Well, as a matter of fact, it is. It’s R code evaluated through a command-line tool called `Rio` [@Rio]. All that we can say at this moment, is that also this approach succeeds at merging the two columns. We’ll discuss this nifty command-line tool later.

### Combining Multiple CSV Files 

#### Concatenate Vertically 

Vertical concatenation may be necessary in cases where you have, for example, a data set which is generated on a daily basis, or where each data set represents a different, say, market or product. Let’s simulate the latter by splitting up our beloved Iris data set into three CSV files, so that we have something to combine again. We’ll use `fieldsplit` [@fieldsplit], which is part of the `CRUSH` suite of command-line tools:


```bash
$ < iris.csv fieldsplit -d, -k -F species -p . -s .csv
```

Here, the command-line arguments specify: the delimiter (`-d`), that we want to keep the header in each file (`-k`), the column whose values dictate the possible output files (`-F`), the relative output path (`-p`), and the filename suffix (`-s`), respectively. Because the *species* column in the Iris data set contains three different values, we end up with three CSV files, each with 50 data points and a header:


```bash
$ wc -l Iris-*.csv
  51 Iris-setosa.csv
  51 Iris-versicolor.csv
  51 Iris-virginica.csv
 153 total
```

You could just concatenate the files back using `cat` and removing the headers of all but the first file using `header -d` as follows:


```bash
$ cat Iris-setosa.csv <(< Iris-versicolor.csv header -d) \
> <(< Iris-virginica.csv header -d) | sed -n '1p;49,54p' | csvlook
|---------------+-------------+--------------+-------------+------------------|
|  sepal_length | sepal_width | petal_length | petal_width | species          |
|---------------+-------------+--------------+-------------+------------------|
|  4.6          | 3.2         | 1.4          | 0.2         | Iris-setosa      |
|  5.3          | 3.7         | 1.5          | 0.2         | Iris-setosa      |
|  5.0          | 3.3         | 1.4          | 0.2         | Iris-setosa      |
|  7.0          | 3.2         | 4.7          | 1.4         | Iris-versicolor  |
|  6.4          | 3.2         | 4.5          | 1.5         | Iris-versicolor  |
|  6.9          | 3.1         | 4.9          | 1.5         | Iris-versicolor  |
|---------------+-------------+--------------+-------------+------------------|
```

Note that we’re merely using `sed` to only print the header and the first three body rows that belonged to the second file in order to illustrate success. While this method works, it’s easier (and less prone to errors) to use `csvstack` [@csvstack]:


```bash
$ csvstack Iris-*.csv | sed -n '1p;49,54p' | csvlook
|---------------+-------------+--------------+-------------+------------------|
|  sepal_length | sepal_width | petal_length | petal_width | species          |
|---------------+-------------+--------------+-------------+------------------|
|  4.6          | 3.2         | 1.4          | 0.2         | Iris-setosa      |
|  5.3          | 3.7         | 1.5          | 0.2         | Iris-setosa      |
|  5.0          | 3.3         | 1.4          | 0.2         | Iris-setosa      |
|  7.0          | 3.2         | 4.7          | 1.4         | Iris-versicolor  |
|  6.4          | 3.2         | 4.5          | 1.5         | Iris-versicolor  |
|  6.9          | 3.1         | 4.9          | 1.5         | Iris-versicolor  |
|---------------+-------------+--------------+-------------+------------------|
```

If the species column did not exist, you can create a new column based on the filename using `csvstack`:


```bash
$ csvstack Iris-*.csv -n species --filenames
```

Alternatively, you could specify the group names using `-g`:


```bash
$ csvstack Iris-*.csv -n class -g a,b,c | csvcut -C species |
> sed -n '1p;49,54p' | csvlook
|--------+--------------+-------------+--------------+--------------|
|  class | sepal_length | sepal_width | petal_length | petal_width  |
|--------+--------------+-------------+--------------+--------------|
|  a     | 4.6          | 3.2         | 1.4          | 0.2          |
|  a     | 5.3          | 3.7         | 1.5          | 0.2          |
|  a     | 5.0          | 3.3         | 1.4          | 0.2          |
|  b     | 7.0          | 3.2         | 4.7          | 1.4          |
|  b     | 6.4          | 3.2         | 4.5          | 1.5          |
|  b     | 6.9          | 3.1         | 4.9          | 1.5          |
|--------+--------------+-------------+--------------+--------------|
```

The new column *class* is added at the front. If you’d like to change the order you can use `csvcut` as discussed earlier in this section.

#### Concatenate Horizontally 

Let’s say you have three CSV files that want to put side by side. We use `tee` [@tee] to save the result of `csvcut` in the middle of the pipeline:


```bash
$ < data/tips.csv csvcut -c bill,tip | tee data/bills.csv | head -n 3 | csvlook
|--------+-------|
|  bill  | tip   |
|--------+-------|
|  16.99 | 1.01  |
|  10.34 | 1.66  |
|--------+-------|
$ < data/tips.csv csvcut -c day,time | tee data/datetime.csv |
> head -n 3 | csvlook -I
|------+---------|
|  day | time    |
|------+---------|
|  Sun | Dinner  |
|  Sun | Dinner  |
|------+---------|
$ < data/tips.csv csvcut -c sex,smoker,size | tee data/customers.csv |
> head -n 3 | csvlook
|---------+--------+-------|
|  sex    | smoker | size  |
|---------+--------+-------|
|  Female | No     | 2     |
|  Male   | No     | 3     |
|---------+--------+-------|
```

Assuming that the rows line up, you can simply `paste` [@paste] the files together:


```bash
$ paste -d, data/{bills,customers,datetime}.csv | head -n 3 | csvlook -I
|--------+------+--------+--------+------+-----+---------|
|  bill  | tip  | sex    | smoker | size | day | time    |
|--------+------+--------+--------+------+-----+---------|
|  16.99 | 1.01 | Female | No     | 2    | Sun | Dinner  |
|  10.34 | 1.66 | Male   | No     | 3    | Sun | Dinner  |
|--------+------+--------+--------+------+-----+---------|
```

Here, the command-line argument `-d` instructs `paste` to use a comma as the delimiter.

#### Joining 

Sometimes data cannot simply by combined by vertical or horizontal concatenation. In some cases, especially in relational databases, the data is spread over multiple tables (or files) in order to minimize redundancy. Imagine we wanted to extend the Iris data set with more information about the three types of Iris flowers, namely the USDA identifier. It so happens that we have separate CSV file with these identifiers:


```bash
$ csvlook irismeta.csv
|------------------+----------------------------------------------+----------|
|  species         | wikipedia_url                                | usda_id  |
|------------------+----------------------------------------------+----------|
|  Iris-versicolor | http://en.wikipedia.org/wiki/Iris_versicolor | IRVE2    |
|  Iris-virginica  | http://en.wikipedia.org/wiki/Iris_virginica  | IRVI     |
|  Iris-setosa     |                                              | IRSE     |
|------------------+----------------------------------------------+----------|
```

What this data set and the Iris data set have in common is the species column. We can use `csvjoin` [@csvjoin] to join the two data sets:


```bash
$ csvjoin -c species iris.csv irismeta.csv | csvcut -c sepal_length,\
> sepal_width,species,usda_id | sed -n '1p;49,54p' | csvlook
|---------------+-------------+-----------------+----------|
|  sepal_length | sepal_width | species         | usda_id  |
|---------------+-------------+-----------------+----------|
|  4.6          | 3.2         | Iris-setosa     | IRSE     |
|  5.3          | 3.7         | Iris-setosa     | IRSE     |
|  5.0          | 3.3         | Iris-setosa     | IRSE     |
|  7.0          | 3.2         | Iris-versicolor | IRVE2    |
|  6.4          | 3.2         | Iris-versicolor | IRVE2    |
|  6.9          | 3.1         | Iris-versicolor | IRVE2    |
|---------------+-------------+-----------------+----------|
```

Of course we can also use the SQL approach using `csvsql`, which is, as per usual, a bit longer (but potentially much more flexible):


```bash
$ csvsql --query 'SELECT i.sepal_length, i.sepal_width, i.species, m.usda_id '\
> 'FROM iris i JOIN irismeta m ON (i.species = m.species)' \
> iris.csv irismeta.csv | sed -n '1p;49,54p' | csvlook
|---------------+-------------+-----------------+----------|
|  sepal_length | sepal_width | species         | usda_id  |
|---------------+-------------+-----------------+----------|
|  4.6          | 3.2         | Iris-setosa     | IRSE     |
|  5.3          | 3.7         | Iris-setosa     | IRSE     |
|  5.0          | 3.3         | Iris-setosa     | IRSE     |
|  7.0          | 3.2         | Iris-versicolor | IRVE2    |
|  6.4          | 3.2         | Iris-versicolor | IRVE2    |
|  6.9          | 3.1         | Iris-versicolor | IRVE2    |
|---------------+-------------+-----------------+----------|
```

## Further Reading 

* Molinaro, Anthony. 2005. <em>SQL Cookbook</em>. O’Reilly Media.
* Goyvaerts, Jan, and Steven Levithan. 2012. <em>Regular Expressions Cookbook</em>. 2nd Ed. O’Reilly Media.
* Dougherty, Dale, and Arnold Robbins. 1997. <em>Sed &amp; Awk</em>. 2nd Ed. O’Reilly Media.
 




<!--chapter:end:05.Rmd-->

# Managing Your Data Workflow {#chapter-6-managing-your-data-workflow}

We hope that by now, you have come to appreciate that the command line is a very convenient environment for exploratory data analysis. You may have noticed that, as a consequence of working with the command line, we:

- Invoke many different commands.
- Create custom command-line tools.
- Obtain and generate many (intermediate) files.

As this process is of an exploratory nature, our workflow tends to be rather chaotic, which makes it difficult to keep track of what we’ve done. It is very important that our steps can be reproduced, whether that is by ourselves or by others. When we, for example, continue with a project from a few weeks earlier, chances are that we have forgotten which commands we have ran, on which files, in which order, and with which parameters. Imagine the difficulty passing on your analysis to a collaborator.

You may recover some lost commands by digging into your Bash history, but this is, of course, not a good approach. A better approach would be to save your commands to a shell script *run.sh*. This allows you and your collaborators to at least reproduce the analysis. A shell script is, however, a sub-optimal approach because:

- It is difficult to read and to maintain.
- Dependencies between steps are unclear.
- Every step gets executed every time, which is inefficient and sometimes undesirable.

This is where Drake comes in handy [@drake]. Drake is command-line tool created by Factual that allows you to:

- Formalize your data workflow steps in terms of input and output dependencies.
- Run specific steps of your workflow from the command line.
- Use inline code.
- Store and retrieve data from external sources.

## Overview 

Managing your data workflow with Drake is the main topic of this chapter. As such, you’ll learn about:

- Defining your workflow with a so-called Drakefile.
- Thinking about your workflow in terms of input and output dependencies.
- Build specific targets.

## Introducing Drake 

Drake organizes command execution around data and its dependencies. Your data processing steps are formalized in a separate text file (a workflow). Each step usually has one or more inputs and outputs. Drake automatically resolves their dependencies and determines which commands need to be run and in which order.

This means that when you have, say, an SQL query that takes ten minutes, it only has to be executed when the result is missing or when the query has changed afterwards. Also, if want to (re-)run a specific step, Drake only considers to (re-)run the steps on which it depends. This can save you a lot of time.

The benefit of having a formalized workflow allows you to pick up easily your project after a few weeks and to collaborate with others. We strongly advise you to do this, even when you think this will be a one-off project, because you’ll never know when to run certain steps again, or when you want to reuse certain steps in another project.

## Installing Drake 

Drake has quite a few dependencies, which makes its installation process rather involved. For the following instructions we assume that you are on Ubuntu.

\BeginKnitrBlock{rmdtip}

If you’re using the Data Science Toolbox, then you already have Drake installed, and you may safely skip this section.
\EndKnitrBlock{rmdtip}

Drake is written in the programming language Clojure which means that it runs on the Java Virtual Machine (JVM). There are pre-built jars available but because Drake is in active development, we will build it from source. For this, you will need to install Leiningen.


```bash
$ sudo apt-get install openjdk-6-jdk
$ sudo apt-get install leiningen
```

Then, clone the Drake repository from Factual:


```bash
$ git clone https://github.com/Factual/drake.git
```

And build the uberjar using Leiningen:


```bash
$ cd drake
$ lein uberjar
```

This creates *drake.jar*. Copy this file to a directory which is on your *\$PATH*, for example, *\~/bin*:


```bash
$ mv drake.jar ~/bin/
```

At this point you should already be able to run Drake:


```bash
$ cd ~/bin/
$ java -jar drake.jar
```

This is not really convenient for two reasons: (1) the Java Virtual Machine (JVM) takes a long time to start and (2) you can only run it from that directory. We advise you to install Drip, which is a launcher for the JVM that provides much faster startup times than the `java` command. First, clone the Drip repository from Flatland:


```bash
$ git clone https://github.com/flatland/drip.git
$ cd drip
$ make prefix=~/bin install
```

Then, create a Bash script that allows you to run Drake from everywhere:


```bash
$ cd ~/bin
$ cat << 'EOF' > drake
> #!/bin/bash
> drip -cp $(dirname $0)/drake.jar drake.core "$@"
> EOF
$ chmod +x drake
```

To verify that you have correctly installed both Drake and Drip, you can run the following command, preferably from a different directory:


```bash
$ drake --version
Drake Version 0.1.6
```

\BeginKnitrBlock{rmdnote}

Drip speeds up Java because it reserves an instance of the JVM, after it has been run once. Because of this, you will only notice the speed up from the second time onwards.
\EndKnitrBlock{rmdnote}

## Obtain Top E-books from Project Gutenberg 

For the remainder of this chapter, we’ll use the following task as a running example. Our goal is to turn the command that we use to solve this task into a Drake workflow. We start out simple, and work our way towards an advanced workflow in order to explain to you the various concepts and syntax of Drake.

Project Gutenberg is an ambitious project that, since 1971, has archived and digitized over 42,000 books and offers these as free e-books. On its website you can find the top hundred most downloaded books. Let’s assume that we are interested in the top five downloads of Project Gutenberg. Because this list is available in HTML it is straightforward to obtain the top five downloads:


```bash
$ curl -s 'http://www.gutenberg.org/browse/scores/top' |  
> grep -E '^<li>' |                                       
> head -n 5 |                                             
> sed -E "s/.*ebooks\/([0-9]+).*/\\1/" > data/top-5       
```

This command:

- Downloads the HTML.
- Extracts the list items.
- Keeps only the top five items.
- Saves e-book IDs to *data/top-5*.

The output of the command is:


```bash
$ cat data/top-5
1342
76
11
1661
1952
```

If you want to be able to reproduce this, that is, once again at a later time, the easiest thing you can do is put this command in a script as we’ve seen in [Chapter 4](#chapter-4-creating-reusable-command-line-tools). If you execute this script again, the HTML will be downloaded again as well. There are three common reasons why you might want to be able to control whether certain steps are run. First, because this step may take a very long time. Second, because you want to continue with the same data. Third, the data may come from an API which has certain rate limits. It would be a good idea to let one step save the data to a file and then let subsequent steps operate on that file so that you don’t have to make any redundant computations or API calls. Now, the first reason is not really a problem in our example because the HTML can be downloaded fast enough. However, in some cases the data may come from other sources and may comprise of gigabytes of data.

## Every Workflow Starts with a Single Step 

In this section we’ll convert the above command into a Drake workflow. A workflow is just a text file. You’d usually name this file *Drakefile* because Drake uses that file if no other file is specified at the command line. A workflow with just a single step would look like Example \@ref(exm:drakefile).

\BeginKnitrBlock{example}\iffalse{-91-65-32-119-111-114-107-102-108-111-119-32-119-105-116-104-32-106-117-115-116-32-97-32-115-105-110-103-108-101-32-115-116-105-112-93-}\fi{}
<span class="example" id="exm:drakefile"><strong>(\#exm:drakefile)  \iffalse (A workflow with just a single stip) \fi{} </strong></span>
\EndKnitrBlock{example}
```
top-5 <-                                                    
    curl -s 'http://www.gutenberg.org/browse/scores/top' |  
    grep -E '^<li>' |                                       
    head -n 5 |                                             
    sed -E "s/.*ebooks\/([0-9]+).*/\\1/" > top-5            
```

Let’s go through this file. The first line, which contains the arrow pointing to the left, is our step definition. The left side of this arrow, which says *top-5*, is the name or output of this step. Any inputs to this step would appear on the right side of this arrow, but since this step has no input, it’s empty. Defining inputs and outputs is what allows Drake to recognize the dependencies between steps, and to figure out whether and when which steps need to be executed in order to fulfill a certain output. This output is also known as a target. As you can see, the body of this step is literally our command from before but then indented.

- The arrow (*←*) denotes the name of the step and its dependencies. More on this later.
- The body is indented.
- Select only list items.
- Get the first five items.
- Extract the id, and save to file *top-5*. Note that *top-5* was already specified in the step definition and that *5* has now been used three times. We are going to address that later.

This workflow is as simple as it gets. It doesn’t offer any advantages over having our command in a Bash script. But don’t worry, we promise you that it will get more exciting. For now, let’s run Drake and see what it does with our first workflow:


```bash
$ drake
The following steps will be run, in order:
  1: top-5 <-  [missing output]
Confirm? [y/n] y
Running 1 steps with concurrence of 1...

--- 0. Running (missing output): top-5 <-
--- 0: top-5 <-  -> done in 0.35s
Done (1 steps run).
```

If we do not specify any specific workflow file, then Drake will use *./Drakefile*. Drake first determines which steps need to be run. In our case, the one and only step will be run because it’s missing the output. This means that there’s no file named *data/top-5*. Drake asks for confirmation before it will execute these steps. We press `y`, and very soon thereafter we see that Drake is done. Drake did not complain about any errors in our steps. Let’s verify that we have the top five books by looking at the output file *data/top-5*:


```bash
$ cat data/top-5
1342
76
11
1661
1952
```

Now we do have the output file. Let’s run Drake again:


```bash
$ drake
The following steps will be run, in order:
  1: top-5 <-  [no-input step]
Confirm? [y/n] n
Aborted.
```

As you can see, Drake wants to execute the step again! However, now mentions a different reason, namely, that there is no input step *\[no-input-step\]*. Its default behavior is to check whether the input has changed by looking at the timestamp of the input. However, since we didn’t specify any input, Drake doesn’t know whether or not this step should be run again. We can disable this default behavior to check timestamps as follows:

```
top-5 <- [-timecheck]
    curl -s 'http://www.gutenberg.org/browse/scores/top' |
    grep -E '^<li>' |
    head -n 5 |
    sed -E "s/.*ebooks\/([0-9]+)\">([^<]+)<.*/\\1,\\2/" > top-5
```

The square brackets around *\[-timecheck\]* indicate that this is an option to the step. The minus (*-*) means that we wish to disable checking timestamps. Now, this step is only run when the output is missing.

We’re going to use different filenames so that we keep old versions. We can specify a different workflow name (other than *Drakefile*) with the `-w` option. Let’s run Drake once more:


```bash
$ mv Drakefile 01.drake
$ drake -w 01.drake
Nothing to do.
```

Our very first workflow is already saving us time because Drake detects that the step was not required to be executed again. However, we can do much better than this. This workflow has three shortcomings that we’re going to address in the next section.

## Well, That Depends 

Our workflow contains just a single step, which means that, just like having a simple Bash script, everything will be executed all the time. So the first thing we are going to do is to split up this single step into two steps, where the first step downloads the HTML, and the second step processes this HTML. The second step obviously depends on the first step. We can define this dependency in our workflow.

You may have noticed that the number 5 is specified three times. If you ever wanted to get the top, say, top 10 e-books from Project Gutenberg, we would have to change our workflow in three places. This is inefficient and needs to be addressed. Luckily, Drake supports variables.

It may not be immediately obvious from our workflow, but our data resides in the same location as the script. It is better to have the data live in a separate location and have it separated from any code that generates this data. Not only does it keep our project cleaner, it also allows us to delete the generated data files easier, and we can easily specify that we do not like the data files to be included in any version control system such as `git` [@git]. Let’s have a look:

```
NUM:=5                                                              
BASE=data/                                                          

top.html <- [-timecheck]
    curl -s 'http://www.gutenberg.org/browse/scores/top' > $OUTPUT  

top-$[NUM] <- top.html                                              
    < $INPUT grep -E '^<li>' |
    head -n $[NUM] |
    sed -E "s/.*ebooks\/([0-9]+)\">([^<]+)<.*/\\1,\\2/" > $OUTPUT
```

- You can specify variables in Drake, preferably at the beginning of the file, by specifying the variable name, then an equal sign, and then the value. The name of the variable doesn’t have to be in all capitals, but it does make them stand out more. As you can see, we have used for the variable *NUM* the *:=* instead of *=*. This means that if the variable *NUM* is already set, it will not be overridden. This allows us to specify the value of *NUM* from the command line before we run Drake.
- The *BASE* variable is a special variable. Drake will treat every file specified in the workflow as if it were in this base directory.
- We now have two steps. The first step has the same input as before, but now the output is a different file, namely, *top.html*. This output is defined again as the input of step two. This is how Drake knows that the second step depends on the first step.
- We have used two more special variables: *INPUT* and *OUTPUT*. Values of these two special variables are set to what we have defined as the input and output of that step, respectively. This way, we don’t have to specify the input and output of a certain step twice. Furthermore, it allows us to easily reuse certain steps in any future workflows.

Let’s execute this new workflow using Drake:


```bash
$ drake -w 02.drake
The following steps will be run, in order:
  1: ../../data/top.html <-  [missing output]
  2: ../../data/top-5 <- ../../data/top.html [projected timestamped]
Confirm? [y/n] y
Running 2 steps with concurrence of 1...

--- 0. Running (missing output): ../../data/top.html <-
--- 0: ../../data/top.html <-  -> done in 0.89s
--- 1. Running (missing output): ../../data/top-5 <- ../../data/top.html
--- 1: ../../data/top-5 <- ../../data/top.html -> done in 0.02s
Done (2 steps run).
```

Now, let’s assume that we want instead of the top 5 e-books, the top 10 e-books. We can set the *NUM* variable from the command line and run Drake again:


```bash
$ NUM=10 drake -w 02.drake
The following steps will be run, in order:
  1: ../../data/top-10 <- ../../data/top.html [missing output]
Confirm? [y/n] y
Running 1 steps with concurrence of 1...

--- 1. Running (missing output): ../../data/top-10 <- ../../data/top.html
--- 1: ../../data/top-10 <- ../../data/top.html -> done in 0.02s
Done (1 steps run).
```

As you can see, Drake now only needs to execute the second step, because the output of the first step has already been satisfied. Again, downloading an HTML file is not such a big deal, but can you imagine the implications if you were dealing with 10 GB worth of data?

## Rebuilding Certain Targets 

The list of the top 100 e-books on project Gutenberg changes daily. We’ve seen that if we run the Drake workflow again then the HTML containing this list is not being downloaded again. Luckily, Drake allows us to run certain steps again, so that we can update this HTML file:


```bash
$ drake -w 02.drake '=top.html'
```

There is a more convenient way than using the output filename to specify which step you want to execute again. We can add so-called *tags* to both the input and output of steps. A tag starts with a "%". It is a good idea to choose a short and descriptive tag name so that you can easily specify this at the command line. Let’s add the tag *%html* to the first step and *%filter* to the second step:

```
NUM:=5
BASE=data/

top.html, %html <- [-timecheck]
    curl -s 'http://www.gutenberg.org/browse/scores/top' > $OUTPUT

top-$[NUM], %filter <- top.html
    < $INPUT grep -E '^<li>' |
    head -n $[NUM] |
    sed -E "s/.*ebooks\/([0-9]+)\">([^<]+)<.*/\\1,\\2/" > $OUTPUT
```

We can now rebuild the first step by specifying the *%html* tag:


```bash
$ drake -w 03.drake '=%html'
```

## Discussion 

One of the beauties of the command line is that allows you to play with your data. You can easily execute different commands and process different data files. It is a very interactive and iterative process. After a while, it is easy to forget which steps you have taken to get the desired result. It is therefore very important to document your steps every once in a while. This way, if you or one of your colleagues picks up your project after some time, the same result can be produced again by executing the same steps.

We have shown you that just putting every command in one bash script is suboptimal. We have proposed to use Drake as a command-line tool to manage your data workflow. By using a running example, we have shown you how to define steps and the dependencies between them. We’ve also discussed how to use variables and tags.

There’s nothing more fun than just playing with your data and forget everything else. But you have to trust us when we say that it’s worthwhile to keep a record of what you have done by means of a Drake workflow. Not only will it make your life easier, but you will also start thinking about your data workflow in terms of steps. Just as with your command-line toolbox, which you expand over time. It makes you more efficient over time, the same holds for Drake workflows. The more steps you have defined, The easier it gets to keep doing it, because very often you can reuse certain steps. We hope that you will get used to Drake, and that it will make your life easier.

We’ve only been able to scratch the surface with Drake. Some of its more advanced features are:

- Asynchronous execution of steps.
- Support for inline Python and R code.
- Upload and download data from HDFS S3.

## Further Reading 

* Factual. 2014. “Drake.” <a href="https://github.com/Factual/drake" class="uri">https://github.com/Factual/drake</a>.



<!--chapter:end:06.Rmd-->

# Exploring Data {#chapter-7-exploring-data}

Now that we have obtained and scrubbed our data, we can continue with the third step of the OSEMN model, which is to explore it. After all that hard work, (unless you already had clean data lying around!), it is time for some fun.

Exploring is the step where you familiarize yourself with the data. Being familiar with the data is essential when you want to extract any value from it. For example, knowing what kind of features the data has, means you know which ones are worth further exploring and which ones you can use to answer any questions that you have.

Exploring your data can be done from three perspectives. The first perspective is to inspect the data and its properties. Here, we want to know, for example, what the raw data looks like, how many data points the data set has, and what kind of features the data set has.

The second perspective from which we can explore out data is to compute descriptive statistics. This perspective is useful for learning more about the individual features. One advantage of this perspective is that the output is often brief and textual and can therefore be printed on the command line.

The third perspective is to create visualizations of the data. From this perspective we can gain insight into how multiple features interact. We’ll discuss a way of creating visualizations that can be printed on the command line. However, visualizations are best suited to be displayed on a graphical user interfaces. An advantage of visualizations over descriptive statistics is that they are more flexible and that they can convey much more information.

## Overview 

In this chapter, you’ll learn how to:

- Inspect the data and its properties.
- Compute descriptive statistics.
- Create data visualizations inside and outside the command line.

## Inspecting Data and its Properties 

In this section we’ll demonstrate how to inspect your data set and its properties. Because the upcoming visualization and modeling techniques expect the data to be in tabular format, we’ll assume that the data is in CSV format. You can use the techniques described in [Chapter 5](#chapter-5-scrubbing-data) to convert your data to CSV if necessary.

For simplicity sake, we’ll also assume that your data has a header. In the first subsection we are going to determine whether that is the case. Once we know we have a header, we can continue answering the following questions:

- How many data points and features does the data set have?
- What does the raw data look like?
- What kind of features does the data set have?
- Can some of these features be treated as categorical or as factors?

### Header Or Not, Here I Come 

You can check whether your file has a header by printing the first few lines:

    $ #? [echo]
    $ head file.csv | csvlook

It is then up to you to decide whether the first line is indeed a header or already the first data point. When the data set contains no header or when its header contains newlines, you’re best off going back to [Chapter 5](#chapter-5-scrubbing-data) and correct that.

### Inspect All The Data 

If you want to inspect the raw data, then it’s best not to use the `cat` command-line tool, since `cat` prints all the data to the screen in one go. In order to inspect the raw data at your own pace, we recommend to use `less` [@less] with the `-S` command-line argument:

    $ #? [echo]
    $ less -S file.csv

The `-S` command-line argument ensures that long lines are not being wrapped when they don’t fit in the terminal. Instead, `less` allows you to scroll horizontally to see the rest of the lines. The advantage of `less` is that it does not load the entire file into memory, which is good for viewing large files. Once you’re in `less`, you can scroll down a full screen by pressing `<Space>`. Scrolling horizontally is done by pressing `<Left>` and `<Right>`. Press `g` and `G` to go to start and the end of the file, respectively. Quiting `less` is done by pressing `q`. Read the man page for more key bindings.

If you want the data set to be nicely formatted, you can add in `csvlook`:

    $ #? [echo]
    $ < file.csv csvlook | less -S

Unfortunately, `csvlook` needs to read the entire file into memory in order to determine the width of the columns. So, when you want to inspect a very large file, then either you may want to get a subset (using `sample`, for example) or you may need to be patient.

### Feature Names and Data Types 

In order to gain insight into the data set, it is useful to print the feature names and study them. After all, the feature names may indicate the meaning of the feature. You can use the following `sed` expression for this:

    $ < data/iris.csv sed -e 's/,/\n/g;q'

Note that this basic command assumes that the file is delimited by commas. Just as reminder: if you intend to use this command often, you could define a function in your *.bashrc* file called, say, *names*:

\BeginKnitrBlock{example}\iffalse{-91-93-}\fi{}
<span class="example" id="exm:unnamed-chunk-1"><strong>(\#exm:unnamed-chunk-1)  \iffalse () \fi{} </strong></span>
\EndKnitrBlock{example}

```bash
names () { sed -e 's/,/\n/g;q'; }
```

Which you can then you use like this:


```bash
$ < data/investments.csv names
company_permalink
company_name
company_category_list
company_market
company_country_code
company_state_code
company_region
company_city
investor_permalink
investor_name
investor_category_list
investor_market
investor_country_code
investor_state_code
investor_region
investor_city
funding_round_permalink
funding_round_type
funding_round_code
funded_at
funded_month
funded_quarter
funded_year
raised_amount_usd
```

We can go a step further than just printing the column names. Besides the names of the columns, it would be very useful to know what type of values each column contains. Examples of data types are a string of characters, a numerical value, or a date. Assume that we have the following toy data set:


```bash
$ < data/datatypes.csv csvlook
|-----+--------+-------+----------+------------------+------------+----------|
|  a  | b      | c     | d        | e                | f          | g        |
|-----+--------+-------+----------+------------------+------------+----------|
|  2  | 0.0    | FALSE | "Yes!"   | 2011-11-11 11:00 | 2012-09-08 | 12:34    |
|  42 | 3.1415 | TRUE  | Oh, good | 2014-09-15       | 12/6/70    | 0:07 PM  |
|  66 |        | False | 2198     |                  |            |          |
|-----+--------+-------+----------+------------------+------------+----------|
```

We’ve already used `csvsql` in [Chapter 5](#chapter-5-scrubbing-data) to execute SQL queries directly on CSV data. When no command-line arguments are passed, it generates the necessary SQL statement that would be needed if we were to insert this data into an actual database. We can use the output also for ourselves to inspect what the inferred column types are:


```bash
csvsql data/datatypes.csv
CREATE TABLE datatypes (
        a INTEGER NOT NULL,
        b FLOAT,
        c BOOLEAN NOT NULL,
        d VARCHAR(8) NOT NULL,
        e DATETIME,
        f DATE,
        g TIME,
        CHECK (c IN (0, 1))
);
```

provides on overview of what the various SQL data types mean. If a column has the *NOT NULL* string printed after the data type, then that column contains no missing values.

+-----------------------+-----------------------+-----------------------+
| Type                  | Python                | SQL                   |
+=======================+=======================+=======================+
| Character string      | unicode               | VARCHAR               |
+-----------------------+-----------------------+-----------------------+
| Boolean               | bool                  | BOOLEAN               |
+-----------------------+-----------------------+-----------------------+
| Integer               | int                   | INTEGER               |
+-----------------------+-----------------------+-----------------------+
| Real number           | float                 | FLOAT                 |
+-----------------------+-----------------------+-----------------------+
| Date                  | datetime.date         | DATE                  |
+-----------------------+-----------------------+-----------------------+
| Time                  | datetime.time         | TIME                  |
+-----------------------+-----------------------+-----------------------+
| Date and time         | datetime.datetime     | DATETIME              |
+-----------------------+-----------------------+-----------------------+

: Python versus SQL data types

### Unique Identifiers, Continuous Variables, and Factors 

Knowing the data type of each feature is not enough. It is also essential to know what each feature represents. Having knowledge about the domain is very useful here, however we may also get some ideas from the data itself.

Both a string and an integer could be a unique identifier or could represent a category. In the latter case, this could be used to assign a color to your visualization. If an integer denotes, say, the ZIP Code, then it doesn’t make sense to compute the average.

To determine whether a feature should be treated as a unique identifier or categorical variable (or factor in R terms), you could count the number of unique values for a specific column:


```bash
$ cat data/iris.csv | csvcut -c species | body "sort | uniq | wc -l"
species
3
```

Or we can use `csvstat` [@csvstat], which is part of `csvkit`, to get the number of unique values for each column:


```bash
$ csvstat data/investments2.csv --unique
  1. company_permalink: 27342
  2. company_name: 27324
  3. company_category_list: 8759
  4. company_market: 443
  5. company_country_code: 150
  6. company_state_code: 147
  7. company_region: 1079
  8. company_city: 3305
  9. investor_permalink: 11176
 10. investor_name: 11135
 11. investor_category_list: 468
 12. investor_market: 134
 13. investor_country_code: 111
 14. investor_state_code: 80
 15. investor_region: 549
 16. investor_city: 1198
 17. funding_round_permalink: 41790
 18. funding_round_type: 13
 19. funding_round_code: 15
 20. funded_at: 3595
 21. funded_month: 295
 22. funded_quarter: 121
 23. funded_year: 34
 24. raised_amount_usd: 6143
```

If the number of unique values is low compared to the number of rows, then that feature may indeed be treated as a categorical one (such as *funding\_round\_type*). If the number is equal to the number of rows, it may be a unique identifier (such as *company\_permalink*).

## Computing Descriptive Statistics 

### csvstat 

The command-line tool `csvstat` gives a lot of information. For each feature (column), it shows:

- The data type in Python terminology (see Table 7-1 for a comparison between Python and SQL data types).
- Whether it has any missing values (nulls).
- The number of unique values.
- Various descriptive statistics (maximum, minimum, sum, mean, standard deviation, and median) for those features for which it is appropriate.

We invoke `csvstat` as follows:


```bash
$ csvstat data/datatypes.csv
  1. a
        <type 'int'>
        Nulls: False
        Values: 2, 66, 42
  2. b
        <type 'float'>
        Nulls: True
        Values: 0.0, 3.1415
  3. c
        <type 'bool'>
        Nulls: False
        Unique values: 2
        5 most frequent values:
                False:  2
                True:   1
  4. d
        <type 'unicode'>
        Nulls: False
        Values: 2198, "Yes!", Oh, good
  5. e
        <type 'datetime.datetime'>
        Nulls: True
        Values: 2011-11-11 11:00:00, 2014-09-15 00:00:00
  6. f
        <type 'datetime.date'>
        Nulls: True
        Values: 2012-09-08, 1970-12-06
  7. g
        <type 'datetime.time'>
        Nulls: True
        Values: 12:34:00, 12:07:00

Row count: 3
```

This gives a very verbose output. For a more concise output specify one of the statistics arguments:

- `--max` (maximum)
- `--min` (minimum)
- `--sum` (sum)
- `--mean` (mean)
- `--median` (median)
- `--stdev` (standard deviation)

- `--nulls` (whether column contains nulls)
- `--unique` (unique values)
- `--freq` (frequent values)
- `--len` (max value length)

For example:


```bash
$ csvstat data/datatypes.csv --null
  1. a: False
  2. b: True
  3. c: False
  4. d: False
  5. e: True
  6. f: True
  7. g: True
```

You can select a subset of features with the `-c` command-line argument. This accepts both integers and column names:


```bash
$ csvstat data/investments2.csv -c 2,13,19,24
  2. company_name
        <type 'unicode'>
        Nulls: True
        Unique values: 27324
        5 most frequent values:
                Aviir:  13
                Galectin Therapeutics:  12
                Rostima:        12
                Facebook:       11
                Lending Club:   11
        Max length: 66
 13. investor_country_code
        <type 'unicode'>
        Nulls: True
        Unique values: 111
        5 most frequent values:
                USA:    20806
                GBR:    2357
                DEU:    946
                CAN:    893
                FRA:    737
        Max length: 15
 19. funding_round_code
        <type 'unicode'>
        Nulls: True
        Unique values: 15
        5 most frequent values:
                a:      7529
                b:      4776
                c:      2452
                d:      1042
                e:      384
        Max length: 10
 24. raised_amount_usd
        <type 'int'>
        Nulls: True
        Min: 0
        Max: 3200000000
        Sum: 359891203117
        Mean: 10370010.1748
        Median: 3250000
        Standard Deviation: 38513119.1802
        Unique values: 6143
        5 most frequent values:
                10000000:       1159
                1000000:        1074
                5000000:        1066
                2000000:        875
                3000000:        820

Row count: 41799
```

Please note that `csvstat`, just like `csvsql`, employs heuristics to determine the data type, and therefore may not always get it right. We encourage you to always do a manual inspection as discussed in the previous subsection. Moreover, the type may be a character string or integer that doesn’t say anything about how it should be used.

As a nice extra, `csvstat` outputs, at the very end, the number of data points (rows). Newlines and commas inside values are handles correctly. To only see the relevant line, we can use `tail`:

    $ csvstat data/iris.csv | tail -n 1

If you only want to see the actual number number of data points, you can use, for example, the following `sed` expression to extract the number:

    $ csvstat data/iris.csv | sed -rne '${s/^([^:]+): ([0-9]+)$/\2/;p}'

### Using R from the Command Line using Rio 

In this section we would like to introduce you to a command-line tool called `Rio`, which is essentially a small, nifty wrapper around the statistical programming environment R. Before we explain what Rio does and why it exists, lets talk a bit about R itself.

R is a very powerful statistical software package to analyze data and create visualizations. It’s an interpreted programming language, has an extensive collection of packages, and offers its own REPL (Read-Eval-Print-Loop), which allows you, similar to the command line, to play with your data. Unfortunately, R is quite separated from the command line. Once you start it, you’re in a separate environment. R doesn’t really play well with the command line because you cannot pipe any data into it and it also doesn’t support any one-liners that you can specify.

For example, imagine that you have a CSV file called *tips.csv*, and you would like compute the tip percentage, and save the result. To accomplish this in R you would first startup R:

    $ #? [echo]
    $ R

And then run the following commands:

```r
> tips <- read.csv('tips.csv', header = T, sep = ',', stringsAsFactors = F)
> tips.percent <- tips$tip / tips$bill * 100
> cat(tips.percent, sep = '\n', file = 'percent.csv')
> q("no")
```

Afterwards, you can continue with the saved file *percent.csv* on the command line. Note that there is only one command that is associated with what we want to accomplish specifically. The other commands are necessary boilerplate. Typing in this boilerplate in order to accomplish something simple is cumbersome and breaks your workflow. Sometimes, you only want to do one or two things at a time to your data. Wouldn’t it be great if we could harness the power of R and be able to use it from the command line?

This is where `Rio` comes in. The name Rio stands for *R input/output*, because it enables you to use R as a filter on the command line. You simply pipe CSV data into `Rio` and you specify the R commands that you want to run on it. Let’s perform the same task as before, but now using `Rio`:

    $ < data/tips.csv Rio -e 'df$tip / df$bill * 100' | head -n 10

`Rio` can execute multiple R command that are separated by semicolons. So, if you wanted to add a column called *percent* to the input data, you could do the following:

    $ < data/tips.csv Rio -e 'df$percent <- df$tip / df$bill * 100; df' | head

These small one-liners are possible because `Rio` takes care of all the boilerplate. Being able to use the command line for this and capture the power of R into a one-liner is fantastic, especially if you want to keep on working on the command line. `Rio` assumes that the input data is in CSV format with a header. (By specifying the `-n` command-line argument `Rio` does not consider the first row to be the header and creates default column names.) Behind the scenes, `Rio` writes the piped data to a temporary CSV file and creates a script that:

- Import required libraries.
- Loads the CSV file as a data frame.
- Generates a `ggplot2` object if needed (more on this in the next section).
- Runs the specified commands.

- Prints the result of the last command to standard output.

So now, if you wanted to do one or two things to your data set with R, you can specify it as a one-liner, and keep on working on the command line. All the knowledge that you already have about R can now be used from the command line. With `Rio`, you can even create sophisticated visualizations, as you will see later in this chapter.

Rio doesn’t have to be used as a filter, meaning the output doesn’t have to be a in CSV format per se. You can compute

    $ < data/iris.csv Rio -e 'mean(df$sepal_length)'
    $ < data/iris.csv Rio -e 'sd(df$sepal_length)'
    $ < data/iris.csv Rio -e 'sum(df$sepal_length)'

If we wanted to compute the five summary statistics, we would do:


```bash
$ < iris.csv Rio -e 'summary(df$sepal_length)'
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max.
  4.300   5.100   5.800   5.843   6.400   7.900
```

You can also compute the skewness (symmetry of the distribution) and kurtosis (peakedness of the distribution), but then you need to have the `moments` package installed:

    $ #? [echo]
    $ < data/iris.csv Rio -e 'skewness(df$sepal_length)'
    $ < data/iris.csv Rio -e 'kurtosis(df$petal_width)'

Correlation between two features:


```bash
$ < tips.csv Rio -e 'cor(df$bill, df$tip)'
0.6757341
```

Or a correlation matrix:


```bash
$ < data/tips.csv csvcut -c bill,tip | Rio -f cor | csvlook
|--------------------+--------------------|
|  bill              | tip                |
|--------------------+--------------------|
|  1                 | 0.675734109211365  |
|  0.675734109211365 | 1                  |
|--------------------+--------------------|
```

Note that with the command-line argument `-f`, we can specify the function to apply to the data frame `df`. In this case, it is the same as `-e cor(df)`.

You can even create a stem plot [@Tukey1977] using `Rio`:

    $ < data/iris.csv Rio -e 'stem(df$sepal_length)'

## Creating Visualizations 

In this section we’re going to discuss how to create visualizations at the command line. We’ll be looking at two different software packages: gnuplot and ggplot. First, we’ll introduce both packages. Then, we’ll demonstrate how to create several different types of visualizations using both of them.

### Introducing Gnuplot and Feedgnuplot 

The first software package to create visualizations that we’re discussing in this chapter is Gnuplot. Gnuplot has been around since 1986. Despite being rather old, its visualization capabilities are quite extensive. As such, it’s impossible to do it justice. There are other good resources available, including *Gnuplot in Action* by @Janert2009.

To demonstrate the flexibility (and its archaic notation), consider Example \@ref(exm:script-gnuplot), which is copied from the Gnuplot website (<http://gnuplot.sourceforge.net/demo/histograms.6.gnu>).

\BeginKnitrBlock{example}\iffalse{-91-67-114-101-97-116-105-110-103-32-97-32-104-105-115-116-111-103-114-97-109-32-117-115-105-110-103-32-71-110-117-112-108-111-116-93-}\fi{}
<span class="example" id="exm:script-gnuplot"><strong>(\#exm:script-gnuplot)  \iffalse (Creating a histogram using Gnuplot) \fi{} </strong></span>
\EndKnitrBlock{example}
```
# set terminal pngcairo  transparent enhanced font "arial,10" fontscale 1.0 size
# set output 'histograms.6.png'
set border 3 front linetype -1 linewidth 1.000
set boxwidth 0.75 absolute
set style fill   solid 1.00 border lt -1
set grid nopolar
set grid noxtics nomxtics ytics nomytics noztics nomztics \
 nox2tics nomx2tics noy2tics nomy2tics nocbtics nomcbtics
set grid layerdefault   linetype 0 linewidth 1.000,  linetype 0 linewidth 1.000
set key outside right top vertical Left reverse noenhanced autotitles columnhead
set style histogram columnstacked title  offset character 0, 0, 0
set datafile missing '-'
set style data histograms
set xtics border in scale 1,0.5 nomirror norotate  offset character 0, 0, 0 auto
set xtics  norangelimit
set xtics   ()
set ytics border in scale 0,0 mirror norotate  offset character 0, 0, 0 autojust
set ztics border in scale 0,0 nomirror norotate  offset character 0, 0, 0 autoju
set cbtics border in scale 0,0 mirror norotate  offset character 0, 0, 0 autojus
set rtics axis in scale 0,0 nomirror norotate  offset character 0, 0, 0 autojust
set title "Immigration from Northern Europe\n(columstacked histogram)"
set xlabel "Country of Origin"
set ylabel "Immigration by decade"
set yrange [ 0.00000 : * ] noreverse nowriteback
i = 23
plot 'immigration.dat' using 6 ti col, '' using 12 ti col,      '' using 13 ti c
```

Please note that this is trimmed to 80 characters wide. The above script generates the following image:

\begin{figure}

{\centering \includegraphics[width=6.94in]{images/histograms.6} 

}

\caption{Immigration Plot by Gnuplot}(\#fig:unnamed-chunk-14)
\end{figure}

Gnuplot is different from most command-line tools we’ve been using for two reasons. First, it uses a script instead of command-line arguments. Second, the output is always written to a file and not printed to standard output.

One great advantage of Gnuplot being around for so long, and the main reason we’ve included it in this book, is that it’s able to produce visualizations **for** the command line. That is, it’s able to print its output to the terminal without the need for a graphical user interface (GUI). Even then, you would need to set up a script.

Luckily, there is a command-line tool called `feedgnuplot` [@feedgnuplot], which can help us with setting up a script for Gnuplot. `feedgnuplot` is entirely configurable through command-line arguments. Plus, it reads from standard input. After we have introduced `ggplot2`, we’re going to create a few visualizations using `feedgnuplot`.

One great feature of `feedgnuplot` that we would like to mention here, is that it allows you to plot streaming data. The following is a snapshot of a continuously updated plot based on random input data:


```bash
$ while true; do echo $RANDOM; done | sample -d 10 | feedgnuplot --stream \
> --terminal 'dumb 80,25' --lines --xlen 10

  30000 ++-----+------------+-------------+-------------+------------+-----++
        |      +            *             +             +            +      |
        |      :            **            :             *******      :      *
  25000 ++.................*.*..........................*.....*............+*
        |      :           *: *           :            *:      *     :     *|
        |      :           *: *           :            *:      *     :     *|
        |      :          * :  *          :           * :       *    :    * |
  20000 ++................*....*......................*.........*.........*++
        |      :          * :   *         :          *  :       *    :    * |
        |      :         *  :   *         :          *  :        *   :   *  |
  15000 ++....**.........*.......*..................*............*.......*.++
        | **** :*        *  :    *        :         *   :         *  :   *  |
        **     :*        *  :     *      ****      *    :         *  :  *   |
  10000 ++.......*......*.........*....**....*.....*..............*.....*..++
        |      :  *     *   :      * **   :   *   *     :          * : *    |
        |      :   *    *   :      **     :    ** *     :          * : *    |
        |      :   *   *    :             :      *      :          * : *    |
   5000 ++..........*..*.........................*..................*.*....++
        |      :     * *    :             :             :           *:*     |
        |      +     **     +             +             +            *      |
      0 ++-----+------*-----+-------------+-------------+------------*-----++
              2350         2352          2354          2356         2358
```

### Introducing ggplot2 

A more modern software package for creating visualizations is ggplot, which is an implementation of the grammar of graphics in R [@Wickham2009].

Thanks to the grammar of graphics and using sensible defaults, `ggplot2` commands tend to be very short and expressive. When used through `Rio`, this is a very convenient way of creating visualizations from the command line.

To demonstrate it’s expressiveness, we’ll recreate the histogram plot generated above by gnuplot, with the help of `Rio`. Because `Rio` expects the data set to be comma-delimited, and because `ggplot2` expects the data in *long* format, we first need to scrub and transform the data a little bit:


```bash
$ < data/immigration.dat sed -re '/^#/d;s/\t/,/g;s/,-,/,0,/g;s/Region/'\
> 'Period/' | tee data/immigration.csv | head | cut -c1-80
Period,Austria,Hungary,Belgium,Czechoslovakia,Denmark,France,Germany,Greece,Irel
1891-1900,234081,181288,18167,0,50231,30770,505152,15979,388416,651893,26758,950
1901-1910,668209,808511,41635,0,65285,73379,341498,167519,339065,2045877,48262,1
1911-1920,453649,442693,33746,3426,41983,61897,143945,184201,146181,1109524,4371
1921-1930,32868,30680,15846,102194,32430,49610,412202,51084,211234,455315,26948,
1931-1940,3563,7861,4817,14393,2559,12623,144058,9119,10973,68028,7150,4740,3960
1941-1950,24860,3469,12189,8347,5393,38809,226578,8973,19789,57661,14860,10100,1
1951-1960,67106,36637,18575,918,10984,51121,477765,47608,43362,185491,52277,2293
1961-1970,20621,5401,9192,3273,9201,45237,190796,85969,32966,214111,30606,15484,
```

The `sed` expression consists of four parts, delimited by semicolons:

1.  Remove lines that start with *\#*.

2.  Convert tabs to commas.

3.  Change dashes (missing values) into zero’s.

4.  Change the feature name *Region* into *Period*.

We then select only the columns that matter using `csvcut` and subsequently convert the data from a wide format to a long one using the `Rio` and the `melt` function which part of the R package `reshape2`:


```bash
$ < data/immigration.csv csvcut -c Period,Denmark,Netherlands,Norway,\
> Sweden | Rio -re 'melt(df, id="Period", variable.name="Country", '\
> 'value.name="Count")' | tee data/immigration-long.csv | head | csvlook
|------------+-------------+--------|
|  Period    | Country     | Count  |
|------------+-------------+--------|
|  1891-1900 | Denmark     | 50231  |
|  1901-1910 | Denmark     | 65285  |
|  1911-1920 | Denmark     | 41983  |
|  1921-1930 | Denmark     | 32430  |
|  1931-1940 | Denmark     | 2559   |
|  1941-1950 | Denmark     | 5393   |
|  1951-1960 | Denmark     | 10984  |
|  1961-1970 | Denmark     | 9201   |
|  1891-1900 | Netherlands | 26758  |
|------------+-------------+--------|
```

Now, we can use `Rio` again, but then with an expression that builds up a `ggplot2` visualization:


```bash
$ < data/immigration-long.csv Rio -ge 'g + geom_bar(aes(Country, Count,'\
> ' fill=Period), stat="identity") + scale_fill_brewer(palette="Set1") '\
> '+ labs(x="Country of origin", y="Immigration by decade", title='\
> '"Immigration from Northern Europe\n(columstacked histogram)")' | display
```

\begin{figure}

{\centering \includegraphics[width=32.81in]{images/rio-immigration} 

}

\caption{Immigration plot by Rio and ggplot2}(\#fig:unnamed-chunk-19)
\end{figure}

The `-g` command-line argument indicates that Rio should load the `ggplot2` package. The output is an image in PNG format. You can either view the PNG image via `display`, which is part of ImageMagick [@display] or you can redirect the output to a PNG file. If you’re on a remote terminal then you probably won’t be able to see any graphics. A workaround for this is to start a webserver from a particular directory:


```bash
$ python -m SimpleHTTPServer 8000
```

Make sure that you have access to the port (8000 in this case). If you save the PNG image to the directory from which the webserver was launched, then you can access the image from your browser at <http://localhost:8000/file.png>.

### Histograms 

Using `Rio`:


```bash
$ < data/tips.csv Rio -ge 'g+geom_histogram(aes(bill))' | display
```

\begin{figure}

{\centering \includegraphics[width=32.81in]{images/rio-histogram} 

}

\caption{Histogram}(\#fig:unnamed-chunk-22)
\end{figure}

Using `feedgnuplot`:


```bash
< data/tips.csv csvcut -c bill | feedgnuplot --terminal 'dumb 80,25' \
--histogram 0 --with boxes --ymin 0 --binwidth 1.5 --unset grid --exit



  25 ++----+------+-----+--***-+-----+------+-----+------+-----+------+----++
     +     +      +     +*** * +     +      +     +      +     +      +     +
     |                   * * *                                              |
     |               *** * * *                                              |
  20 ++              * * * * *                                             ++
     |            **** * * * *                                              |
     |            * ** *** * * ***                                          |
     |            * ** * * * * * *                                          |
  15 ++           * ** * * * * * *                                         ++
     |            * ** * * * * * *                                          |
     |            * ** * * * * * *                                          |
     |            * ** * * * * * * ***                                      |
  10 ++           * ** * * * *** *** *                                     ++
     |            * ** * * * * * * * *                                      |
     |          *** ** * * * * * * * ***** ***                              |
     |          * * ** * * * * * * * * * *** *                              |
   5 ++       *** * ** * * * * * * * * * * * *   ***                       ++
     |        * * * ** * * * * * * * * * * * * *** *                        |
     |        * * * ** * * * * * * * * * * * *** * ********   *** ***       |
     +  ***+*** * * ** *+* * * * * * * * * *+* * *+** * *+* ***+* * * ***   +
   0 ++-***+***********************************************-*****-***-***--++
     0     5      10    15     20    25     30    35     40    45     50    55
```

### Bar Plots 

Using `Rio`:


```bash
$ < data/tips.csv Rio -ge 'g+geom_bar(aes(factor(size)))' | display
```

\begin{figure}

{\centering \includegraphics[width=32.81in]{images/rio-barplot} 

}

\caption{Bar Plot}(\#fig:unnamed-chunk-25)
\end{figure}

Using `feedgnuplot`:


```bash
$ < data/tips.csv | csvcut -c size | header -d | feedgnuplot --terminal \
> 'dumb 80,25' --histogram 0  --with boxes --unset grid --exit



  160 ++--------+----***********----+---------+---------+---------+--------++
      +         +    *    +    *    +         +         +         +         +
  140 ++             *         *                                           ++
      |              *         *                                            |
      |              *         *                                            |
  120 ++             *         *                                           ++
      |              *         *                                            |
  100 ++             *         *                                           ++
      |              *         *                                            |
      |              *         *                                            |
   80 ++             *         *                                           ++
      |              *         *                                            |
   60 ++             *         *                                           ++
      |              *         *                                            |
      |              *         *                                            |
   40 ++             *         *********************                       ++
      |              *         *         *         *                        |
   20 ++             *         *         *         *                       ++
      |              *         *         *         *                        |
      +    ***********    +    *    +    *    +    *********************    +
    0 ++---*************************************************************---++
      0         1         2         3         4         5         6         7
```

### Density Plots 

Using `Rio`:


```bash
$ < data/tips.csv Rio -ge 'g+geom_density(aes(tip / bill * 100, fill=sex), '\
> 'alpha=0.3) + xlab("percent")' | display
```

\begin{figure}

{\centering \includegraphics[width=32.81in]{images/rio-densityplot} 

}

\caption{Density Plot}(\#fig:unnamed-chunk-28)
\end{figure}

Since `feedgnuplot` cannot generate density plots, it’s best to just generate a histogram.

### Box Plots 

Using `Rio`:


```bash
$ < data/tips.csv Rio -ge 'g+geom_boxplot(aes(time, bill))' | display
```

\begin{figure}

{\centering \includegraphics[width=32.81in]{images/rio-boxplot} 

}

\caption{Box Plot}(\#fig:unnamed-chunk-30)
\end{figure}

Drawing a box plot is unfortunately not possible with `feedgnuplot`.

### Scatter Plots 

Using `Rio`:


```bash
$ < data/tips.csv Rio -ge 'g+geom_point(aes(bill, tip, color=time))' | display
```

\begin{figure}

{\centering \includegraphics[width=32.81in]{images/rio-scatterplot} 

}

\caption{Scatter Plot}(\#fig:unnamed-chunk-32)
\end{figure}

Using `feedgnuplot`:


```bash
< data/tips.csv csvcut -c bill,tip | tr , ' ' | header -d | feedgnuplot \
--terminal 'dumb 80,25' --points --domain --unset grid --exit --style 'pt' '14'



  10 ++----+------+-----+------+-----+------+-----+------+-----+------+A---++
     +     +      +     +      +     +      +     +      +     +      +     +
   9 ++                                                            A       ++
     |                                                                      |
   8 ++                                                                    ++
     |                                                  A                   |
     |                                                                      |
   7 ++                                          A                 A       ++
     |                             A     A                                  |
   6 ++                              A    A    A                           ++
     |                             A        A                               |
   5 ++       A                 A A   A A   AA A  AA      A  A     A       ++
     |                                A       A    A     A                  |
   4 ++          A     A  AAAA AAA A  A A  A          A                    ++
     |                A   AAAAA AAA AA            A             A           |
     |              A  AAAAAAA AA A A  AA   A AA                            |
   3 ++           A   AAAAAAAAAAA A A    AA           AA A                 ++
     |              AAAAAAA AA  A A A     A                   A             |
   2 ++        AA AAAAAAAAA A  A  A AA  A A A                              ++
     +     +   AAAAAAAA +A   AA+     + A    +     +      +     +      +     +
   1 ++--A-+A-A---+--AA-+--A---+-----+------+--A--+------+-----+------+----++
     0     5      10    15     20    25     30    35     40    45     50    55
```

### Line Graphs 


```bash
$ < data/immigration-long.csv Rio -ge 'g+geom_line(aes(x=Period, '\
> 'y=Count, group=Country, color=Country)) + theme(axis.text.x = '\
> 'element_text(angle = -45, hjust = 0))' | display
```

\begin{figure}

{\centering \includegraphics[width=32.81in]{images/rio-linegraph} 

}

\caption{Line Graph}(\#fig:unnamed-chunk-35)
\end{figure}


```bash
$ < data/immigration.csv | csvcut -c Period,Denmark,Netherlands,Norway,Sweden |
> header -d | tr , ' ' | feedgnuplot --terminal 'dumb 80,25' --lines \
> --autolegend --domain --legend 0 "Denmark" --legend 1 "Netherlands" \
> --legend 2 "Norway" --legend 3 "Sweden" --xlabel "Period" --unset grid --exit



  250000 ++-----%%%-------+-------+--------+-------+-------+--------+------++
         +  %%%% + %      +       +        +       +       + Denmark+****** +
         |%%        %                                    Netherlands ###### |
         |          %                                         Norway $$$$$$ |
  200000 ++          %                                        Sweden %%%%%%++
         |        $   %                                                     |
         |       $ $   %                                                    |
         |      $   $  %                                                    |
  150000 ++   $$     $  %                                                  ++
         |   $        $  %                                                  |
         |  $          $  %                                                 |
  100000 ++$            $ %                                                ++
         |$              $ %%%%%%%%%%                                       |
         |                $          %                                      |
         |    ***********  $$$$$$$$$$$%                                     |
   50000 +****  #########**           $%%                  #######         ++
         |  ####           ********    $$%              ###       ##        |
         |##                       ******##           ##$$$$$$$$$$$$#       |
         +       +        +       +      **###########$$*************       +
       0 ++------+--------+-------+--------*************---+--------+------++
        1890    1900     1910    1920     1930    1940    1950     1960    1970
                                       Period
```

### Summary 

Both `Rio` with `ggplot2` and `feedgnuplot` with Gnuplot have their advantages. The plots generated by `Rio` are obviously of much higher quality. It offers a consistent syntax that lends itself well for the command line. The only down-side would be that the output is not viewable from the command line. This is where `feedgnuplot` may come in handy. Each plot has roughly the same command-line arguments. As such, it would be straightforward to create a small Bash script that would make generating plots from and for the command line even easier. After all, with the command line having such a low resolution, we don’t need a lot of flexibility.

## Further Reading 

* Wickham, Hadley. 2009. <em>ggplot2: Elegant Graphics for Data Analysis</em>. Springer.
* Janert, Philipp K. 2009. <em>Gnuplot in Action</em>. Manning Publications.
* Tukey, John W. 1977. <em>Exploratory Data Analysis</em>. Pearson.
 

<!--chapter:end:07.Rmd-->

# Parallel Pipelines {#chapter-8-parallel-pipelines}

In the previous chapters, we have been dealing with commands and pipelines that take care of an entire task at once. In practice, however, you may find yourself facing a task which requires the same command or pipeline to run multiple times. For, example, you may need to:

- Scrape hundreds of web pages.
- Make dozens of API calls and transform their output.
- Train a classifier for a range of parameter values.
- Generate scatter plots for every pair of features in your dataset.

In any of the above examples, there is a certain form of repetition involved. With your favorite scripting or programming language, you take care of this with a for loop or a while loop. On the command line, the first thing you might be inclined to do is to press `<Up>` (which brings back the previous command), modify it if necessary, and press `<Enter>` (which runs the command again). This is fine for two or three times, but imagine doing this for, say, dozens of files. Such an approach quickly becomes cumbersome and time-inefficient. The good news is that we can write such loops on the command line as well. This chapter is all about repetition.

Sometimes, repeating a fast command on after the other (in serial) is sufficient. When you have multiple cores (and perhaps even multiple machines) it would be nice if you could make use of those, especially when you’re faced with a data-intensive task. When using multiple cores or machines, the total running time of may be reduced significantly. In this chapter we will introduce a very powerful tool called GNU Parallel that can take care of exactly this. GNU Parallel allows us to apply a command or pipeline with a range of arguments such as numbers, lines, and files. Plus, it allows us to run our commands in parallel.

## Overview 

This intermezzo chapter discusses several approaches to speed up tasks that require commands and pipelines to be run many times. The main goal of this chapter is to demonstrate to you the flexibility and power of a tool called GNU Parallel. Because this tool can be combined with any other tool discussed in this book, it will positively change the way you use the command line for data science. In this chapter, you’ll learn about:

- Running commands in serial to a range of numbers, lines, and files.
- Breaking a large task into several smaller tasks.
- Running pipelines in parallel using GNU Parallel.
- Distributing pipelines on multiple machines.

## Serial Processing 

Before we dive into parallelization, we will look at looping in a serial fashion. It’s worthwhile to know how to do this because this functionality is always available, the syntax closely resembles looping in other programming languages, and it will really make you appreciate the tool GNU Parallel.

From the examples provided in the introduction of this chapter, we can distill three types of items to loop over: (1) numbers, (2) lines, and (3) files. These three types of items will be discussed in the next three subsections, respectively.

### Looping Over Numbers 

Imagine that we need to compute the square of every even integer between 0 and 100. There’s a tool called `bc`, which is basically a calculator on the command line where you can pipe an equation to. The command to compute the square of 4 looks as follows:


```bash
$ echo "4^2" | bc
16
```

For a one-off calculation, this is perfect. However, as mentioned in the introduction, we would be creazy to press `<Up>`, change the number, and press `<Enter>` 51 times! In this case it is better to let Bash do the hard work for us by using a for loop:


```bash
$ for i in {0..100..2}  
> do
> echo "$i^2" | bc      
> done | tail           
6724
7056
7396
7744
8100
8464
8836
9216
9604
10000
```

There are a number of things going on here:

- Bash has a feature called brace expansion, which transforms *{0..100..2}* into a list separated by spaces: *0 2 4 … 98 100*.
- The variable *i* is assigned the value *1* in the first iteration, *2* in the second iteration, and so forth. The value of this variable can be employed in commands by prefixing it with a dollar sign *\$*. The shell will replace *\$i* with its value before `echo` is being executed. Note that there can be more than one command between `do` and `done`.
- We pipe the output of the for loop to `tail` so that we see the last ten values, only.

Although the syntax may appear a bit odd compared to your favorite programming language, it is worth remembering this because it is always available in the bash shell. We will shortly introduce a better and more flexible way of repeating commands.

### Looping Over Lines 

The second type of items we can loop over are lines. These lines can come from either a file or from standard input. This is a very generic approach because the lines can contain anything, including: numbers, dates, and email adresses.

Imagine that we want to send an email to our customers. Let’s generate some fake users using the <https://randomuser.me/> API:


```bash
$ curl -s "https://randomuser.me/api/1.2/?results=5" > data/users.json
$ < data/users.json jq -r '.results[].email' > data/emails.txt
$ cat data/emails.txt
kaylee.anderson64@example.com
arthur.baker92@example.com
chloe.graham66@example.com
wyatt.nelson80@example.com
peter.coleman75@example.com
```

We can loop over the lines from *emails.txt* with a while-loop:


```bash
$ while read line                                       
> do
> echo "Sending invitation to ${line}."                 
> done < data/emails.txt                                
Sending invitation to kaylee.anderson64@example.com.
Sending invitation to arthur.baker92@example.com.
Sending invitation to chloe.graham66@example.com.
Sending invitation to wyatt.nelson80@example.com.
Sending invitation to peter.coleman75@example.com.
```

- In this case we need to use a while loop because Bash does not know beforehand how many lines the input consists of.
- Although the curly braces around the *line* variable are not necessary in this case (since variable names cannot contain periods), it’s still good practice.
- This redirection can also be placed before `while`.

You can also provide input to the while loop interactively by specifying the special file standard input */dev/stdin*. Press `<Ctrl-D>` when you are done.


```bash
$ while read i; do echo "You typed: $i."; done < /dev/stdin
one
You typed: one.
two
You typed: two.
three
You typed: three.
```

This method, however, has the disadvantage that, once you press `<Enter>`, the command(s) between `do` and `done` are run immediately for that line of input.

### Looping Over Files 

In this section we discuss the third type of item that we often need to loop over: files.

To handle special characters, use globbing (i.e., pathname expansion) instead of `ls`:


```bash
$ for filename in *.csv
> do
> echo "Processing ${filename}."
> done
Processing countries.csv.
```

Just as with brace expansion with numbers, the *\*.csv* is first expanded into a list before it is being processed by the for loop.

A more elaborate alternative to finding files is `find` [@find], which:

- Allows for elaborate searching on properties such as size, access time, and permissions.
- Handles dashes.
- Handles special characters such as spaces and newlines.


```bash
$ find data -name '*.csv' -exec echo "Processing {}" \;
Processing data/countries.csv
Processing data/movies.csv
Processing data/top250.csv
```

Here’s the same but then using `parallel`:


```bash
$ find data -name '*.csv' -print0 | parallel -0 echo "Processing {}"
Processing data/countries.csv
Processing data/movies.csv
Processing data/top250.csv
```

The `-print0` option allows file names that contain newlines or other types of white space to be correctly interpreted by programs that process the find output. If you are absolutely certain that the filenames contain no special characters such as spaces and newlines, then you can omit `-print0` and `-0` options.

\BeginKnitrBlock{rmdtip}

If the list to process becomes too complex, you can always store the result into a temporary file and then use the method to loop over lines from a file.
\EndKnitrBlock{rmdtip}

## Parallel Processing 

Assume that we have a very long running command, such as the one shown in Example \@ref(exm:slow-sh).

\BeginKnitrBlock{example}\iffalse{-91-126-47-98-111-111-107-47-99-104-48-56-47-115-108-111-119-46-115-104-93-}\fi{}
<span class="example" id="exm:slow-sh"><strong>(\#exm:slow-sh)  \iffalse (~/book/ch08/slow.sh) \fi{} </strong></span>
\EndKnitrBlock{example}

```bash
#!/bin/bash
echo "Starting job $1"
duration=$((1+RANDOM%5))                
sleep $duration
echo "Job $1 took ${duration} seconds"
```

- *\$RANDOM* is an internal Bash function that returns a pseudorandom integer between 0 and 32767. Taking the remainder of the division of that number by 5 and adding 1 ensures that the number is between 1 and 5.

This process does not take up all the resources we have available. And it so happens that we need to run this command a lot of times. For example, we need to download a whole sequence of files.

A naive way to parallelize is to run the commands in the background:


```bash
$ cd ~/book/ch08
$ for i in {1..4}; do
> (slow.sh $i; echo Processed $i) &  
> done
[1] 3334
[2] 3335
[3] 3336
[4] 3338
$ Starting job 2
Starting job 1
Starting job 3
Starting job 4
Job 4 took 1 seconds
Processed 4
Job 3 took 4 seconds
Job 2 took 4 seconds
Processed 3
Processed 2
Job 1 took 4 seconds
Processed 1
```

- Parentheses create a subshell. The ampersand ensures that it will be executed in the background.

The problem with subshells is that they are executed all at once. There is no mechanism to control the maximum number of processes. You are not advised to use this.


```bash
$ while read i; do
> (slow.sh "$i"; ) &
> done < data/movies.txt
[1] 3404
[2] 3405
[3] 3406
Starting job Star Wars
Starting job Matrix
Starting job Home Alone
[4] 3407
[5] 3410
$ Starting job Back to the Future
Starting job Indiana Jones
Job Home Alone took 2 seconds
Job Matrix took 2 seconds
Job Star Wars took 2 seconds
Job Back to the Future took 3 seconds
Job Indiana Jones took 4 seconds
```

\BeginKnitrBlock{rmdnote}

Not everything can be parallelized: API calls may be limited to a certain number, or some commands can only have one instance.
\EndKnitrBlock{rmdnote}

\BeginKnitrBlock{rmdimportant}

Quoting is important. If we did not quote *\$i*, then only the first word of each movie would have been passed to the script *slow.sh*.
\EndKnitrBlock{rmdimportant}

There are two problems with this naive approach. First, there’s no way to control how many processes you are running concurrently. Second, logging: which output belongs to which input.


```bash
$ < data/movies parallel -j3 slow.sh "{}"
Starting job Star Wars
Job Star Wars took 3 seconds
Starting job Home Alone
Job Home Alone took 3 seconds
Starting job Matrix
Job Matrix took 4 seconds
Starting job Indiana Jones
Job Indiana Jones took 1 seconds
Starting job Back to the Future
Job Back to the Future took 5 seconds
```

### Introducing GNU Parallel 

GNU Parallel is a command-line tool written by Ole Tange. This tool allows us to parallelize commands and pipelines. The beauty of this tool is that existing tools can be used as they are; they do not need to be modified.

\BeginKnitrBlock{rmdcaution}

You may have noticed that we keep writing GNU Parallel. That’s because there are two tools with the name "parallel". If you make use of the Data Science Toolbox then you already have the correct one installed. Otherwise, please double check that you have installed the correct tool installed by running `parallel --version`.
\EndKnitrBlock{rmdcaution}

Before we go into the details of GNU Parallel, here’s a little teaser to show you how easy it is to parallelize the for loop stated above:


```bash
$ seq 5 | parallel "echo {}^2 | bc"
1
4
9
16
25
```

This is `parallel` in its simplest form: without any arguments. As you can see it basically acts as a for loop. (We’ll explain later what is going on exactly.) With no less than 110 command-line arguments (!), GNU Parallel offers a lot of additional functionality. Don’t worry, by the end of this chapter, you’ll have a solid understanding of the most important ones.

Install GNU Parallel by running the following commands:


```bash
$ wget http://ftp.gnu.org/gnu/parallel/parallel-latest.tar.bz2
$ tar -xvjf parallel-latest.tar.bz2 > extracted-files
$ cd $(head -n 1 extracted-files)
$ ./configure && make && sudo make install
```

You can verify that you have correctly installed GNU Parallel:


```bash
$ parallel --version | head -n 1
GNU parallel 20140622
```

You can safely delete the created files and directories.


```bash
$ cd ..
$ rm -r $(head -n 1 extracted-files)
$ rm parallel-latest.tar.bz2 extracted-files
```

\BeginKnitrBlock{rmdtip}

If you use `parallel` as often as us then you may want to create an alias (for example `p`) by adding *alias p=parallel* to your *.bashrc*. (In this chapter we’ll just use `parallel` for clarity.)
\EndKnitrBlock{rmdtip}

### Specifying Input 

The most important argument to GNU Parallel, is the command that you would like to run for every input. The question is: where should the input item be inserted in the command line? If you do not specify anything, then the input item will be appended to the command. While this is usually what you want, we advise you to be explicit about where the input item should be inserted in the command using one or more placeholders.

\BeginKnitrBlock{rmdnote}

There are many ways to provide input to GNU Parallel. We prefer piping the input (as we do throughout this chapter) because that is generally applicable and allows us to construct a pipeline from left to right. Please consult the man page of parallel to read about other ways to provide input.
\EndKnitrBlock{rmdnote}

In most cases, you probably want to use the entire input item as it is. For this, you only need one placeholder. You specify the placeholder, in other words, where to put the input item, with two curly braces:


```bash
$ seq 5 | parallel echo {}
```

When the input item is a file, there are a couple of special placeholders you can use to modify the file name. For example, with *{./}*, only the base name of the file name will be used.

If the input line has multiple parts separated by a delimiter you can add numbers to the placeholders. For example:


```bash
$ < input.csv | parallel -C, "mv {1} {2}"
```

Here, you can apply the same placeholder modifiers. It is also possible to reuse the same input item. If the input to parallel is a CSV file with a header, then you can use the column names as placeholders:


```bash
$ < input.csv | parallel -C, --header : "invite {name} {email}"
```

Sometimes you just want to run the same command without any changing inputs. This is also possible in parallel. We just have to specify the `-N0` parameter and give as input as many lines as you want to execute:


```bash
$ seq 5 | parallel -N0 "echo The command line rules"
The command line rules
The command line rules
The command line rules
The command line rules
```

\BeginKnitrBlock{rmdtip}

If you ever wonder whether your GNU Parallel command is set up correctly, you can add the `--dryrun` option. Instead of actually executing the command, GNU Parallel will print out all the commands exactly as if they would have been executed.
\EndKnitrBlock{rmdtip}

### Controlling the Number of Concurrent Jobs 

By default, parallel runs one job per CPU core. You can control the number of jobs that will be run in parallel with the `-j` command-line argument, which is short for *jobs*. Simply specifying a number means that many jobs will be run in parallel. If you put a plus sign in front of the number then parallel will run *N* jobs plus the number of CPU cores. If you put a minus sign in front of the number then parallel will run *N-M* jobs. Where *N* is the number of CPU cores. You can also specify a percentage to the `-j` parameter. So, the default is 100% of the number of CPU cores. The optimal number of jobs to run in parallel depends on the actual commands you are running.


```bash
$ seq 5 | parallel -j0 "echo Hi {}"
Hi 1
Hi 2
Hi 3
Hi 4
Hi 5
```


```bash
$ seq 5 | parallel -j200% "echo Hi {}"
Hi 1
Hi 2
Hi 3
Hi 4
Hi 5
```

If you specify `-j1`, then the commands will be run in serial. Even though this doesn’t do the name of the tool of justice, it still has its uses. For example, when you need to access an API which only allows one connection at a time. If you specify `-j0`, then parallel will run as many jobs in parallel as possible. This can be compared to our loop with subshells. This is not advised.

### Logging and Output 

To save the output of each command, you might be tempted to the following:


```bash
$ seq 5 | parallel "echo \"Hi {}\" > data/ch08/hi-{}.txt"
```

This will save the output into individual files. Or, if you want to save everything into one big file you could do the following:


```bash
$ seq 5 | parallel "echo Hi {}" >> data/ch08/one-big-file.txt
```

However, GNU Parallel offers the `--results` option, which stores the output of each job into a separate file, where the filename is based on the input values:


```bash
$ seq 5 | parallel --results data/ch08/outdir "echo Hi {}"
Hi 1
Hi 2
Hi 3
Hi 4
Hi 5
$ find data/ch08/outdir
data/ch08/outdir
data/ch08/outdir/1
data/ch08/outdir/1/1
data/ch08/outdir/1/1/stderr
data/ch08/outdir/1/1/stdout
data/ch08/outdir/1/3
data/ch08/outdir/1/3/stderr
data/ch08/outdir/1/3/stdout
data/ch08/outdir/1/5
data/ch08/outdir/1/5/stderr
data/ch08/outdir/1/5/stdout
data/ch08/outdir/1/2
data/ch08/outdir/1/2/stderr
data/ch08/outdir/1/2/stdout
data/ch08/outdir/1/4
data/ch08/outdir/1/4/stderr
data/ch08/outdir/1/4/stdout
```

When you’re running multiple jobs in parallel, the order in which the jobs are run may not correspond to the order of the input. The output of jobs is therefore also mixed up. To keep the same order, simply specify the `--keep-order` option or `-k` option.

Sometimes it’s useful to record which input generated which output. GNU Parallel allows you to *tag* the output with the `--tag` option:


```bash
$ seq 5 | parallel --tag "echo Hi {}"
1       Hi 1
2       Hi 2
3       Hi 3
4       Hi 4
5       Hi 5
```

### Creating Parallel Tools 

The `bc` tool, which we used in the beginning of the chapter, is not parallel by itself. However, we can parallelize it using `parallel`. The Data Science toolbox contains a tool called `pbc` [@pbc]. Its code is shown in Example \@ref(exm:script-pbc).

\BeginKnitrBlock{example}\iffalse{-91-80-97-114-97-108-108-101-108-32-98-99-93-}\fi{}
<span class="example" id="exm:script-pbc"><strong>(\#exm:script-pbc)  \iffalse (Parallel bc) \fi{} </strong></span>
\EndKnitrBlock{example}

```bash
#!/usr/bin/env bash
parallel -C, -k -j100% "echo '$1' | bc -l"
```

This tool allows us to simplify the code used in the beginning of the chapter too:


```bash
$ seq 100 | pbc '{1}^2' | tail
8281
8464
8649
8836
9025
9216
9409
9604
9801
10000
```

## Distributed Processing 

Sometimes you need more power than your local machine, even with all its cores, can offer. Luckily, GNU Parallel can also leverage the power of remote machines, which really allows us to speed up our pipeline.

What’s great is that GNU Parallel does not have to be installed on the remote machine. All that’s required is that you can connect to the remote machine via SSH, which is also what GNU Parallel uses to distribute our pipeline. (Having GNU Parallel installed is helpful because it can then determine how many cores to employ on each remote machine; more on this later.)

First, we’re going to obtain a list of running AWS EC2 instances. Don’t worry if you don’t have any remote machines, you can replace any occurrence of `--slf hostnames`, which tells GNU Parallel which remote machines to use, with `--sshlogin :`. This way, you can still follow along with the examples in this section.

Once we know which remote machines to take over, we’re going to consider three flavors of distributed processing:

- Simply running ordinary commands on remote machines.
- Distributing local data directly among remote machines.

    -   Sending files to remote machines, process them, and retrieve the results.

### Get List of Running AWS EC2 Instances 

In this section we’re creating a file named *hostnames* that will contain one hostname of a remote machine per line. We’re using Amazon Web Services as an example. If you’re using a different cloud computing service, or have your own servers, please make sure that you create a *hostnames* file yourself.

We can obtain a list of running AWS EC2 instances from the commanding using `aws`, the command-line interface to the AWS API [@aws]. If you’re not using the Data Science Toolbox, install `awscli` using `pip` [@pip] as follows:


```bash
$ pip install awscli
```

With `aws`, you can virtually do everything you can do with the online AWS Management Console. We use this command to obtain a list of running EC2 instances from AWS, but it can do a lot more.

We assume that you know how to launch instances, either through the online Management Console or through the `aws` command-line tool.

The command `aws ec2 describe-instances` returns a lot of information about all your EC2 instances in JSON format (see <http://docs.aws.amazon.com/cli/latest/reference/ec2/describe-instances.html>). We extract the relevant fields using `jq`:


```bash
$ aws ec2 describe-instances | jq '.Reservations[].Instances[] | '\
> '{public_dns: .PublicDnsName, state: .State.Name}'
{
  "state": "running",
  "public_dns": "ec2-54-88-122-140.compute-1.amazonaws.com"
}
{
  "state": "stopped",
  "public_dns": null
}
```

The possible states of an EC2 instance are: *pending*, *running*, *shutting-down*, *terminated*, *stopping*, and *stopped*. Since we can only distribute our pipeline to running instances, we filter out the non-running instances:


```bash
$ aws ec2 describe-instances | jq -r '.Reservations[].Instances[] | '\
> 'select(.State.Name=="running") | .PublicDnsName' > hostnames
$ cat hostnames
ec2-54-88-122-140.compute-1.amazonaws.com
ec2-54-88-89-208.compute-1.amazonaws.com
```

(If we would leave out `-r`, which stands for *raw*, the hostnames would have been surrounded by double quotes.) We save the output to *hostnames*, so that we can pass this to `parallel` later.

As mentioned, `parallel` employs `ssh` to connect to the EC2 instances. Add the following to *\~/.ssh/config*, so that `ssh` knows how to connect to the EC2 instances:

```
Host *.amazonaws.com
    IdentityFile ~/.ssh/MyKeyFile.pem
    User ubuntu
```

Depending on your which distribution your running, your username may be different than *ubuntu*.

### Running Commands on Remote Machines 

The first flavor of distributed processing is to simply run ordinary commands on remote machines. Let’s first double check that parallel is working by running the command-line tools `hostname` List of hosts:


```bash
$ parallel --nonall --slf hostnames hostname
ip-172-31-23-204
ip-172-31-23-205
```

Here, `--slf` is short for `--sshloginfile` and `--nonall` instructs `parallel` to execute the same command on every remote machine in the *hostnames* file without using any parameters. Remember, if you don’t have any remote machines to utilize, you can replace `--slf hostnames` with `--sshlogin :` so that the command is run on your local machine:


```bash
$ parallel --nonall --sshlogin : hostname
data-science-toolbox
```

Running the same command on every remote machine once only requires one core per machine. If we wanted to distribute the list of arguments passed in to `parallel` then it could potentially use more than one core. If the number of cores are not specified explicitly, `parallel` will try to determine this:

    $ seq 2 | parallel --slf hostnames echo 2>&1 | fold
    bash: parallel: command not found
    parallel: Warning: Could not figure out number of cpus on ec2-54-88-122-140.comp
    ute-1.amazonaws.com (). Using 1.
    1
    2

In this case, we have `parallel` installed on one of the two remote machines. We’re getting a warning message indicating that `parallel` is not found on one of them. As a result, `parallel` cannot determine the number of cores and will default to using one core. When you receive this warning message, you can do one of the following four things:

- Don’t worry, and be happy with using one core per machine.
- Specify the number of jobs per machine via `-j`.
- Specify the number of cores to use per machine by putting, for example, *2/* if you want two cores, in front of each hostname in the *hostnames* file.
- Install GNU Parallel using a package manager. For example, on Ubuntu:


```bash
$ parallel --nonall --slf hostnames "sudo apt-get install -y parallel"
```

### Distributing Local Data among Remote Machines 

The second flavor of distributed processing is to distribute local data directly among remote machines. Imagine you have one very large data set that you want to process it using multiple remote machines. For simplicity, we’re going to sum all integers from 1 to 1000. First, let’s double check that our input is actually being distributed by printing the hostname of the remote machine and the length of the input it received using `wc`:


```bash
$ seq 1000 | parallel -N100 --pipe --slf hosts  "(hostname; wc -l) | paste -sd:"
ip-172-31-23-204:100
ip-172-31-23-205:100
ip-172-31-23-205:100
ip-172-31-23-204:100
ip-172-31-23-205:100
ip-172-31-23-204:100
ip-172-31-23-205:100
ip-172-31-23-204:100
ip-172-31-23-205:100
ip-172-31-23-204:100
```

We can verify that our 1000 numbers get distributed evenly in subsets of 100 (as specified by `-N100`). Now, we’re ready to sum all those numbers:


```bash
seq 1000 | parallel -N100 --pipe --slf hosts "paste -sd+ | bc" | paste -sd+ | bc
500500
```

Here, we immediately also sum the ten sums we get back from the remote machines. Let’s double check the answer is correct:


```bash
$ seq 1000 | paste -sd+ | bc
500500
```

Good, that works. If you have a larger command that you want to execute on the remote machines, you can also put it in a separate script and upload it script with `parallel`.

Let’s create a very simple command-line tool called *sum*:


```bash
#!/usr/bin/env bash
paste -sd+ | bc
```

Don’t forget to make it executable as discussed in [Chapter 4](#chapter-4-creating-reusable-command-line-tools). The following command first uploads the file *sum*:

    $ seq 1000 | parallel -N100 --basefile sum --pipe --slf hosts './sum' | ./sum
    500500

Of course, summing 1000 numbers is only a toy example. It would have been much faster to do this locally. However, we hope it’s clear from this that GNU Parallel can be incredibly powerful.

### Processing Files on Remote Machines 

The third flavor of distributed processing is to send files to remote machines, process them, and retrieve the results. Imagine that we want to count for each borough of New York City, how often they receive service calls on 311. We don’t have that data on our local machine yet, so let’s first obtain it from <https://data.cityofnewyork.us/> using their great API:


```bash
$ seq 0 100 900 | parallel  "curl -sL 'http://data.cityofnewyork.us/resource'"\
> "'/erm2-nwe9.json?\$limit=100&\$offset={}' | jq -c '.[]' | gzip > {#}.json.gz"
```

Note that `jq -c '.[]'` is used to flatten the array of JSON objects so that there’s one line. We now have 10 files containing compressed JSON data. Let’s see what one line of JSON looks like:


```bash
$ zcat 1.json.gz | head -n 1 | fold
{"school_region":"Unspecified","park_facility_name":"Unspecified","x_coordinate_
state_plane":"945974","agency_name":"Department of Health and Mental Hygiene","u
nique_key":"147","facility_type":"N/A","status":"Assigned","school_address":"Uns
pecified","created_date":"2006-08-29T21:25:23","community_board":"01 STATEN ISLA
ND","incident_zip":"10302","school_name":"Unspecified","location":{"latitude":"4
0.62745427115626","longitude":"-74.13789056665027","needs_recoding":false},"comp
laint_type":"Food Establishment","city":"STATEN ISLAND","park_borough":"STATEN I
SLAND","school_state":"Unspecified","longitude":"-74.13789056665027","intersecti
on_street_1":"DECKER AVENUE","y_coordinate_state_plane":"167905","due_date":"200
6-10-05T21:25:23","latitude":"40.62745427115626","school_code":"Unspecified","sc
hool_city":"Unspecified","address_type":"INTERSECTION","intersection_street_2":"
BARRETT AVENUE","school_number":"Unspecified","resolution_action_updated_date":"
2006-10-06T00:00:17","descriptor":"Handwashing","school_zip":"Unspecified","loca
tion_type":"Restaurant/Bar/Deli/Bakery","agency":"DOHMH","borough":"STATEN ISLAN
D","school_phone_number":"Unspecified"}
```

If we were to get the total number of service calls per borough on our local machine, we would run the following command:


```bash
$ zcat *.json.gz |               
> ./jq -r '.borough' |           
> tr '[A-Z] ' '[a-z]_' |         
> sort | uniq -c |               
> awk '{print $2","$1}' |        
> header -a borough,count |      
> csvsort -rc count | csvlook    
|----------------+--------|
|  borough       | count  |
|----------------+--------|
|  unspecified   | 467    |
|  manhattan     | 274    |
|  brooklyn      | 103    |
|  queens        | 77     |
|  bronx         | 44     |
|  staten_island | 35     |
|----------------+--------|
```

Because this is quite a long pipeline, and because we’re using it again in a moment with `parallel`, it’s worth to go over it:

- Expand all compressed files using `zcat`.
- For each call, extract the name of the borough using `jq`.
- Convert borough names to lowercase and replace spaces with underscores (because `awk` splits on whitespace by default).
- Count the occurrences of each borough using `sort` and `uniq`.

- Reverse the count and borough and make it comma delimited using `awk`.
- Add a header using `header`.
- Sort by count and print table using `csvsort` [@csvsort].

Imagine, for a moment, that our own machine is so slow that we simply cannot perform this pipeline locally. We can use GNU Parallel to distribute the local files among the remote machines, let them do the processing, and retrieve the results:


```bash
$ ls *.json.gz |                                                            
> parallel -v --basefile jq \                                               
> --trc {.}.csv \                                                           
> --slf hostnames \                                                         
> "zcat {} | ./jq -r '.borough' | tr '[A-Z] ' '[a-z]_' | sort | uniq -c |"\
> " awk '{print \$2\",\"\$1}' > {.}.csv"                                    
zcat 10.json.gz | ./jq -r '.borough' | sort | uniq -c | awk '{print $2","$1}'
zcat 2.json.gz | ./jq -r '.borough' | sort | uniq -c | awk '{print $2","$1}'
zcat 1.json.gz | ./jq -r '.borough' | sort | uniq -c | awk '{print $2","$1}'
zcat 3.json.gz | ./jq -r '.borough' | sort | uniq -c | awk '{print $2","$1}'
zcat 4.json.gz | ./jq -r '.borough' | sort | uniq -c | awk '{print $2","$1}'
zcat 5.json.gz | ./jq -r '.borough' | sort | uniq -c | awk '{print $2","$1}'
zcat 6.json.gz | ./jq -r '.borough' | sort | uniq -c | awk '{print $2","$1}'
zcat 7.json.gz | ./jq -r '.borough' | sort | uniq -c | awk '{print $2","$1}'
zcat 8.json.gz | ./jq -r '.borough' | sort | uniq -c | awk '{print $2","$1}'
zcat 9.json.gz | ./jq -r '.borough' | sort | uniq -c | awk '{print $2","$1}'
```

This long command breaks down as follows:

- Print the list of files and pipe it into `parallel`.
- Transmit the `jq` binary to each remote machine. Lucklily, jq has no dependencies. This file will be removed from the remote machine at the end because we specified `--trc` (which implies the `--cleanup` command-line argument).
- The command-line argument `--trc {.}.csv` is short for `--transfer --return {.}.csv --cleanup`. (The replacement string *{.}* gets replaced with the input filename without the last extension.) Here, this means that the JSON file gets transfered to the remote machine, the CSV file gets returned to the local machine, and both files will be removed after each job from the remote machine.
- Specify a list of hostnames. Remember, if you want to try this out locally, you can specify `--sshlogin :` instead of `--self hostnames`.

- Note the escaping in the `awk` expression. Quoting can sometimes be tricky. Here, the dollar signs and the double quotes are escaped. In quoting ever gets too confusing, remember that you put the pipeline into a separate command-line tool just as we did with `sum`.

If we, at some point during this command, run `ls` on one of the remote machines, we could see that `parallel` indeed transfers (and cleans up) the binary `jq`, the JSON files, and CSV files:


```bash
$ ssh $(head -n 1 hostnames) ls
1.json.csv
1.json.gz
jq
```

Each CSV file looks like this:


```bash
$ cat 1.json.csv
bronx,3
brooklyn,5
manhattan,24
queens,3
staten_island,2
unspecified,63
```

We can sum the counts in each CSV file using Rio and the `aggregate` function in R:


```bash
$ cat *.csv | header -a borough,count |
> Rio -e 'aggregate(count ~ borough, df, sum)' |
> csvsort -rc count | csvlook
|----------------+--------|
|  borough       | count  |
|----------------+--------|
|  unspecified   | 467    |
|  manhattan     | 274    |
|  brooklyn      | 103    |
|  queens        | 77     |
|  bronx         | 44     |
|  staten_island | 35     |
|----------------+--------|
```

Or, if you prefer to use SQL to aggregate results, you can use `csvsql` as discussed in [Chapter 5](#chapter-5-scrubbing-data):


```bash
$ cat *.csv | header -a borough,count |
> csvsql --query 'SELECT borough, SUM(count) AS count FROM stdin '\
> 'GROUP BY borough ORDER BY count DESC' | csvlook
|----------------+--------|
|  borough       | count  |
|----------------+--------|
|  unspecified   | 467    |
|  manhattan     | 274    |
|  brooklyn      | 103    |
|  queens        | 77     |
|  bronx         | 44     |
|  staten_island | 35     |
|----------------+--------|
```

## Discussion 

As data scientists, we work with data, and sometimes a lot of data. This means that sometimes we need to run a command multiple times or distribute data-intensive commands over multiple cores. In this chapter we have shown you how easy it is to parallelize commands. GNU Parallel is a very powerful and flexible tool to speed up ordinary command-line tools and distribute them over multiple cores and remote machines. It offers a lot of functionality and in this chapter we’ve only been able to scratch the surface. Some features of GNU Parallel are that we haven’t covered:

- Different ways of specifying input.
- Keep a log of all the jobs.
- Only start new jobs when the machine is under a certain load.
- Timeout, resume, and retry jobs.

Once you have a basic understanding of GNU Parallel and its most important options, we recommend that you take a look at its tutorial listed in the Further Reading section.

## Further Reading 

* Tange, O. 2011. “GNU Parallel - the Command-Line Power Tool.”<em>;Login: The USENIX Magazine</em> 36 (1). Frederiksberg, Denmark:42–47. <a href="http://www.gnu.org/s/parallel" class="uri">http://www.gnu.org/s/parallel</a>.
* Tange, Ole. 2014. “GNU Parallel.” <a href="http://www.gnu.org/software/parallel" class="uri">http://www.gnu.org/software/parallel</a>.
* Services, Amazon Web. 2014. “AWS Command Line Interface.” <a href="http://aws.amazon.com/cli" class="uri">http://aws.amazon.com/cli</a>.






<!--chapter:end:08.Rmd-->

# Modeling Data {#chapter-9-modeling-data}

In this chapter we’re going to perform the fourth and last step of the OSEMN model that we can do on a computer: modeling data. Generally speaking, to model data is to create an abstract or higher-level description of your data. Just like with creating visualizations, it’s like taking a step back from the individual data points.

However, visualizations, on the one hand, are characterized by shapes, positions, and colors such that we can interpret them by looking at them. Models, on the other hand, are internally characterized by a bunch of numbers, which means that computers can use them, for example, to make predictions about a new data points. (We can still visualize models so that we can try to understand them and see how they are performing.)

In this chapter we’ll consider four common types of algorithms to model data:

- Dimensionality reduction.
- Clustering.
- Regression.
- Classification.

These four algorithms come from the field of machine learning. As such, we’re going to change our vocabulary a bit. Let’s assume that we have a CSV file, also known as a *data set*. Each row, except for the header, is considered to be a *data point*. For simplicity we assume that each column that contains numerical values is an input *feature*. If a data point also contains a non-numerical field, such as the *species* column in the Iris data set, then that is known as the data point’s *label*.

The first two types of algorithms (dimensionality reduction and clustering) are most often unsupervised, which means that they create a model based on the features of the data set only. The last two types of algorithms (regression and classification) are by definition supervised algorithms, which means that they also incorporate the labels into the model.

\BeginKnitrBlock{rmdcaution}

This is by no means an introduction to machine learning. That implies that we must skim over many details. We strongly advise that you become familiar with an algorithm before applying it blindly to your data.
\EndKnitrBlock{rmdcaution}

## Overview 

In this chapter, you’ll learn how to:

- Reduce the dimensionality of your data set.
- Identify groups of data points with three clustering algorithms.
- Predict the quality of white wine using regression.
- Classify wine as red or white via a prediction API.

## More Wine Please! 

In this chapter, we’ll be using a data set of wine tastings. Specifically, red and white Portuguese "Vinho Verde" wine. Each data point represents a wine, and consists of 11 physicochemical properties: (1) fixed acidity, (2) volatile acidity, (3) citric acid, (4) residual sugar, (5) chlorides, (6) free sulfur dioxide, (7) total sulfur dioxide, (8) density, (9) pH, (10) sulphates, and (11) alcohol. There is also a quality score. This score lies between 0 (very bad) and 10 (excellent) and is the median of at least three evaluation by wine experts. More information about this data set is available at <http://archive.ics.uci.edu/ml/datasets/Wine+Quality>.

There are two data sets: one for white wine and one for red wine. The very first step is to obtain the two data sets using `curl` (and of course `parallel` because we haven’t got all day):


```bash
$ cd ~/book/ch09
$ parallel "curl -sL http://archive.ics.uci.edu/ml/machine-learning-databases"\
> "/wine-quality/winequality-{}.csv > data/wine-{}.csv" ::: red white
```

The triple colon is yet another way we can pass data to `parallel`. Let’s inspect both data sets using `head` and count the number of rows using `wc -l`:


```bash
$ head -n 5 wine-{red,white}.csv | fold
==> wine-red.csv <==
"fixed acidity";"volatile acidity";"citric acid";"residual sugar";"chlorides";"f
ree sulfur dioxide";"total sulfur dioxide";"density";"pH";"sulphates";"alcohol";
"quality"
7.4;0.7;0;1.9;0.076;11;34;0.9978;3.51;0.56;9.4;5
7.8;0.88;0;2.6;0.098;25;67;0.9968;3.2;0.68;9.8;5
7.8;0.76;0.04;2.3;0.092;15;54;0.997;3.26;0.65;9.8;5
11.2;0.28;0.56;1.9;0.075;17;60;0.998;3.16;0.58;9.8;6

==> wine-white.csv <==
"fixed acidity";"volatile acidity";"citric acid";"residual sugar";"chlorides";"f
ree sulfur dioxide";"total sulfur dioxide";"density";"pH";"sulphates";"alcohol";
"quality"
7;0.27;0.36;20.7;0.045;45;170;1.001;3;0.45;8.8;6
6.3;0.3;0.34;1.6;0.049;14;132;0.994;3.3;0.49;9.5;6
8.1;0.28;0.4;6.9;0.05;30;97;0.9951;3.26;0.44;10.1;6
7.2;0.23;0.32;8.5;0.058;47;186;0.9956;3.19;0.4;9.9;6
$ wc -l wine-{red,white}.csv
  1600 wine-red.csv
  4899 wine-white.csv
  6499 total
```

At first sight this data appears to be very clean already. Still, let’s scrub this data a little bit so that it conforms more with what most command-line tools are expecting. Specifically, we’ll:

- Convert the header to lowercase.
- Convert the semi-colons to commas.
- Convert spaces to underscores.
- Remove unnecessary quotes.

These things can all be taken care of by ‘tr\`. Let’s use a for loop this time---for old times’ sake---to process both data sets:


```bash
for T in red white; do
< wine-$T.csv tr '[A-Z]; ' '[a-z],_' | tr -d \" > wine-${T}-clean.csv
done
```

Let’s also create a data set by combining the two data sets. We’ll use `csvstack` to add a column named "type" which will be "red" for rows of the first file, and "white" for rows of the second file:


```bash
$ HEADER="$(head -n 1 wine-red-clean.csv),type"
$ csvstack -g red,white -n type wine-{red,white}-clean.csv |
> csvcut -c $HEADER > wine-both-clean.csv
```

The new column *type* is added to the beginning of the table. Because some of the command-line tools that we’ll use in this chapter assume that the class label is the last column, we’ll rearrange the columns by using `csvcut`. Instead of typing all 13 columns, we temporary store the desired header into a variable *\$HEADER* before we call `csvstack`.

It’s good to check whether there are any missing values in this data set:


```bash
$ csvstat wine-both-clean.csv --nulls
  1. fixed_acidity: False
  2. volatile_acidity: False
  3. citric_acid: False
  4. residual_sugar: False
  5. chlorides: False
  6. free_sulfur_dioxide: False
  7. total_sulfur_dioxide: False
  8. density: False
  9. ph: False
 10. sulphates: False
 11. alcohol: False
 12. quality: False
 13. type: False
```

Excellent! Just out of curiosity, let’s see what the how the distribution of quality looks like for both red and white wines.


```bash
$ < wine-both-clean.csv Rio -ge 'g+geom_density(aes(quality, '\
'fill=type), adjust=3, alpha=0.5)' | display
```

\begin{figure}

{\centering \includegraphics[width=32.81in]{images/ch09-wine-quality-density} 

}

\end{figure}

From the density plot we can see the quality of white wine is distributed more towards higher values. Does this mean that white wines are overall better than red wines, or that the white wine experts more easily give higher scores than red wine experts? That’s something that the data doesn’t tell us. Or is there perhaps a correlation between alcohol and quality? Let’s use Rio and ggplot again to find out:


```bash
$ < wine-both-clean.csv Rio -ge 'ggplot(df, aes(x=alcohol, y=quality, '\
> 'color=type)) + geom_point(position="jitter", alpha=0.2) + '\
> 'geom_smooth(method="lm")' | display
```

\begin{figure}

{\centering \includegraphics[width=32.81in]{images/ch09-wine-alcohol-vs-quality} 

}

\end{figure}

Eureka! Ahem, let’s carry on with some modeling, shall we?

## Dimensionality Reduction with Tapkee 

The goal of dimensionality reduction is to map high-dimensional data points onto a lower dimensional mapping. The challenge is to keep similar data points close together on the lower-dimensional mapping. As we’ve seen in the previous section, our wine data set contained 13 features. We’ll stick with two dimensions because that’s straight forward to visualize.

Dimensionality reduction is often regarded as being part of exploring step. It’s useful for when there are too many features for plotting. You could do a scatter-plot matrix, but that only shows you two features at a time. It’s also useful as a pre-processing step for other machine learning algorithms.

Most dimensionality reduction algorithms are unsupervised. This means that they don’t employ the labels of the data points in order to construct the lower-dimensional mapping.

In this section we’ll look at two techniques: PCA, which stands for Principal Components Analysis [@Pearson1901] and t-SNE, which stands for t-distributed Stochastic Neighbor Embedding [@van2008visualizing].

### Introducing Tapkee 

Tapkee is a C++ template library for dimensionality reduction [@Lisitsyn2013]. The library contains implementations of many dimensionality reduction algorithms, including:

- Locally Linear Embedding
- Isomap
- Multidimensional scaling
- PCA
- t-SNE

Tapkee’s website: <http://tapkee.lisitsyn.me/>, contains more information about these algorithms. Although Tapkee is mainly a library that can be included in other applications, it also offers a command-line tool. We’ll use this to perform dimensionality reduction on our wine data set.

### Installing Tapkee 

If you aren’t running the Data Science Toolbox, you’ll need to download and compile Tapkee yourself. First make sure that you have `CMake` installed. On Ubuntu, you simply run:


```bash
$ sudo apt-get install cmake
```

Please consult Tapkee’s website for instructions for other operating systems. Then execute the following commands to download the source and compile it:


```bash
$ curl -sL https://github.com/lisitsyn/tapkee/archive/master.tar.gz > \
> tapkee-master.tar.gz
$ tar -xzf tapkee-master.tar.gz
$ cd tapkee-master
$ mkdir build && cd build
$ cmake ..
$ make
```

This creates a binary executable named `tapkee`.

### Linear and Non-linear Mappings 

First, we’ll scale the features using standardization such that each feature is equally important. This generally leads to better results when applying machine learning algorithms.

To scale we use a combination of `cols` and `Rio`:


```bash
$ < wine-both.csv cols -C type Rio -f scale > wine-both-scaled.csv
```

Now we apply both dimensionality reduction techniques and visualize the mapping using `Rio-scatter`:


```bash
$ < wine-both-scaled.csv cols -C type body tapkee --method pca |
> header -r x,y,type | Rio-scatter x y type |
> tee tapkee-wine-pca.png | display
```

\begin{figure}

{\centering \includegraphics[width=7in]{images/tapkee-wine-pca} 

}

\caption{PCA}(\#fig:unnamed-chunk-15)
\end{figure}


```bash
$ < wine-both-scaled.csv cols -C type body tapkee --method t-sne |
> header -r x,y,type | Rio-scatter x y type |
> tee tapkee-wine-t-sne.png | display
```

\begin{figure}

{\centering \includegraphics[width=7in]{images/tapkee-wine-t-sne} 

}

\caption{t-SNE}(\#fig:unnamed-chunk-17)
\end{figure}

Note that there’s not a single GNU core util (i.e., classic command-line tool) in this one-liner. Now that’s the power of the command line!

## Clustering with Weka 

In this section we’ll be clustering our wine data set into groups. Like, dimensionality reduction, clustering is usually unsupervised. It can be used go gain an understanding of how your data is structured. Once the data has been clustered, you can visualize the result by coloring the data points according to their cluster assignment. For most algorithms you specify upfront how many groups you want the data to be clustered in; some algorithms are able to determine a suitable number of groups.

For this task we’ll use Weka, which is being maintained by the Machine Learning Group at the University of Waikato [@Hall2009]. If you already know Weka, then you probably know it as a software with a graphical user interface. However, as you’ll see, Weka can also be used from the command line (albeit with some modifications). Besides clustering, Weka can also do classification and regression, but we’re going to be using other tools for those machine learning tasks.

### Introducing Weka 

You may ask, surely there are better command-line tools for clustering? And you are right. One reason we include Weka in this chapter is to show you how you can work around these imperfections by building additional command-line tools. As you spend more time on the command line and try out other command-line tools, chances are that you come across one that seems very promising at first, but does not work as you expected. A common imperfection is the command-line tool does not handle standard in or standard out correctly. In the next section we’ll point out these imperfections and demonstrate how we work around them.

### Taming Weka on the Command Line 

Weka can be invoked from the command line, but it’s definitely not straightforward or user friendly. Weka is programmed in Java, which means that you have to run `java`, specify the location of the *weka.jar* file, and specify the individual class you want to call. For example, Weka has a class called *MexicanHat*, which generates a toy data set. To generate 10 data points using this class, you would run:


```bash
$ java -cp ~/bin/weka.jar weka.datagenerators.classifiers.regression.MexicanHat\
>  -n 10 | fold
%
% Commandline
%
% weka.datagenerators.classifiers.regression.MexicanHat -r weka.datagenerators.c
lassifiers.regression.MexicanHat-S_1_-n_10_-A_1.0_-R_-10..10_-N_0.0_-V_1.0 -S 1
-n 10 -A 1.0 -R -10..10 -N 0.0 -V 1.0
%
@relation weka.datagenerators.classifiers.regression.MexicanHat-S_1_-n_10_-A_1.0
_-R_-10..10_-N_0.0_-V_1.0

@attribute x numeric
@attribute y numeric

@data

4.617564,-0.215591
-1.798384,0.541716
-5.845703,-0.072474
-3.345659,-0.060572
9.355118,0.00744
-9.877656,-0.044298
9.274096,0.016186
8.797308,0.066736
8.943898,0.051718
8.741643,0.072209
```

Don’t worry about the output of this command, we’ll discuss that later. At this moment, we’re concerned with the usage of Weka. There are a couple of things to note here:

- You need run `java`, which is counter-intuitive.
- The jar file contains over 2000 classes, and only about 300 of those can be used from the command line directly. How do you know which ones?
- You need to specify entire namespace of the class: `weka.datagenerators.classifiers.regression.MexicanHat`. How are you supposed to remember that?

Does this mean that we’re going to give up on Weka? Of course not! Since Weka does contain a lot of useful functionality, we’re going to tackle these issues in the next three subsections.

#### An Improved Command-line Tool for Weka 

Save the following snippet as a new file called `weka` and put it somewhere on your *PATH*:


```bash
#!/usr/bin/env bash
java -Xmx1024M -cp ${WEKAPATH}/weka.jar "weka.$@"
```

Subsequently, add the following line to your *.bashrc* file so that `weka` can be called from anywhere:


```bash
$ export WEKAPATH=/home/vagrant/repos/weka
```

We can now call the previous example with:


```bash
$ weka datagenerators.classifiers.regression.MexicanHat -n 10
```

#### Usable Weka Classes 

As mentioned, the file *weka.jar* contains over 2000 classes. Many of them cannot be used from the command line directly. We consider a class usable from the command line when it provides us with a help message if we invoke it with `-h`. For example:


```bash
$ weka datagenerators.classifiers.regression.MexicanHat -h

Data Generator options:

-h
        Prints this help.
-o <file>
        The name of the output file, otherwise the generated data is
        printed to stdout.
-r <name>
        The name of the relation.
-d
        Whether to print debug informations.
-S
        The seed for random function (default 1)
-n <num>
        The number of examples to generate (default 100)
-A <num>
        The amplitude multiplier (default 1.0).
-R <num>..<num>
        The range x is randomly drawn from (default -10.0..10.0).
-N <num>
        The noise rate (default 0.0).
-V <num>
        The noise variance (default 1.0).
```

Now that’s usable. This, for example, is not a usable class:


```bash
$ weka filters.SimpleFilter -h
java.lang.ClassNotFoundException: -h
        at java.net.URLClassLoader$1.run(URLClassLoader.java:202)
        at java.security.AccessController.doPrivileged(Native Method)
        at java.net.URLClassLoader.findClass(URLClassLoader.java:190)
        at java.lang.ClassLoader.loadClass(ClassLoader.java:306)
        at sun.misc.Launcher$AppClassLoader.loadClass(Launcher.java:301)
        at java.lang.ClassLoader.loadClass(ClassLoader.java:247)
        at java.lang.Class.forName0(Native Method)
        at java.lang.Class.forName(Class.java:171)
        at weka.filters.Filter.main(Filter.java:1344)
-h
```

The following pipeline runs `weka` with every class in *weka.jar* and `-h` and saves the standard output and standard error to a file with the same name as the class:


```bash
$ unzip -l $WEKAPATH/weka.jar |
> sed -rne 's/.*(weka)\/([^g])([^$]*)\.class$/\2\3/p' |
> tr '/' '.' |
> parallel --timeout 1 -j4 -v "weka {} -h > {} 2>&1"
```

We now have 749 files. With the following command we save the filename of every files which does not contain the string *Exception* to *weka.classes*:


```bash
$ grep -L 'Exception' * | tee $WEKAPATH/weka.classes
```

This still comes down to 332 classes! Here are a few classes that might be of interest):

- `attributeSelection.PrincipalComponents`
- `classifiers.bayes.NaiveBayes`
- `classifiers.evaluation.ConfusionMatrix`
- `classifiers.functions.SimpleLinearRegression`
- `classifiers.meta.AdaBoostM1`
- `classifiers.trees.RandomForest`

- `clusterers.EM`
- `filters.unsupervised.attribute.Normalize`

As you can see, `weka` offers a whole range of classes and functionality.

#### Adding Tab Completion 

At this moment, you still need to type in the entire class name yourself. You can add so-called tab completion by adding the following snippet to your *.bashrc* file after you export *WEKAPATH*:


```bash
_completeweka() {
  local curw=${COMP_WORDS[COMP_CWORD]}
  local wordlist=$(cat $WEKAPATH/weka.classes)
  COMPREPLY=($(compgen -W '${wordlist[@]}' -- "$curw"))
  return 0
}
complete -o nospace -F _completeweka weka
```

This function makes use of the *weka.classes* file we generated earlier. If you now type: `weka clu<Tab><Tab><Tab>` on the command line, you are presented with a list of all classes that have to do with clustering:

    $ weka clusterers.
    clusterers.CheckClusterer
    clusterers.CLOPE
    clusterers.ClusterEvaluation
    clusterers.Cobweb
    clusterers.DBSCAN
    clusterers.EM
    clusterers.FarthestFirst
    clusterers.FilteredClusterer
    clusterers.forOPTICSAndDBScan.OPTICS_GUI.OPTICS_Visualizer
    clusterers.HierarchicalClusterer
    clusterers.MakeDensityBasedClusterer
    clusterers.OPTICS
    clusterers.sIB
    clusterers.SimpleKMeans
    clusterers.XMeans

Creating a command-line tool `weka` and adding tab completion makes sure that Weka is a little bit more friendly to use on the command line.

### Converting between CSV to ARFF Data Formats 

Weka uses ARFF as a file format. This is basically CSV with additional information about the columns. We’ll use two convenient command-line tools to convert between CSV and ARFF, namely `csv2arff` (see Example \@ref(exm:csv2arff) ) and `arff2csv` (see Example \@ref(exm:arff2csv)).

\BeginKnitrBlock{example}\iffalse{-91-67-111-110-118-101-114-116-32-67-83-86-32-116-111-32-65-82-70-70-93-}\fi{}
<span class="example" id="exm:csv2arff"><strong>(\#exm:csv2arff)  \iffalse (Convert CSV to ARFF) \fi{} </strong></span>
\EndKnitrBlock{example}

```bash
#!/usr/bin/env bash
weka core.converters.CSVLoader /dev/stdin
```

\BeginKnitrBlock{example}\iffalse{-91-67-111-110-118-101-114-116-32-65-82-70-70-32-116-111-32-67-83-86-93-}\fi{}
<span class="example" id="exm:arff2csv"><strong>(\#exm:arff2csv)  \iffalse (Convert ARFF to CSV) \fi{} </strong></span>
\EndKnitrBlock{example}

```bash
#!/usr/bin/env bash
weka core.converters.CSVSaver -i /dev/stdin
```

### Comparing Three Cluster Algorithms 

Unfortunately, in order to cluster data using Weka, we need yet another command-line tool to help us with this. The *AddCluster* class is needed to assign data points to the learned clusters. Unfortunately, this class does not accept data from standard input, not even when we specify *-i /dev/stdin* because it expects a file with the *.arff* extension. We consider this to be bad design. The source code of `weka-cluster` is:


```bash
#!/usr/bin/env bash
ALGO="$@"
IN=$(mktemp --tmpdir weka-cluster-XXXXXXXX).arff

finish () {
        rm -f $IN
}
trap finish EXIT

csv2arff > $IN
weka filters.unsupervised.attribute.AddCluster -W "weka.${ALGO}" -i $IN \
-o /dev/stdout | arff2csv
```

Now we can apply the EM clustering algorithm and save the assignment as follows:


```bash
$ cd data
$ < wine-both-scaled.csv csvcut -C quality,type |          
> weka-cluster clusterers.EM -N 5 |                        
> csvcut -c cluster > data/wine-both-cluster-em.csv        
```

- Use the scaled features, and don’t use the features quality and type for the cluster.
- Apply the algorithm using `weka-cluster`.
- Only save the cluster assignment.

We’ll run the same command again for *SimpleKMeans* and *Cobweb* algorithms. Now we have three files with cluster assignments. Let’s create a t-SNE mapping in order to visualize the cluster assignments:


```bash
$ < wine-both-scaled.csv csvcut -C quality,type | body tapkee --method t-sne |
> header -r x,y > wine-both-xy.csv
```

Next, the cluster assignments are combined with the t-SNE mapping using `paste` and a scatter plot is created using `Rio-scatter`:


```bash
$ parallel -j1 "paste -d, wine-both-xy.csv wine-both-cluster-{}.csv | "\
> "Rio-scatter x y cluster | display" ::: em simplekmeans cobweb
```

\begin{figure}

{\centering \includegraphics[width=32.81in]{images/ch09-wine-cluster-em} 

}

\caption{EM}(\#fig:unnamed-chunk-33)
\end{figure}

\begin{figure}

{\centering \includegraphics[width=32.81in]{images/ch09-wine-cluster-simplekmeans} 

}

\caption{SimpleKMeans}(\#fig:unnamed-chunk-34)
\end{figure}

\begin{figure}

{\centering \includegraphics[width=32.81in]{images/ch09-wine-cluster-cobweb} 

}

\caption{Cobweb}(\#fig:unnamed-chunk-35)
\end{figure}

Admittedly, we have through a lot of trouble taming Weka. The exercise was worth it, because some day you may run into a command-line tool that works different from what you expect. Now you know that there are always ways to work around such command-line tools.

## Regression with SciKit-Learn Laboratory 

In this section, we’ll be predicting the quality of the white wine, based on their physicochemical properties. Because the quality is a number between 0 and 10, we can consider predicting the quality as a regression task. Generally speaking, using training data points, we train three regression models using three different algorithms.

We’ll be using the SciKit-Learn Laboratory (or SKLL) package for this. If you’re not using the Data Science Toolbox, you can install SKLL using `pip`:


```bash
$ pip install skll
```

If you’re running Python 2.7, you also need to install the following packages:


```bash
$ pip install configparser futures logutils
```

### Preparing the Data 

SKLL expects that the train and test data have the same filenames, located in separate directories. However, in this example, we’re going to use cross-validation, meaning that we only need to specify a training data set. Cross-validation is a technique that splits up the whole data set into a certain number of subsets. These subsets are called folds. (Usually, five or ten folds are used.)

We need to add an identifier to each row so that we can easily identify the data points later (the predictions are not in the same order as the original data set):


```bash
$ mkdir train
$ wine-white-clean.csv nl -s, -w1 -v0 | sed '1s/0,/id,/' > train/features.csv
```

### Running the Experiment 

Create a configuration file called *predict-quality.cfg*:

```ini
[General]
experiment_name = Wine
task = cross_validate

[Input]
train_location = train
featuresets = [["features.csv"]]
learners = ["LinearRegression","GradientBoostingRegressor","RandomForestRegressor"]
label_col = quality

[Tuning]
grid_search = false
feature_scaling = both
objective = r2

[Output]
log = output
results = output
predictions = output
```

We run the experiment using the *run\_experiment* command-line tool \[cite:run\_experiment\]:


```bash
$ run_experiment -l evaluate.cfg
```

The `-l` command-line argument indicates that we’re running in local mode. SKLL also offers the possibility to run experiments on clusters. The time it takes to run the experiment depends on the complexity of the chosen algorithms.

### Parsing the Results 

Once all algorithms are done, the results can now be found in the directory *output*:


```bash
$ cd output
$ ls -1
Wine_features.csv_GradientBoostingRegressor.log
Wine_features.csv_GradientBoostingRegressor.predictions
Wine_features.csv_GradientBoostingRegressor.results
Wine_features.csv_GradientBoostingRegressor.results.json
Wine_features.csv_LinearRegression.log
Wine_features.csv_LinearRegression.predictions
Wine_features.csv_LinearRegression.results
Wine_features.csv_LinearRegression.results.json
Wine_features.csv_RandomForestRegressor.log
Wine_features.csv_RandomForestRegressor.predictions
Wine_features.csv_RandomForestRegressor.results
Wine_features.csv_RandomForestRegressor.results.json
Wine_summary.tsv
```

SKLL generates four files for each learner: one log, two with results, and one with predictions. Moreover, SKLL generates a summary file, which contains a lot of information about each individual fold (too much to show here). We can extract the relevant metrics using the following SQL query:


```bash
$ < Wine_summary.tsv csvsql --query "SELECT learner_name, pearson FROM stdin "\
> "WHERE fold = 'average' ORDER BY pearson DESC" | csvlook
|----------------------------+----------------|
|  learner_name              | pearson        |
|----------------------------+----------------|
|  RandomForestRegressor     | 0.741860521533 |
|  GradientBoostingRegressor | 0.661957860603 |
|  LinearRegression          | 0.524144785555 |
|----------------------------+----------------|
```

The relevant column here is *pearson*, which indicates the Pearson’s ranking correlation. This is value between -1 and 1 that indicates the correlation between the true ranking (of quality scores) and the predicted ranking. Let’s paste all the predictions back to the data set:


```bash
$ parallel "csvjoin -c id train/features.csv <(< output/Wine_features.csv_{}"\
> ".predictions | tr '\t' ',') | csvcut -c id,quality,prediction > {}" ::: \
> RandomForestRegressor GradientBoostingRegressor LinearRegression
$ csvstack *Regres* -n learner --filenames > predictions.csv
```

And create a plot using `Rio`:


```bash
$ < predictions.csv Rio -ge 'g+geom_point(aes(quality, round(prediction), '\
> 'color=learner), position="jitter", alpha=0.1) + facet_wrap(~ learner) + '\
> 'theme(aspect.ratio=1) + xlim(3,9) + ylim(3,9) + guides(colour=FALSE) + '\
> 'geom_smooth(aes(quality, prediction), method="lm", color="black") + '\
> 'ylab("prediction")' | display
```

\begin{figure}

{\centering \includegraphics[width=32.81in]{images/ch09-wine-quality-predictions} 

}

\end{figure}

## Classification with BigML 

In this fourth and last modeling section we’re going to classify wines as either red or wine. For this we’ll be using a solution called BigML, which provides a prediction API. This means that the actual modeling and predicting takes place in the cloud, which is useful if you need a bit more power than your own computer can offer.

Although prediction APIs are relatively young, they are upcoming, which is why we’ve included one in this chapter. Other providers of prediction APIs are Google (see <https://developers.google.com/prediction>) and PredictionIO (see <http://prediction.io>). One advantage of BigML is that they offer a convenient command-line tool called `bigmler` [@bigmler] that interfaces with their API. We can use this command-line like any other presented in this book, but behind the scenes, our data set is being sent to BigML’s servers, which perform the classification and send back the results.

### Creating Balanced Train and Test Data Sets 

First, we create a balanced data set to ensure that both class are represented equally. For this, we use `csvstack` [@csvstack], `shuf` [@shuf], `head`, and `csvcut`:


```bash
$ csvstack -n type -g red,white wine-red-clean.csv \                   
> <(< wine-white-clean.csv body shuf | head -n 1600) |                 
> csvcut -c fixed_acidity,volatile_acidity,citric_acid,\               
> residual_sugar,chlorides,free_sulfur_dioxide,total_sulfur_dioxide,\
> density,ph,sulphates,alcohol,type > wine-balanced.csv
```

This long command breaks down as follows:

- `csvstack` is used to combine multiple data sets. It creates a new column *type*, which has the value *red* for all rows coming from the first file *wine-red-clean.csv* and *white* for all rows coming from the second file.
- The second file is passed to `csvstack` using file redirection. This allows us to create a temporary file using `shuf`, which creates a random permutation of the *wine-white-clean.csv* and `head` which only selects the header and the first 1559 rows.
- Finally, we reorder the columns of this data set using `csvcut` because by default, `bigmler` assumes that the last column is the label.

Let’s verify that *wine-balanced.csv* is actually balanced by counting the number of instances per class using `parallel` and `grep`:


```bash
$ parallel --tag grep -c {} wine-balanced.csv ::: red white
red      1599
white    1599
```

As you can see, the data set *wine-balanced.csv* contains both 1599 red and 1599 white wines. Next we split into train and test data sets using `split` [@split]:


```bash
$ < wine-balanced.csv header > wine-header.csv                   
$ tail -n +2 wine-balanced.csv | shuf | split -d -n r/2          
$ parallel --xapply "cat wine-header.csv x0{1} > wine-{2}.csv" \ 
> ::: 0 1 ::: train test
```

This is another long command that deserves to be broken down:

- Get the header using `header` and save it to a temporary file named *wine-header.csv*
- Mix up the red and white wines using `tail` and `shuf` and split it into two files named *x00* and *x01* using a round robin distribution.
- Use `cat` to combine the header saved in *wine-header.csv* and the rows stored in *x00* to save it as *wine-train.csv*; similarly for *x01* and *wine-test.csv*. The `--xapply` command-line argument tells `parallel` to loop over the two input sources in tandem.

Let’s check again number of instances per class in both *wine-train.csv* and *wine-test.csv*:


```bash
$ parallel --tag grep -c {2} wine-{1}.csv ::: train test ::: red white
train red       821
train white     778
test white      821
test red        778
```

That looks like are data sets are well balanced. We’re now ready to call the prediction API using `bigmler`.

### Calling the API 

\BeginKnitrBlock{rmdnote}

You can obtain a BigML username and API key at <https://bigml.com/developers>. Be sure to set the variables *BIGML\_USERNAME* and *BIGML\_API\_KEY* in *.bashrc* with the appropriate values.
\EndKnitrBlock{rmdnote}

The API call is quite straightforward, and the meaning of each command-line argument is obvious from it’s name.


```bash
$ bigmler --train data/wine-train.csv \
> --test data/wine-test-blind.csv \
> --prediction-info full \
> --prediction-header \
> --output-dir output \
> --tag wine \
> --remote
```

The file *wine-test-blind.csv* is just *wine-test* with the *type* column (so the label) removed. After this call is finished, the results can be found in the *output* directory:


```bash
$ tree output
output
├── batch_prediction
├── bigmler_sessions
├── dataset
├── dataset_test
├── models
├── predictions.csv
├── source
└── source_test

0 directories, 8 files
```

### Inspecting the Results 

The file which is of most interest is *output/predictions.csv*:


```bash
$ csvcut output/predictions.csv -c type | head
type
white
white
red
red
white
red
red
white
red
```

We can compare these predicted labels with the labels in our test data set. Let’s count the number of misclassifications:


```bash
$ paste -d, <(csvcut -c type data/wine-test.csv) \        
> <(csvcut -c type output/predictions.csv) |
> awk -F, '{ if ($1 != $2) {sum+=1 } } END { print sum }' 
766
```

- First, we combine the *type* columns of both *data/wine-test.csv* and *output/predictions.csv*.
- Then, we use `awk` to keep count of when the two columns differ in value.

As you can see, BigML’s API misclassified 766 wines out of 1599. This isn’t a good result, but please note that we just blindly applied an algorithm to a data set, which we normally wouldn’t do.

### Conclusion 

BigML’s prediction API has proven to be easy to use. As with many of the command-line tools discussed in this book, we’ve barely scratched the surface with BigML. For completeness, we should mention that:

- BigML’s command-line tool also allows for local computations, which is useful for debugging.
- Results can also be inspected using BigML’s web interface.
- BigML can also perform regression tasks.

Please see <https://bigml.com/developers> for a complete overview of BigML’s features.

Although we’ve only been able to experiment with one prediction API, we do believe that prediction APIs in general are worthwhile to consider for doing data science.

## Further Reading 

* Cortez, P., A. Cerdeira, F. Almeida, T. Matos, and J. Reis. 2009. “Modeling Wine Preferences by Data Mining from Physicochemical Properties.” <em>Decision Support Systems</em> 47 (4). Elsevier:547–53.
* Hall, Mark, Eibe Frank, Geoffrey Holmes, Bernhard Pfahringer, Peter Reutemann, and Ian H. Witten. 2009. “The WEKA Data Mining Software: An Update.” <em>SIGKDD Explorations</em> 11 (1). ACM.
* Pearson, K. 1901. “On Lines and Planes of Closest Fit to Systems of Points in Space.” <em>Philosophical Magazine</em> 2 (11):559–72.
* Maaten, Laurens van der, and Geoffrey Everest Hinton. 2008. “Visualizing Data Using T-SNE.” <em>Journal of Machine Learning Research</em> 9:2579–2605.







<!--chapter:end:09.Rmd-->

# Conclusion {#chapter-10-conclusion}

In this final chapter, the book comes to a close. We'll first recap what we have discussed in the previous nine chapters, and will then offer you three pieces of advice and provide some resources to further explore the related topics we touched upon. Finally, in case you have any questions, comments, or new command-line tools to share, we provide a few ways to get in touch.

## Let's Recap 

This book explored the power of employing the command line to perform data science tasks. It is an interesting observation that the challenges posed by this relatively young field can be tackled by such a time-tested technology. It is our hope that you now see what the command line is capable of. The many command-line tools offer all sorts of possibilities that are well suited to the variety of tasks encompassing data science.

There are many definitions for data science available. In [Chapter 1](#chapter-1-introduction), we introduced the OSEMN model as defined by Mason and Wiggens, because it is a very practical one that translates to very specific tasks. The acronym OSEMN stands for obtaining, scrubbing, exploring, modeling, and interpreting data. [Chapter 1](#chapter-1-introduction) also explained why the command line is very suitable for doing these data science tasks.

In [Chapter 2](#chapter-2-getting-started), we explained how you can set up your own Data Science Toolbox and install the bundle that is associated with this book. [Chapter 2](#chapter-2-getting-started) also provided an introduction to the essential tools and concepts of the command line.

The OSEMN model chapters---[Chapter 3](#chapter-3-obtaining-data) (obtaining), [Chapter 5](#chapter-5-scrubbing-data) (scrubbing), [Chapter 7](#chapter-7-exploring-data) (exploring), and [Chapter 9](#chapter-9-modeling-data) (modeling)---focused on performing those practical tasks using the command line. We haven’t devoted a chapter to the fifth step, interpreting data, because, quite frankly, the computer, let alone the command line, is of very little use here. We have, however, provided some pointers for further reading on this topic.

In the three intermezzo chapters, we looked at some broader topics of doing data science at the command line, topics which are not really specific to one particular step. In [Chapter 4](#chapter-4-creating-reusable-command-line-tools), we explained how you can turn one-liners and existing code into reusable command-line tools. In [Chapter 6](#chapter-6-managing-your-data-workflow), we described how you can manage your data workflow using a command-line tool called Drake. In [Chapter 8](#chapter-8-parallel-pipelines), we demonstrated how ordinary command-line tools and pipelines can be run in parallel using GNU Parallel. These topics can be applied at any point in your data workflow.

It is impossible to demonstrate all command-line tools that are available and relevant for doing data science. New command-line tools are created on a daily basis. As you may have come to understand by now, this book is more about the idea of using the command line, rather than giving you an exhaustive list of tools.


## Three Pieces of Advice 

You probably spent quite some time reading these chapters and perhaps also following along with the code examples. In the hope that it maximizes the return on this investment and increases the probability that you’ll continue to incorporate the command line into your data science workflow, we would like to offer you three pieces of advice: (1) be patient, (2) be creative, and (3) be practical. In the next three subsections we elaborate on each piece of advice.

### Be Patient 

The first piece of advice that we can give is to be patient. Working with data on the command line is different from using a programming language, and therefore it requires a different mindset.

Moreover, the command-line tools themselves are not without their quirks and inconsistencies. This is partly because they have been developed by many different people, over the course of multiple decades. If you ever find yourself at a loss regarding their mind-dazzling options, don’t forget to use --help, man, or your favorite search engine to learn more.

Still, especially in the beginning, it can be a frustrating experience. Trust us, you will become more proficient as you practice using the command line and its tools. The command line has been around for many decades, and will be around for many more to come. It is a worthwhile investment.

### Be Creative 

The second, related piece of advice is to be creative. The command line is very flexible. By combining the command-line tools, you can accomplish more than you might think.

We encourage you to not immediately fall back onto your programming language. And when you do have to use a programming language, think about whether the code can be generalized or reused in some way. If so, consider creating your own command-line tool with that code using the steps we discussed in [Chapter 4](#chapter-4-creating-reusable-command-line-tools). If you believe your command-line tool may be beneficial for others, you could even go one step further by making it open source.

### Be Practical 

The third piece of advice is to be practical. Being practical is related to being creative, but deserves a separate explanation. In the previous subsection, we mentioned that you should not immediately fall back to a programming language. Of course, the command line has its limits. Throughout the book, we have emphasized that the command line should be regarded as a companion approach to doing data science.

We’ve discussed four steps for doing data science at the command line. In practice, the applicability of the command line is higher for step 1 than it is for step 4. You should use whatever approach works best for the task at hand. And it’s perfectly fine to mix and match approaches at any point in your workflow. The command line is wonderful at being integrated with other approaches, programming languages, and statistical environments. There’s a certain trade-off with each approach, and part of becoming proficient at the command line is to learn when to use which.

In conclusion, when you’re patient, creative, and practical, the command line will make you a more efficient and productive data scientist.

## Where To Go From Here? 

As this book is on the intersection of the command line and data science, many related topics have only been touched upon. Now, it’s up to you to further explore these topics. The following subsections provide a list of topics and suggested resources to consult.

### APIs 

* Russell, Matthew. 2013. <em>Mining the Social Web</em>. 2nd Ed. O’Reilly Media.
* Warden, Pete. 2011. <em>Data Source Handbook</em>. O’Reilly Media.


### Shell Programming 

* Winterbottom, David. 2014. “Commandlinefu.com.” <a href="http://www.commandlinefu.com" class="uri">http://www.commandlinefu.com</a>.
* Peek, Jerry, Shelley Powers, Tim O’Reilly, and Mike Loukides. 2002. <em>Unix Power Tools</em>. 3rd Ed. O’Reilly Media.
* Goyvaerts, Jan, and Steven Levithan. 2012. <em>Regular Expressions Cookbook</em>. 2nd Ed. O’Reilly Media.
* Cooper, Mendel. 2014. “Advanced Bash-Scripting Guide.” <a href="http://www.tldp.org/LDP/abs/html" class="uri">http://www.tldp.org/LDP/abs/html</a>.
* Robbins, Arnold, and Nelson H. F. Beebe. 2005. <em>Classic Shell Scripting</em>. O’Reilly Media.


### Python, R, and SQL 

* Wickham, Hadley. 2009. <em>ggplot2: Elegant Graphics for Data Analysis</em>. Springer.
* McKinney, Wes. 2012. <em>Python for Data Analysis</em>. O’Reilly Media.
* Rossant, Cyrille. 2013. <em>Learning Ipython for Interactive Computing and Data Visualization</em>. Packt Publishing.


### Interpreting Data 

* Shron, Max. 2014. <em>Thinking with Data</em>. O’Reilly Media.
* Patil, DJ. 2012. <em>Data Jujitsu</em>. O’Reilly Media.


## Getting in Touch 

This book would not have been possible without the many people who created the command line and the numerous command-line tools. It’s safe to say that the current ecosystem of command-line tools for data science is a community effort. We have only been able to give you a glimpse of the many command-line tools available. New ones are created everyday, and perhaps some day you will create one yourself. In that case, we would love to hear from you. We’d also appreciate it if you would drop us a line whenever you have a question, comment, or suggestion. There are a couple of ways to get in touch:

- Email: <jeroen@datascienceworkshops.com>
- Twitter: [\@jeroenhjanssens](https://twitter.com/jeroenhjanssens/)
- Book website: <http://datascienceatthecommandline.com/>
- Book GitHub repository: <https://github.com/jeroenjanssens/data-science-at-the-command-line>



<!--chapter:end:10.Rmd-->



<!--chapter:end:12-references.Rmd-->

