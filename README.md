# MLCHECK-formalise
A repository containing a [link](https://figshare.com/s/2071cc68a5a39c1b881d) to the code and data to reproduce the results of the paper "Property-Driven Testing of Black-Box Functions" published in FormaliSE-2022.



## VM
This artifact contains a single VM file named formalise. As in Github we could not upload the VM file due to its large size. You can find the VM [here.](https://figshare.com/s/2071cc68a5a39c1b881d) 
This VM is prepared by using Oracle VirtualBox. You can download VirtualBox from here: https://www.virtualbox.org/

Assuming that you have successfully installed VirtualBox or is already installed in your machine, first of all, you need to import the VM in VirtualBox. This you can do either by double clicking on the VM formalise or by going to File -> Import Appliance and then add the VM.
Below are the specifications of the VM formalise.

General: Ubuntu 20.04 64-bit
System: Base memory 15 GB, 3 CPU
Storage: SATA 80.00 GB
username: formalise
password: formalise


## Running the experiments

Once you have successfully opened the VM, the next step is to reproduce results. For this, you have to first go to ~/home/ folder. There you should see two folders named Table3nd5 and Table4. Next, we describe how to reproduce the results for Table 3, 4, and 5 from the paper.

### Results for Table 3 and Table 5
Please note that, due to high number of test cases (a test case is: an aggregation function/model + a property), and due to longer execution time, we do not provide the results for the entire Table 3 and 5. Instead, we provide a subset of the results presented on the paper. Please run the following commands to reproduce the results:

```
(base) formalise@formalise-VirtualBox:~$ cd Table3nd5/
(base) formalise@formalise-VirtualBox:~/Table3nd5$ python AggregationFunctions.py  
```
After running the command, some warning messages will show regarding cuda in tensorflow. This warning can be ignored as cuda is not needed in our framework. Then it would ask you for an input:
'Do you want to run a short or a long version?:'

Now if you give 'short' as input and enter, then it would run for approximately 20-25 minutes and will produce the results in Table3_Results.csv and also in Table5_results.csv file. In file Table3_Results.csv you should see a table like Table 3 presented on paper. All the entries except the entry of 3\Pi (last column) have the values N/N, which implies the other cases have not been evaluated. Therefore, the short version will show you the result like in the paper only for 3\pi and for the properties from str.mon. till intern.. You will also see a similar output in Table5_results.csv file which would correspond to Table 5 from the paper.

If you give 'long' as the input and enter, then the program would run a significantly long time (approximately 3 hours) and will produce the results for Min, Max, Mid, S_{p} and 3\pi and for the properties from str.mon. till intern..Except for these entries, the other entries would show N/N values as they have not been computed. The results will be stored in Table3_Results.csv and Table5_results.csv same as before.
 

### Results for Table 4

Due to the same reasons, we do not provide all the results presented in Table 4 in the paper. Please run the following the commands to reproduce the results:
```
(base) formalise@formalise-VirtualBox:~$ cd Table4
(base) formalise@formalise-VirtualBox:~/Table4$ python RegressionModel.py
```
When the tool will start running, some warning messages will appear which can be ignored. Again, it will ask whether 'short' or 'long' version to run. If you wish to run the short version then it will reproduce the results for DeepSet model for all the properties in Table 4. This version will run approximately 45-50 minutes to complete. 

If you opt for the longer version, then the program will run for approximately 2 hours and produce the results for LAF and DeepSet models and for all the properties. The other cells will contain N/N values as mentioned before.  


Please remember that, during the execution of the framework, some intermediate files will be generated. This is expected.

We attach a screenshot of the Table3_Results.csv, Table4_Results.csv and Table5_results.csv to show how those would look like after running the code.


## IMPORTANT 

All the experiments performed in the paper are run 10 times to obtain the final results. This is done to avoid randomness in our experimental results. But running the experiments 10 times would take a significantly long time with extensive hardware resources. Therefore, here we only provide the code which execute the test cases only once.

The code provided and the test cases are chosen so that the randomness can be minimized as much as possible. 
But still, after that, some randomness in our tool and in the computation of test cases persist. Hence, there can be some discrepancies in the exact results presented in Table 3, 4 and 5 on paper. Specifically, you could see it in Table 5 where the no. of retrainings are taken as average over 10 runs. Please consider this fact while reviewing our artifact.

If you need to interrupt the execution of the artifact by pressing ctrl+c, then before starting new execution, please at least remove assumeStmnt.txt and assertStmnt.txt. Otherwise it will start to give you errors.


### Tip
Due to small window size of the VM, you might have problem opening the .csv file completely. Once you open the .csv file partially, you can press enter which will enable you to open it in a full screen mode.















   
