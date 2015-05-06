% White Box Testing
% Author: Anthony Wittemann
% 6 May 2015

## Overview
- White Box Testing is based on elements in the **CODE**
- **White Box Testing assumes that executing a faulty element is necessary for revealing the fault**

### Example Program
1. Read P 
2. Read Q 
3. IF P+Q > 100 THEN 
4. Print “Large” 
5. ENDIF 
6. If P > 50 THEN 
7. Print “P Large” 
8. ENDIF

![Image of Flowchart](https://07871e11-a-62cb3a1a-s-sites.googlegroups.com/site/swtestingconcepts/home/test-design-techniques/for-white-box/statement-branch-and-path-coverage/coverage.png?attachauth=ANoY7cqyyxk7aKq7Aef_wn0PIYBnu-zq7op9KjZbf6muaEUIF2jRETZ485N1ctKQbq16h-4nhNLkpTClgRE-mdvYDaJFSY-x2YgGoul33OlHToHd_3eCnFIoeDbcl2n1n6DZyCVwHGw3iCVuA7kSd1P3S5O-pP1x-Gr6YO-RfZFuPMOeYt70AIYEpvByIk5gtjWYd_gQwY8QH6npmThLPBKe7WB7nokpbAwqMHQ-EHlEkMKP_wp6MBsdIJTTzX8XFmYtpmujGXeXqQe4Y3xIS9N1ZR4b_rhs88ANCp7COVPS7OX_k-zAlFBlFLCmkISnxqEn5UkORXHrFU0OWwXzPmT5S9SiL2HSYA%3D%3D&attredirects=0)

## Statement Coverage
Statement Coverage = (# executed statements) / (# statements)


## Branch Coverage
Branch Coverage = (# traversed branches) / (# edges)


## Basic Condition Coverage
Basic Condition Coverage = (# boolean values assumed by all basic conditions) / (# boolean values of all basic conditions)
- full condition coverage does not guarantee full branch coverage
- This metric is similar to branch coverage but has better sensitivity to the control flow


## Compound Condition Coverage
Test requirements: All possible combinations of basic conditions
Very thorough, but also very expensive for non-trivial programs.
- For languages with short circuit operators such as C, C++, and Java, an advantage of multiple condition coverage is that it requires very thorough testing. For these languages, multiple condition coverage is very similar to basic condition coverage.
- A disadvantage of this metric is that it can be tedious to determine the minimum set of test cases required, especially for very complex Boolean expressions.
- An additional disadvantage of this metric is that the number of test cases required could vary substantially among conditions that have similar complexity. For example, consider the following two C/C++/Java conditions.


### Memorize this:
- 100% Path coverage will imply 100% Statement coverage
- 100% Branch coverage will imply 100% Statement coverage
- 100% Path coverage will imply 100% Branch coverage


## Questions
- You're a senior software developer at Buber and are mentoring a nuber Buber intern. The intern claims that since his white box tests have 100% statement coverage that his job is done and he can go swimming in the bay with sharks. Should you allow him to go play in the bay with sharks or does he have more work to do? 



**Answer:** Well, the white box testing is incomplete, since 100% statement coverage does not imply 100% branch coverage or 100% path coverage, but since he can't do white box testing correctly you should definately let him make friends with sharks :smiling_imp:

- 
