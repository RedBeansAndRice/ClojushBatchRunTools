# ClojushBatchRunTools
currently runs each of Tom Helmuth's default 12 GP problems on a list of parent selection arguments

command syntax = python McFly_launcher.py BatchTag numberOfRuns parentSelectionMethod1 parentSelectionMethod2 .. etc.

where batchTag is just any helpful tag you want to include to keep track of this group of runs, numberOfRuns is the number of Runs per
each combination of parameters and parentSelectionMethods are formatted in the manner typical of clojush (:'s not included) i.e. Lexicase, TemperedLexicase, LWLexicase

so
lein run clojush.problems.software.double-letters :parent-selection :Lexicase
lein run clojush.problems.software.double-letters :parent-selection :LWLexicase
lein run clojush.problems.software.double-letters :parent-selection :TemperedLexicase
... 42 times for each problem (or a runfly equivalent)

or 36 calls to

python fly_launcher.py

after setting the number of runs, problem, parent selection method and output directory each time

becomes

python McFly_launcher.py BatchTest1 42 TemperedLexicase LWLexicase Lexicase

Currently root of output directory is configured in the script (so it will go to my files if you dont change it)

Plan to add greater flexibility for different clojush arguments and adjusting the list of problems that are included in the batch
