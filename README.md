
#  Deep Learning based projector defocus compensation in Single pixel imaging                       

## Python code
###### Please use the code below to load the files and compute the output 
###### a) Model h5 file
###### b) the target file
									  
									  
| Author| SRIZVI|
| --- | --- |
| License| Academic free license V3 (afl-3.0) |
| Version | 1.0 |
| URL| https://github.com/Sdriz/Defocus_compensation_in_SPI|



```python


### Defocus compensation model
### The h5. file can be downloaded to inspect the DCNN model with trained weights, parameters etc.


### Loading the model file
model = load_model('defocus_compensate_model.h5')


### Model summary 
model.summary()

### Loading the target recostructed by FSI at high projector defocusing

target=io.loadmat('target.mat')

### Preprocessing for network

target=target['img']
target=(target-np.min(target))/(np.max(target)-np.min(target))

#### Ouput of Model on the PDEF effected target
   
result_target = model.predict(target.reshape(1,96,96,1))

```

```python

### Supplementary

#####Loading target one by one 
#different targets can be loaded from:

import h5py

def load_dataset(file_location,target):
    hf = h5py.File( file_location , 'r')
    fl = hf[target]
    new_array = np.array(fl)
    hf.close()
    return new_array

#Insert location

file_location = ''

#### Testing data

tar_container = ['target2',  'target2', 'target3','target4']

tar_dict = {}
for elm in Who:
   tar_load = 'repository/Original_images/' + iter
    tar_dict[iter] = load_dataset(file_location, tar_load)
   
```	


### DATASET
https://cs.stanford.edu/~acoates/stl10/

### ABSTRACT
To be updated

### Citation

To be updated


