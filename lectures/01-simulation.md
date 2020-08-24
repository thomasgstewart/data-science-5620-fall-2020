<!-- <style> -->
<!-- blockquote { -->
<!-- background-color: #a6bddb50; -->
<!-- font-family: "helvetica"; -->
<!-- font-size:110%; -->
<!-- } -->
<!-- blockquote li{ -->
<!-- padding-bottom:10px; -->
<!-- } -->
<!-- svg { -->
<!-- width:none; -->
<!-- height:none; -->
<!-- } -->
<!-- </style> -->
Simulation
==========

**Simulation** is repeated execution of a procedure --- usually by computer --- in order to understand the characteristics of the procedure.

Example
-------

What is the probability that at least one birthday is shared in a class of 30 individuals?

``` r
generate_class <- function(class_size){
  birthdays <- sample(1:366, class_size, replace = TRUE, prob = c(rep(1,365), .25))
  data.frame(student_id = 1:class_size, birthday = birthdays)
}

check_birthday <- function(class){
  class_summary <- class %>% 
    summarize(n = n(), n_bday = n_distinct(birthday)) %>% 
    mutate(shared = n > n_bday)
  class_summary[["shared"]]
}

replicates <- replicate(10000, 30 %>% generate_class %>% check_birthday)
mean(replicates)
```

Example
-------

What is the distribution of *runs* is a sequence of 100 flips of a fair coin?

Operating characteristic
========================

Key properties of a procedure are often called **operating characteristics**. Generally, one wants to know the *distribution* of an operating characteristic over repeated executions of the study.

Operating characteristics are the currency by which we evaluate and compare data science procedures.

Examples/Questions
------------------

1.  A data scientist claims to have developed a tool to identify college freshman that are highly likely to join the armed forces. What operating characteristics would you like to know about the tool?

2.  A data scientist develops an algorithm for estimating the probability that a credit card transaction is fraudulent or not. What operating characteristics are important?

Operating characteristics are premised on the classic "long-run" interpretation of probabilistic events. As such, they can be simulated by simply repeating the planned procedure and observing how often some event happens.

General advice for computing tasks
==================================

So you want to perform a simulation study? Start with the tgs axioms of computing:

1.  **The act of turning on the computer does not magically endow you with understanding of your task.** If you do not know how you will perform an analysis or simulation before you turn on your computer, you will not know how to do it afterwards either.

2.  **Use modular/functional programming.** Functional programming means that you identify and write short, single purpose functions for each distinct task in your program. (Examples below.) This will allow you to develop your code in a systematic way, and it will provide a natural method for debugging your code. You will simply need to verify that the different sub-functions are working as expected.

The big picture of simulation studies for stochastic processes
==============================================================

In a setting where one is trying to understand a random process, there are population parameters that one hopes to estimate by collecting and analyzing data. The population parameters are unknown, and the accuracy of the conclusions is unknown.

![](./assets/b2.svg)

The big picture of simulation studies for inference
===================================================

In a typical data analysis setting, there are population parameters that one hopes to estimate by collecting and analyzing data. The population parameters are unknown, and the accuracy of the conclusions is unknown.

![](./assets/a.svg)

In a simulation setting, the researcher sets the population parameters then generates data using the parameters. After completing the analysis, the researcher can then evaluate the accuracy of the conclusions. By repeating this process several times, the researcher can estimate the operating characteristics for *the specific set of population parameters used to simulate the data*.

**Caveat emptor:** Simulations are essentialy computational proofs on a case-by-case basis (e.g., this result happens for this parameter set, that result happens for that parameter set). It is up to you make the conneciton between different settings, notice patterns, and make a case for general patterns of behavior under certain circumstances. Simuations lack the natural generalizibiltiy of a mathematical proof, so the results don't necessary hold for all sets of parameter values.

![](./assets/b.svg)

The framework described above suggests how one may write modular code to perform the simulation. One can write a function to perform each of the primary tasks. For example:

![](./assets/c.svg)
