# M to ME keff mapping and validation against proteomics data
Scripts to map keffs using iML1515 to iJL1678b keffs. This repository contains all of the resources necessary to reproduce the simulations from ["Machine learning applied to enzyme turnover numbers reveals protein structural correlates and improves metabolic models"](https://www.nature.com/articles/s41467-018-07652-6?WT.feed_name=subjects_machine-learning)

The simulated models are then compared (by mass or mole fraction) against the proteomics data from ["The quantitative and condition-dependent Escherichia coli proteome"](https://www.nature.com/articles/nbt.3418) 

To run the relevant simulations and validations clone the repository and run:

```python
python run_all_keff_simulations_and_validations.py
```

this will use solve using gurobi v8.1 in low precision, to use qminos edit the solver argument in `maximize_growth_rate` in `run_all_simulations_and_validations.py` to:

```python
run_simulations.maximize_growth_rate(model, media, simulation_savefile_name, solver='qminos', precision=1e-12)
```

## Dependencies
- Python 3.6
- COBRApy - v0.5.11
- [COBRAme](https://github.com/SBRG/cobrame) - v0.0.9
- [ECOLIme](https://github.com/SBRG/ecolime) - v0.0.9
- [solvemepy](https://github.com/SBRG/solvemepy) - v1.0.1
- matplotlib
- pandas
- numpy
- gurobi v8.1 or qminos
