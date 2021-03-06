# ABM-FGCM
## Model Flow
![image](https://github.com/Jian-SiangHong1038/ABM-FGCM/blob/master/Model%20Flow.png)
## Platform
TAMU HPRC Terra

## Version
1. Python 3.7.2
2. networkx/2.3-intel-2019a-Python-3.7.2
3. libspatialindex/1.8.5-GCCcore-8.2.0 
## Usage

```python
$ source env/bin/activate            # Activate virtual environment 
(Command line should show environment name on left)
```

```
$ module load libspatialindex/1.8.5-GCCcore-8.2.0          
$ module load networkx/2.3-intel-2019a-Python-3.7.2			   
```
#### Example
```
python main.py
```
## Input File
1. ABM for infected model (SEIR model)
    1. TX_Counties.geojson
        1. Population
        2. geometry data
    2. TX_prob.csv
        1. Mobility probability
2. FCM
    1. testCase.txt
        1. Node names
        2. Node values
            - C1 is the ratio of infected individuals in the area
            - C2 is the ratio of recovered individuals in the area
        3. Edge values

## Output File
file at `/SimulationResults/OutputData/`

1. CP (short for City Population): This pandas dataframe maintains the entire state of the city, including health of each agent and its permanent list of contacts. It can be accessed by tests as well as intervention policies. A row of CP is an agent and a column is an attribute, e.g., "id".

2. TestingHistory: This is a numpy array which maintain the test status of each agent (row) on each day (column). Agents that test positive on a day are marked +1, those that test negative are marked -1, and those that are not tested are marked 0.

3. InterventionHistory: This is a list which contains all the interventions applied till date.

## References
1. [ANALYZING AND SIMPLIFYING MODEL UNCERTAINTY IN FUZZY COGNITIVE MAPS](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8247923 "Title") 
2. [How Reliable are Test Numbers for Revealing the COVID-19 Ground Truth and Applying Interventions?](https://arxiv.org/abs/2004.12782 "Title")
3. [Individual Decision Making Can Drive Epidemics: A Fuzzy Cognitive Map Study](https://ieeexplore.ieee.org/document/6475999 "Title")
