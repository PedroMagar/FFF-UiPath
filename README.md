### Fast Flow Framework - UiPath ###
**FFF-UiPath**

FFF is a framework for fast RPA development and ease of use in mind.

It follow good pratices of each tool and also keep a good usability and consistency.

### Overview ###
1. **Init**
 + *LoadConfiguration* - Load config data from file and from assets.

2. **Get Data**
 + *Retrieve Data* - Extract base data to work with.
 
3. **Transaction**
 + *Transactions* - Core process automated should be placed here.
    + *Transaction State Machine* - State machine that will contain each step of the process creating a *checkpoint* between each step.
 + *Transitions*
    + *Next Transaction* - Select next transaction by incrementing intTransactionNumber.
    + *Exception* - Any exception (System exception or rule violation) that ocurre during process execution.
    + *End Prcocess* - No more transaction to process or a **Stop** was requested by Orchestrator.
 
4. **Error Handler**
 +  *Get Exception* - Default behaviour to handle exception.
 +  *Next Step* - Check whether it is necessary to continue with the current transaction or skip to the next one.

5. **End Process**
 +  *Final Steps* - Final steps of the process. Ex.: Send an e-mail, writing a log file, closing applications used, etc.

### How to Use ###

This framerwork work on UiPath 19.10 or newer. It is already pre-configured to run a synthetic project to display messages in the log based on an input CSV file.

You can specify the input on Data/Config.xlsx for your desired file, you can also change the "Get Data" state from "Main.xaml" file to get a DataTable from Orchestrator and not from a file.

Chosen your input method, the next step is to open "Transaction" state from "Main.xaml" file and add your input treatment on the sequence "Arrange Input Data". After correctly handling the input, you can start adding each step of the process as a state on the 'Transaction State Machine' linking each one to the next state. Process step can be defiened as every progress during the process before an irrevertible change, this way will be possible to return to the last sucessfull point of a process in case something went wrong or inform correctly where the process stopped.

After the process automation is concluded, you can change the "Error Handler" behaviour to decide what happen when there is an error during the execution, if it should retry the transaction, skip to next or even stop the process.

Lastly you must add on the "End" state from "Main.xaml" the final steps of your automation, normaly in this state you would close used aplications, writing a report and some times even send this report by e-mail.

### 3rd Party Code ###
The file **LoadConfiguration.xaml** comes from **ReFrameWork Template** which is Copyright (c) 2019 UiPath under MIT license.
