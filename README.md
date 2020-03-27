# Pleak Leakage Detection analysis

## Prerequisites

You need to locate [pleak-backend](https://github.com/pleak-tools/pleak-backend), [pleak-frontend](https://github.com/pleak-tools/pleak-frontend) and [pleak-pe-bpmn-editor](https://github.com/pleak-tools/pleak-pe-bpmn-editor) directories all in the same directory. Specify names for the first three modules in the config.json file.
Read more from sub-repositories how to build each module.

To use Leakage Detection analyser, install:

[mCRL2](https://www.mcrl2.org/web/user_manual/download.html)

## Using

You can use the analyser through [Pleak PE-BPMN editor](https://github.com/pleak-tools/pleak-pe-bpmn-editor). Validate the model and if it is correct, run "Leakage detection" analysis.

Or run the jar file:
- insert the path of the file ".bpmn" that you want to analyze
- insert the number corresponding to one of the following actions:
  - 1 -> to check if a task T knows about a set of data D
    - a list of ID-task and NAME-task is displayed: insert only the ID of the chosen one
    - a list of data is diplayed: insert one or more name (divede by the comma) 
  - 2 -> to check if a participant P knows about a set of data D
    - a list of  ID-participant and NAME-participant is displayed: insert only the ID of the chosen one
    - a list of data is diplayed: insert one or more name (divede by the comma)
  - 3 -> to verify if secret sharing/ additive secret sharing / function secret sharing protocol is violated or not
  - 4 -> to verify if it's always possible to RECONSTRUCT a secret
  - 5 -> to verify if private key / symmetric key encryption is violated or not
- output:
  - false, if the property is not satisfied, i.e. task T or participant P doens't know about the set of data D or secret sharing is NOT violated
  - true, property is satisfied, i.e. task T or participant P knows about the set of data D or secret sharing is violated. The path leading to the satisfication of the property is printed out.
  
To have a look about the files generated during the analysis go to the folder ".../result_FSAT" before starting a new analysis, i.e. before answering the question "continue(Y/N)", since all the files are deleted at each iteration.


   
