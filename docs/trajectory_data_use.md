# Trajectory Data Use

For every video analyzed, there are also two csv files for the separated living and dead trajectories in the [trajectory_data](../trajectory_data) folder. 

To use these csv files in your code, they need to be reformatted slightly to match the results of trackpy tracking. I find that this is helpful when trying to use this with other trackpy functions. The code below will import the csv file as a Pandas dataframe and reformat to match the trackpy results:

```
df = pd.read_csv('mtb-group/trajectory_data/living-dead_filename.csv', index_col=["frame", "index"])
df.rename(columns={'frame.1': 'frame'}, inplace=True)
```

The second classifier code file [classify.ipynb](../living-dead/classifier/classify.ipynb) includes code at the end to save separated living and dead data into csv files.
