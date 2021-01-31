This repository contains the code to generate and simulate the models described in Tarit Konuntakiet's DPhil thesis on integrated modelling of whole-plant metabolism and growth, completed at the University of Oxford, UK in 2021. A full copy of the thesis can be obtained from http://ora.ox.ac.uk/. Two different whole-plant metabolic models of growth are presented in the thesis, FM-SoFBA-SiFBA and WholePlantMetabolism. 

### FM-SoFBA-SiFBA

This model runs in MATLAB and can be executed by using the following command: `[ShootFreshWeight] = frameworkmodel(data_set);`. Set `data_set` as `1` to simulate the growth and environmental conditions described in the thesis. The command returns shoot fresh weight predictions over the growth period. Note that the simulation may not proceed if the COBRA Toolbox has not been initialised yet by executing `initCobraToolbox`.

### WholePlantMetabolism

Two model versions of WholePlantMetabolism are presented in the thesis. In its current veriosn, WholePlantMetabolism is parameterised for growth in tomato plants (v1 for vegetative growth and v2 for reproductive growth) and runs in Python 3.

For WholePlantMetabolism v1 (contained in the [WholePlantMetabolis_v1 folder](WholePlantMetabolism_v1), key model parameters can be retrieved from [parameters.csv](WholePlantMetabolism_v1/parameters.csv). Organ-specific biomass data is stored in [tomatoBiomassEquations.csv](WholePlantMetabolism_v1/tomatoBiomassEquations.csv). To simulate plant growth using WholePlantMetabolism v1, execute the code in [WholePlantMetabolism.py](WholePlantMetabolism_v1/WholePlantMetabolism.py), which returns leaf, stem, and root mass predictions as csv files in the [Output folder](WholePlantMetabolism_v1/Output). Metabolic flux predictions can also be returned by specifying the days of interest in days after sowing as a numpy array using the `outputCycle` attribute of the `plantMainCopy` class in [WholePlantMetabolism.py](WholePlantMetabolism_v1/WholePlantMetabolism.py).

For WholePlantMetabolism v2 (contained in the [WholePlantMetabolis_v2 folder](WholePlantMetabolism_v2), model parameters contained as csv files in the [Parameters folder](WholePlantMetabolism_v2/parameters). In addition to parameter files contained in WholePlantMetabolism v1, the extended model version also contains files listing dyanmic fruit biomass composition ([fruitBiomassComposition.csv](WholePlantMetabolism_v2/fruitBiomassComposition.csv)) and tomato shoot phytomer structure ([tomMask.csv](WholePlantMetabolism_v2/tomMask.csv)). Growth in WholePlantMetabolism v2 can be simulated by executing the code in [WholePlantMetabolism.py](WholePlantMetabolism_v2/WholePlantMetabolism.py), which returns growth predictions as outputs to the [Output folder](WholePlantMetabolism_v2/Output).
