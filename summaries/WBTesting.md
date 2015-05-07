% White Box Testing - Lecture 16
% Author: Anthony Wittemann
% 6 May 2015

## Overview
- White Box Testing is based on elements in the **CODE**
- **White Box Testing assumes that executing a faulty element is necessary for revealing the fault**



## Statement Coverage
**Statement Coverage = (# executed statements) / (# statements)**

See Slides 4 & 5 for Example

## Branch Coverage
**Branch Coverage = (# traversed branches) / (# edges)**
- each condition in a decision takes on all possible outcomes at least once, and each point of entry to a program or subroutine is invoked at least once. That is, every branch (decision) taken each way, true and false. 
- It helps in validating all the branches in the code making sure that no branch leads to abnormal behavior of the application. 

See Slides 7, 8 & 9 for Example

## Basic Condition Coverage
**Basic Condition Coverage = (# boolean values assumed by all basic conditions) / (# boolean values of all basic conditions)**
- full condition coverage does not guarantee full branch coverage
- This metric is similar to branch coverage but has better sensitivity to the control flow

See Slide 11 for Example

## Compound Condition Coverage
Test requirements: All possible combinations of basic conditions
Very thorough, but also very expensive for non-trivial programs.
- :+1: For languages with short circuit operators such as C, C++, and Java, an advantage of multiple condition coverage is that it requires very thorough testing. For these languages, multiple condition coverage is very similar to basic condition coverage.
- :-1: A disadvantage of this metric is that it can be tedious to determine the minimum set of test cases required, especially for very complex Boolean expressions.
- :-1: An additional disadvantage of this metric is that the number of test cases required could vary substantially among conditions that have similar complexity. For example, consider the following two C/C++/Java conditions.

ex1: 
if (a or b) and c then

1. a=false, b=false, c=false
2. a=false, b=false, c=true
3. a=false, b=true, c=false
4. a=false, b=true, c=true
5. a=true, b=false, c=false
6. a=true, b=false, c=true
7. a=true, b=true, c=false
8. a=true, b=true, c=true
 
ex2:
( ( ( ( a || b ) && c ) || d ) && e )

How many test requirements? 

answer: 2^5 = 32

## Path Coverage
- All possible control paths taken, including all loop paths taken zero, once, and multiple (ideally, maximum) items in path coverage technique, the test cases are prepared based on the logical complexity measure of a procedural design. 
- In this type of testing every statement in the program is guaranteed to be executed at least one time. 
- Flow Graph, Cyclomatic Complexity and Graph Metrics are used to arrive at basis path
- Often, faults are revealed only exercising a sequence of decisions (e.g., after many iterations of a loop)
- The **path adequacy criterion** requires each path in the program to be exercised by at least one test case
- The criterion is impractical, even for simple programs
- Therefore, criteria that consider only a subset of paths have been defined

#### Basis Path Coverage
- Requirements: Set of basis paths in the program. Based on the concept of cyclomatic complexity, which is the number of independent paths in the basis set (paths as vectors)

#### Loop Coverage
- All paths that contain at most **n** iterations of any loop in the program
- Problem is: for what value of **n**?

## Data Flow Coverage
- Basic idea: Test definitions (d) and uses (u) of variables
- Test requirements: sets of du-pairs with respect to variable v
 * a definition of v is a reference to v where the value of v is changed (e.g., assignment to v, input a value of v)
 * a use v is a reference to v where the value of v is fetched but not changed (e.g., v on right-hand side of assignment, v is output)
 * a def-clear subpath for a definition d of v and a use u of v is a subpath in the CFG between d and u on which v is not redefined


### Memorize this:
- 100% Path coverage will imply 100% Statement coverage
- 100% Branch coverage will imply 100% Statement coverage
- 100% Path coverage will imply 100% Branch coverage


## Questions
- :question: You're a senior software developer at Buber and are mentoring a nuber Buber intern. The nuber explains that for his complex program that took him 2 weeks to write, he has a super simple statement coverage which he claims is 1. Is he right?

### nuber's Program
1. Read P 
2. Read Q 
3. IF P+Q > 100 THEN 
4. Print “Large” 
5. ENDIF 
6. If P > 50 THEN 
7. Print “P Large” 
8. ENDIF

![Image of Flowchart](https://07871e11-a-62cb3a1a-s-sites.googlegroups.com/site/swtestingconcepts/home/test-design-techniques/for-white-box/statement-branch-and-path-coverage/coverage.png?attachauth=ANoY7cqyyxk7aKq7Aef_wn0PIYBnu-zq7op9KjZbf6muaEUIF2jRETZ485N1ctKQbq16h-4nhNLkpTClgRE-mdvYDaJFSY-x2YgGoul33OlHToHd_3eCnFIoeDbcl2n1n6DZyCVwHGw3iCVuA7kSd1P3S5O-pP1x-Gr6YO-RfZFuPMOeYt70AIYEpvByIk5gtjWYd_gQwY8QH6npmThLPBKe7WB7nokpbAwqMHQ-EHlEkMKP_wp6MBsdIJTTzX8XFmYtpmujGXeXqQe4Y3xIS9N1ZR4b_rhs88ANCp7COVPS7OX_k-zAlFBlFLCmkISnxqEn5UkORXHrFU0OWwXzPmT5S9SiL2HSYA%3D%3D&attredirects=0)

- **Answer:** To calculate Statement Coverage, you find out the shortest number of paths following 
which all the nodes will be covered. Here by traversing through path 1A-2C-3D-E-4G-5H all 
the nodes are covered. So by traveling through only one path all the nodes 12345 are covered, 
so the Statement coverage in this case is 1. Turns out the intern is right:exclamation: 

- :question:  The intern claims that since his white box tests have 100% statement coverage that his job is done and he can go swimming in the bay with sharks. Should you allow him to go play in the bay with sharks or does he have more work to do? 


- **Answer:** Well, the white box testing is incomplete, since 100% statement coverage does not imply 100% branch coverage or 100% path coverage, but since he can't do white box testing correctly you should definately let him make friends with sharks :smiling_imp:

- :question: After a plunge in the cold bay water :ocean:, the nuber Buber intern now realizes that branch coverage and path coverage are also important. In an effort to redeam himself, he finds a branch coverage of 2 and a path coverage of 3. He now claims that he has 100% coverage for Statement, Branch and Path Coverage. Has he redeamed himself?


- **Answer:** To calculate Branch Coverage, you need to find out the minimum number of paths which will 
ensure covering of all the edges. In this case there is no single path which will ensure coverage of all the edges in one go. By following paths 1A-2C-3D-E-4G-5H, maximum number of edges (A, C, D, E, G and H) are covered but edges B and F are left. To covers these edges we can follow  1A-2B-E-4F. By the combining the above two paths we can ensure of traveling through all the paths. Hence Branch Coverage is 2. The aim is to cover all possible true/false decisions. Well Done intern :ok_hand:

Path Coverage ensures covering of all the paths from start to end.
All possible paths are:
* 1A-2B-E-4F
* 1A-2B-E-4G-5H
* 1A-2C-3D-E-4G-5H
* 1A-2C-3D-E-4F
 
 
So path coverage is 4, not 3. Silly intern :koala:

