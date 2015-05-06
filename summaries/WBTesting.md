% White Box Testing
% Author: Anthony Wittemann
% 6 May 2015

## Overview
- White Box Testing is based on elements in the **CODE**
- **White Box Testing assumes that executing a faulty element is necessary for revealing the fault**


ex:
1. Read P 
2. Read Q 
3. IF P+Q > 100 THEN 
4.    Print “Large” 
5. ENDIF 
6. If P > 50 THEN 
7.    Print “P Large” 
8. ENDIF

## Statement Coverage
Statement Coverage = (# executed statements) / (# statements)






### Memorize this:
- 100% Path coverage will imply 100% Statement coverage
- 100% Branch coverage will imply 100% Statement coverage
- 100% Path coverage will imply 100% Branch coverage


## Questions
- You're a senior software developer at Buber and are mentoring a nuber Buber intern. The intern claims that since his white box tests have 100% statement coverage that his job is done and he can go swimming in the bay with sharks. Should you allow him to go play in the bay with sharks or does he have more work to do? 



**Answer:** Well, the white box testing is incomplete, since 100% statement coverage does not imply 100% branch coverage or 100% path coverage, but since he can't do white box testing correctly you should definately let him make friends with sharks :smiling_imp:

- 
