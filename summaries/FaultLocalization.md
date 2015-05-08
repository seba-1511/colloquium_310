% Fault Localization
% Author: Justine Cocchi
% 7 May 2015

# Overview
Fault localization aims to figure out which specific parts of your code caused tests to fail down to the exact faulty line of code.
Because fault localization is an expensive (in both time and money) and mostly manual process, it is important to use the proper tools to locate faults, hence Tarantula emerged as the best technique.

# Important Concepts

## Current Fault Localization Techniques: *slide 2*
Current fault localization techniques are very labor intensive and not governed by a strict process.

* Run through failed test with debugger
* Comment out chunks of code until you find the broken section
* Output certain variables and comments to mark progression through program

## Tarantula: *slide 4*
Statements that are primarily executed by failed test cases are more suspicious than statements that are primarily executed by passing test cases. However, suspicious lines can be executed by passing tests and correct lines can be executed by failed ones in moderation.
Since this technique ignores the data dependency, it is hard to find the bugs which are not in the suspicious code area but have data dependence with it. Essentially, if the test doesn't cover code that contains a fault, then Tarantula can't find it.

#### Common Uses: *slide 5*
* Nightly-build process
* Test-driven development
* Regression Testing

#### Process: *slide 7*
* Instrument program to measure coverage
* Record coverage for each test case
* Record pass/ fail for each test case
* Calculate suspiciousness of each statement
     * suspiciousness(s) = (failed(s) / total failed) / ((passed(s) / total passed) + (failed(s) / total failed))
* Rank suspicious statements 
     * After you find and fix a fault, run test suite again and recalculate to find new most suspicious statement
     * Repeat until all tests pass

See slides 8-16 for an example. 

## Metrics for Evaluating Fault Localization: *slide 17*

#### Empirical Study: *slides 17-18*
The subjects of the study are listed in the table on slide 17. They come from Siemens suite, a commonly used testing suite for comparing fault localization techniques. This means when you calculate the percentage of code examined to find the fault, you can easily compare to other fault localization techniques to measure effectiveness.

See slides 20 and 21 for graph of effectiveness of Tarantula compared to the ideal and worse cases.

#### Visualization *slide 22-27*
Color summarizes pass/fail results of test cases that executed.

* Statment level
* File level
* System level


# Exam Questions

* What is the overarching goal of fault localization?
* What are the drawbacks of current fault localization techniques? 
* Describe the Tarantula process.
* How do you calculate the suspiciousness of a line of code in Tarantula?
* What are two of the most important things you need for Tarantula to work? 
* How do you calculate the percent of program examined to find each fault?