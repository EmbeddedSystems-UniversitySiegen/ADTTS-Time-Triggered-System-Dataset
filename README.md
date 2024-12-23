# Time-Triggered-System-Dataset
Dataset for EPM
这个数据集组是由一个基于多核时间触发调度系统的自动驾驶仿真任务生成的。它们主要用于时间触发系统中的事件预测任务和相关属性预测任务。数据集的名称为它的生成时间。我们的论文中的模型是基于2024.07.15 15h29m36s数据集训练的。欢迎引用我们的论文：。

- [Get Dataset Quickly](#get-dataset-quickly)
- [Files](#files)

 
# Get Dataset Quickly

```python
import numpy as np
# Please use the dataset path after unziping
datasetPath = "<the dataset path>"

# obtian 5 sub-datasets from subdataset.npz file
subdatasetPath = os.path.join(datasetPath, "subdataset.npz")

# load dataset dictionary
_subdataset = np.load(subdatasetPath)

# example for showing you how to obtain these 5 sub-datasets and
# create your own sub-dataset dictionary.
subdataset = {'header':_subdataset['header'],
              'task':_subdataset['task'],
              'event':_subdataset['event'],
              'attr':_subdataset['attr'],
              'cpu':_subdataset['cpu']}

# show their shape             
print(subdataset['header'].shape,
      subdataset['task'].shape,
      subdataset['event'].shape,
      subdataset['attr'].shape,
      subdataset['cpu'].shape)

# show the name of event attributes
attrNameList = list(_subdataset['attr_name'])
print(attrNameList)

# create prefix (data) sequence and suffix (label) sequence based on them
# ...
``````

# Files
```plaintext
2024.07.15 15h29m36s.zip/
├── Data Set Check/     # Data check folder.
│   ├── Data            # Data used for the report file.
│   ├── Figures         # Figures used for the report file.
│   ├── Models          # Typically empty.
│   ├── PathDic.json    # Vechicle trajectory data used for the report file.
│   └── Report.pdf      # The simulation report file for showing results and
|                       # checking the dataset. 
├── Config.json         # Simulation configuration file, including the parameters
|                       # of task, event, message, and time-triggered system.
├── FGC.csv             # Filtered dataset
├── GlobalContext.csv   # Raw dataset generated from the simulation directly.
├── subdataset.npy      # Sub-dataset dictionary that can be used directly.
├── system_dataset.csv  # CPU utility dataset
└── README.md           
``````
