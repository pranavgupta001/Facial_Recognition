# Introduction to fastai
The fastai library simplifies training fast and accurate neural nets using modern best practices. It's based on research in to deep learning best practices undertaken at fast.ai, including "out of the box" support for vision, text, tabular, and collab (collaborative filtering) models.
# Module structure
# 1. Import
fastai is designed to support both interactive computing as well as traditional software development. For interactive computing, where convenience and speed of experimentation is a priority, data scientists often prefer to grab all the symbols they need, with import *. Therefore, fastai is designed to support this approach, without compromising on maintainability and understanding.
In order to do so, the module dependencies are carefully managed (see next section), with each exporting a carefully chosen set of symbols when using import *.
# 2. Dependencies
At the base of everything are the two modules core and torch_core (we're not including the fastai. prefix when naming modules in these docs). They define the basic functions we use in the library; core only relies on general modules, whereas torch_core requires pytorch. Most type-hinting shortcuts are defined there too (at least the one that don't depend on fastai classes defined later). Nearly all modules below import torch_core.
Then, there are three modules directly on top of torch_core:
#
basic_data, which contains the class that will take a Dataset or pytorch DataLoader to wrap it in a DeviceDataLoader (a class that sits on top of a DataLoader and is in charge of putting the data on the right device as well as applying transforms such as normalization) and regroup then in a DataBunch.
#
layers, which contains basic functions to define custom layers or groups of layers
#
metrics, which contains all the metrics
