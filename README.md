### Fast Flow Framework - UiPath ###
**FFF-UiPath**

FFF is a framework for fast RPA development and ease of use in mind.

Despite following good pratices, it's not following the best pratices of each tool. Usability and consistency were prioritize.

### Overview ###
1. **Init**
 + *LoadConfiguration* - Load config data from file and from assets

2. **Get Data**
 + *Retrieve Data* - Extract base data to work with
 
3. **Transaction**
 + *Transitions*
    + *Next Transaction* - Select next transaction by incrementing intTransactionNumber
    + *Exception* - Some exception (System exception or rule violation) ocurred during the process
    + *End Prcocess* - No more transaction to process or a **Stop** was requested by Orchestrator
 
4. **Error Handler**

5. **End Process**

### How to Use ###

### 3rd Party Code ###
The file **LoadConfiguration.xaml** comes from **ReFrameWork Template** which is Copyright (c) 2019 UiPath under MIT license.
