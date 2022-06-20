# MAP-independence_Thesis_Simon_Janssen
This repository is used for the thesis project:

### Test-selection strategies to increase the number of MAP-independent variables

The repository consists of multiple files that were used to evaluate the seven different test-selection strategies:
- In-degree
- Out-degree
- Total degree
- Distance to the explanation variable
- Expected utility
- Expected Gini index
- Mutual information

## Simulations
The program that is used in order to run the simulations can be found under the `Simulations_MAP_algorithm.zip` tab. This java program can be used to first randomly partition a Bayesian network into an evidence set with random joint value assignment, an explanation set consisting of one explanation variable and a set of intermediate variables. Subsequently, the program can compute for this Bayesian network the maximal subset of intermediate variables that are MAP-independent and for every variable that is not MAP-independent, it can compute the test-selection strategy values for the in-degree, out-degree, total degree (specific for ALARM network) and the expected utility, expected Gini index and mutual information. The distance in the graph has to be read of from the network itself, as computing this can take a very long time. 

After computing the test-selection strategy values for every intermediate variable that is not MAP-independent, it can be seen which of these variables would be best to observe by computing the expected number of MAP-independent variables that you get when observing the variable. In the end, the variable with the highest expected number of MAP-independent variables would be best to observe.

## Data
The data consists of two files, namely the `Simulation data.csv` and the `Heuristic data.csv`. 

The `Simulation data.csv` file contains general information about a simulation run, which includes:
- The hypothesis variable
- The set of evidence variables (including joint value assignment)
- The size of the evidence set
- The total number of MAP-independent variables
- The best variable to observe if available
- The expected number of MAP-independent variables for the best variable to observe if available

The `Heuristic data.csv` contains the data about the test-selection strategy values for the different variables in a simulation run, including
- The number of the simulation run
- The variable name (for the MAP-dependent variables in the simulation run)
- The in-degree of the variable
- The out-degree of the variable
- The total degree of the variable
- The distance of the variable to the explanation variable
- The expected utility for the variable
- The expected Gini index for the variable
- The mutual information of the variable with the explanation variable
- The expected number of MAP-independent variables that you get when observing the variable
- The current number of MAP-independent variables
- The minimum number of MAP-independent variables for observing a variable to a specific value assignment
- The maximum number of MAP-independent variables for observing a variable to a specific value assignment

## Analysis
The analysis is carried out in python and consists of an `Analysis Simulations.ipynb` file. Using the analysis file, the results of the study can be replicated and the figures can be reconstructed. Both rank-approximation and value-approximation are carried out in this file, as well as gathering some general information from the simulation runs.
