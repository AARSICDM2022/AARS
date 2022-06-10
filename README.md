# AARS
## Install

Follow these steps:

1. Make sure you have a recent C++ compiler with support for C++14.
2. Make sure you have `cmake` 2.8 or newer.
3. Enter AARSICDM2022 root directory.
4. Invoke `build.sh`

The source codes are implemented in C++14 and it can be compiled using any standard-conforming compiler.

Installation Examples:

* Installing : `bash build.sh or ./build.sh`
* Compiling for debugging: edit `build.sh` and add `-DCMAKE_BUILD_TYPE=Debug` to the `cmake` call.
* For separate building please remove other ADD_SUBDIRECTORY () from CMakeLists.txt in root directory then build and run.
	a. For example, we want to build only Test Example, then we have to keep ADD_SUBDIRECTORY(TestExample) in line number 44 and remove line 45, 46, 47.
	b. Then type "bash build.sh" without qoutes. 
	c. Similarly, we have to do for RANDOM, BNSL( Baysian Network Structure Learning), ARM (Association Rule Mining).

## Example
	1. For testing AARS in Test Example folder.
		* If we want to change data name in line 48, data size in line 47, parent set in 59 and child in 61 then please again build after change.
		* Results will be shown in terminal screen.
	2. For testing Random in SourceCodeForRandomQueries.
		* We have use three types of query files (i.e., alarm.txt (1K queries) , Qalarm.txt(100K queries) and Qalarm_qv1.txt(1M queries)) in the query folder.
		* We test Qalarm.txt(100K queries) where size of the parent variables are incresing after 5260 queries up to 15. To test this please set the line no 60 in RANDOM_AARS.cpp accordingly and then build. Please set pasize = 15 in line no 4 in testRandom.sh and run.
		* We have also test Qalarm_qv1.txt where qv1 means number of parent variable in the parent set in 1 (one). To test this please set the line no 61 in RANDOM_AARS.cpp accordingly. Please set pasize = 1 in line no 4 in testRandom.sh because for this test program wil ignore this valueand run.
		* Last number in each line in any query files indicates child variable.
	3. For testing BNSL in SourceCodeForBNSL. 
		* To see the average performance in BNSL please set learning limit "LrnLimit> 1" in line no. 55 in "BNSL_AARS.cpp" and build. Similar changes are required for others.
	4. For testing ARM in SourceCodeForARM.
		* Please set "MinSupport" and "MinConfidence" accordingly.
## Experimental Results
	1. Results will be write in csv file in particular folder (i.e., RANDOM, BNSL, ARM) in the output folder.
	2. We have also given obtained results in csv files. And all statistics in excel file.
	3. In "RANDOM" folder, there are three different folder namely "ResultsOf1Kqueries", "ResultsOn100Kqueries" and "Results_Of_100K_Queries_Incresing_parentsetsize".
	4. We have reported statistics in Figure 3 and Table 1 in the main submited paper given in "ResultsOf1Kqueries".
	5. We have mentioned about 100K queries in Experiment 1 in Experimental section. The results are given in folder "ResultsOn100Kqueries".
	6. We have shown results in Table 1 with incresing parentset variable in supplementary materials (SM) are given in folder "Results_Of_100K_Queries_Incresing_parentsetsize".
	7. In "BNSL" folder, Results of Table 3 in submitted paper are given.
	8. In "ARM" folder, Results of  Figure 4 in submitted paper and Table 3 in SM are given.
	9. All execution time are recorded in microseconds. but reported in seconds(Sec.) in the main paper. In SM, execution time is also shown in hh:mm:ss in Table 1.
	10. For memory, we have noted "Maximum resident set size" wil be shown in the terminal screen. 
	11. Null values in csv or excel files is indicates aproaches could be executed due to longer time or error signals on particular datasets.
	
## Datasets
	* We have used eight different datasets i.e., alarm, barley, child, hailfinder, mildew, pathfinder, win95pts for random test and BNSL
	* For ARM, we have used binary version of these datasets.
	* These datasets with different instances (i.e., 1K, 10K, 100K, 1M, 10M) are in the datafolder.

	


	
		
