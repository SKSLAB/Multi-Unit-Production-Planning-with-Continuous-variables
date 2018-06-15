# Multi-unit production planning with continuous variables
##### An optimization test suite involving 1287 and 2624 continuous variables

This submission can be used to evaluate the performance of optimization techniques on problems with large number of continuous variables. This optimization problem arises for maximization of Profit in Production Planning. However these files can be used as black-box optimization problems.

There are eight minimization optimization problems in this suite (case1.p, case2.p, case3.p, case4.p, case5.p, case6.p, case7.p and cas8.p).

Each of them has the following format
```
[ F, XCorrected] = case1(X);
```
Input: 
	population (or solution, denoted by X) and its <br />
Output: 
	(i) the corrected population (denoted by XCorrected), and <br />
	(ii) the objective function value of the corrected population members (F). X is corrected to XCorrected as most algorithms fail to satisfy the complex constraints and XCorrected is not worse to X.

The file ProblemDetails.p can be used to determine the lower and upper bounds along with the function handle for each of the cases.

The format is `[lb, ub, fobj] = ProblemDetails(ca);`

Input: 
	ca is an integer from 1 to 8.<br />
Output: 
	(i) the lower bound (lb), <br />
	(ii) the upper bound (ub), and <br />
	(iii) function handle (fobj).

The file Script.m shows how to use these files along with an optimization algorithm (SanitizedTLBO).

Case 1, Case 2, Case 5 and Case 6 have a problem dimension of 1287 continuous variables whereas 
Case 3, Case 4, Case 7 and Case 8 have a problem dimension of 2624 continuous variables.

**Note:** <br />
  1. The inbuilt optimization algorithms in MATLAB require that the objective function file return only the values of the objective function and cannot be directly used to solve these problems.

  2. Conventionally, the algorithm provides X and requires F. But in these problems, in addition to F, XCorrected is provided by the objective function file.

  3. The current best known solutions (rounded to two decimals), using computational intelligence algorithms, are<br />
  Case 1: -683.03; Case 2: -820.49; Case 3: -1024.56; Case 4: -1292.25 <br />
  Case 5: -714.29; Case 6: -823.65; Case 7: -1118.28; Case 8: -1420.48 
  4. Case 1 - 4 have the same problem structure but employ different data; Case 5 - 8 has same set of data as compared to Case 1 - 4, but do not employ a certain feature (flexible) of the problem.<br />
  5. The objective function files are capable of determining the objective function values of multiple solutions (i.e., if required, the entire population can be sent to the objective function file).

**Reference:** Sandeep Singh Chauhan, Prakash Kotecha,An efficient multi-unit production planning strategy based on continuous variables, Applied Soft Computing,2018,ISSN 1568-4946, 
https://doi.org/10.1016/j.asoc.2018.03.012.