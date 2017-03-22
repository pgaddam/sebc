####1 Plug the hardware numbers for your cluster into the spreadsheet
* Updated the spreadsheet

####2 Inspect the derived/default values. Adjust as necessary
* Reduced OS level Memory usage for given configuration. 10% of available 256 GB RAM is alot of OS level activities. So, reduced it to 1% to maximize the availabilty of memory for Yarn.

####3 What criteria affects workload factor? What does a value of 1, 2, or 4 signify?
* Workload is defining the intesity and resources expected for workload items. Byt changing this value its effecting the parallel processing of the by either increading or decreasing the mappers and reducers that we can used for the job